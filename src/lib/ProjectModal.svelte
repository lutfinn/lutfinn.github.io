<script>
  let { project = null, onClose = () => {} } = $props();

  function handleKeydown(e) {
    if (e.key === 'Escape') {
      onClose();
    }
  }
</script>

<svelte:window onkeydown={handleKeydown} />

{#if project}
  <!-- Backdrop -->
  <div 
    class="modal-backdrop" 
    onclick={onClose} 
    onkeydown={(e) => { if (e.key === 'Enter' || e.key === ' ') onClose(); }}
    role="button" 
    tabindex="0"
    aria-label="Close modal backdrop"
  >
    <!-- Modal Container -->
    <div 
      class="modal-container glass-card" 
      onclick={(e) => e.stopPropagation()} 
      onkeydown={(e) => e.stopPropagation()}
      role="dialog" 
      tabindex="-1"
      aria-modal="true"
    >
      <div class="modal-header">
        <div>
          <span class="modal-category">{project.category} System</span>
          <h2 class="modal-title">{project.title}</h2>
          <div class="modal-client">Client / Ecosystem: <strong>{project.client}</strong> • {project.period}</div>
        </div>
        <button class="modal-close-btn" onclick={onClose} aria-label="Close modal">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="18" y1="6" x2="6" y2="18"></line><line x1="6" y1="6" x2="18" y2="18"></line></svg>
        </button>
      </div>

      <div class="modal-body">
        <!-- Overview -->
        <div class="modal-section">
          <h4 class="section-label">System Architecture Overview</h4>
          <p class="modal-text">{project.description}</p>
        </div>

        <!-- Measurable Impact -->
        <div class="modal-section impact-box">
          <div class="impact-header">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
            <span>Quantifiable Enterprise Impact & Reliability</span>
          </div>
          <p class="impact-text">{project.impact}</p>
        </div>

        <!-- Tech Stack -->
        <div class="modal-section">
          <h4 class="section-label">Engineering Stack & Protocol Standards</h4>
          <div class="modal-tech-list">
            {#each project.tech as t}
              <span class="modal-tech-chip">{t}</span>
            {/each}
          </div>
        </div>

        {#if project.url}
          <div class="modal-footer">
            <a href={project.url} target="_blank" rel="noopener noreferrer" class="btn btn-primary">
              <span>Visit Production System</span>
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path><polyline points="15 3 21 3 21 9"></polyline><line x1="10" y1="14" x2="21" y2="3"></line></svg>
            </a>
          </div>
        {/if}
      </div>
    </div>
  </div>
{/if}

<style>
  .modal-backdrop {
    position: fixed;
    inset: 0;
    z-index: 2000;
    background: rgba(3, 7, 18, 0.85);
    backdrop-filter: blur(12px);
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px;
    animation: fadeIn 0.2s ease;
  }

  .modal-container {
    width: 100%;
    max-width: 680px;
    background: #0d1527;
    border: 1px solid rgba(6, 182, 212, 0.4);
    box-shadow: 0 25px 60px -15px rgba(0, 0, 0, 0.8), 0 0 40px rgba(6, 182, 212, 0.2);
    border-radius: var(--radius-lg);
    padding: 36px;
    animation: slideUp 0.25s cubic-bezier(0.16, 1, 0.3, 1);
    max-height: 90vh;
    overflow-y: auto;
  }

  .modal-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    border-bottom: 1px solid var(--border-subtle);
    padding-bottom: 20px;
    margin-bottom: 24px;
    gap: 16px;
  }

  .modal-category {
    font-size: 11px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--cyan);
    font-family: var(--font-mono);
  }

  .modal-title {
    font-size: 24px;
    font-weight: 800;
    color: #ffffff;
    margin-top: 4px;
    line-height: 1.25;
  }

  .modal-client {
    font-size: 13px;
    color: var(--text-muted);
    margin-top: 4px;
  }

  .modal-client strong {
    color: #cbd5e1;
  }

  .modal-close-btn {
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid var(--border-subtle);
    color: var(--text-muted);
    width: 38px;
    height: 38px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.2s ease;
    flex-shrink: 0;
  }

  .modal-close-btn:hover {
    background: rgba(255, 255, 255, 0.15);
    color: #ffffff;
    transform: rotate(90deg);
  }

  .modal-section {
    margin-bottom: 22px;
  }

  .section-label {
    font-size: 12.5px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.8px;
    color: var(--text-dim);
    margin-bottom: 8px;
  }

  .modal-text {
    font-size: 15px;
    color: #cbd5e1;
    line-height: 1.65;
  }

  .impact-box {
    background: rgba(16, 185, 129, 0.08);
    border: 1px solid rgba(16, 185, 129, 0.25);
    border-radius: var(--radius-md);
    padding: 16px 20px;
  }

  .impact-header {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 13px;
    font-weight: 700;
    color: #34d399;
    margin-bottom: 6px;
  }

  .impact-text {
    font-size: 14px;
    color: #e2e8f0;
    line-height: 1.5;
  }

  .modal-tech-list {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .modal-tech-chip {
    font-size: 12px;
    padding: 4px 12px;
    border-radius: 6px;
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    color: #38bdf8;
    font-family: var(--font-mono);
  }

  .modal-footer {
    border-top: 1px solid var(--border-subtle);
    padding-top: 20px;
    margin-top: 10px;
    display: flex;
    justify-content: flex-end;
  }

  @keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
  }

  @keyframes slideUp {
    from { opacity: 0; transform: translateY(20px) scale(0.96); }
    to { opacity: 1; transform: translateY(0) scale(1); }
  }

  @media (max-width: 576px) {
    .modal-container {
      padding: 22px;
    }
    .modal-title {
      font-size: 20px;
    }
  }
</style>
