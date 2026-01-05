<script>
  export let navigate = (p) => (location.pathname = p);
  let lang = 'ENG';

  function toggleLang() {
    lang = lang === 'ENG' ? 'JP' : 'ENG';
  }
</script>

<main class="container">
  <!-- Top bar with language toggle and PDF download -->
  <div class="top-bar">
    <div class="lang-toggle">
      <button on:click={toggleLang}>
        {lang === 'ENG' ? '日本語' : 'ENG'}
      </button>
    </div>
    <div class="resume-download">
      <a href="/public/Maaraba_Rania_Resume_2025_12.pdf" download>
        {lang === 'ENG' ? '↓ Download Most Recent Resume' : '↓ 履歴書をダウンロード'}
      </a>
    </div>
  </div>

  <!-- Header with nav -->
  <header class="resume-header">
    <div class="header-bar">
      <h1 class="title">{lang === 'ENG' ? 'Resume' : '履歴書'}</h1>
      <nav class="nav">
        <a href="/" on:click|preventDefault={() => navigate('/')}>Home</a>
        <a href="/about" on:click|preventDefault={() => navigate('/about')}>About</a>
        <a href="/projects" on:click|preventDefault={() => navigate('/projects')}>Projects</a>
        <a href="/resume" on:click|preventDefault={() => navigate('/resume')}>Resume</a>
      </nav>
    </div>
  </header>

  <!-- Hard-coded resume content -->
  <section class="resume-section">
    <h2>{lang === 'ENG' ? 'Education' : '学歴'}</h2>
        <div class="resume-item">
            <h3>
            {lang === 'ENG'
                ? 'University of Cincinnati — B.S. Computer Science, Minor in Japanese Culture & Language'
          : 'シンシナティ大学の学士のコンピュータ科学、日本の文化の副専攻'}
            </h3>
            <p class="date">
            {lang === 'ENG' ? '2023 – 2027' : '2023年〜2027年'}
            </p>
        </div>
  </section>



  <section class="resume-section">
  <h2>{lang === 'ENG' ? 'Experience' : '仕事の経験'}</h2>

    <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? "McDonald's Coporate — Global Women in Technology Mentee"
        : 'マックドナルドコーポレート • グローバル女性技術メンティー'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? 'Feb 2025 – Present' : '2025年2月から原稿まで'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? "With the assignment of a Software Engineer at McDonald's, I am developing skills in professional development, career-oriented projects, tactics, real-world problems, and personal development skills" : 'マックのソフトウェア工学者と玄人の発展とか、指導とか作っていらしゃいます。'}</li>
      <li>{lang === 'ENG' ? 'Frequent practice in technical interviews as well as project deliverables to a non-tech related audience. Participated in-person with their Global Women in Technology Program highlighting the authenticity and knowledge of leadership roles in their cooperate careers' : '技術的な面接を練習し、アナログ人間にプロジェクトの成果物をお作りなります。'}</li>
    </ul>
  </div>

  <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? 'GMi Companies — Information Services Engineering Intern'
        : 'GMi会社 • 情報サービスエンジニアリングインターン'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? '2024 – 2025' : '2024年〜2025年'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? 'Developed code in C/AL with Microsoft Dynamics NAV which primarily included coding projects for creating better quality of life for floor workers as well as developing and utilising Microsoft Report Builder.' : 'マイクロソフト•ダイナミックス•ナブでC/ALコードを蓄えし、'}</li>
      <li>{lang === 'ENG' ? 'Collaborated with many departments across the company from Marketing to Logistics to Finance. Was able to develop over 45 quality of life and other project improvements to the system while working alongside other interns.' : '航空宇宙エンジニアと安全システムで協力。'}</li>
    </ul>

    <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? 'Code Ninjas - Code Sensei'
        : 'Web開発 — Svelte/Tailwindを用いたレスポンシブアプリケーション'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? ' 2021 – 2023' : '2025年1月〜現在'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? "A school-based chain that worked on K-8 coding skills by game development. Helped instruct programming learning primarlly in JavaScript to help bring a student's game idea to life." : 'ENG/日本語切替付きポートフォリオサイトを構築。'}</li>
      <li>{lang === 'ENG' ? "Lead weekend 'clubs' in development of Java for creating Minecraft mods as well as Lua for Roblox games. Cultivated personal programming and engineering skills by designing and developing custom coding exercises projects for students to help promote expression and education. " : 'TailwindCSSでブランド化されたレイアウトを設計。'}</li>
    </ul>
  </div>
  
  </div>

  
</section>

<section class="resume-section">
  <h2>{lang === 'ENG' ? 'Activites' : '職務経験'}</h2>

  <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? 'UCRO - University of Cincinnati Rocketry'
        : '航空宇宙システムプロジェクト — フライト制御ソフトウェア開発'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? 'June 2025 – Present' : '2024年5月〜2024年8月'}
    </p>
    <p class="postions">
      {lang === 'ENG' ? 'Boosted Dart Avionics Coder | 2025 Mentorship Program Mentee' : '2024年5月〜2024年8月'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? 'Developed embedded C++ modules for flight control fitted for a boosted dart on a collaberative level. Created code for projects that require dual deployment systems as well as experiments to run within the launch window' : 'フライト制御用の組込みC++モジュールを開発。'}</li>
      <li>{lang === 'ENG' ? "Selected as a mentee to develop my NAR L2 certifiable rocket under the current club's President who is in addition Level 2 Certified. Developing several skills from intial structures and development of the rocket to 3D modeling skills with Fusion360" : '航空宇宙エンジニアと安全システムで協力。'}</li>
    </ul>
  </div>

  <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? 'Turning Point USA University of Cincinnati'
        : 'Web開発 — Svelte/Tailwindを用いたレスポンシブアプリケーション'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? 'Sept 2025 – Present' : '2025年1月〜現在'}
    </p>
    <p class="postions">
      {lang === 'ENG' ? 'Member and Volunteer' : '2024年5月〜2024年8月'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? 'Promoting conversations across the spectrum as well as educating young College Americans on current affairs and the Word of the Lord' : 'ENG/日本語切替付きポートフォリオサイトを構築。'}</li>
      <li>{lang === 'ENG' ? 'Helping lead and organise events to protect high-level political figures as well as inform the community of such events. Fortunate to be able to host Vivek Ramaswamy and Riley Gaines ' : 'TailwindCSSでブランド化されたレイアウトを設計。'}</li>
    </ul>
  </div>

  <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? 'University of Cincinnati Symphonic Orchesta'
        : 'Web開発 — Svelte/Tailwindを用いたレスポンシブアプリケーション'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? '2023 – 2024' : '2025年1月〜現在'}
    </p>
    <p class="postions">
      {lang === 'ENG' ? 'Violinist' : '2024年5月〜2024年8月'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? 'Performed and rehered throughout the school year to perform with a professional sound rivaling many of the starting Orchestras in the Conservatory of Music at the University of Cincinnati' : 'ENG/日本語切替付きポートフォリオサイトを構築。'}</li>
      <li>{lang === 'ENG' ? "Enforced strict discipline to keep up a high level of study as well as performing and practicing professional-level pieces such as Rossini's Barber of Seville, Bizet Carmen, and Rachmaninoff's Piano Concerto No. 2" : 'TailwindCSSでブランド化されたレイアウトを設計。'}</li>
    </ul>
  </div>
</section>

<section class="resume-section">
  <h2>{lang === 'ENG' ? 'Projects' : '職務経験'}</h2>

  <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? 'National Association of Rocketry Level 2 Certification — NAR L2 Rocket Build & Avionics'
        : 'Web開発 — Svelte/Tailwindを用いたレスポンシブアプリケーション'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? 'Sept 2025 – Present' : '2025年1月〜現在'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? 'Building a L2 certifible rocket through UCRO and NAR to achieve Level 2 certificiation with a diameter of 4in. Developed using Open Rocket with two parachutes that achieved an apogee of 5,000ft' : 'ENG/日本語切替付きポートフォリオサイトを構築。'}</li>
      <li>{lang === 'ENG' ? 'Designed a completley custom 3D printed avionics bay using Fusion360 with a custom flight computer' : 'TailwindCSSでブランド化されたレイアウトを設計。'}</li>
    </ul>
  </div>

  <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? 'Radiji - Local Japanese Kanji Dictonary App'
        : 'Web開発 — Svelte/Tailwindを用いたレスポンシブアプリケーション'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? 'June 2024 – Present' : '2025年1月〜現在'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? 'Local app designed to allow users to be able to easily access and learn new Kanji on the go' : 'ENG/日本語切替付きポートフォリオサイトを構築。'}</li>
      <li>{lang === 'ENG' ? 'Developing in JavaScript with React and Postgres with backend integration' : 'TailwindCSSでブランド化されたレイアウトを設計。'}</li>
    </ul>
  </div>

  <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? "Univeristy of Cincinnati Rocketry — Boosted Dart Avionics Development"
        : '航空宇宙システムプロジェクト — フライト制御ソフトウェア開発'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? 'Sept 2025 – December 2025' : '2024年5月〜2024年8月'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? 'Developed embedded C++ modules for flight control and logging' : 'フライト制御用の組込みC++モジュールを開発。'}</li>
      <li>{lang === 'ENG' ? "Collaborated with structures team to ensure the avionics bay's compatibility with the boosted dart" : '航空宇宙エンジニアと安全システムで協力。'}</li>
    </ul>
  </div>

  <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? 'Svelte Portfolio through User Interfaces Course'
        : 'Web開発 — Svelte/Tailwindを用いたレスポンシブアプリケーション'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? 'Aug 2025 – December 2025' : '2025年1月〜現在'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? 'Developed several user interface projects with Svelte' : 'ENG/日本語切替付きポートフォリオサイトを構築。'}</li>
      <li>{lang === 'ENG' ? 'Created projects allowing users to journal, pick out outfits based on compatibility, re-designed a Univeristy of Cincinnati page, as well as created an interface to help users learn alternative medicines' : 'TailwindCSSでブランド化されたレイアウトを設計。'}</li>
    </ul>
  </div>

  <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? 'Rockets for Schools Competition — High Power Rocket Avionics Design & Development'
        : 'Web開発 — Svelte/Tailwindを用いたレスポンシブアプリケーション'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? 'Jan 2022 – May 2022 ' : '2025年1月〜現在'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? 'Built a custom L2 rocket with avionics bay to launch over Lake Michigan to read the sublimation rate of Dry Ice as the rocekt reaches apogee' : 'ENG/日本語切替付きポートフォリオサイトを構築。'}</li>
      <li>{lang === 'ENG' ? 'Developed by hand the electronics board, programming, and saudering ' : 'TailwindCSSでブランド化されたレイアウトを設計。'}</li>
    </ul>
  </div>

  <div class="resume-item">
    <h3>
      {lang === 'ENG'
        ? 'National Association of Rocketry Level 1 Certification — NAR L1 Rocket Build'
        : 'Web開発 — Svelte/Tailwindを用いたレスポンシブアプリケーション'}
    </h3>
    <p class="date">
      {lang === 'ENG' ? 'Aug 2021 – Nov 2021' : '2025年1月〜現在'}
    </p>
    <ul>
      <li>{lang === 'ENG' ? 'Created a fiber-glass rocket and had a sucessful launch leading to my NAR Jr Level 1 Certification ' : 'ENG/日本語切替付きポートフォリオサイトを構築。'}</li>
      <li>{lang === 'ENG' ? 'Developed and designed the rocket from start to finish, learning the intricates of working with fiberglass and carbon fiber' : 'TailwindCSSでブランド化されたレイアウトを設計。'}</li>
    </ul>
  </div>
</section>


  <section class="resume-section">
    <h2>{lang === 'ENG' ? 'Skills' : 'スキル'}</h2>
    <ul>
      <li>{lang === 'ENG' ? 'Languages: C++, Python, JavaScript, SQL, LabVIEW' : '言語: C++, Python, JavaScript, 日本語（JLPT N4）'}</li>
      <li>{lang === 'ENG' ? 'Software: DynamicsNAV, Fusion360, Arduuino, Pandas, Numpy' : 'フレームワーク: Svelte, TailwindCSS'}</li>
      <li>{lang === 'ENG' ? 'Focus: Aerospace avionics systems, UI design, embedded software' : '専門分野: 航空宇宙システム、UIデザイン、組込みソフトウェア'}</li>
    </ul>
  </section>
</main>

<style>
    .resume-item {
    margin-bottom: 2rem;
    }

    .resume-item h3 {
    font-size: 1.2rem;
    font-weight: 600;
    color: #0b2545;
    margin: 0;
    }

    .resume-item .date {
    font-size: 0.95rem;
    color: #567;
    margin: 0.25rem 0 0.75rem 0; /* small gap below title */
    text-align: left; /* ensures left alignment */
    }

    .resume-item ul {
    list-style: disc;
    padding-left: 1.5rem;
    color: #334155;
    }
  .top-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
  }

  .lang-toggle button {
    border: 2px solid #567;
    background: none;
    color: #567;
    padding: 0.4rem 1rem;
    border-radius: 6px;
    cursor: pointer;
    font-weight: 600;
  }

  .resume-download a {
    color: #567;
    font-weight: 600;
    text-decoration: none;
    border: 2px solid #567;
    padding: 0.4rem 1rem;
    border-radius: 6px;
    transition: background 0.2s ease;
  }

  .resume-download a:hover {
    background: #f0f0f0;
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

  .resume-section {
    margin-top: 2rem;
  }

  .resume-section h2 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
    color: #0b2545;
  }

  .resume-section ul {
    list-style: none;
    padding: 0;
  }

  .resume-section li {
    margin-bottom: 0.5rem;
    color: #334155;
  }
</style>
