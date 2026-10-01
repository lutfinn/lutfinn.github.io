<script>
  import { cvData } from '../data/cv-data.js';
  const { references } = cvData;
</script>

<section id="references" class="section-padding references-section">
  <div class="container">
    <div class="references-header text-center">
      <span class="section-subtitle">Endorsements & Governance</span>
      <h2 class="section-heading">
        Verified Professional <span class="gradient-text">References</span>
      </h2>
      <p class="section-desc" style="margin: 0 auto;">
        Executive leaders and managers across the Telkom Indonesia Group and telecommunication industry who have supervised and partnered on my deliverables.
      </p>
    </div>

    <div class="references-grid">
      {#each references as ref}
        <div class="glass-card ref-card">
          <div class="ref-quote-mark">“</div>
          <div class="ref-content">
            <h3 class="ref-name">{ref.name}</h3>
            <div class="ref-title">{ref.title}</div>
            <div class="ref-org">{ref.organization}</div>
            <div class="ref-relationship">{ref.relationship}</div>
          </div>

          <div class="ref-actions">
            {#if ref.email}
              <a href={`mailto:${ref.email}`} class="ref-btn" title={`Email ${ref.name}`}>
                <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
                <span>{ref.email}</span>
              </a>
            {/if}
            {#if ref.phone}
              <a href={`tel:${ref.phone.replace(/[^0-9+]/g, '')}`} class="ref-btn" title={`Call ${ref.name}`}>
                <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path></svg>
                <span>{ref.phone}</span>
              </a>
            {/if}
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .references-header {
    margin-bottom: 50px;
  }
  .text-center {
    text-align: center;
  }

  .references-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 24px;
  }

  .ref-card {
    padding: 30px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    position: relative;
    overflow: hidden;
    border: 1px solid rgba(255, 255, 255, 0.08);
  }

  .ref-quote-mark {
    position: absolute;
    top: 10px;
    right: 20px;
    font-size: 80px;
    font-family: serif;
    color: rgba(255, 255, 255, 0.03);
    line-height: 1;
    pointer-events: none;
  }

  .ref-name {
    font-size: 18px;
    font-weight: 800;
    color: #ffffff;
    margin-bottom: 4px;
  }

  .ref-title {
    font-size: 13.5px;
    font-weight: 600;
    color: var(--cyan);
    margin-bottom: 4px;
  }

  .ref-org {
    font-size: 12.5px;
    color: #94a3b8;
    margin-bottom: 12px;
  }

  .ref-relationship {
    font-size: 12px;
    color: var(--text-dim);
    font-style: italic;
    border-top: 1px solid var(--border-subtle);
    padding-top: 12px;
    margin-bottom: 20px;
  }

  .ref-actions {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .ref-btn {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 12px;
    color: #cbd5e1;
    text-decoration: none;
    padding: 6px 10px;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 6px;
    transition: all 0.2s ease;
    word-break: break-all;
  }

  .ref-btn:hover {
    background: rgba(6, 182, 212, 0.12);
    border-color: rgba(6, 182, 212, 0.3);
    color: #38bdf8;
  }

  .ref-btn svg {
    color: var(--cyan);
    flex-shrink: 0;
  }
</style>
