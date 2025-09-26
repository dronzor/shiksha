<script>
  import "../app.css";
  

  let openMenu = null; // track which dropdown is open

  let menu1;
  let menu2;

  function toggleMenu(menu) {
    openMenu = openMenu === menu ? null : menu;
  }
  function getMaxHeight(el, isOpen) {
    return isOpen ? `${el.scrollHeight}px` : '0px';
  }
</script>

<div style="background-color: #FCFCFC;" class="flex h-screen ">
  <!-- Sidebar -->
  <aside style="background-color: #FCFCFC; color:#646464" class="w-64 flex flex-col">
    <!-- Logo / Brand -->
    <div class="p-2 text-3xl font-Pacifico text-center border-b border-gray-300">
      Shiksha
    </div>

    <!-- Navigation -->
    <nav class="flex-1 p-2 overflow-y-auto custom-scrollbar">

		<!-- Direct Links -->
  		<a href="/" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">Home</a>
  		<a href="/technical-forum" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">Technical Forum</a>
  		<a href="/aptara-fonts" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">Aptara Fonts</a>
  		<a href="/documentation" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">Documentation / User Guide</a>
  		<a href="/process-information" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">Process Information</a>
  		<a href="/downloads" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">Downloads</a>
  		<a href="/mathml-support" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">MathML Support</a>
  		<a href="/powermanage-pdf-config" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">PowerManage PDF Config</a>
  		<a href="/ppg-server-volumes" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">PPG Server Volumes</a>
  		<a href="/als-log" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">ALS LOG</a>
  		<a href="/powerl2x-log" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">PowerL2X Log</a>
  		<a href="/ccd-accuracy-report" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">CCD Accuracy Report</a>
  		<a href="/latex-autostructuring-report" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">Latex Autostructuring Report</a>
  		<a href="/pdg-log-files" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">PDG LOG Files</a>
  		<a href="/font-upload" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">Font Upload</a>
  		<a href="/tex-faq" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">Tex FAQ</a>
  		<a href="/our-team" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">Our Team</a>
  		<a href="/site-map" class="block px-4 py-2 text-style hover:bg-gray-700 rounded">Site Map</a>


      <!-- Dropdown 1 -->
    <div class="text-style">
    <button
      class="flex w-full justify-between items-center px-4 py-2 hover:bg-gray-700 rounded"
      on:click={() => toggleMenu('menu1')}
      aria-expanded={openMenu === 'menu1'}
      aria-controls="menu1"
    >
      <span>Menu 1</span>
      <span>{openMenu === 'menu1' ? '-' : '+'}</span>
    </button>

    	<div
        id="menu1"
      	bind:this={menu1}
      	class="ml-6 mt-1 space-y-1 overflow-hidden transition-all duration-300"
      	style="max-height: {menu1 ? getMaxHeight(menu1, openMenu === 'menu1') : '0px'}"
    	>
      		<a href="/option1" class="block px-2 py-1 hover:bg-gray-700 rounded">Option 1</a>
      		<a href="/option2" class="block px-2 py-1 hover:bg-gray-700 rounded">Option 2</a>
    	</div>
    </div>

    <div class="text-style">
    <button
      class="flex w-full justify-between items-center px-4 py-2 hover:bg-gray-700 rounded"
      on:click={() => toggleMenu('menu2')}
    >
      <span>Settings</span>
      <span>{openMenu === 'menu2' ? '-' : '+'}</span>
    </button>

    <div
      bind:this={menu2}
      class="ml-6 mt-1 space-y-1 overflow-hidden transition-all duration-300"
      style="max-height: {menu2 ? getMaxHeight(menu2, openMenu === 'menu2') : '0px'}"
    >
      <a href="/profile" class="block px-2 py-1 hover:bg-gray-700 rounded">Profile</a>
      <a href="/security" class="block px-2 py-1 hover:bg-gray-700 rounded">Security</a>
    </div>
    </div>
    </nav>
  </aside>

  <!-- Main Content -->
  <div class="flex-1 flex flex-col">
    <!-- Header -->
    <header class="h-14 bg-white flex items-center text-3xl px-4 shadow">
      <h1 class="text-lg font-semibold">Dashboard</h1>
    </header>

    <!-- Content -->
    <main class="flex-1 p-6 overflow-y-auto">
		<slot/>
    </main>

    <!-- Footer -->
    <footer class="h-12 bg-white border-t flex items-center justify-center text-sm">
		  © 2025 Aptara
    </footer>
  </div>
</div>


<style>
  @import url('https://fonts.googleapis.com/css2?family=Lobster+Two:ital,wght@0,400;0,700;1,400;1,700&family=Pacifico&display=swap');

  /* Custom Scrollbar only for elements with .custom-scrollbar */
  .custom-scrollbar::-webkit-scrollbar {
    width: 8px; /* scrollbar width */
  }



  .custom-scrollbar::-webkit-scrollbar-track {
    background: #374151; /* bg-gray-700 */
  }

  .custom-scrollbar::-webkit-scrollbar-thumb {
    background-color: #9ca3af; /* gray-400 */
    border-radius: 4px;
  }

  .custom-scrollbar::-webkit-scrollbar-thumb:hover {
    background-color: #d1d5db; /* gray-300 */
  }

  /* Firefox */
  .custom-scrollbar {
    scrollbar-width: thin;
    scrollbar-color: #9ca3af #374151;
  }

  .font-Pacifico {
  font-family: 'Pacifico', sans-serif;
  }
  
  .text-style {
  font-size: 0.875rem; 
  line-height: 1.25rem; 
  font-family: Arial, sans-serif; 
  font-weight: 400;
  }
</style>
