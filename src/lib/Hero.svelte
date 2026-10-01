<script>
  import { cvData } from '../data/cv-data.js';

  const { personal, metrics } = cvData;
</script>

<section class="hero-section">
  <div class="container hero-container">
    <!-- Left Hero Column: Copy & Actions -->
    <div class="hero-content">
      <div class="badge badge-glow hero-badge">
        <span class="status-dot"></span>
        <span>25+ Years Enterprise Engineering Leadership</span>
      </div>

      <h1 class="hero-title">
        Architecting <span class="gradient-text">National Telecom</span>, Financial Switches & Enterprise Cloud Systems
      </h1>

      <p class="hero-lead">
        I am <strong>{personal.name}</strong>, a Senior Principal Solutions Architect with over a quarter-century of frontline engineering excellence for <strong>Telkom Group</strong>, <strong>Telkomsigma</strong>, and high-throughput financial switching institutions.
      </p>

      <div class="hero-highlights">
        <div class="highlight-chip">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
          <span>Pioneered Telkomsel ISO 8583 Recharge Gateway (99.99% Uptime)</span>
        </div>
        <div class="highlight-chip">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
          <span>Engineered Telkom eRUPS (Odoo ERP Framework) & Threat Map Telemetry</span>
        </div>
        <div class="highlight-chip">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
          <span>Mastery in Java Spring Boot, Python, Oracle, Linux & Microservices</span>
        </div>
      </div>

      <div class="hero-actions">
        <a href="#projects" class="btn btn-primary hero-btn-main">
          <span>Explore Flagship Systems</span>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
        </a>

        <a href="./cv.html" target="_blank" class="btn btn-secondary hero-btn-cv">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path><polyline points="7 10 12 15 17 10"></polyline><line x1="12" y1="15" x2="12" y2="3"></line></svg>
          <span>Download Executive CV</span>
        </a>

        <a href={`https://wa.me/${personal.phoneClean}`} target="_blank" class="btn btn-outline hero-btn-wa" title="Chat on WhatsApp">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M.057 24l1.687-6.163c-1.041-1.804-1.588-3.849-1.587-5.946.003-6.556 5.338-11.891 11.893-11.891 3.181.001 6.167 1.24 8.413 3.488 2.245 2.248 3.481 5.236 3.48 8.414-.003 6.557-5.338 11.892-11.893 11.892-1.99-.001-3.951-.5-5.688-1.448l-6.305 1.654zm6.597-3.807c1.676.995 3.276 1.591 5.392 1.592 5.448 0 9.886-4.434 9.889-9.885.002-5.462-4.415-9.89-9.881-9.892-5.452 0-9.887 4.434-9.889 9.884-.001 2.225.651 3.891 1.746 5.634l-.999 3.648 3.742-.981zm11.387-5.464c-.074-.124-.272-.198-.57-.347-.297-.149-1.758-.868-2.031-.967-.272-.099-.47-.149-.669.149-.198.297-.768.967-.941 1.165-.173.198-.347.223-.644.074-.297-.149-1.255-.462-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.297-.347.446-.521.151-.172.2-.296.3-.495.099-.198.05-.372-.025-.521-.075-.148-.669-1.611-.916-2.206-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.695.248-1.29.173-1.414z"/></svg>
          <span>WhatsApp</span>
        </a>
      </div>
    </div>

    <!-- Right Hero Column: Holographic Photo & Floating Badges -->
    <div class="hero-visual">
      <div class="visual-glow-halo"></div>
      
      <div class="avatar-card">
        <div class="avatar-inner">
          <img src="./profile.png" alt="Lutfi Nailufar Nurdin" class="hero-photo" />
          <div class="photo-overlay-shine"></div>
        </div>
      </div>

      <!-- Floating Tech Chips -->
      <div class="floating-badge badge-1 animate-float">
        <span class="icon">⚡</span>
        <div>
          <div class="title">ISO 8583 Protocol</div>
          <div class="desc">Telkomsel Recharge Gateway</div>
        </div>
      </div>

      <div class="floating-badge badge-2 animate-float" style="animation-delay: 1.5s;">
        <span class="icon">🛡️</span>
        <div>
          <div class="title">Telkom Threat Map</div>
          <div class="desc">Real-time Cyber Telemetry</div>
        </div>
      </div>

      <div class="floating-badge badge-3 animate-float" style="animation-delay: 2.8s;">
        <span class="icon">🏛️</span>
        <div>
          <div class="title">Telkom eRUPS</div>
          <div class="desc">Odoo ERP • Zero-Downtime</div>
        </div>
      </div>
    </div>
  </div>

  <!-- Bottom Metric Counters -->
  <div class="container">
    <div class="metrics-strip glass-card">
      {#each metrics as m}
        <div class="metric-item">
          <div class="metric-val gradient-text">{m.value}</div>
          <div class="metric-lbl">{m.label}</div>
          <div class="metric-sub">{m.desc}</div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .hero-section {
    padding-top: 130px;
    padding-bottom: 70px;
    position: relative;
    overflow: hidden;
  }

  .hero-container {
    display: grid;
    grid-template-columns: 1.25fr 1fr;
    gap: 48px;
    align-items: center;
    margin-bottom: 60px;
  }

  .hero-badge {
    margin-bottom: 20px;
    font-size: 13px;
    padding: 6px 16px;
  }

  .hero-title {
    font-size: 46px;
    font-weight: 800;
    line-height: 1.18;
    margin-bottom: 22px;
    letter-spacing: -1px;
  }

  .hero-lead {
    font-size: 17px;
    color: var(--text-muted);
    line-height: 1.65;
    margin-bottom: 24px;
  }

  .hero-lead strong {
    color: #ffffff;
  }

  .hero-highlights {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-bottom: 32px;
  }

  .highlight-chip {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 14px;
    color: #cbd5e1;
  }

  .highlight-chip svg {
    color: var(--cyan);
    flex-shrink: 0;
  }

  .hero-actions {
    display: flex;
    align-items: center;
    gap: 14px;
    flex-wrap: wrap;
  }

  .hero-btn-main {
    padding: 14px 28px;
    font-size: 15px;
  }

  .hero-btn-cv, .hero-btn-wa {
    padding: 14px 20px;
    font-size: 15px;
  }

  .hero-btn-wa svg {
    color: #25d366;
  }

  /* Visual Column */
  .hero-visual {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 440px;
  }

  .visual-glow-halo {
    position: absolute;
    width: 380px;
    height: 380px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(14, 165, 233, 0.25) 0%, rgba(99, 102, 241, 0.15) 50%, transparent 70%);
    filter: blur(50px);
    z-index: 0;
  }

  .avatar-card {
    position: relative;
    z-index: 1;
    width: 320px;
    height: 380px;
    border-radius: 28px;
    padding: 10px;
    background: linear-gradient(135deg, rgba(255,255,255,0.15) 0%, rgba(14, 165, 233, 0.2) 50%, rgba(99, 102, 241, 0.2) 100%);
    box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.7), 0 0 40px rgba(14, 165, 233, 0.2);
  }

  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 20px;
    overflow: hidden;
    position: relative;
    background: #0f172a;
  }

  .hero-photo {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center 20%;
    display: block;
    filter: contrast(1.05) brightness(1.02);
  }

  .photo-overlay-shine {
    position: absolute;
    inset: 0;
    background: linear-gradient(180deg, transparent 60%, rgba(15, 23, 42, 0.8) 100%);
    pointer-events: none;
  }

  /* Floating Badges */
  .floating-badge {
    position: absolute;
    z-index: 2;
    background: rgba(15, 23, 42, 0.88);
    backdrop-filter: blur(14px);
    border: 1px solid rgba(255, 255, 255, 0.12);
    border-radius: 14px;
    padding: 10px 14px;
    display: flex;
    align-items: center;
    gap: 10px;
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.5);
    max-width: 240px;
  }

  .floating-badge .icon {
    font-size: 20px;
    background: rgba(255, 255, 255, 0.06);
    width: 36px;
    height: 36px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }

  .floating-badge .title {
    font-size: 12px;
    font-weight: 700;
    color: #ffffff;
    line-height: 1.2;
  }

  .floating-badge .desc {
    font-size: 11px;
    color: var(--cyan);
    margin-top: 2px;
  }

  .badge-1 {
    top: 20px;
    left: -20px;
    border-color: rgba(6, 182, 212, 0.3);
  }

  .badge-2 {
    bottom: 40px;
    left: -30px;
    border-color: rgba(99, 102, 241, 0.3);
  }

  .badge-3 {
    top: 50%;
    right: -25px;
    transform: translateY(-50%);
    border-color: rgba(16, 185, 129, 0.3);
  }

  /* Metrics Strip */
  .metrics-strip {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    padding: 28px 36px;
    gap: 24px;
    border: 1px solid rgba(255, 255, 255, 0.08);
  }

  .metric-item {
    text-align: center;
    position: relative;
  }

  .metric-item:not(:last-child)::after {
    content: '';
    position: absolute;
    right: -12px;
    top: 15%;
    height: 70%;
    width: 1px;
    background: rgba(255, 255, 255, 0.08);
  }

  .metric-val {
    font-size: 38px;
    font-weight: 900;
    line-height: 1.1;
    font-family: var(--font-display);
    margin-bottom: 6px;
  }

  .metric-lbl {
    font-size: 14px;
    font-weight: 700;
    color: #ffffff;
    margin-bottom: 4px;
  }

  .metric-sub {
    font-size: 12px;
    color: var(--text-muted);
    line-height: 1.4;
  }

  @media (max-width: 992px) {
    .hero-container {
      grid-template-columns: 1fr;
      text-align: center;
    }
    .hero-title {
      font-size: 36px;
    }
    .hero-highlights {
      align-items: center;
    }
    .hero-actions {
      justify-content: center;
    }
    .metrics-strip {
      grid-template-columns: 1fr 1fr;
    }
    .metric-item:not(:last-child)::after {
      display: none;
    }
  }

  @media (max-width: 640px) {
    .hero-title {
      font-size: 30px;
    }
    .metrics-strip {
      grid-template-columns: 1fr;
      gap: 20px;
      padding: 20px;
    }
    .floating-badge {
      display: none;
    }
    .avatar-card {
      width: 260px;
      height: 310px;
    }
  }
</style>
