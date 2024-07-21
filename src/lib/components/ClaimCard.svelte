<script >
  import { text } from "@sveltejs/kit";

export let claimText;
export let claimType;
// export let sources;
export let timeStampStart;
export let timeStampEnd;
let textColor = "";
let bgColor = "";
let badgeColor = "";

$: {
    if(claimType === "verified"){
        textColor = "7EAE72"
        bgColor = "bg-[#DFF3DA]"
        badgeColor = "bg-[#7EAE72]"
    }
    else if (claimType === "false"){
        textColor = "D54F4F"
        bgColor = "bg-[#F8CECE]"
        badgeColor = "bg-[#D54F4F]"
    }
    else{
        textColor = "F8C464"
        bgColor = "bg-[#FEF0D6]"
        badgeColor = "bg-[#F8C464]"
    }
}
</script>

<div class="card w-[584px] h-[200px] shadow-md border-2 {bgColor}">
    <div class="badge border-0 {badgeColor} text-white font-bold absolute right-0 top-0 m-3">{timeStampStart} : {timeStampEnd}</div>
  <div class="card-body">
      <div class="card-title text-[#{textColor}] cursor-pointer pt-[5px]">
        <h2>
          <span class="inline-block max-w-[35ch] overflow-hidden text-ellipsis whitespace-nowrap">{claimText}</span>
        </h2>
    </div>
 </div>
</div>
