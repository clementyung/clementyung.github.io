---
title: "Hi, I'm Clement Yung"
layout: default
---

<div class="profile-container">
  
  <div class="profile-image-col">
    <div class="hanging-assembly">
      
      <div class="hanging-anchor" id="hanging-card">
        <div class="hanging-pole"></div>
        <div class="hanging-frame">
          <img src="\pics\Front_Photo.jpg" alt="Clement Yung" class="profile-photo">
        </div>
      </div>

    </div>
  </div>
  
  <div class="profile-text-col" id="profile-biography">
    <h2 class="section-title">Welcome!</h2>
    <p>
      I am Clement (Cheuk Wai) Yung, a PhD student in Mathematics at the University of Toronto. 
      I am supervised by Asst. Prof. Spencer Unger, and I am researching the intersections between set theory and Ramsey theory.
    </p>

    <h2 class="section-title">About me</h2>
    <div class="about-list-container">
      
      <div class="about-item about-dropdown-trigger" id="uoft-dropdown">
        <div class="about-icon-side">
          <img src="/pics/Logo_UofT.png" alt="University of Toronto Logo" class="about-logo">
        </div>
        <div class="about-text-side">
          <div class="about-title-row">
            <span class="about-title">University of Toronto</span>
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" class="dropdown-chevron">
              <polyline points="6 9 12 15 18 9"></polyline>
            </svg>
          </div>
          <div class="about-subtitle">2022 - 2027 (Expected)</div>
          
          <div class="dropdown-drawer">
            <div class="drawer-content">
              Doctor in Philosophy (Mathematics)<br>
              Advisor: Spencer Unger
            </div>
          </div>
        </div>
      </div>

      <div class="about-item about-dropdown-trigger" id="nus-dropdown">
        <div class="about-icon-side">
          <img src="/pics/Logo_NUS.png" alt="National University of Singapore Logo" class="about-logo">
        </div>
        <div class="about-text-side">
          <div class="about-title-row">
            <span class="about-title">National University of Singapore</span>
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" class="dropdown-chevron">
              <polyline points="6 9 12 15 18 9"></polyline>
            </svg>
          </div>
          <div class="about-subtitle">2018 - 2022</div>
          
          <div class="dropdown-drawer">
            <div class="drawer-content">
              Bachelor of Science (Mathematics)<br>
              with a second major in Statistics<br>
              GPA: 4.95/5.00 (Highest Distinction)
            </div>
          </div>
        </div>
      </div>

      <div class="about-item">
        <div class="about-icon-side">
          <img src="/pics/Flag_Singapore.png" alt="Singapore Flag" class="about-logo">
        </div>
        <div class="about-text-side centered-text-side">
          <div class="about-title">Raised in Singapore</div>
        </div>
      </div>

      <div class="about-item">
        <div class="about-icon-side">
          <img src="/pics/Flag_Hong_Kong.png" alt="Hong Kong Flag" class="about-logo">
        </div>
        <div class="about-text-side centered-text-side">
          <div class="about-title">Born in Hong Kong</div>
        </div>
      </div>

    </div>
  </div>

</div>

<style>
  /* Container establishes top alignment for the columns */
  .profile-container {
    display: flex;
    flex-direction: row;
    align-items: flex-start; 
    justify-content: space-between;
    gap: 48px;
    margin: 20px auto 40px auto;
    max-width: 1000px;
    position: relative;
  }

  .profile-image-col {
    flex: 0 0 45%;
    display: flex;
    justify-content: center;
    position: relative;
    perspective: 1000px;
  }

  /* =======================================================
     CLEAN LIST STRUCTURE & INTERACTIVE DROPDOWN DRAWER
     ====================================================== */
  .about-list-container {
    display: flex;
    flex-direction: column;
    gap: 20px;
    margin-top: 16px;
    width: 100%;
    max-width: 500px;
  }

  .about-item {
    display: flex;
    flex-direction: row;
    align-items: flex-start; /* Aligns logos to top-line when dropdown text expands */
    gap: 16px;
  }

  .about-dropdown-trigger {
    cursor: pointer;
    user-select: none;
    padding: 4px 8px;
    margin-left: -8px;
    margin-right: -8px;
    border-radius: 8px;
    transition: background-color 0.2s ease;
  }

  /* Subtle highlight on hover to show interactivity */
  .about-dropdown-trigger:hover {
    background-color: rgba(0, 0, 0, 0.03);
  }
  html[data-theme="dark"] .about-dropdown-trigger:hover {
    background-color: rgba(255, 255, 255, 0.04);
  }

  .about-icon-side {
    flex: 0 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 44px;
    height: 44px;
    margin-top: 2px; /* Centers icon alignment perfectly with the top line of text */
  }

  .about-logo {
    max-width: 100%;
    max-height: 100%;
    object-fit: contain;
    filter: drop-shadow(0px 2px 4px rgba(0,0,0,0.08));
  }

  html[data-theme="dark"] .about-logo {
    filter: brightness(1.05) contrast(1.02);
  }

  .about-text-side {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    text-align: left;
    flex: 1;
  }

  /* Specific class to vertically center text rows without sub-labels */
  .centered-text-side {
    height: 44px; /* Matches icon side height context */
    justify-content: center;
    margin-top: 2px; /* Keeps geometric alignment balanced with top rows */
  }

  .about-title-row {
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .about-title {
    font-weight: bold;
    font-size: 16px;
    color: var(--text-main);
    line-height: 1.3;
  }

  /* Structural UI Chevron element */
  .dropdown-chevron {
    color: var(--text-muted);
    opacity: 0.7;
    transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1);
  }

  /* Rotate indicator when active */
  .about-dropdown-trigger.is-expanded .dropdown-chevron {
    transform: rotate(180deg);
    color: var(--text-main);
    opacity: 1;
  }

  .about-subtitle {
    font-weight: normal;
    font-size: 14px;
    color: var(--text-muted);
    line-height: 1.3;
    margin-top: 2px;
  }

  /* Smooth height calculation drawer using grid layout mechanics */
  .dropdown-drawer {
    display: grid;
    grid-template-rows: 0fr;
    transition: grid-template-rows 0.3s cubic-bezier(0.16, 1, 0.3, 1);
    overflow: hidden;
  }

  .about-dropdown-trigger.is-expanded .dropdown-drawer {
    grid-template-rows: 1fr;
  }

  /* Contains secondary meta lines to calculate text metrics dynamically */
  .drawer-content {
    min-height: 0;
    font-size: 14px;
    line-height: 1.5;
    color: var(--text-main);
    padding-top: 8px;
    opacity: 0;
    transform: translateY(-4px);
    transition: opacity 0.25s ease, transform 0.25s ease;
  }

  .about-dropdown-trigger.is-expanded .drawer-content {
    opacity: 0.9;
    transform: translateY(0);
    transition-delay: 0.05s;
  }

  /* =======================================================
     DESKTOP ENGINE (Defaults)
     ======================================================= */
  .hanging-assembly {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    max-width: 380px;
    margin-top: -110px; 
    position: relative;
    z-index: 25;
    animation: dropDownFrame 1.2s cubic-bezier(0.16, 1, 0.3, 1) both;
  }

  .hanging-anchor {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    transform-origin: top center; 
    cursor: pointer;
    transition: transform 0.5s cubic-bezier(0.16, 1, 0.3, 1);
  }

  .hanging-anchor.dangling {
    animation: dangleEffect 1.5s cubic-bezier(0.25, 0.46, 0.45, 0.94) both;
  }

  .hanging-pole {
    width: 6px;
    height: 110px; 
    background-color: var(--border-color);
    box-shadow: 2px 0px 5px rgba(0, 0, 0, 0.15);
  }

  .hanging-frame {
    width: 100%;
    aspect-ratio: 4 / 5; 
    border-radius: 24px; 
    overflow: hidden;
    border: 4px solid var(--border-color);
    background-color: var(--bg-middle);
    box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.3);
    user-select: none;
    -webkit-user-drag: none;
  }

  .profile-photo {
    width: 100%;
    height: 100%;
    object-fit: cover; 
    display: block;
    pointer-events: none;
  }

  .profile-text-col {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    padding-top: 10px;
    transition: margin-top 0.5s cubic-bezier(0.16, 1, 0.3, 1);
  }

  .profile-text-col p {
    font-size: 17px;
    line-height: 1.6;
    margin-bottom: 16px;
    color: var(--text-main);
  }

  @keyframes dropDownFrame {
    0% { transform: translateY(-200px); opacity: 0; }
    100% { transform: translateY(0); opacity: 1; }
  }

  @keyframes dangleEffect {
    0% { transform: rotate(0deg); }
    15% { transform: rotate(5deg); }
    30% { transform: rotate(-4deg); }
    45% { transform: rotate(3deg); }
    60% { transform: rotate(-2deg); }
    75% { transform: rotate(1deg); }
    90% { transform: rotate(-0.5deg); }
    100% { transform: rotate(0deg); }
  }

  /* =======================================================
     MOBILE RESPONSIVE ENGINE (Dynamic Layout Flow)
     ======================================================= */
  @media (max-width: 768px) {
    .profile-container {
      flex-direction: column;
      align-items: center;
      text-align: center;
      gap: 0px;
    }

    .about-list-container {
      margin: 16px auto 0 auto;
    }

    .about-item {
      justify-content: center;
    }

    .about-dropdown-trigger {
      justify-content: flex-start;
      margin-left: auto;
      margin-right: auto;
      width: 100%;
      max-width: 290px;
    }

    .about-title-row {
      justify-content: flex-start;
    }

    .about-text-side {
      text-align: left;
    }

    .centered-text-side {
      height: auto;
      margin-top: 14px; /* Keeps basic structural flow balance on small screens */
    }

    .profile-image-col {
      position: absolute;
      top: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 100%;
      height: 0px; 
      z-index: 35;
    }

    .hanging-assembly {
      margin-top: 0px; 
      animation: none; 
      pointer-events: auto;
    }

    .hanging-anchor {
      transform: translateY(-420px);
    }

    .hanging-anchor.mobile-expanded {
      transform: translateY(-170px);
    }

    .hanging-pole {
      height: 110px;
    }

    .hanging-frame {
      max-width: 240px;
      border-bottom-width: 5px;
    }

    .profile-text-col {
      width: 100%;
      align-items: center;
      box-sizing: border-box;
      margin-top: 20px;
      padding: 0 16px;
      z-index: 10;
    }

    .profile-text-col.mobile-pushed {
      margin-top: 270px;
    }
  }
</style>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const card = document.getElementById('hanging-card');
    const biography = document.getElementById('profile-biography');
    
    // Main Panel Layout Routines
    if (card && biography) {
      card.addEventListener('click', (e) => {
        // Halt event escalation if clicking any dropdown list item
        if (e.target.closest('.about-dropdown-trigger')) return;

        const isMobile = window.innerWidth <= 768;
        if (isMobile) {
          card.classList.toggle('mobile-expanded');
          biography.classList.toggle('mobile-pushed');
        } else {
          if (!card.classList.contains('dangling')) {
            card.classList.add('dangling');
          }
        }
      });

      card.addEventListener('animationend', (event) => {
        if (event.animationName === 'dangleEffect') {
          card.classList.remove('dangling');
        }
      });
    }

    // Dynamic Selector Loop to handle all dropdown toggles independently
    const dropdowns = document.querySelectorAll('.about-dropdown-trigger');
    dropdowns.forEach(dropdown => {
      dropdown.addEventListener('click', (e) => {
        e.stopPropagation(); // Stops interaction from running desktop picture shake logic
        dropdown.classList.toggle('is-expanded');
      });
    });
  });
</script>