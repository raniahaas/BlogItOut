<script>
  import './app.css';
  import Home from './home.svelte';
  import Projects from './projects.svelte';
  import Resume from './resume.svelte';
  import Me from './whoami.svelte';
  import Gallery from './gallery.svelte';

  let route = location.pathname;

  function navigate(path) {
    history.pushState({}, '', path);
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




