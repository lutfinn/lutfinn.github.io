<script>
  import { cvData } from '../data/cv-data.js';
  const { experiences } = cvData;

  let activeExp = $state(0);
  let showAllRoles = $state(true);

  function setActive(idx) {
    activeExp = idx;
  }
</script>

<section id="experience" class="section-padding experience-section">
  <div class="container">
    <div class="experience-header text-center">
      <span class="section-subtitle">Career Milestones</span>
      <h2 class="section-heading">
        25+ Years of Proven <span class="gradient-text">Engineering Leadership</span>
      </h2>
      <p class="section-desc" style="margin: 0 auto;">
        From architecting the early telecommunication web portals of Indonesia to spearheading enterprise systems for Telkom Group and state-owned enterprises today.
      </p>
    </div>

    <!-- Timeline Container -->
    <div class="timeline-container">
      {#each experiences as exp, idx}
        <div class="timeline-block" class:active-block={activeExp === idx}>
          <div class="timeline-marker">
            <div class="marker-dot"></div>
            {#if idx < experiences.length - 1}
              <div class="marker-line"></div>
            {/if}
          </div>

          <div class="timeline-card glass-card">
            <div class="card-top">
              <div>
                <span class="role-badge">{exp.role}</span>
                <h3 class="company-heading">{exp.company}</h3>
                <div class="company-sub">{exp.companyDesc}</div>
              </div>
              <div class="period-box">
                <span class="period-text">{exp.period}</span>
                <span class="location-text">📍 {exp.location}</span>
              </div>
            </div>

            <!-- Highlights -->
            <div class="highlights-container">
              <h4 class="highlights-title">Key Architectural Highlights & Contributions:</h4>
              <ul class="highlights-list">
                {#each exp.highlights as h}
                  <li>
                    <span class="highlight-bullet">▹</span>
                    <span>{@html h}</span>
                  </li>
                {/each}
              </ul>
            </div>

            <!-- Tech Stack Tags -->
            <div class="tags-row">
              <span class="tags-label">Technologies:</span>
              <div class="tags-list">
                {#each exp.tags as t}
                  <span class="tech-tag">{t}</span>
                {/each}
              </div>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .experience-header {
    margin-bottom: 50px;
  }
  .text-center {
    text-align: center;
  }

  .timeline-container {
    position: relative;
    max-width: 1000px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 32px;
  }

  .timeline-block {
    display: grid;
    grid-template-columns: 40px 1fr;
    gap: 20px;
  }

  .timeline-marker {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
  }

  .marker-dot {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background: #0f172a;
    border: 3px solid var(--cyan);
    box-shadow: 0 0 12px rgba(6, 182, 212, 0.6);
    z-index: 2;
    flex-shrink: 0;
    margin-top: 24px;
  }

  .marker-line {
    width: 2px;
    background: linear-gradient(180deg, var(--cyan) 0%, rgba(99, 102, 241, 0.2) 100%);
    flex-grow: 1;
    margin-top: 8px;
    margin-bottom: -16px;
  }

  .timeline-card {
    padding: 32px;
    border: 1px solid rgba(255, 255, 255, 0.08);
  }

  .timeline-card:hover {
    border-color: rgba(6, 182, 212, 0.4);
    box-shadow: 0 12px 35px -8px rgba(0, 0, 0, 0.5), 0 0 25px rgba(6, 182, 212, 0.15);
  }

  .card-top {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 20px;
    border-bottom: 1px solid var(--border-subtle);
    padding-bottom: 20px;
    margin-bottom: 20px;
    flex-wrap: wrap;
  }

  .role-badge {
    font-size: 12px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.8px;
    color: var(--cyan);
    display: inline-block;
    margin-bottom: 6px;
    font-family: var(--font-mono);
  }

  .company-heading {
    font-size: 22px;
    font-weight: 800;
    color: #ffffff;
    line-height: 1.25;
  }

  .company-sub {
    font-size: 13px;
    color: var(--text-muted);
    margin-top: 4px;
  }

  .period-box {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 4px;
  }

  .period-text {
    font-size: 13px;
    font-weight: 700;
    color: #ffffff;
    background: rgba(14, 165, 233, 0.15);
    border: 1px solid rgba(14, 165, 233, 0.3);
    padding: 4px 12px;
    border-radius: var(--radius-full);
    font-family: var(--font-mono);
  }

  .location-text {
    font-size: 12px;
    color: var(--text-dim);
  }

  .highlights-container {
    margin-bottom: 20px;
  }

  .highlights-title {
    font-size: 13px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    color: var(--text-dim);
    margin-bottom: 12px;
    font-weight: 600;
  }

  .highlights-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .highlights-list li {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 14px;
    color: #cbd5e1;
    line-height: 1.6;
  }

  .highlight-bullet {
    color: var(--cyan);
    flex-shrink: 0;
    font-size: 14px;
    margin-top: 1px;
  }

  .tags-row {
    display: flex;
    align-items: center;
    gap: 12px;
    flex-wrap: wrap;
    border-top: 1px solid var(--border-subtle);
    padding-top: 16px;
  }

  .tags-label {
    font-size: 12px;
    color: var(--text-dim);
    font-weight: 600;
  }

  .tags-list {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .tech-tag {
    font-size: 11.5px;
    padding: 3px 10px;
    border-radius: 4px;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.08);
    color: #94a3b8;
    font-family: var(--font-mono);
  }

  @media (max-width: 768px) {
    .timeline-block {
      grid-template-columns: 1fr;
    }
    .timeline-marker {
      display: none;
    }
    .timeline-card {
      padding: 22px;
    }
    .period-box {
      align-items: flex-start;
    }
  }
</style>
