<script  lang="ts">
import ClaimCard from '$lib/components/ClaimCard.svelte';
import TranscriptionBlock from '$lib/components/TranscriptionBlock.svelte'
import VideoPlayer from '$lib/components/VideoPlayer.svelte';
  import { string } from '@tensorflow/tfjs';
import { videoLink } from '../../stores.js'; // Adjust the path as needed

let currClaim="";
let videoUrl ="";
videoLink.subscribe(value => {
        videoUrl = value;
        });

  const baseUrl = "http://localhost:8000/fact_check";
  // Create a URL object to manage the query parameters
  const url = new URL(baseUrl);

  // Append query parameters
  url.searchParams.append("video_url", videoUrl);

 
  /**
   * @type {any[]}
   */
  let fetchDataResult;

  let mock = new Map();
  let sentences = []
  mock.set('text', 'turtles are green');
  mock.set('claimType', 'verified')
  mock.set('sources', ['nyt', 'the onion'])
  mock.set('textual_reason', 'this is definitely right lmao')
  mock.set('timeStampStart', '0:31')
  mock.set('timeStampEnd', '0:40')

  let falseCount = 0;
  let verifiedCount = 0;
  let uncertainCount = 0;

  fetch(url,  {
      method: "POST",
      body: "{}",
      headers: {
        "Content-Type": "application/json",
      }})
		.then(response => { 
		   console.log(' response', response)
		   console.log(' r.json() >', response.clone().json()) //
		   response.json()
			   .then(json => {
					console.log('json', json)
				    fetchDataResult = json	
            
            for (let i = 0; i < fetchDataResult.length; i++) {
              // @ts-ignore
              if(fetchDataResult[i].claimType === "verified"){
                verifiedCount += 1;
              }
              // @ts-ignore
              else if(fetchDataResult[i].claimType === "uncertain"){
                uncertainCount += 1;
              }
              // @ts-ignore
              else if(fetchDataResult[i].claimType === "false"){
                falseCount += 1;
              }
            }

            for (let i = 0; i < fetchDataResult.length; i++) {
              sentences.append(fetchDataResult[i].text)
            }
		     })
		     .catch(error => console.log(error))
	})

  console.log(fetch)
  // @ts-ignore
  



</script>

{#if fetchDataResult}
<div class="flex w-full flex-col pt-10 pr-[100px] pl-[100px] lg:flex-row">
	<div class="card rounded-box grid flex-grow place-items-center min-h-[500px]"><div class="flex w-full flex-col border-opacity-50">
		<div class="card bg-base-300 rounded-box grid min-h-[250px] place-items-center">
			<VideoPlayer/>
		</div>
		<div class="rounded-box grid min-h-[250px] mt-[15px] place-items-center">
      {#each fetchDataResult as dataResult, index (index)}

      <ClaimCard claimText={fetchDataResult[index].text} textualReason={fetchDataResult[index].textualReason} claimType={fetchDataResult[index].claimType} timeStampStart={fetchDataResult[index].timeStampStart} timeStampEnd={fetchDataResult[index].timeStampStart} sources={fetchDataResult[index].sources}/>
    {/each}
    </div>
    
  </div></div>
	<div class="divider lg:divider-horizontal min-h-[500px]"></div>
	<div class="card rounded-box grid h-32 place-items-center "><TranscriptionBlock obj={fetchDataResult} falseCount={falseCount} verifiedCount={verifiedCount} uncertainCount={uncertainCount} sentences={sentences}/></div>
  </div>
{:else}
  <div class ="h-screen flex justify-center items-center">
    <img class="absolute scale-[50%] pb-[250px] pr-[25px] animation-pulse transition-all"src='/LoadingIcon.svg' alt="logo loading">
    <div class="scale-125 ">Analyzing content </div> <span class=" loading loading-dots loading-sm ml-[22px] mt-[13px]"></span>
  </div>
{/if}






