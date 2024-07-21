<script>
import TranscriptionBlock from '$lib/components/TranscriptionBlock.svelte'
import VideoPlayer from '$lib/components/VideoPlayer.svelte';
</script>

<div class="flex w-full flex-col pt-10 pr-[100px] pl-[100px] lg:flex-row">
	<div class="card rounded-box grid flex-grow place-items-center min-h-[500px]"><div class="flex w-full flex-col border-opacity-50">
		<div class="card bg-base-300 rounded-box grid min-h-[250px] place-items-center">
			<VideoPlayer/>
		</div>
		<div class="card bg-base-300 rounded-box grid min-h-[250px] mt-[40px] place-items-center">little card that has statemetn</div>
	  </div></div>
	<div class="divider lg:divider-horizontal min-h-[500px]"></div>
	<div class="card rounded-box grid h-32 place-items-center "><TranscriptionBlock falseCount={100} verifiedCount={100} uncertainCount={100} transcript={"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Auctor elit sed vulputate mi sit. At lectus urna duis convallis convallis tellus id interdum. Mi proin sed libero enim sed. Morbi tincidunt augue interdum velit euismod in pellentesque massa. Porttitor rhoncus dolor purus non enim praesent elementum. Id leo in vitae turpis massa. Iaculis eu non diam phasellus vestibulum lorem sed risus ultricies. Quisque egestas diam in arcu. Quis lectus nulla at volutpat diam ut venenatis tellus in. Elementum integer enim neque volutpat ac. Euismod elementum nisi quis eleifend quam adipiscing vitae proin. Ornare aenean euismod elementum nisi quis eleifend quam adipiscing vitae. Vel turpis nunc eget lorem dolor sed viverra ipsum. Id venenatis a condimentum vitae sapien. In nulla posuere sollicitudin aliquam ultrices sagittis orci. \n "}/></div>
  </div>



