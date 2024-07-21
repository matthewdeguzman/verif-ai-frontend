<script >
export let claimText;
export let claimType;
// export let timeStampStart;
// export let timeStampEnd;
let textColor = "";
let bgColor = "";

$: {
    if(claimType === "verified"){
        textColor = "7EAE72"
        bgColor = "bg-[#DFF3DA]"
    }
    else if (claimType === "false"){
        textColor = "D54F4F"
        bgColor = "bg-[#F8CECE]"

    }
    else{
        textColor = "F8C464"
        bgColor = "bg-[#FEF0D6]"
    }
}
</script>

<div class="card w-[584px] h-[200px] shadow-md border-2 border-[#{textColor}] {bgColor}">
  <div class="card-body">
    <details class="relative">
      <summary class="card-title text-[#{textColor}] cursor-pointer">
        <h2 class="inline-block max-w-[35ch] overflow-hidden text-ellipsis whitespace-nowrap">
          “{claimText}”
        </h2>
       
    </details>
  </div>
</div>
