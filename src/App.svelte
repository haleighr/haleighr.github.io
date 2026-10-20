<script>
  import resume from './assets/Haleigh_Renfroe_Resume_2026.pdf'
  import secret from './assets/image.png'

  let showSecret = $state(false)

  const projects = [
    { name: 'Alternative Appalachia', year: 'Sep 2026 - Present', desc: 'A website made with Svelte that allows people to find alternative shows and events around Appalachia. People can also submit flyers to events they are hosting.', link: 'https://alternative-appalachia.web.app/' },
    { name: 'Anechoic Chamber Turntable', year: 'Jun 2026 - Present', desc: 'Helped write the firmware (C) and controller (Python) for an antenna turntable at MSU.', link: 'https://github.com/msu-ssc/anechoic-turntable' },
    { name: 'Facelock - Senior Capstone', year: 'Aug 2025 - May 2026', desc: 'My senior project; a Python program that gives real time security to everyday laptops with constant 3D face recognition. Won Most Outstanding Senior Research Project.', link: 'https://github.com/haleighr/capstone-facelock' },
    { name: 'Junior College Basketball Recruiting Database', year: 'Jan 2026 - May 2026', desc: 'A team-built full-stack recruiting platform that gathers NJCAA player data into one searchable database, actively used by the MSU women\'s basketball team. I built frontend features in React and Vite for filtering and comparing athletes.', link: null },
  ]

  const blinkies = ['family-guy', 'bliss', '70s-show', 'geek', 'sprite', 'surfer', 'clubpenguin', 'zombies', 'nyancat']

  const visitors = String(Math.floor(Math.random() * 90000) + 10000).padStart(6, '0')
</script>

<div class="page">
  <header class="banner">
    <h1>Haleigh Renfroe</h1>
    <div class="marquee">
      <div class="track">
        {#each [...blinkies, ...blinkies] as b}
          <img src="/blinkies/{b}.gif" alt="" width="150" height="20" />
        {/each}
      </div>
    </div>
  </header>

  <div class="layout">
    <nav class="sidebar box">
      <div class="box-title">Navigation</div>
      <ul>
        <li><a href="#about">» About Me</a></li>
        <li><a href="#projects">» Projects</a></li>
        <li><a href="#contact">» Contact</a></li>
      </ul>
      <div class="counter">
        <p>You are visitor #</p>
        <div class="digits">{visitors}</div>
      </div>
    </nav>

    <main>
      <section id="about" class="box">
        <div class="box-title">About Me</div>
        <div class="box-body">
          <p>Hi :) I'm Haleigh! I'm currently a software engineer for Morehead State University's Space Science Center.
            I write a lot of Python at my job, but I've been getting into web design in my personal time. When I'm not writing code, I like to play bass and drums, hang out with my cat Tina, and drink Pepsi while I play on my Nintendo Wii.
            If you'd like to check out my resume, click the button below!
          </p>
          <a class="button" href={resume} target="_blank" rel="noreferrer">Resume :3</a>
        </div>
      </section>

      <section id="projects" class="box">
        <div class="box-title">Projects</div>
        <div class="box-body">
          {#each projects as p}
            <div class="project">
              <h3>{#if p.link}<a href={p.link}>{p.name}</a>{:else}{p.name}{/if} <span class="year">[{p.year}]</span></h3>
              <p>{p.desc}</p>
            </div>
          {/each}
        </div>
      </section>

      <section id="contact" class="box">
        <div class="box-title">Contact</div>
        <div class="box-body">
          <p>Want to get in touch? Drop me a line!</p>
          <ul class="links">
            <li>✉ Email: <a href="mailto:haleighrenfroe@gmail.com">haleighrenfroe@gmail.com</a></li>
            <li>⌨ GitHub: <a href="https://github.com/haleighr">github.com/haleighr</a></li>
            <li>☍ LinkedIn: <a href="https://linkedin.com/in/haleigh-renfroe">linkedin.com/in/haleigh-renfroe</a></li>
          </ul>
        </div>
      </section>
    </main>
  </div>

  <footer>
    <hr />
    <p><button class="secret" onclick={() => (showSecret = true)}>©</button> 2026 Haleigh Renfroe &nbsp;|&nbsp; Made with Svelte &nbsp;|&nbsp; Cursors from <a href="https://www.rw-designer.com/cursor-set/old-roblox">rw-designer.com</a></p>
  </footer>
</div>

{#if showSecret}
  <div class="popup box">
    <div class="box-title popup-title">
      secret.png
      <button onclick={() => (showSecret = false)}>X</button>
    </div>
    <img src={secret} alt="A tortoiseshell cat resting on a bed" />
  </div>
{/if}
