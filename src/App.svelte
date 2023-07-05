<script>
  import "./global.css" 
  import Router from 'svelte-spa-router'

  import Home from "./index.svelte"
  import Ref from "./ref/index.svelte"

  const routes = {
        '/': Home,
        '/ref': Ref,
        '*': Home
    }; //path <=> .svelte
</script>

<Router routes={routes}/>