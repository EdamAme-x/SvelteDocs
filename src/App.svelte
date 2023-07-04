<script>
  import "./global.css" 
  import Router from 'svelte-spa-router'

  import Home from "./index.svelte"
  import Docs from "./index.svelte"

  const routes = {
        '/': Home,
        '/docs': Docs,
        '*': Home
    }; //path <=> .svelte
</script>

<Router routes={routes}/>