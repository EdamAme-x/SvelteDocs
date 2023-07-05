<script>
  // Lite <=> Dark
  import LiteMode from '../assets/sun.svg'
  import DarkMode from "../assets/moon.svg"
  import { writable } from 'svelte/store';

  import { onMount } from 'svelte';
  
  function toTop() {
    location.href = "/";
  }

  const mode = writable(localStorage.getItem("_mode") || "Lite");

  let ModeImg;

  
  
 onMount(() => {
  let themeStyle = document.querySelector("[docs-theme]");
  if (!themeStyle) {
    themeStyle = document.createElement("style");
    themeStyle.setAttribute("docs-theme", "");
    document.head.appendChild(themeStyle);
  }
});

function DarkView() {
  let themeStyle = document.querySelector("[docs-theme]");
  if (themeStyle) {
    themeStyle.innerHTML = `
      body {
        color: #fff !important;
        background-color: #2c3e49 !important;
        transition: .25s;
      }
    `;
  }else {
    setTimeout(() => {
    
    let themeStyle = document.querySelector("[docs-theme]");
    if (themeStyle) {
      themeStyle.innerHTML = `
        body {
          color: #fff !important;
          background-color: #2c3e49 !important;
          transition: .25s;
        }
      `;
    
    }
    },100) // plz fix
  }
}

function LiteView() {
  let themeStyle = document.querySelector("[docs-theme]");
  if (themeStyle) {
    themeStyle.innerHTML = `
      body {
        color: #2c3e49 !important;
        background-color: #fff !important;
        transition: .25s;
      }
    `;
  }
}

  $: {
    if ($mode === "Lite") {
      ModeImg = LiteMode;
      LiteView()
    } else {
      ModeImg = DarkMode;
      DarkView()
    }
  }

  const changeMode = () => {
    mode.update((value) => {
      const newMode = value === "Lite" ? "Dark" : "Lite";
      localStorage.setItem("_mode", newMode);
      return newMode;
    });
  };
</script>

<header>
  <h1 on:click={toTop}>Svelte Docs</h1>
  <nav>
    <img src={ModeImg} on:click={changeMode} alt="LiteIcon" height="30" class="icon">
    <a href="/ref">
      Reference
    </a>
    <a href="https://github.com/EdamAme-x/SvelteDocs">
      GitHub
    </a>
  </nav>
</header>
<hr color="#2c3e50"/>

<style>
  h1 {
    margin: 0;
    padding: 10px 18px 0px 10px;
    font-size: 1.25rem;
    font-weight: 600;
    opacity: 0.95;
  }

  header {
    width: 100vw;
    height: auto;
    display: flex;
  }

  hr {
    height: 0.3px;
    opacity: 0.15;
  }

  nav {
    display: flex;
    margin-right: 25px;
    margin-left: auto;
  }

  nav a {
    color: inherit;
    text-decoration: none;
    font-weight: 600;
    font-size: 0.9rem;
    padding: 14px 8px 0px 8px;
  }

  .icon {
    margin-top: 8px;
    margin-right: 3px;
  }
</style>
