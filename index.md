---
layout: page
title: Home
---
<div class="hero">
  <div class="card">
    <div class="card-image">
      <img src="{{ '/assets/images/test.jpeg' | relative_url }}" alt="Profile photo">
    </div>
    <div class="card-content">
      <h1>Hey! I'm Ameya</h1>
      <p>
        I'm a Master's student in Computer Science at Arizona State University, where I get to geek out over math, compilers, machine learning, and systems programming. My research focuses on optimizing machine learning models for high-performance, heterogeneous hardware through advanced compilation techniques.
      </p>
      <div class="connect-text">Connect with me</div>
      <div class="social-links">
        <a href="#" class="social-icon" data-modal="email" aria-label="Email">
          <svg viewBox="0 0 24 24"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
        </a>
        <a href="#" class="social-icon" data-modal="github" aria-label="GitHub">
          <svg viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.207 11.387.6.11.793-.26.793-.577v-2.165c-3.338.726-4.033-1.61-4.033-1.61-.546-1.386-1.333-1.754-1.333-1.754-1.089-.745.083-.73.083-.73 1.205.085 1.84 1.238 1.84 1.238 1.07 1.834 2.807 1.304 3.492.997.108-.775.42-1.304.763-1.604-2.665-.3-5.466-1.334-5.466-5.93 0-1.31.47-2.38 1.236-3.22-.124-.303-.536-1.52.117-3.176 0 0 1.008-.322 3.3 1.23a11.52 11.52 0 013.003-.404c1.02.005 2.045.137 3.003.404 2.29-1.552 3.297-1.23 3.297-1.23.655 1.657.243 2.873.12 3.176.77.84 1.235 1.91 1.235 3.22 0 4.61-2.805 5.628-5.475 5.922.43.372.823 1.1.823 2.222v3.293c0 .32.19.694.8.576C20.565 21.796 24 17.3 24 12c0-6.63-5.37-12-12-12z"/></svg>
        </a>
        <a href="#" class="social-icon" data-modal="linkedin" aria-label="LinkedIn">
          <svg viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.327-.024-3.036-1.849-3.036-1.85 0-2.134 1.445-2.134 2.939v5.666H9.357V9h3.415v1.561h.049c.476-.9 1.637-1.849 3.37-1.849 3.602 0 4.267 2.37 4.267 5.455v6.285zM5.337 7.433a2.07 2.07 0 11.002-4.139 2.07 2.07 0 01-.002 4.139zM6.813 20.452H3.862V9h2.95v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.225 0z"/></svg>
        </a>
      </div>
    </div>
  </div>
</div>

<div class="modal" id="modal">
  <div class="modal-content">
    <button class="modal-close" aria-label="Close modal">×</button>
    <h2 id="modal-title"></h2>
    <p id="modal-desc"></p>
    <a href="#" id="modal-action-btn" class="modal-action-btn"></a>
  </div>
</div>

<script>
  const modal = document.getElementById('modal');
  const modalTitle = document.getElementById('modal-title');
  const modalDesc = document.getElementById('modal-desc');
  const modalActionBtn = document.getElementById('modal-action-btn');
  const modalClose = document.querySelector('.modal-close');
  const navbarToggle = document.querySelector('.navbar-toggle');
  const navbarMenu = document.querySelector('.navbar-menu');

  function showModal({ title, desc, action }) {
    modalTitle.textContent = title;
    modalDesc.textContent = desc;
    if (action) {
      modalActionBtn.style.display = 'inline-flex';
      modalActionBtn.textContent = action.text;
      if (action.type === 'copy') {
        modalActionBtn.href = '#';
        modalActionBtn.onclick = (e) => {
          e.preventDefault();
          navigator.clipboard.writeText(desc).then(() => {
            modalActionBtn.textContent = 'Copied!';
            setTimeout(() => modalActionBtn.textContent = action.text, 1500);
          });
        };
      } else if (action.type === 'link') {
        modalActionBtn.href = action.url;
        modalActionBtn.target = '_blank';
        modalActionBtn.onclick = null;
      }
    } else {
      modalActionBtn.style.display = 'none';
    }
    modal.classList.add('active');
  }

  function hideModal() {
    modal.classList.remove('active');
  }

  navbarToggle.addEventListener('click', () => {
    navbarMenu.classList.toggle('active');
  });

  modalClose.addEventListener('click', hideModal);
  modal.addEventListener('click', (e) => {
    if (e.target === modal) hideModal();
  });

  document.querySelectorAll('.social-icon').forEach(icon => {
    icon.addEventListener('click', (e) => {
      e.preventDefault();
      const type = icon.dataset.modal;
      if (type === 'email') {
        showModal({
          title: 'Get in Touch',
          desc: 'agurjar2@asu.edu',
          action: { text: 'Copy Email', type: 'copy' }
        });
      } else if (type === 'github') {
        showModal({
          title: 'My GitHub',
          desc: 'Explore my projects and code.',
          action: { text: 'Visit GitHub', type: 'link', url: 'https://github.com/Ameya674' }
        });
      } else if (type === 'linkedin') {
        showModal({
          title: 'My LinkedIn',
          desc: 'Connect with me professionally.',
          action: { text: 'Visit LinkedIn', type: 'link', url: 'https://www.linkedin.com/in/ameyagurjar/' }
        });
      }
    });
  });

  // Dynamically set card aspect ratio to match viewport
  function setCardAspectRatio() {
    const card = document.querySelector('.hero .card');
    if (card) {
      const aspectRatio = window.innerWidth / window.innerHeight;
      card.style.aspectRatio = `${aspectRatio}`;
    }
  }

  window.addEventListener('resize', setCardAspectRatio);
  setCardAspectRatio();
</script>