<script>
  export let navigate = (p) => (location.pathname = p);
  import img from './assets/IMG_2650.JPG';
  import img_projects from './assets/01J5XHR97RMQMVBGT32QAQ9QXZ-low-res-branded-.JPEG';
  import img_resume from './assets/IMG_4840.jpeg';
  import img_aboutme from './assets/S1211062025075509.JPG'

</script>

<main class="container">
  <!-- Header bar (unchanged) -->
  <header class="home-header">
    <div class="header-bar">
      <h1 class="title">Rania Haas</h1>
      <nav class="nav">
        <a href="/" on:click|preventDefault={() => navigate('/')}>Home</a>
        <a href="/about" on:click|preventDefault={() => navigate('/about')}>About</a>
        <a href="/projects" on:click|preventDefault={() => navigate('/projects')}>Projects</a>
        <a href="/resume" on:click|preventDefault={() => navigate('/resume')}>Resume</a>
      </nav>
    </div>
    <p class="subtitle">Avionics, Japanese, and more in-depth parts of my professional career!</p>

     <h1 class="title"></h1>
      <p class="subtitle"> </p>
  </header>

  <!-- Scrapbook collage inside main area -->
  <section class="scrapbook">
    <!-- Polaroid photo -->
    <div class="polaroid">
      <img src={img} alt="Rania Haas" />
      <p class="caption">Graduating Class of 2027 with B.S. in Computer Science and Certificate in Japanese Language and Culture from the University of Cincinnati</p>
    </div>

    <section class="scrapbook-grid">
      <div class="scrap-item" on:click={() => navigate('/about')}>
        <img src={img_aboutme} alt="About Me" />
        <p class="caption">About Me</p>
      </div>

      <div class="scrap-item" on:click={() => navigate('/resume')}>
        <img src={img_resume} alt="Resume" />
        <p class="caption">Resume</p>
      </div>

      <div class="scrap-item" on:click={() => navigate('/projects')}>
        <img src={img_projects} alt="Projects" />
        <p class="caption">Projects</p>
      </div>

    </section>

  </section>

</main>

<style>
  /* Keep your original header/nav styles */
  .header-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .title {
    font-family: 'Imperial Script', cursive;
    font-size: 3.5rem;
    margin: 0;
    color: #0b2545;
  }

  .subtitle {
    font-size: 1.2rem;
    color: #567;
    margin-top: 0.5rem;
  }

  .nav {
    display: flex;
    gap: 1.5rem;
    font-weight: 500;
  }

  .nav a {
    color: #567;
    text-decoration: none;
  }

  .nav a:hover {
    text-decoration: underline;
  }

  /* Scrapbook collage */
  .scrapbook {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 2rem;
    margin-top: 2rem;
  }

  /* Polaroid photo */
  .polaroid {
    background: #fff;
    padding: 0.5rem;
    box-shadow: 0 6px 18px rgba(0,0,0,0.15);
    transform: rotate(-3deg);
  }
  .polaroid img {
    width: 100%;
    border-bottom: 2px solid #eee;
  }
  .caption {
    text-align: center;
    font-size: 0.9rem;
    margin-top: 0.5rem;
  }

  .scrapbook-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.scrap-item {
  background: #fdfcf7;
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 2px 2px 8px rgba(0,0,0,0.1);
  padding: 0.5rem;
  cursor: pointer;
  transform: rotate(var(--rotate, 0deg));
  transition: transform 0.2s ease;
}

.scrap-item:hover {
  transform: scale(1.03) rotate(0deg);
}

.scrap-item img {
  width: 100%;
  border-radius: 4px;
  object-fit: cover;
}

.caption {
  text-align: center;
  font-family: 'Courier New', monospace;
  font-size: 0.95rem;
  margin-top: 0.5rem;
  color: #444;
}

.scrap-item {
  background: #fdfcf7;
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 2px 2px 8px rgba(0,0,0,0.1);
  padding: 0.4rem;
  cursor: pointer;
  transform: rotate(var(--rotate, 0deg));
  transition: transform 0.2s ease;
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 220px; /* reduced from 300px */
  overflow: hidden;
}

.scrap-item img {
  width: 100%;
  height: 150px; /* reduced from 220px */
  object-fit: cover;
  border-radius: 4px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
}

.caption {
  text-align: center;
  font-family: 'Courier New', monospace;
  font-size: 0.85rem; /* slightly smaller */
  margin-top: 0.3rem;
  color: #444;
}







</style>
