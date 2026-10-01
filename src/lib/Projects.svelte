<script>
  import { cvData } from '../data/cv-data.js';
  import ProjectModal from './ProjectModal.svelte';

  const { projects } = cvData;

  let activeCategory = $state('All');
  let selectedProject = $state(null);

  const categories = ['All', 'Enterprise', 'Fintech', 'Telecom', 'Cloud', 'IoT', 'Security', 'Web3', 'Web'];

  let filteredProjects = $derived(
    activeCategory === 'All' 
      ? projects 
      : projects.filter(p => p.category.toLowerCase() === activeCategory.toLowerCase())
  );

  function openProjectModal(p) {
    selectedProject = p;
  }

  function closeProjectModal() {
    selectedProject = null;
  }
</script>

<section id="projects" class="section-padding projects-section">
  <div class="container">
    <div class="projects-header text-center">
      <span class="section-subtitle">Flagship Deliverables</span>
      <h2 class="section-heading">
        Enterprise, Fintech & <span class="gradient-text">Telecom Platforms</span>
      </h2>
      <p class="section-desc" style="margin: 0 auto;">
        Real-world mission-critical systems engineered to withstand high transactional throughput, zero-downtime legal governance, and cybersecurity threats.
      </p>
    </div>

    <!-- Category Tabs Filter -->
    <div class="filter-tabs">
      {#each categories as cat}
        <button 
          class="filter-btn" 
          class:active={activeCategory === cat}
          onclick={() => activeCategory = cat}
        >
          {cat}
        </button>
      {/each}
    </div>

    <!-- Projects Grid -->
    <div class="projects-grid">
      {#each filteredProjects as p}
        <div class="glass-card project-card">
          <div class="project-card-header">
            <div>
              <span class="category-pill">{p.category}</span>
              <h3 class="card-title">{p.title}</h3>
              <div class="card-client">Client: <strong>{p.client}</strong></div>
            </div>
            {#if p.url}
              <a href={p.url} target="_blank" rel="noopener noreferrer" class="link-badge" title="Open live production link">
                <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path><polyline points="15 3 21 3 21 9"></polyline><line x1="10" y1="14" x2="21" y2="3"></line></svg>
                <span>Live</span>
              </a>
            {/if}
          </div>

          <p class="card-desc">{p.description}</p>

          <!-- Impact Snippet -->
          <div class="impact-snippet">
            <span class="impact-icon">⚡</span>
            <span>{p.impact}</span>
          </div>

          <!-- Tech Stack -->
          <div class="card-tech">
            {#each p.tech as t}
              <span class="tech-chip">{t}</span>
            {/each}
          </div>

          <!-- Action Footer -->
          <div class="card-footer">
            <button class="btn btn-secondary btn-details" onclick={() => openProjectModal(p)}>
              <span>Architecture Specs</span>
              <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="9 18 15 12 9 6"></polyline></svg>
            </button>
            <span class="project-period">{p.period}</span>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- Deep Dive Architecture Modal -->
<ProjectModal project={selectedProject} onClose={closeProjectModal} />

<style>
  .projects-header {
    margin-bottom: 40px;
  }
  .text-center {
    text-align: center;
  }

  .filter-tabs {
    display: flex;
    justify-content: center;
    gap: 8px;
    margin-bottom: 40px;
    flex-wrap: wrap;
  }

  .filter-btn {
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.08);
    color: var(--text-muted);
    padding: 8px 18px;
    border-radius: var(--radius-full);
    font-size: 13.5px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .filter-btn:hover {
    background: rgba(255, 255, 255, 0.08);
    color: #ffffff;
    border-color: rgba(255, 255, 255, 0.2);
  }

  .filter-btn.active {
    background: var(--cyan);
    color: #080c14;
    border-color: var(--cyan);
    font-weight: 700;
    box-shadow: 0 0 16px rgba(6, 182, 212, 0.4);
  }

  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    gap: 24px;
  }

  .project-card {
    padding: 28px;
    display: flex;
    flex-direction: column;
    border: 1px solid rgba(255, 255, 255, 0.08);
    transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
  }

  .project-card:hover {
    transform: translateY(-6px);
    border-color: rgba(6, 182, 212, 0.4);
    box-shadow: 0 16px 40px -10px rgba(0, 0, 0, 0.6), 0 0 30px rgba(6, 182, 212, 0.15);
  }

  .project-card-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 14px;
    gap: 12px;
  }

  .category-pill {
    font-size: 11px;
    font-weight: 700;
    text-transform: uppercase;
    color: var(--cyan);
    letter-spacing: 0.8px;
    display: inline-block;
    margin-bottom: 4px;
    font-family: var(--font-mono);
  }

  .card-title {
    font-size: 19px;
    font-weight: 800;
    color: #ffffff;
    line-height: 1.3;
  }

  .card-client {
    font-size: 12.5px;
    color: var(--text-muted);
    margin-top: 4px;
  }

  .card-client strong {
    color: #cbd5e1;
  }

  .link-badge {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    padding: 3px 8px;
    background: rgba(16, 185, 129, 0.15);
    border: 1px solid rgba(16, 185, 129, 0.3);
    border-radius: var(--radius-full);
    color: #34d399;
    font-size: 11px;
    font-weight: 600;
    text-decoration: none;
    flex-shrink: 0;
  }

  .link-badge:hover {
    background: rgba(16, 185, 129, 0.25);
  }

  .card-desc {
    font-size: 14px;
    color: #94a3b8;
    line-height: 1.6;
    margin-bottom: 16px;
    flex-grow: 1;
  }

  .impact-snippet {
    background: rgba(6, 182, 212, 0.08);
    border: 1px solid rgba(6, 182, 212, 0.2);
    border-radius: 8px;
    padding: 10px 12px;
    font-size: 12.5px;
    color: #38bdf8;
    line-height: 1.45;
    margin-bottom: 18px;
    display: flex;
    gap: 8px;
    align-items: flex-start;
  }

  .impact-icon {
    flex-shrink: 0;
  }

  .card-tech {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 20px;
  }

  .tech-chip {
    font-size: 11px;
    padding: 3px 8px;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 4px;
    color: #cbd5e1;
    font-family: var(--font-mono);
  }

  .card-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid var(--border-subtle);
    padding-top: 14px;
  }

  .btn-details {
    padding: 6px 14px;
    font-size: 12.5px;
  }

  .project-period {
    font-size: 12px;
    color: var(--text-dim);
    font-family: var(--font-mono);
  }

  @media (max-width: 640px) {
    .projects-grid {
      grid-template-columns: 1fr;
    }
  }
</style>
