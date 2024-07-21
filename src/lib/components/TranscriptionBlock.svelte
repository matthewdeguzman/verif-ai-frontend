<script>
import FalseIcon from "./FalseIcon.svelte";
import VerifiedIcon from "./VerifiedIcon.svelte";
import Uncertainicon from "./UncertainIcon.svelte";
import DownButton from "./DownButton.svelte";
import UpButton from "./UpButton.svelte";

export let falseCount = 0;
export let verifiedCount = 0;
export let uncertainCount = 0;
export let sentences = [];
export let obj;

let transcript= sentences.join(" ")

</script>

<div class="card bg-base-100 w-[584px] shadow-md border-2 border-[#D9D9D9]">
  <span class="card-title pt-[50px] pb-[10px] pl-[30px] shadow-md">
    <h2>Transcript</h2>
    <span class="pt-[5px]">
    <div class="badge border-0 text-[#D54F4F]"> <span class="pr-[3px]"><FalseIcon/></span><span>{falseCount} False</span></div>
    <div class="badge border-0 text-[#7EAE72]"> <span class="pr-[3px]"><VerifiedIcon/></span><span>{verifiedCount} Verified</span></div>
    <div class="badge border-0 text-[#F8C464]"> <span class="pr-[3px]"><Uncertainicon/></span><span>{uncertainCount} Uncertain</span></div>
  </span>
  </span>
<div>
    <div class="card-body max-h-[610px] overflow-y-auto">
      <div class="top-0 right-0 absolute pt-[15px] pr-[30px]"><DownButton/>{" "}<UpButton/></div>
      <p class="text-[#757575]">{transcript}</p>
      </div>
    </div>
  </div>