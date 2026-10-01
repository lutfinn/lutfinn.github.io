<script>
  import Navbar from './lib/Navbar.svelte';
  import Hero from './lib/Hero.svelte';
  import About from './lib/About.svelte';
  import Experience from './lib/Experience.svelte';
  import Projects from './lib/Projects.svelte';
  import Skills from './lib/Skills.svelte';
  import References from './lib/References.svelte';
  import Contact from './lib/Contact.svelte';
</script>

<div id="top" class="app-root">
  <Navbar />
  <main>
    <Hero />
    <About />
    <Experience />
    <Projects />
    <Skills />
    <References />
    <Contact />
  </main>
</div>

<style>
  .app-root {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    position: relative;
    z-index: 1;
  }

  main {
    flex-grow: 1;
  }
</style>
