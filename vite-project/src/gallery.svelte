<script>
  import { onMount } from 'svelte';
  import CodePanel from './codePannel.svelte';
  export let navigate = (p) => (location.pathname = p);

  //json
  import albums from './albums.json'


  //similar code to projects
  let expanded = null;
  $: selected = albums.find(a => a.id === expanded) || null;

  let galleryIndex = 0;

  let isZoomed = false;
  let zoomSrc = null;
  let zoomCaption = "";

  function nextZoomImage() {
    const len = selected.images.length;
    const nextIndex = (selected.images.indexOf(zoomSrc) + 1) % len;
    zoomSrc = selected.images[nextIndex];
    zoomCaption = selected.captions?.[nextIndex] || "";
  }

  function prevZoomImage() {
    const len = selected.images.length;
    const prevIndex = (selected.images.indexOf(zoomSrc) - 1 + len) % len;
    zoomSrc = selected.images[prevIndex];
    zoomCaption = selected.captions?.[prevIndex] || "";
  }

  function openAlbum(id) {
    expanded = id;
    galleryIndex = 0;
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  function closeAlbum() {
    expanded = null;
    galleryIndex = 0;
  }

   function nextImage() {
    if (!selected) return;
    const len = (selected.images?.length || 1);
    galleryIndex = (galleryIndex + 1) % len;
  }

  function prevImage() {
    if (!selected) return;
    const len = (selected.images?.length || 1);
    galleryIndex = (galleryIndex - 1 + len) % len;
  }

  function onKeydown(e) {
    if (!selected) return;
    if (e.key === 'Escape') closeAlbum();
    if (e.key === 'ArrowRight') nextImage();
    if (e.key === 'ArrowLeft') prevImage();
  }

  $: {
    if (selected) {
      window.addEventListener('keydown', onKeydown);
    } else {
      window.removeEventListener('keydown', onKeydown);
    }
  }

</script>

<main class="container">
  <header class="projects-header">
    <div class="header-bar">
      <h1 class="title">Photos</h1>
      <nav class="nav">
        <a href="/" on:click|preventDefault={() => navigate('/')}>Home</a>
        <a href="/about" on:click|preventDefault={() => navigate('/about')}>About</a>
        <a href="/projects" on:click|preventDefault={() => navigate('/projects')}>Projects</a>
        <a href="/resume" on:click|preventDefault={() => navigate('/resume')}>Resume</a>
        <a href="/gallery" on:click|preventDefault={() => navigate('/gallery')}>Gallery</a>
      </nav>
    </div>
    <p class="subtitle">Click an album to view photos.</p>
  </header>

  <!--albums-->
  {#if !selected}
    <h2 class="section-title">Photo Albums</h2>

    <div class="project-list" role="list">
      {#each albums as album}
        <article
          class="project-row"
          role="listitem"
          on:click={() => openAlbum(album.id)}
        >
          <img
            class="thumb"
            src={album.thumb}
            alt={album.title}
            loading="lazy"
          />

          <div class="meta">
            <h3 class="proj-title">{album.title}</h3>
            <p class="preview">{album.preview}</p>
          </div>
        </article>
      {/each}
    </div>

  {:else}

    <section class="project-focus">

      <div class="focus-controls">
        <button class="back-btn" on:click={closeAlbum}>← Back</button>

        <div class="nav-controls">
            <button class="nav-btn" on:click={prevImage}>◀</button>

            <div class="image-count">
            {galleryIndex + 1} / {selected.images.length}
            </div>

            <button class="nav-btn" on:click={nextImage}>▶</button>
        </div>
    </div>


      <header class="focus-header">
        <div class="focus-left">
          <h2 class="focus-title">{selected.title}</h2>
          <p class="lead">{selected.preview}</p>
        </div>

        <div class="gallery">
          <div class="main-image-wrap">
            <img
              class="main-image"
              src={selected.images[galleryIndex]}
              alt={selected.captions?.[galleryIndex] || selected.title}
            />
          </div>

          {#if selected.captions && selected.captions[galleryIndex]}
            <p class="caption-text">
              {selected.captions[galleryIndex]}
            </p>
          {/if}
        </div>
      </header>

    </section>
  {/if}
</main>

{#if isZoomed}
  <div class="zoom-modal" on:click={() => (isZoomed = false)}>
    <div class="zoom-content" on:click|stopPropagation>

      <button class="zoom-arrow left" on:click={prevZoomImage}>◀</button>

      <img class="zoom-img" src={zoomSrc} alt={zoomCaption} />

      <button class="zoom-arrow right" on:click={nextZoomImage}>▶</button>

      <p class="zoom-caption">{zoomCaption}</p>
    </div>
  </div>
{/if}

<style>
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

  .projects { margin-top: 1.5rem; }

  .section-title { margin: 0 0 0.75rem 0; color: #0b2545; }

  .project-list {
    display: flex;
    flex-direction: column;
    gap: 0.9rem;
    max-height: 60vh;
    overflow-y: auto;
    padding-right: 0.5rem;
  }

  .project-row {
    display: flex;
    gap: 0.9rem;
    align-items: center;
    padding: 0.6rem;
    border-radius: 8px;
    background: #fafafa;
    border: 1px solid #e6e6e6;
    cursor: pointer;
    transition: transform 0.12s ease, box-shadow 0.12s ease;
  }
  .project-row:hover { transform: translateY(-3px); box-shadow: 0 6px 18px rgba(0,0,0,0.06); }

  .thumb { width: 72px; height: 72px; object-fit: cover; border-radius: 6px; flex: 0 0 72px; box-shadow: 0 2px 6px rgba(0,0,0,0.08); }
  .thumb.placeholder { background: linear-gradient(135deg,#eee,#f7f7f7); }

  .meta { display:flex; flex-direction:column; min-width:0; }
  .proj-title {
    margin:0;
    font-size:1.05rem;
    color:#0b2545;
    white-space:nowrap;
    overflow:hidden;
    text-overflow:ellipsis;
  }

  .preview {
    margin:0.25rem 0 0;
    color:#334155;
    font-size:0.9rem;
    display:-webkit-box;
    -webkit-line-clamp:2;
    -webkit-box-orient:vertical;
    overflow:hidden;
  }

  .row-meta { margin-top:0.4rem; display:flex; gap:0.6rem; align-items:center; color:#567; font-size:0.85rem; }
  .role { font-weight:600; color:#234; }
  .date { color:#567; }

  .project-focus { margin-top:1rem; padding:1rem; background:#fff; border-radius:8px; border:1px solid #e6e6e6; }
  .focus-controls { display:flex; justify-content:space-between; align-items:center; gap:1rem; margin-bottom:0.75rem; }
  .back-btn { background:none; border:2px solid #567; color:#567; padding:0.4rem 0.8rem; border-radius:6px; cursor:pointer; font-weight:600; }
    .nav-controls {
    display: flex;
    align-items: center;
    gap: 1rem;
    }

    .image-count {
    font-size: 1rem;
    color: #475569;
    min-width: 3rem;
    text-align: center;
    }
  .nav-btn { background:#f5f5f5; border:1px solid #ddd; padding:0.3rem 0.6rem; border-radius:6px; cursor:pointer; }

  .focus-header { display:flex; gap:1.25rem; align-items:flex-start; flex-wrap:wrap; }
  .focus-left { flex:1 1 360px; min-width:260px; }
  .focus-title { margin:0 0 0.25rem 0; color:#0b2545; font-size:1.6rem; }
  .meta-row { display:flex; gap:0.6rem; align-items:center; margin-bottom:0.5rem; flex-wrap:wrap; }
  .tags { display:flex; gap:0.4rem; }
  .tag { background:#f0f6ff; color:#0b2545; padding:0.15rem 0.5rem; border-radius:6px; font-size:0.8rem; }

  .lead { margin:0 0 0.75rem 0; color:#334155; }

  .links { display:flex; gap:0.6rem; flex-wrap:wrap; margin-bottom:0.5rem; }
  .link { color:#0b2545; text-decoration:underline; font-weight:600; }

  .tech { color:#334155; font-size:0.95rem; margin-top:0.5rem; }

.gallery {
  width: 100%;
  display: flex;
  justify-content: center;
  margin-top: 1rem;
}

.main-image-wrap {
  width: 100%;
  max-width: 900px;
  height: auto;
  border-radius: 10px;
  overflow: hidden;
  background: #f7f7f7;
}

.main-image {
  width: 100%;
  height: auto;
  object-fit: cover;
}

.thumb-row {
  display: none;
}

  .thumb-btn { border:1px solid #eee; padding:0; background:#fff; border-radius:6px; cursor:pointer; }
  .thumb-btn img { width:64px; height:48px; object-fit:cover; display:block; border-radius:6px; }
  .thumb-btn.active { outline:3px solid rgba(11,37,69,0.12); }

  .no-image { color:#567; padding:1rem; border-radius:6px; background:#fafafa; }

  .focus-body { margin-top:1rem; color:#444; line-height:1.6; }
  .focus-body ul { margin-left:1.2rem; }

  /* responsive */
  @media (max-width: 900px) {
    .focus-header { flex-direction:column; }
    .gallery { width:100%; max-width:100%; min-width:0; }
    .main-image-wrap { height:220px; }
  }

  .zoom-modal {
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.85);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 999999;
    pointer-events: auto;
  }

  .zoom-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 12px;
  }

  .zoom-caption {
    color: whitesmoke;
    font-size: 1rem;
    text-align: center;
    max-width: 80%;
  }

  .zoom-img {
    max-width: 90vw;
    max-height: 80vh;
    border-radius: 8px;
    box-shadow: 0 0 20px rgba(0,0,0,0.5);
    object-fit: contain;
  }

  .zoom-arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(255,255,255,0.2);
    border: none;
    color: white;
    font-size: 2rem;
    padding: 8px 12px;
    cursor: pointer;
    border-radius: 6px;
    z-index: 1000000;
  }

  .zoom-arrow.left {
    left: 20px;
  }

  .zoom-arrow.right {
    right: 20px;
  }

  .zoom-arrow:hover {
    background: rgba(255,255,255,0.35);
  }

.project-list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.2rem;
  padding: 0.5rem 0;
}

.project-row {
  display: flex;
  flex-direction: column;
  background: #fafafa;
  border: 1px solid #e6e6e6;
  border-radius: 10px;
  overflow: hidden;
  cursor: pointer;
  transition: transform 0.12s ease, box-shadow 0.12s ease;
}

.project-row:hover {
  transform: translateY(-4px);
  box-shadow: 0 6px 18px rgba(0,0,0,0.06);
}

.thumb {
  width: 100%;
  height: 220px;
  object-fit: cover;
  display: block;
}

.meta {
  padding: 0.75rem 1rem;
}

.proj-title {
  margin: 0;
  font-size: 1.2rem;
  color: #0b2545;
}

.preview {
  margin-top: 0.4rem;
  color: #334155;
  font-size: 0.95rem;
}

.caption-text {
  margin-top: 0.75rem; 
  font-size: 1rem;
  color: #334155;
  text-align: center;
  max-width: 90%;
  margin-left: auto;
  margin-right: auto;
}

.main-image {
  width: auto;
  max-width: 100%;
  max-height: 80vh;
  object-fit: contain;
  display: block;
  margin: 0 auto;
}




</style>

