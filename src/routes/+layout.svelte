<script>
	import "../app.css";
</script>
<nav class="bg-white border-b border-gray-200">
	<div class="container mx-auto px-4">
	  <div class="flex justify-between items-center h-16">
		<div class="flex items-center">
		  <!-- Logo -->
		  <a href="/" class="text-xl font-bold text-gray-800">
			<img src='/Verif.ai.svg' alt="Verif.ai Logo" class="logo h-8" />
			<!-- Verif.ai -->
		  </a>
		</div>
		<div class="hidden md:flex space-x-4">
		  <!-- Navbar Links -->
		  <a href="/" class="text-gray-700 hover:text-gray-900">Home</a>
		  <a href="/about" class="text-gray-700 hover:text-gray-900">About</a>
		</div>
		<div class="md:hidden">
		  <!-- Mobile Menu Button -->
		  <button class="text-gray-700 hover:text-gray-900 focus:outline-none focus:text-gray-900" id="mobile-menu-button">
			<svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
			  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
			</svg>
		  </button>
		</div>
	  </div>
	</div>
	<!-- Mobile Menu -->
	<div class="md:hidden" id="mobile-menu">
	  <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
		<a href="/" class="block text-gray-700 hover:text-gray-900">Home</a>
		<a href="/about" class="block text-gray-700 hover:text-gray-900">About</a>
		<a href="/contact" class="block text-gray-700 hover:text-gray-900">Contact</a>
	  </div>
	</div>
  </nav>
<slot />