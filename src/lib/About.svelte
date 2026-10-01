<script>
  import { cvData } from '../data/cv-data.js';
  const { personal, summary } = cvData;
</script>

<section id="about" class="section-padding about-section">
  <div class="container">
    <div class="about-header text-center">
      <span class="section-subtitle">Career Profile & Philosophy</span>
      <h2 class="section-heading">
        Bridging Complex Enterprise Demands Into <span class="gradient-text">Zero-Downtime Reality</span>
      </h2>
      <p class="section-desc" style="margin: 0 auto;">
        With over 25 years in the trenches of Indonesian telecom and financial infrastructure, I combine executive architectural governance with battle-tested code craftsmanship.
      </p>
    </div>

    <!-- 3 Strategic Pillars Cards -->
    <div class="pillars-grid">
      <div class="glass-card pillar-card">
        <div class="pillar-icon pillar-icon-cyan">
          <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg>
        </div>
        <h3 class="pillar-title">Mission-Critical Resilience</h3>
        <p class="pillar-desc">
          Architect of systems where failure is not an option. From the <strong>Telkom eRUPS</strong> (annual shareholder assemblies governing billions in equity) to the <strong>Telkom Threat Map</strong> monitoring active cyber attacks across Indonesia's core telecom backbone.
        </p>
        <div class="pillar-tag">Zero Downtime • Legal Compliance</div>
      </div>

      <div class="glass-card pillar-card">
        <div class="pillar-icon pillar-icon-indigo">
          <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"></rect><line x1="12" y1="8" x2="12" y2="12"></line><line x1="8" y1="12" x2="16" y2="12"></line></svg>
        </div>
        <h3 class="pillar-title">Financial Switching & Protocols</h3>
        <p class="pillar-desc">
          Deep mastery of the <strong>ISO 8583 financial switching protocol</strong>, transaction gateways, PPOB systems, reconciliation engines, and bank switching links. Designed the Telkomsel recharge gateway operating since 2003.
        </p>
        <div class="pillar-tag">ISO 8583 • Payment Gateways</div>
      </div>

      <div class="glass-card pillar-card">
        <div class="pillar-icon pillar-icon-emerald">
          <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="16 18 22 12 16 6"></polyline><polyline points="8 6 2 12 8 18"></polyline></svg>
        </div>
        <h3 class="pillar-title">Polyglot Craftsmanship</h3>
        <p class="pillar-desc">
          Not tied to a single framework. Hands-on expert in <strong>Java Spring Boot, Python (FastAPI/Django), Node.js, Oracle DB, PostgreSQL, and Linux kernel administration</strong>, enabling objective architectural decision-making.
        </p>
        <div class="pillar-tag">Java • Python • Oracle • Linux</div>
      </div>
    </div>

    <!-- Detailed Background & Personal Data -->
    <div class="glass-card bio-box">
      <div class="bio-grid">
        <div class="bio-text">
          <h3 class="bio-title">Over 25 Years of Technical Evolution</h3>
          <p>
            My engineering path began in 1998/1999 during the dawn of the commercial internet in Indonesia. From developing web portal infrastructure for Telkom Indonesia Multimedia Division and building early Public Key Infrastructure (PKI) with Linux & OpenSSL in 2001, to operating national-scale recharge switches and contemporary enterprise microservices at Telkomsigma today.
          </p>
          <p>
            I believe modern architectural greatness requires both the macro lens of enterprise business strategy and the micro discipline of clean code, socket-level protocol optimization, database indexing, and 24/7 high-availability operations.
          </p>

          <div class="bio-stats">
            <div class="bio-stat">
              <span class="bio-stat-label">Formal Education</span>
              <span class="bio-stat-val">Universitas Terbuka (S1 In Progress, 2024 - Present) & SMK Telkom Malang</span>
            </div>
            <div class="bio-stat">
              <span class="bio-stat-label">Current Organization</span>
              <span class="bio-stat-val">PT. Sigma Cipta Caraka (Telkomsigma)</span>
            </div>
            <div class="bio-stat">
              <span class="bio-stat-label">Location</span>
              <span class="bio-stat-val">Depok / Jakarta, Indonesia</span>
            </div>
          </div>
        </div>

        <div class="bio-aside">
          <div class="quick-facts-card">
            <h4>Executive Snapshot</h4>
            <ul class="fact-list">
              <li>
                <span class="bullet">✔</span>
                <span><strong>Role:</strong> Lead Programmer Analyst & Solutions Architect</span>
              </li>
              <li>
                <span class="bullet">✔</span>
                <span><strong>Track Record:</strong> 25+ Years uninterrupted production delivery</span>
              </li>
              <li>
                <span class="bullet">✔</span>
                <span><strong>Core Specialization:</strong> Distributed Systems, Telecom & ISO 8583</span>
              </li>
              <li>
                <span class="bullet">✔</span>
                <span><strong>Languages:</strong> Indonesian (Native), English (Technical / Professional)</span>
              </li>
              <li>
                <span class="bullet">✔</span>
                <span><strong>Availability:</strong> Enterprise Advisory, Systems Architecture & Tech Leadership</span>
              </li>
            </ul>

            <a href="./cv.html" target="_blank" class="btn btn-primary" style="width: 100%; margin-top: 18px; font-size: 13.5px;">
              View Complete Verified CV
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .about-header {
    margin-bottom: 50px;
  }
  .text-center {
    text-align: center;
  }

  .pillars-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
    margin-bottom: 40px;
  }

  .pillar-card {
    padding: 32px 28px;
    display: flex;
    flex-direction: column;
  }

  .pillar-icon {
    width: 54px;
    height: 54px;
    border-radius: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 20px;
  }

  .pillar-icon-cyan {
    background: rgba(6, 182, 212, 0.12);
    color: #38bdf8;
    border: 1px solid rgba(6, 182, 212, 0.3);
  }

  .pillar-icon-indigo {
    background: rgba(99, 102, 241, 0.12);
    color: #818cf8;
    border: 1px solid rgba(99, 102, 241, 0.3);
  }

  .pillar-icon-emerald {
    background: rgba(16, 185, 129, 0.12);
    color: #34d399;
    border: 1px solid rgba(16, 185, 129, 0.3);
  }

  .pillar-title {
    font-size: 19px;
    font-weight: 700;
    margin-bottom: 12px;
    color: #ffffff;
  }

  .pillar-desc {
    font-size: 14px;
    color: var(--text-muted);
    line-height: 1.6;
    margin-bottom: 20px;
    flex-grow: 1;
  }

  .pillar-desc strong {
    color: #e2e8f0;
  }

  .pillar-tag {
    font-size: 12px;
    font-weight: 600;
    color: var(--cyan);
    font-family: var(--font-mono);
  }

  /* Bio Box */
  .bio-box {
    padding: 40px;
  }

  .bio-grid {
    display: grid;
    grid-template-columns: 1.5fr 1fr;
    gap: 40px;
    align-items: center;
  }

  .bio-title {
    font-size: 24px;
    font-weight: 800;
    margin-bottom: 16px;
    color: #ffffff;
  }

  .bio-text p {
    font-size: 15px;
    color: #cbd5e1;
    line-height: 1.7;
    margin-bottom: 16px;
  }

  .bio-stats {
    display: flex;
    flex-direction: column;
    gap: 12px;
    margin-top: 24px;
    border-top: 1px solid var(--border-subtle);
    padding-top: 20px;
  }

  .bio-stat {
    display: flex;
    justify-content: space-between;
    font-size: 13.5px;
  }

  .bio-stat-label {
    color: var(--text-dim);
    font-weight: 500;
  }

  .bio-stat-val {
    color: #ffffff;
    font-weight: 600;
  }

  .quick-facts-card {
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: var(--radius-md);
    padding: 24px;
  }

  .quick-facts-card h4 {
    font-size: 16px;
    margin-bottom: 16px;
    color: var(--cyan);
    text-transform: uppercase;
    letter-spacing: 1px;
  }

  .fact-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .fact-list li {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 13.5px;
    color: #cbd5e1;
    line-height: 1.4;
  }

  .fact-list .bullet {
    color: #10b981;
    flex-shrink: 0;
  }

  @media (max-width: 992px) {
    .pillars-grid {
      grid-template-columns: 1fr;
    }
    .bio-grid {
      grid-template-columns: 1fr;
    }
    .bio-box {
      padding: 24px;
    }
  }
</style>
