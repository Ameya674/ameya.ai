---
layout: page
title: Projects
---

<div class="projects">
  <h1 style="text-align: center; margin-bottom: 2rem;">My Projects</h1>
  
  <div class="card">
    <div class="card-image">
      <img src="{{ '/assets/images/gshare.jpg' | relative_url }}" alt="Custom Branch Predictor">
    </div>
    <div class="card-content">
      <h1>Custom GShare Branch Predictor for gem5</h1>
      <p>
        A custom gshare branch predictor using 6-bit PC and global history with a NAND-indexed 64-entry PHT and 2-bit saturating counters. Integrated into gem5 and evaluated on embedded benchmarks.
      </p>
      <a href="https://github.com/Ameya674/gshare_branch_predictor" class="github-btn" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.207 11.387.6.11.793-.26.793-.577v-2.165c-3.338.726-4.033-1.61-4.033-1.61-.546-1.386-1.333-1.754-1.333-1.754-1.089-.745.083-.73.083-.73 1.205.085 1.84 1.238 1.84 1.238 1.07 1.834 2.807 1.304 3.492.997.108-.775.42-1.304.763-1.604-2.665-.3-5.466-1.334-5.466-5.93 0-1.31.47-2.38 1.236-3.22-.124-.303-.536-1.52.117-3.176 0 0 1.008-.322 3.3 1.23a11.52 11.52 0 013.003-.404c1.02.005 2.045.137 3.003.404 2.29-1.552 3.297-1.23 3.297-1.23.655 1.657.243 2.873.12 3.176.77.84 1.235 1.91 1.235 3.22 0 4.61-2.805 5.628-5.475 5.922.43.372.823 1.1.823 2.222v3.293c0 .32.19.694.8.576C20.565 21.796 24 17.3 24 12c0-6.63-5.37-12-12-12z"/></svg>
        View on GitHub
      </a>
    </div>
  </div>

  

  <div class="card">
    <div class="card-image">
      <img src="{{ '/assets/images/lruipv.jpg' | relative_url }}" alt="LRU_Variation Policy screenshot">
    </div>
    <div class="card-content">
      <h1>LRU_Variation Cache Policy for gem5</h1>
      <p>
        A custom cache replacement policy for gem5 that approximates LRU using an Insertion and Promotion Vector (IPV). Tracks recency with shared metadata and integrates seamlessly with cache hierarchy components.
      </p>
      <a href="https://github.com/Ameya674/lru_ipv_policy" class="github-btn" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.207 11.387.6.11.793-.26.793-.577v-2.165c-3.338.726-4.033-1.61-4.033-1.61-.546-1.386-1.333-1.754-1.333-1.754-1.089-.745.083-.73.083-.73 1.205.085 1.84 1.238 1.84 1.238 1.07 1.834 2.807 1.304 3.492.997.108-.775.42-1.304.763-1.604-2.665-.3-5.466-1.334-5.466-5.93 0-1.31.47-2.38 1.236-3.22-.124-.303-.536-1.52.117-3.176 0 0 1.008-.322 3.3 1.23a11.52 11.52 0 013.003-.404c1.02.005 2.045.137 3.003.404 2.29-1.552 3.297-1.23 3.297-1.23.655 1.657.243 2.873.12 3.176.77.84 1.235 1.91 1.235 3.22 0 4.61-2.805 5.628-5.475 5.922.43.372.823 1.1.823 2.222v3.293c0 .32.19.694.8.576C20.565 21.796 24 17.3 24 12c0-6.63-5.37-12-12-12z"/></svg>
        View on GitHub
      </a>
    </div>
  </div>


</div>