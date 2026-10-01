<script>
  let isScrolled = $state(false);
  let mobileMenuOpen = $state(false);

  function handleScroll() {
    isScrolled = window.scrollY > 40;
  }

  function toggleMobileMenu() {
    mobileMenuOpen = !mobileMenuOpen;
  }

  function closeMobileMenu() {
    mobileMenuOpen = false;
  }
</script>

<svelte:window onscroll={handleScroll} />

<header class="navbar" class:scrolled={isScrolled}>
  <div class="container nav-container">
    <a href="#top" class="brand">
      <div class="brand-avatar">
        <img src="./profile.png" alt="Lutfi Nurdin" />
      </div>
      <div class="brand-info">
        <span class="brand-name">Lutfi Nailufar Nurdin</span>
        <span class="brand-status">
          <span class="status-dot"></span>
          Principal Solutions Architect
        </span>
      </div>
    </a>

    <!-- Desktop Navigation -->
    <nav class="nav-links">
      <a href="#about" class="nav-link">About</a>
      <a href="#experience" class="nav-link">Experience</a>
      <a href="#projects" class="nav-link">Enterprise Systems</a>
      <a href="#skills" class="nav-link">Competencies</a>
      <a href="#references" class="nav-link">References</a>
      <a href="#contact" class="nav-link">Contact</a>
    </nav>

    <!-- Nav Actions -->
    <div class="nav-actions">
      <a href="./cv.html" target="_blank" class="btn btn-secondary nav-btn-cv" title="Open executive printable CV">
        <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path><polyline points="14 2 14 8 20 8"></polyline><line x1="16" y1="13" x2="8" y2="13"></line><line x1="16" y1="17" x2="8" y2="17"></line><polyline points="10 9 9 9 8 9"></polyline></svg>
        <span>View CV (Print)</span>
      </a>
      <a href="#contact" class="btn btn-primary nav-btn-cta">
        <span>Get in Touch</span>
      </a>

      <!-- Mobile Hamburger Button -->
      <button class="mobile-toggle" onclick={toggleMobileMenu} aria-label="Toggle navigation">
        <span class="bar" class:active={mobileMenuOpen}></span>
        <span class="bar" class:active={mobileMenuOpen}></span>
        <span class="bar" class:active={mobileMenuOpen}></span>
      </button>
    </div>
  </div>

  <!-- Mobile Menu Dropdown -->
  {#if mobileMenuOpen}
    <div class="mobile-menu">
      <nav class="mobile-nav-links">
        <a href="#about" onclick={closeMobileMenu}>About</a>
        <a href="#experience" onclick={closeMobileMenu}>Experience</a>
        <a href="#projects" onclick={closeMobileMenu}>Enterprise Systems</a>
        <a href="#skills" onclick={closeMobileMenu}>Competencies</a>
        <a href="#references" onclick={closeMobileMenu}>References</a>
        <a href="#contact" onclick={closeMobileMenu}>Contact</a>
        <div class="mobile-menu-divider"></div>
        <a href="./cv.html" target="_blank" class="btn btn-secondary" style="width: 100%; justify-content: center;">
          📄 View Printable CV
        </a>
      </nav>
    </div>
  {/if}
</header>

<style>
  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    padding: 18px 0;
    transition: all 0.3s ease;
    border-bottom: 1px solid transparent;
  }

  .navbar.scrolled {
    padding: 12px 0;
    background: rgba(7, 11, 18, 0.88);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    box-shadow: 0 10px 30px -10px rgba(0, 0, 0, 0.5);
  }

  .nav-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .brand {
    display: flex;
    align-items: center;
    gap: 12px;
    text-decoration: none;
  }

  .brand-avatar {
    width: 42px;
    height: 42px;
    border-radius: 50%;
    overflow: hidden;
    border: 2px solid rgba(6, 182, 212, 0.5);
    box-shadow: 0 0 12px rgba(6, 182, 212, 0.3);
    flex-shrink: 0;
  }

  .brand-avatar img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .brand-info {
    display: flex;
    flex-direction: column;
  }

  .brand-name {
    font-size: 15px;
    font-weight: 700;
    color: #ffffff;
    line-height: 1.2;
    letter-spacing: -0.2px;
  }

  .brand-status {
    font-size: 11px;
    color: var(--text-muted);
    display: flex;
    align-items: center;
    gap: 6px;
    margin-top: 2px;
  }

  .nav-links {
    display: flex;
    align-items: center;
    gap: 28px;
  }

  .nav-link {
    font-size: 13.5px;
    font-weight: 500;
    color: var(--text-muted);
    text-decoration: none;
    transition: color 0.2s ease;
    position: relative;
  }

  .nav-link:hover {
    color: #ffffff;
  }

  .nav-link:hover::after {
    content: '';
    position: absolute;
    bottom: -6px;
    left: 0;
    right: 0;
    height: 2px;
    background: var(--cyan);
    border-radius: 2px;
  }

  .nav-actions {
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .nav-btn-cv {
    padding: 8px 16px;
    font-size: 13px;
  }

  .nav-btn-cta {
    padding: 8px 18px;
    font-size: 13px;
  }

  .mobile-toggle {
    display: none;
    background: none;
    border: none;
    cursor: pointer;
    flex-direction: column;
    gap: 5px;
    padding: 6px;
  }

  .mobile-toggle .bar {
    width: 22px;
    height: 2px;
    background: #ffffff;
    border-radius: 2px;
    transition: all 0.2s ease;
  }

  .mobile-menu {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background: rgba(10, 15, 26, 0.98);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border-subtle);
    padding: 24px;
    box-shadow: 0 20px 40px rgba(0,0,0,0.6);
  }

  .mobile-nav-links {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .mobile-nav-links a {
    color: #cbd5e1;
    text-decoration: none;
    font-size: 16px;
    font-weight: 600;
  }

  .mobile-menu-divider {
    height: 1px;
    background: var(--border-subtle);
    margin: 8px 0;
  }

  @media (max-width: 992px) {
    .nav-links {
      display: none;
    }
    .mobile-toggle {
      display: flex;
    }
    .nav-btn-cta {
      display: none;
    }
  }

  @media (max-width: 576px) {
    .brand-name {
      font-size: 13.5px;
    }
    .brand-status {
      font-size: 10px;
    }
    .nav-btn-cv span {
      display: none;
    }
    .nav-btn-cv {
      padding: 8px 10px;
    }
  }
</style>
