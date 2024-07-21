<script>
import FalseIcon from "./FalseIcon.svelte";
import VerifiedIcon from "./VerifiedIcon.svelte";
import Uncertainicon from "./UncertainIcon.svelte";
import DownButton from "./DownButton.svelte";
import UpButton from "./UpButton.svelte";

export let falseCount = 0;
export let verifiedCount = 0;
export let uncertainCount = 0;
export let transcript = "Transcript not loaded";
</script>

<div class="card bg-base-100 w-[584px] shadow-xl min-h-[500px]">
    <div class="card-body">
      <div class="top-0 right-0 absolute pt-[15px] pr-[30px]"><DownButton/>{" "}<UpButton/></div>

        <span class="card-title pt-[15px]">
          <h2>Transcript</h2>
          <div class="badge border-0 text-[#D54F4F]"> <span class="pr-[3px]"><FalseIcon/></span><span>{falseCount} False</span></div>
          <div class="badge border-0 text-[#7EAE72]"> <span class="pr-[3px]"><VerifiedIcon/></span><span>{verifiedCount} Verified</span></div>
          <div class="badge border-0 text-[#D9D9D9]"> <span class="pr-[3px]"><Uncertainicon/></span><span>{uncertainCount} Uncertain</span></div>
        </span>
      <div>

      <p class="text-[#757575]">{transcript}</p>
      </div>
    </div>
  </div>