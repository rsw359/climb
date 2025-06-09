<script lang="ts">
 import logo from '../assets/logo.png';
 import logoblk from '../assets/logoblk.jpg';
 

 let darkmode = false;
 let language = 'en';

 function toggleDarkMode() {
  darkmode = !darkmode;
  document.body.style.background = darkmode ? '#111' : '#fff';
  document.body.style.color = darkmode ? '#fff' : '#111';
 }

 function toggleLanguage() {
  language = language === 'EN' ? 'JP' : 'EN';
 }
</script>
<header class="header">
  <img src="{logo} " alt="Climb Logo" class="logo" />
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
    justify-content: center;
    align-items: center;
    padding: 2rem 0 1rem 0;
    
    background: #fff
    ;
  }

  .logo{
    height: 100px;
    filter: invert(1);
    margin: 0;
  }

  .subtitle{
    font-size: 1.5rem;
    text-align: center;
    margin: 2rem 0;
    color: #bbb;
  }

  .footer {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    text-align: center;
    padding: 2rem 0 1rem 0;
    border-top: 1px solid #222;
    background: #111;
    color: #888;
    font-size: 1rem;
    letter-spacing: 1px;
    z-index: 10;
  }
</style>


