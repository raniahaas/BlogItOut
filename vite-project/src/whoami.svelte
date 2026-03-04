<script>
  export let navigate = (p) => (location.pathname = p); // fallback if not provided
  import img from './assets/IMG_2650.JPG';
  let lang = 'ENG'; // default language

  function toggleLang() {
    lang = lang === 'ENG' ? 'JP' : 'ENG';
  }
  
</script>

<main class="container">
  <!-- Language Toggle -->
  <div class="lang-toggle">
    <button on:click={toggleLang}>
      {lang === 'ENG' ? '日本語' : 'ENG'}
    </button>
  </div>

  <!-- Header -->
  <header class="about-header">
    <div class="header-bar">
      <h1 class="title">{lang === 'ENG' ? 'About Me' : 'お紹介'}</h1>
      <nav class="nav">
        <a href="/" on:click|preventDefault={() => navigate('/')}>Home</a>
        <a href="/about" on:click|preventDefault={() => navigate('/about')}>About</a>
        <a href="/projects" on:click|preventDefault={() => navigate('/projects')}>Projects</a>
        <a href="/resume" on:click|preventDefault={() => navigate('/resume')}>Resume</a>
      </nav>
    </div>

    <p class="subtitle">
      {lang === 'ENG'
        ? 'University of Cincinnati - College of Engineering and Applied Sciences Class of 2027'
        : 'シンシナティ大学 の 工学部・応用科学部 2027年卒業予定'}
    </p>

    <img class="profile-wrap" src={img} alt="Rania Haas" />
  </header>

  <!-- Bio -->
  <section class="bio">
    {#if lang === 'ENG'}
      <p>
        Hiya my name is Rania Haas and I am a current Junior at the University of Cincinnati studying Computer Science with a minor in Japanese! I have a passion for aerospace engineering and software development, and I love combining these interests to create innovative solutions.
      </p>
      <p>
        Other than trying to grow as a professional, I love to read and study new languages (both programming and spoken). I'm currently honing my C++ skills and improving my Japanese after getting N4 certified in January of 2025.
      </p>
    {:else}
      <p>
        ヤホ！レンヤ・ハースと申します。シンシナティ大学でコンピュータ科学を勉強し、副専攻。今年、あたしが３年生です。降雨空中とかソフトウェアとか本当に大好きです！プロジェクトを作る時、あたしの大好き物を考えてそうして革新的な解決策を作っていきます。
      </p>
      <p>
        暇があったら、たくさん本を読めるとか、新しい言語（プログラミング言語とか話す言語とか）を勉強したりします。今、C++と日本語を勉強を続けています。２０２５の１月に日本語能力試験のN4を受けました。まだ、N3~N1を続けたいです！
      </p>
    {/if}
  </section>

  <!-- Details -->
  <section class="details">
    <h2>{lang === 'ENG' ? '♡ What I Love' : '♡ 好きなこと'}</h2>
    <ul>
      <li>☆ {lang === 'ENG' ? 'Rockets Rockets Rockets!' : 'ロケットだいよ！アメリカではHPR（ハイパーワーロケット）です'}</li>
      <li>☆ {lang === 'ENG' ? 'Learning the anatomy of Kanji' : '漢字の意味と会報がくを学びます'}</li>
      <li>☆ {lang === 'ENG' ? 'Creating projects that are entertaining' : '楽しいプロジェクトを作ることです'}</li>
      <li>☆ {lang === 'ENG' ? 'Building aerospace systems with precision' : '安全かつ正確に航空宇宙システムを構築することです'}</li>
      <li>☆ {lang === 'ENG' ? 'Reading and learning new topics' : '新しいトピックを学び、読むことです'}</li>
    </ul>
  </section>

  <!-- Socials -->
  <section class="socials">
    <h2>{lang === 'ENG' ? '౨ৎ Connect with Me!' : '౨ৎ 連絡'}</h2>
    <div class="social-icons">
      <!-- LinkedIn -->
      <a href="https://www.linkedin.com/in/rania-maaraba-403987290/" target="_blank" aria-label="LinkedIn">
        <svg class="icon" viewBox="0 0 24 24" fill="currentColor">
          <path d="M4.98 3.5C4.98 4.88 3.87 6 2.5 6S0 4.88 0 3.5 1.12 1 2.5 1 4.98 2.12 4.98 3.5zM.5 8h4V24h-4V8zm7.5 0h3.6v2.16h.05c.5-.95 1.72-1.95 3.55-1.95 3.8 0 4.5 2.5 4.5 5.75V24h-4v-7.5c0-1.8-.03-4.12-2.5-4.12-2.5 0-2.88 1.95-2.88 3.98V24h-4V8z" />
        </svg>
      </a>

      <!-- GitHub -->
      <a href="https://github.com/raniahaas" target="_blank" aria-label="GitHub">
        <svg class="icon" viewBox="0 0 24 24" fill="currentColor">
          <path d="M12 .5C5.73.5.5 5.73.5 12c0 5.08 3.29 9.39 7.86 10.93.58.11.79-.25.79-.56v-2.02c-3.2.7-3.87-1.54-3.87-1.54-.53-1.35-1.3-1.71-1.3-1.71-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.78 2.73 1.27 3.4.97.11-.75.41-1.27.75-1.56-2.56-.29-5.26-1.28-5.26-5.7 0-1.26.45-2.3 1.2-3.11-.12-.29-.52-1.45.11-3.02 0 0 .97-.31 3.18 1.19a11.1 11.1 0 0 1 5.8 0c2.2-1.5 3.17-1.19 3.17-1.19.63 1.57.23 2.73.11 3.02.75.81 1.2 1.85 1.2 3.11 0 4.43-2.7 5.4-5.27 5.69.42.36.8 1.08.8 2.18v3.23c0 .31.21.67.8.56A10.5 10.5 0 0 0 23.5 12C23.5 5.73 18.27.5 12 .5z" />
        </svg>
      </a>

      <!-- Email -->
      <a href="mailto:maarabrn@mail.uc.edu" aria-label="Email">
        <svg class="icon" viewBox="0 0 24 24" fill="currentColor">
          <path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 2v.01L12 13 4 6.01V6h16zM4 18V8l8 5 8-5v10H4z" />
        </svg>
      </a>
    </div>
  </section>

</main>

<style>
  .lang-toggle {
    display: flex;
    justify-content: flex-end;
    margin-bottom: 1rem;
  }

  .lang-toggle button {
    background: none;
    border: 2px solid #567;
    color: #567;
    padding: 0.4rem 1rem;
    font-weight: 600;
    border-radius: 6px;
    cursor: pointer;
    transition: background 0.2s ease;
  }

  .lang-toggle button:hover {
    background: #f0f0f0;
  }
  .socials {
    margin-top: 3rem;
  }

  .socials h2 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
    color: #0b2545;
  }

  .social-icons {
    display: flex;
    gap: 1.5rem;
  }

  .icon {
    width: 32px;
    height: 32px;
    fill: #567;
    transition: transform 0.2s ease;
  }

  .icon:hover {
    transform: scale(1.1);
  }
  .header-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
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
    color: #567;
  }
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

  .profile-wrap {
    float: right;
    width: 150px;
    height: 210px;
    object-fit: cover;
    margin-left: 1.5rem;
    margin-bottom: 1rem;
    border-radius: 6px;
    box-shadow: 0 6px 18px rgba(0, 0, 0, 0.1);
  }


  .about-header p {
    color: #334155;
    line-height: 1.6;
    margin-bottom: 1rem;
  }
</style>
