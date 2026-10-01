<script>
  import { cvData } from '../data/cv-data.js';
  const { personal } = cvData;

  let copiedEmail = $state(false);
  let copiedPhone = $state(false);

  let formName = $state('');
  let formEmail = $state('');
  let formCompany = $state('');
  let formService = $state('Enterprise Solutions Architecture');
  let formMessage = $state('');
  let formSubmitted = $state(false);

  function copyToClipboard(text, type) {
    navigator.clipboard.writeText(text);
    if (type === 'email') {
      copiedEmail = true;
      setTimeout(() => copiedEmail = false, 2500);
    } else {
      copiedPhone = true;
      setTimeout(() => copiedPhone = false, 2500);
    }
  }

  function handleSubmit(e) {
    e.preventDefault();
    if (!formName || !formEmail || !formMessage) return;
    
    // Client-side simulated dispatch
    formSubmitted = true;
  }

  function scrollToTop() {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }
</script>

<section id="contact" class="section-padding contact-section">
  <div class="container">
    <div class="contact-header text-center">
      <span class="section-subtitle">Connect & Collaborate</span>
      <h2 class="section-heading">
        Let’s Discuss Your Next <span class="gradient-text">Architectural Milestone</span>
      </h2>
      <p class="section-desc" style="margin: 0 auto;">
        Available for enterprise architectural advisory, mission-critical systems engineering, and technical leadership consultations.
      </p>
    </div>

    <div class="contact-grid">
      <!-- Left: Direct Contact Information -->
      <div class="contact-cards-col">
        <!-- Email Card -->
        <div class="glass-card contact-card">
          <div class="card-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
          </div>
          <div class="card-info">
            <span class="card-label">Direct Email</span>
            <a href={`mailto:${personal.email}`} class="card-value">{personal.email}</a>
          </div>
          <button class="copy-btn" onclick={() => copyToClipboard(personal.email, 'email')} title="Copy email address">
            {copiedEmail ? '✓ Copied' : 'Copy'}
          </button>
        </div>

        <!-- Phone & WhatsApp Card -->
        <div class="glass-card contact-card">
          <div class="card-icon icon-green">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor"><path d="M.057 24l1.687-6.163c-1.041-1.804-1.588-3.849-1.587-5.946.003-6.556 5.338-11.891 11.893-11.891 3.181.001 6.167 1.24 8.413 3.488 2.245 2.248 3.481 5.236 3.48 8.414-.003 6.557-5.338 11.892-11.893 11.892-1.99-.001-3.951-.5-5.688-1.448l-6.305 1.654zm6.597-3.807c1.676.995 3.276 1.591 5.392 1.592 5.448 0 9.886-4.434 9.889-9.885.002-5.462-4.415-9.89-9.881-9.892-5.452 0-9.887 4.434-9.889 9.884-.001 2.225.651 3.891 1.746 5.634l-.999 3.648 3.742-.981zm11.387-5.464c-.074-.124-.272-.198-.57-.347-.297-.149-1.758-.868-2.031-.967-.272-.099-.47-.149-.669.149-.198.297-.768.967-.941 1.165-.173.198-.347.223-.644.074-.297-.149-1.255-.462-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.297-.347.446-.521.151-.172.2-.296.3-.495.099-.198.05-.372-.025-.521-.075-.148-.669-1.611-.916-2.206-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.695.248-1.29.173-1.414z"/></svg>
          </div>
          <div class="card-info">
            <span class="card-label">Mobile & WhatsApp</span>
            <a href={`https://wa.me/${personal.phoneClean}`} target="_blank" class="card-value">{personal.phone}</a>
          </div>
          <button class="copy-btn" onclick={() => copyToClipboard(personal.phone, 'phone')} title="Copy phone number">
            {copiedPhone ? '✓ Copied' : 'Copy'}
          </button>
        </div>

        <!-- Location Card -->
        <div class="glass-card contact-card">
          <div class="card-icon icon-purple">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path><circle cx="12" cy="10" r="3"></circle></svg>
          </div>
          <div class="card-info">
            <span class="card-label">Base Location</span>
            <span class="card-value">{personal.location}</span>
          </div>
        </div>

        <!-- Official Website Card -->
        <div class="glass-card contact-card">
          <div class="card-icon" style="background: rgba(6, 182, 212, 0.15); color: #38bdf8;">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"></circle><line x1="2" y1="12" x2="22" y2="12"></line><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"></path></svg>
          </div>
          <div class="card-info">
            <span class="card-label">Official Domain</span>
            <a href={personal.website} target="_blank" rel="noopener noreferrer" class="card-value">lutfinn.my.id</a>
          </div>
        </div>

        <!-- Download CV Banner -->
        <div class="cv-download-banner glass-card">
          <div class="banner-text">
            <h4>Need a Formal Resume?</h4>
            <p>Download or print the comprehensive executive CV prepared according to international standards.</p>
          </div>
          <a href="./cv.html" target="_blank" class="btn btn-primary" style="margin-top: 14px; width: 100%;">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="6 9 6 2 18 2 18 9"></polyline><path d="M6 18H4a2 2 0 0 1-2-2v-5a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v5a2 2 0 0 1-2 2h-2"></path><rect x="6" y="14" width="12" height="8"></rect></svg>
            <span>Open Printable Executive CV</span>
          </a>
        </div>
      </div>

      <!-- Right: Interactive Consultation Form -->
      <div class="glass-card form-container">
        <h3 class="form-title">Send a Direct Message</h3>
        <p class="form-subtitle">Fill out the brief form below and I will respond promptly.</p>

        {#if formSubmitted}
          <div class="success-banner">
            <div class="success-icon">✓</div>
            <h4>Thank You, {formName}!</h4>
            <p>Your message regarding <strong>{formService}</strong> has been received. I look forward to connecting with you shortly.</p>
            <button class="btn btn-secondary" style="margin-top: 16px;" onclick={() => formSubmitted = false}>
              Send Another Note
            </button>
          </div>
        {:else}
          <form onsubmit={handleSubmit} class="inquiry-form">
            <div class="form-row">
              <div class="form-group">
                <label for="name">Your Name *</label>
                <input id="name" type="text" required placeholder="e.g. John Doe" bind:value={formName} />
              </div>
              <div class="form-group">
                <label for="email">Work Email *</label>
                <input id="email" type="email" required placeholder="john@enterprise.com" bind:value={formEmail} />
              </div>
            </div>

            <div class="form-row">
              <div class="form-group">
                <label for="company">Company / Organization</label>
                <input id="company" type="text" placeholder="e.g. Telkom Group, Bank Malut..." bind:value={formCompany} />
              </div>
              <div class="form-group">
                <label for="service">Focus Area</label>
                <select id="service" bind:value={formService}>
                  <option value="Enterprise Solutions Architecture">Enterprise Solutions Architecture</option>
                  <option value="Financial Switching & ISO 8583">Financial Switching & ISO 8583</option>
                  <option value="Zero-Downtime Governance (eRUPS)">Zero-Downtime Governance (eRUPS)</option>
                  <option value="Cloud, IoT & Telematics">Cloud, IoT & Telematics</option>
                  <option value="Executive Engineering Advisory">Executive Engineering Advisory</option>
                </select>
              </div>
            </div>

            <div class="form-group">
              <label for="message">Project Scope or Inquiries *</label>
              <textarea id="message" rows="4" required placeholder="Describe your architecture challenges, system requirements, or objectives..." bind:value={formMessage}></textarea>
            </div>

            <button type="submit" class="btn btn-primary submit-btn">
              <span>Send Consultation Request</span>
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="22" y1="2" x2="11" y2="13"></line><polygon points="22 2 15 22 11 13 2 9 22 2"></polygon></svg>
            </button>
          </form>
        {/if}
      </div>
    </div>
  </div>

  <!-- Footer -->
  <footer class="footer">
    <div class="container footer-container">
      <div class="footer-left">
        <div class="footer-brand">Lutfi Nailufar Nurdin</div>
        <div class="footer-copy">© 2026 Lutfi Nailufar Nurdin. All rights reserved. Depok / Jakarta, Indonesia.</div>
      </div>
      <div class="footer-center">
        <span class="tech-badge">Svelte 5</span>
        <span class="tech-badge">Vite</span>
        <span class="tech-badge">ISO 8583</span>
        <span class="tech-badge">Spring Boot</span>
      </div>
      <div class="footer-right">
        <button class="back-to-top" onclick={scrollToTop} aria-label="Back to top">
          <span>Top</span>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="18 15 12 9 6 15"></polyline></svg>
        </button>
      </div>
    </div>
  </footer>
</section>

<style>
  .contact-header {
    margin-bottom: 50px;
  }
  .text-center {
    text-align: center;
  }

  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1.25fr;
    gap: 36px;
    margin-bottom: 80px;
  }

  .contact-cards-col {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .contact-card {
    padding: 20px 24px;
    display: flex;
    align-items: center;
    gap: 16px;
  }

  .card-icon {
    width: 48px;
    height: 48px;
    border-radius: 12px;
    background: rgba(14, 165, 233, 0.15);
    color: var(--cyan);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }

  .icon-green {
    background: rgba(37, 211, 102, 0.15);
    color: #25d366;
  }

  .icon-purple {
    background: rgba(139, 92, 246, 0.15);
    color: #a78bfa;
  }

  .card-info {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
  }

  .card-label {
    font-size: 11.5px;
    text-transform: uppercase;
    letter-spacing: 0.8px;
    color: var(--text-dim);
    font-weight: 600;
  }

  .card-value {
    font-size: 15px;
    font-weight: 700;
    color: #ffffff;
    text-decoration: none;
    margin-top: 2px;
    word-break: break-all;
  }

  .card-value:hover {
    color: var(--cyan);
  }

  .copy-btn {
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    color: var(--text-muted);
    padding: 6px 12px;
    border-radius: 6px;
    font-size: 12px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .copy-btn:hover {
    background: rgba(255, 255, 255, 0.1);
    color: #ffffff;
  }

  .cv-download-banner {
    padding: 24px;
    border: 1px solid rgba(6, 182, 212, 0.3);
    background: linear-gradient(135deg, rgba(14, 21, 37, 0.9) 0%, rgba(14, 165, 233, 0.1) 100%);
  }

  .cv-download-banner h4 {
    font-size: 17px;
    color: #ffffff;
    margin-bottom: 6px;
  }

  .cv-download-banner p {
    font-size: 13.5px;
    color: var(--text-muted);
    line-height: 1.5;
  }

  /* Form */
  .form-container {
    padding: 36px;
  }

  .form-title {
    font-size: 22px;
    color: #ffffff;
    margin-bottom: 6px;
  }

  .form-subtitle {
    font-size: 14px;
    color: var(--text-muted);
    margin-bottom: 24px;
  }

  .inquiry-form {
    display: flex;
    flex-direction: column;
    gap: 18px;
  }

  .form-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .form-group {
    display: flex;
    flex-direction: column;
    gap: 6px;
  }

  .form-group label {
    font-size: 12.5px;
    font-weight: 600;
    color: #cbd5e1;
  }

  .form-group input, .form-group select, .form-group textarea {
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.12);
    border-radius: 8px;
    padding: 10px 14px;
    color: #ffffff;
    font-family: var(--font-main);
    font-size: 14px;
    outline: none;
    transition: all 0.2s ease;
  }

  .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
    border-color: var(--cyan);
    box-shadow: 0 0 15px rgba(6, 182, 212, 0.25);
    background: rgba(255, 255, 255, 0.07);
  }

  .form-group select option {
    background: #0f172a;
    color: #ffffff;
  }

  .submit-btn {
    padding: 14px 24px;
    font-size: 15px;
    margin-top: 6px;
  }

  /* Success */
  .success-banner {
    text-align: center;
    padding: 40px 20px;
  }

  .success-icon {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: rgba(16, 185, 129, 0.15);
    color: #34d399;
    border: 2px solid #10b981;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 28px;
    margin: 0 auto 16px;
  }

  .success-banner h4 {
    font-size: 20px;
    margin-bottom: 8px;
  }

  .success-banner p {
    color: var(--text-muted);
    font-size: 14px;
    max-width: 440px;
    margin: 0 auto;
    line-height: 1.6;
  }

  /* Footer */
  .footer {
    border-top: 1px solid rgba(255, 255, 255, 0.08);
    padding: 30px 0;
    background: rgba(5, 8, 14, 0.95);
  }

  .footer-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
    flex-wrap: wrap;
  }

  .footer-brand {
    font-size: 15px;
    font-weight: 700;
    color: #ffffff;
  }

  .footer-copy {
    font-size: 12px;
    color: var(--text-dim);
    margin-top: 2px;
  }

  .footer-center {
    display: flex;
    gap: 8px;
  }

  .tech-badge {
    font-size: 11px;
    font-family: var(--font-mono);
    padding: 2px 8px;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 4px;
    color: var(--text-dim);
  }

  .back-to-top {
    display: flex;
    align-items: center;
    gap: 6px;
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    color: var(--text-muted);
    padding: 6px 14px;
    border-radius: var(--radius-full);
    font-size: 12px;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .back-to-top:hover {
    background: var(--cyan);
    color: #080c14;
    border-color: var(--cyan);
  }

  @media (max-width: 992px) {
    .contact-grid {
      grid-template-columns: 1fr;
    }
  }

  @media (max-width: 640px) {
    .form-row {
      grid-template-columns: 1fr;
    }
    .form-container {
      padding: 24px;
    }
    .footer-container {
      flex-direction: column;
      text-align: center;
    }
  }
</style>
