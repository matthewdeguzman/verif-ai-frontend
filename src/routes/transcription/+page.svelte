<script>
import ClaimCard from '$lib/components/ClaimCard.svelte';
import TranscriptionBlock from '$lib/components/TranscriptionBlock.svelte'
import VideoPlayer from '$lib/components/VideoPlayer.svelte';
  import { string } from '@tensorflow/tfjs';
import { videoLink } from '../../stores.js'; // Adjust the path as needed

let videoUrl ="";
videoLink.subscribe(value => {
        videoUrl = value;
        });

  const baseUrl = "http://localhost:8000/transcribe_url";
  // Create a URL object to manage the query parameters
  const url = new URL(baseUrl);

  // Append query parameters
  url.searchParams.append("video_url", videoUrl);

 
  let fetchDataResult = true;

  let testResult = "Do you support any legal limits on how late a woman should be able to terminate a pregnancy?. I support Roe v. Wade.. He can take the life of the baby in the ninth month and even after birth.. That is simply not true.. We are not for late term abortion, period, with the COVID, excuse me, with dealing with. everything we have to do with, uh, look.. We had the safest border in history.. Now we have the worst border in history.. There's never been anything like it.. There's no data to support what he said.. Once again, he's exaggerating.. He's lying.. And I'm going to continue to move until we get the total ban on the, the, the, the total. initiative relative to what we're going to do with more border patrol and more asylum. officers.. President Trump?. I really don't know what he said at the end of that sentence.. I don't think he knows what he said either.. If a Republican did that, they'd go to jail.. Thank you, President Trump.. The only person on this stage is a convicted felon is the man I'm looking at right now.. But he could be a convicted felon as soon as he gets out of office.. He caused the inflation and it's killing black families and Hispanic families.. There was no inflation when I became president.. You know why?. The economy was flat on its back.. 15% unemployment.. He decimated the economy.. The only one who wants the war to continue is Hamas.. We are the biggest producer of support for Israel of anyone in the world.. He said the only one who wants to keep going is Hamas.. Actually, Israel is the one, and you should let him go and let him finish the job.. The only existential threat to humanity is climate change, and he didn't do a damn thing. about it.. He wants to undo all that I've done.. The Paris Accord was going to cost us a trillion dollars.. It was a ripoff of the United States.. He never fired people.. I've never seen him fire anybody.. I did fire a lot.. I fired Comey because he was no good.. I fired a lot of the top people at the FBI, drained the swamp.. They were no good.. This guy hasn't fired anybody.. He's the worst president in the history of our country.. He's destroyed our country.. Presidential historians, they've had meetings, and they voted who's the worst president in. American history, best to worst.. They said he was the worst in all of American history.. He will drive us into World War III, and we're closer to World War III than anybody can imagine.. President Xi of China, Kim Jong-un of North Korea, all of these are Putin.. They don't respect him, and he's going to drive us into World War III.. You want to have a war, just let Putin go ahead and take Kiev, make sure they move on,. and see what happens in Poland, Hungary, and other places along that border.. Then you have a war.. The only reason I'm here is he's so bad as a president that I'm going to make America. great again.. For the envy of the world, I'd name me a single major country president who wouldn't trade. places with the United States of America.";

// fetch(url,  {
//       method: "POST",
//       body: "{}",
//       headers: {
//         "Content-Type": "application/json",
//       }})
// 		.then(response => { 
// 		   console.log(' response', response)
// 		   console.log(' r.json() >', response.clone().json()) //
// 		   response.json()
// 			   .then(json => {
// 					console.log('json', json)
// 				    fetchDataResult = json				   
// 		     })
// 		     .catch(error => console.log(error))
// 	})

</script>

{#if fetchDataResult}
<div class="flex w-full flex-col pt-10 pr-[100px] pl-[100px] lg:flex-row">
	<div class="card rounded-box grid flex-grow place-items-center min-h-[500px]"><div class="flex w-full flex-col border-opacity-50">
		<div class="card bg-base-300 rounded-box grid min-h-[250px] place-items-center">
			<VideoPlayer/>
		</div>
		<div class="rounded-box grid min-h-[250px] mt-[15px] place-items-center"><ClaimCard claimText={"20% of people are smelly really long text in this claim"} claimType={"false"} timeStampStart={'0:31'} timeStampEnd={'0:50'}/></div>
	  </div></div>
	<div class="divider lg:divider-horizontal min-h-[500px]"></div>
	<div class="card rounded-box grid h-32 place-items-center "><TranscriptionBlock falseCount={100} verifiedCount={100} uncertainCount={100} transcript={testResult}/></div>
  </div>
{:else}
  <p>loading</p>
{/if}






