<script lang="ts">
 import logo from '../assets/logo.png';
 import logoblk from '../assets/logoblk.jpg';
 

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
  <div class= "logo-nav">

    <img src="{logo} " alt="Climb Logo" class="logo" />
    <nav class="nav">
      <a href="/climbs">Cycling</a>
      <a href="/coffee">Coffee</a>
      <a href="/fashion">Fashion</a>
    </nav>
  </div>
  <div class= 'header-actions'>
    <button class="lang-toggle" on:click={toggleLanguage}>
      {language}
    </button>
    <button class="dark-mode-toggle" on:click={toggleDarkMode}>
      {darkMode ? '☀️' : '🌙'}
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

  .nav a {
    display:flex;
    
    color: #111;
    text-decoration: none;
    font-size: 1.1rem;
    font-weight: 500;
    letter-spacing: 1px;
    padding: 0.5rem 1rem;
    
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
    font-size: 1rem;
    letter-spacing: 1px;
    z-index: 10;
  }
</style>


