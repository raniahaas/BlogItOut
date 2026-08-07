<script>
  import './app.css';
  import Home from './home.svelte';
  import Projects from './projects.svelte';
  import Resume from './resume.svelte';
  import Me from './whoami.svelte';
  import Gallery from './gallery.svelte';

  const base = import.meta.env.BASE_URL;

  function getRoute() {
    let path = location.pathname;
    if (path.startsWith(base)) {
      path = path.slice(base.length - 1); // keep leading slash
    }
    return path || '/';
  }

  let route = getRoute();

  function navigate(path) {
    history.pushState({}, '', base.slice(0,-1) + path);
    route = path;
  }

  window.addEventListener('popstate', () => {
    route = location.pathname;
  });
  /**notes for updating build:
   * 1. npm run dev in vite-project and ensure it works
   * if it doesnt re-install npm
   * 2. npm run build
   * 3. npm run deploy
   * */

</script>

{#if route === '/'}
  <Home {navigate} />
{:else if route === '/projects'}
  <Projects {navigate} />
{:else if route === '/resume'}
  <Resume {navigate} />
{:else if route === '/about'}
  <Me {navigate} />
{:else if route === '/gallery'}
  <Gallery {navigate} />
{:else}
  <Home {navigate} />
{/if}




