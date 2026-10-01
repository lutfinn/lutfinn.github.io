<script>
  import { cvData } from '../data/cv-data.js';
  const { competencies } = cvData;

  let searchQuery = $state('');

  let filteredCompetencies = $derived(
    competencies.map(cat => ({
      ...cat,
      skills: searchQuery.trim() === '' 
        ? cat.skills 
        : cat.skills.filter(s => s.toLowerCase().includes(searchQuery.toLowerCase()))
    })).filter(cat => cat.skills.length > 0)
  );
</script>

<section id="skills" class="section-padding skills-section">
  <div class="container">
    <div class="skills-header text-center">
      <span class="section-subtitle">Technical Competencies</span>
      <h2 class="section-heading">
        Architecture, Protocols & <span class="gradient-text">Core Technologies</span>
      </h2>
      <p class="section-desc" style="margin: 0 auto 30px;">
        Curated across 25+ years of production experience: from deep socket-level financial switching to modern cloud-native enterprise microservices.
      </p>

      <!-- Skill Search Input -->
      <div class="search-box-wrapper">
        <div class="search-box">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
          <input 
            type="text" 
            placeholder="Search skills, protocols, frameworks (e.g. ISO 8583, Spring, Oracle, Python, Docker)..."
            bind:value={searchQuery}
          />
          {#if searchQuery}
            <button class="clear-btn" onclick={() => searchQuery = ''}>×</button>
          {/if}
        </div>
      </div>
    </div>

    <!-- Competencies Grid -->
    <div class="competencies-grid">
      {#each filteredCompetencies as cat}
        <div class="glass-card competency-card">
          <div class="cat-header">
            <div class="cat-indicator"></div>
            <h3 class="cat-title">{cat.category}</h3>
          </div>
          <div class="skills-chips">
            {#each cat.skills as s}
              <div class="skill-item">
                <span class="skill-dot"></span>
                <span class="skill-name">{s}</span>
              </div>
            {/each}
          </div>
        </div>
      {/each}
    </div>

    <!-- Architectural Philosophy Callout -->
    <div class="glass-card arch-callout">
      <div class="callout-icon">💡</div>
      <div class="callout-body">
        <h4>Architectural Philosophy</h4>
        <p>
          "Technology stacks evolve, but core principles remain invariant: zero-downtime resilience, low latency, clear boundaries, strict data consistency, and pragmatic observability. Whether deploying an ISO 8583 switch in 2003 or a cloud-native microservice today, excellence lies in disciplined engineering and deep domain alignment."
        </p>
      </div>
    </div>
  </div>
</section>

<style>
  .skills-header {
    margin-bottom: 40px;
  }
  .text-center {
    text-align: center;
  }

  .search-box-wrapper {
    display: flex;
    justify-content: center;
    margin-top: 10px;
  }

  .search-box {
    width: 100%;
    max-width: 580px;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.12);
    border-radius: var(--radius-full);
    padding: 10px 20px;
    display: flex;
    align-items: center;
    gap: 12px;
    color: var(--text-muted);
    transition: all 0.2s ease;
  }

  .search-box:focus-within {
    border-color: var(--cyan);
    box-shadow: 0 0 20px rgba(6, 182, 212, 0.25);
    background: rgba(255, 255, 255, 0.07);
  }

  .search-box input {
    background: transparent;
    border: none;
    outline: none;
    color: #ffffff;
    font-size: 14px;
    width: 100%;
    font-family: var(--font-main);
  }

  .search-box input::placeholder {
    color: var(--text-dim);
  }

  .clear-btn {
    background: none;
    border: none;
    color: var(--text-muted);
    font-size: 20px;
    cursor: pointer;
    line-height: 1;
    padding: 0 4px;
  }

  .clear-btn:hover {
    color: #ffffff;
  }

  .competencies-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(360px, 1fr));
    gap: 24px;
    margin-bottom: 40px;
  }

  .competency-card {
    padding: 28px;
    border: 1px solid rgba(255, 255, 255, 0.08);
  }

  .cat-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 20px;
    border-bottom: 1px solid var(--border-subtle);
    padding-bottom: 12px;
  }

  .cat-indicator {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background: var(--cyan);
    box-shadow: 0 0 10px rgba(6, 182, 212, 0.7);
  }

  .cat-title {
    font-size: 17px;
    font-weight: 700;
    color: #ffffff;
  }

  .skills-chips {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .skill-item {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 8px 12px;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: var(--radius-sm);
    transition: all 0.2s ease;
  }

  .skill-item:hover {
    background: rgba(14, 165, 233, 0.08);
    border-color: rgba(14, 165, 233, 0.3);
    transform: translateX(4px);
  }

  .skill-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--primary-light);
    flex-shrink: 0;
  }

  .skill-name {
    font-size: 13.5px;
    color: #cbd5e1;
    font-weight: 500;
  }

  /* Arch Callout */
  .arch-callout {
    padding: 30px;
    display: flex;
    gap: 20px;
    align-items: flex-start;
    border: 1px solid rgba(99, 102, 241, 0.3);
    background: linear-gradient(135deg, rgba(14, 21, 37, 0.9) 0%, rgba(22, 33, 56, 0.8) 100%);
  }

  .callout-icon {
    font-size: 32px;
    flex-shrink: 0;
  }

  .callout-body h4 {
    font-size: 16px;
    color: var(--cyan);
    margin-bottom: 8px;
    text-transform: uppercase;
    letter-spacing: 0.8px;
  }

  .callout-body p {
    font-size: 14.5px;
    color: #e2e8f0;
    line-height: 1.65;
    font-style: italic;
  }

  @media (max-width: 640px) {
    .competencies-grid {
      grid-template-columns: 1fr;
    }
    .arch-callout {
      flex-direction: column;
      gap: 12px;
    }
  }
</style>
