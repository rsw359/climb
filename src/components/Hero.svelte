<script lang="ts">
 import logo from '../assets/logo.png';
 import logoblk from '../assets/logoblk.jpg';
 
 let showNav = false;
 let darkMode = false;
 let language = 'en';

 function toggleDarkMode() {
  darkMode = !darkMode;
  document.body.style.background = darkMode ? '#111' : '#fff';
  document.body.style.color = darkMode ? '#fff' : '#111';
 }

 function toggleLanguage() {
  language = language === 'EN' ? 'JP' : 'EN';

 
 }
</script>
<header class="header">
  <div class="logo-nav" role="navigation" on:mouseenter={() => showNav = true} on:mouseleave={() => showNav = false}>
  <img src={logo} alt="Climb Logo" class="logo" />
  <nav class="nav" class:show={showNav}>
    <a href="/climbs">Cycling</a>
    <a href="/coffee">Coffee</a>
    <a href="/fashion">Fashion</a>
  </nav>
</div>
  <div class="header-actions">
  <button class="lang-toggle" on:click={toggleLanguage} title="Toggle Language">
    <!-- Globe SVG icon -->
    <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#111" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="vertical-align: middle;">
      <circle cx="12" cy="12" r="10"/>
      <path d="M2 12h20"/>
      <path d="M12 2a15.3 15.3 0 0 1 0 20"/>
      <path d="M12 2a15.3 15.3 0 0 0 0 20"/>
    </svg>
    <span style="margin-left: 0.5em;">{language}</span>
  </button>
  <button class="dark-mode-toggle" on:click={toggleDarkMode} title="Toggle Dark Mode">
    {#if darkMode}
      <!-- Sun SVG icon -->
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#111" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="vertical-align: middle;">
        <circle cx="12" cy="12" r="5"/>
        <path d="M12 1v2"/>
        <path d="M12 21v2"/>
        <path d="M4.22 4.22l1.42 1.42"/>
        <path d="M18.36 18.36l1.42 1.42"/>
        <path d="M1 12h2"/>
        <path d="M21 12h2"/>
        <path d="M4.22 19.78l1.42-1.42"/>
        <path d="M18.36 5.64l1.42-1.42"/>
      </svg>
    {:else}
      <!-- Moon SVG icon -->
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#111" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="vertical-align: middle;">
        <path d="M21 12.79A9 9 0 1 1 11.21 3a7 7 0 0 0 9.79 9.79z"/>
      </svg>
    {/if}
  </button>
</div>
</header>


<section class='hero'>
  
</section> 

<footer class='footer'>
  <p>&copy; {new Date().getFullYear()} Climb. All rights reserved.</p>
</footer> 

<style>
 :global(body) {
    margin: 0;
    padding: 0;
    font-family: 'Arial', sans-serif;
    background: #fff;
    color: #111;
  }

  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.5rem 3vw 0.5rem 3vw;
    background: #fff;
  }

  .logo-nav {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: .5rem;
  position: relative;
  }
  .logo {
    height: 100px;
    filter: invert(1);
    margin: 0;
    transition: transform 0.3s cubic-bezier(0.4, 2, 0.6, 1);
  }

  .logo-nav:hover .logo {
  transform: scale(1.08) rotate(-6deg);
  box-shadow: 0 4px 24px rgba(0,0,0,0.10);
  }
 

  .header-actions {
    display: flex;
    gap: 1rem;
    align-items: center;
  }

    .lang-toggle {
    background: none;
    border: 1px solid #bbb;
    color: #111;
    border-radius: 1.5rem;
    padding: 0.3rem 1rem;
    font-size: 1rem;
    cursor: pointer;
    transition: background 0.2s, color 0.2s, border 0.2s;
  }
  .lang-toggle:hover, .dark-mode-toggle:hover {
    font-style: italic;
  }

  .nav {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  opacity: 0;
  pointer-events: none;
  transform: translateX(30px);
  transition: opacity 0.4s, transform 0.4s;
  margin-left: 0.5rem;
 
}
.nav a {
  text-decoration: none;
  color: #111;
  font-size: 1.2rem;
 
  transition: background-color 0.3s, color 0.3s;
}
.nav.show {
  opacity: 1;
  pointer-events: auto;
  transform: translateX(0);
}

  .nav a:hover {
    font-style: italic;
  }
  .logo{
    height: 100px;
    filter: invert(1);
    margin: 0;
  }

  /* .subtitle{
    font-size: 1.5rem;
    text-align: center;
    margin: 2rem 0;
    color: #bbb;
  } */

  .footer {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    text-align: center;
    padding: 2rem 0 1rem 0;
    
    background: #fff;
    color: #111;
    font-size: .6rem;
    letter-spacing: 1px;
    z-index: 10;
  }
</style>


