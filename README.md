<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Bindhu & Varun ❤️ Our Beautiful Journey</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #1a0b0b 0%, #2d1414 100%);
      font-family: 'Georgia', 'Times New Roman', serif;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 1rem;
      overflow-x: hidden;
    }

    .heart-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 0;
      overflow: hidden;
    }

    .floating-heart {
      position: absolute;
      font-size: 1.5rem;
      color: rgba(255, 50, 50, 0.12);
      animation: floatHeart 10s ease-in-out infinite;
      animation-delay: calc(var(--delay) * 1s);
    }

    @keyframes floatHeart {
      0%, 100% { transform: translateY(100vh) scale(0.3) rotate(0deg); opacity: 0; }
      10% { opacity: 0.8; }
      90% { opacity: 0.8; }
      100% { transform: translateY(-10vh) scale(1.3) rotate(720deg); opacity: 0; }
    }

    .container {
      max-width: 1100px;
      width: 100%;
      background: rgba(255, 245, 240, 0.92);
      backdrop-filter: blur(8px);
      border-radius: 3rem;
      padding: 2rem;
      box-shadow: 0 30px 60px rgba(0, 0, 0, 0.7), 0 0 0 2px #ffb3b3 inset;
      border: 1px solid #ffcccc;
      min-height: 650px;
      position: relative;
      z-index: 1;
    }

    .pulse-heart {
      display: inline-block;
      animation: pulseHeart 1.2s ease-in-out infinite;
      color: #ff2a2a;
      font-size: 2rem;
    }

    @keyframes pulseHeart {
      0%, 100% { transform: scale(1); text-shadow: 0 0 10px rgba(255,50,50,0.3); }
      30% { transform: scale(1.4); text-shadow: 0 0 30px rgba(255,50,50,0.7); }
      60% { transform: scale(1.1); text-shadow: 0 0 20px rgba(255,50,50,0.5); }
    }

    .music-bar {
      background: #2d1414;
      padding: 0.5rem 1.5rem;
      border-radius: 60px;
      display: inline-flex;
      align-items: center;
      gap: 0.8rem;
      color: #fce4e4;
      font-size: 0.9rem;
      box-shadow: 0 4px 12px rgba(0,0,0,0.3);
      border: 1px solid #b35e5e;
      position: absolute;
      top: 1rem;
      right: 1.5rem;
      z-index: 10;
    }

    .music-bar i {
      color: #ffb3b3;
      cursor: pointer;
      transition: 0.2s;
      font-size: 1.2rem;
    }
    .music-bar i:hover { color: #ff6b6b; transform: scale(1.1); }

    .header {
      text-align: center;
      margin-bottom: 1.2rem;
      padding-top: 0.5rem;
    }

    .header h1 {
      font-size: 2.4rem;
      color: #a12222;
      font-weight: 700;
      text-shadow: 2px 2px 10px rgba(200, 70, 70, 0.3);
    }

    .header h1 i {
      color: #e04e4e;
      animation: pulse 1.6s infinite;
    }

    .subhead {
      font-size: 1rem;
      color: #5a2d2d;
      font-style: italic;
    }

    .subhead .names {
      color: #a12222;
      font-weight: bold;
      font-size: 1.1rem;
    }

    .special-memory {
      background: linear-gradient(135deg, #fff0ec, #ffd9d9);
      border-radius: 2rem;
      padding: 0.8rem 1.5rem;
      display: inline-block;
      margin-top: 0.5rem;
      border: 2px solid #a12222;
      font-weight: bold;
      color: #641e1e;
    }

    .special-memory i {
      color: #a12222;
      margin: 0 0.3rem;
    }

    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.3); color: #ff2a2a; }
    }

    @keyframes trainMove {
      0% { transform: translateX(-10px); }
      100% { transform: translateX(10px); }
    }

    .train-emoji {
      animation: trainMove 2s ease-in-out infinite;
      display: inline-block;
    }

    .progress-scroll {
      display: flex;
      gap: 0.4rem;
      overflow-x: auto;
      padding: 0.5rem 0.2rem 1rem;
      margin: 0.5rem 0 1.2rem;
      justify-content: center;
      flex-wrap: wrap;
      max-height: 80px;
    }

    .progress-dot {
      min-width: 32px;
      height: 32px;
      border-radius: 50%;
      background: #ecc0c0;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      font-size: 0.7rem;
      color: #5a2d2d;
      border: 2px solid #dba8a8;
      transition: 0.3s;
      cursor: pointer;
    }

    .progress-dot.active {
      background: #a12222;
      color: white;
      border-color: #a12222;
      transform: scale(1.15);
    }

    .progress-dot.completed {
      background: #2d7a4a;
      border-color: #2d7a4a;
      color: white;
    }

    .progress-dot.locked {
      opacity: 0.5;
      cursor: not-allowed;
    }

    .page-container {
      position: relative;
      min-height: 400px;
    }

    .page {
      display: none;
      animation: fadeIn 0.5s ease;
    }

    .page.active {
      display: block;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .qa-box {
      background: #fffcf9;
      border-radius: 2rem;
      padding: 2rem;
      border: 2px solid #ffd9d9;
      max-width: 650px;
      margin: 0 auto;
      box-shadow: 0 8px 30px rgba(70, 20, 20, 0.1);
    }

    .qa-box h2 {
      color: #641e1e;
      text-align: center;
      margin-bottom: 1.2rem;
      font-size: 1.6rem;
    }

    .qa-box .question {
      font-size: 1.2rem;
      color: #2d1414;
      margin-bottom: 1.2rem;
      text-align: center;
    }

    .qa-options {
      display: flex;
      flex-direction: column;
      gap: 0.6rem;
      margin: 1rem 0;
    }

    .qa-options button {
      background: #f5e3e3;
      border: 2px solid #dba8a8;
      padding: 0.7rem 1.5rem;
      border-radius: 60px;
      cursor: pointer;
      font-family: inherit;
      font-size: 1rem;
      color: #2d1414;
      transition: 0.2s;
      width: 100%;
      text-align: center;
    }

    .qa-options button:hover:not(:disabled) {
      background: #dba8a8;
      color: white;
      border-color: #a12222;
      transform: scale(1.02);
    }

    .qa-options button.correct {
      background: #2d7a4a;
      color: white;
      border-color: #2d7a4a;
    }

    .qa-options button.wrong {
      background: #a12222;
      color: white;
      border-color: #a12222;
    }

    .qa-options button:disabled {
      opacity: 0.6;
      cursor: not-allowed;
    }

    .qa-feedback {
      text-align: center;
      font-size: 1rem;
      margin: 1rem 0 0.5rem;
      min-height: 2.5rem;
      font-weight: 500;
      color: #1f5e2b;
    }

    .qa-next-btn {
      background: #a12222;
      color: white;
      border: none;
      padding: 0.6rem 2rem;
      border-radius: 60px;
      font-size: 1rem;
      cursor: pointer;
      transition: 0.2s;
      display: block;
      margin: 0.6rem auto 0;
      font-family: inherit;
    }

    .qa-next-btn:hover:not(:disabled) {
      background: #c03939;
      transform: scale(1.05);
    }

    .qa-next-btn:disabled {
      opacity: 0.4;
      cursor: not-allowed;
      transform: none;
    }

    .game-box {
      background: #fffcf9;
      border-radius: 2rem;
      padding: 2rem;
      border: 2px solid #ffd9d9;
      max-width: 650px;
      margin: 0 auto;
      box-shadow: 0 8px 30px rgba(70, 20, 20, 0.1);
      text-align: center;
    }

    .game-box h2 {
      color: #641e1e;
      text-align: center;
      margin-bottom: 1.2rem;
      font-size: 1.6rem;
    }

    .game-box h2 i {
      color: #cc3b3b;
    }

    .scrambled-word {
      font-size: 2.5rem;
      font-weight: bold;
      color: #a12222;
      letter-spacing: 8px;
      margin: 1.5rem 0;
      text-shadow: 2px 2px 10px rgba(200, 70, 70, 0.2);
      font-family: 'Courier New', monospace;
      animation: glowPulse 2s ease-in-out infinite;
    }

    @keyframes glowPulse {
      0%, 100% { text-shadow: 2px 2px 10px rgba(200, 70, 70, 0.2); }
      50% { text-shadow: 2px 2px 30px rgba(200, 70, 70, 0.5); }
    }

    .game-input {
      padding: 0.8rem 1.5rem;
      border-radius: 60px;
      border: 2px solid #dba8a8;
      font-size: 1.2rem;
      width: 80%;
      max-width: 350px;
      text-align: center;
      font-family: inherit;
      background: #fff;
      transition: 0.3s;
    }

    .game-input:focus {
      outline: none;
      border-color: #a12222;
      box-shadow: 0 0 20px rgba(161, 34, 34, 0.15);
    }

    .game-hint {
      color: #7a4a4a;
      font-size: 0.9rem;
      margin: 0.5rem 0 1rem;
      font-style: italic;
    }

    .game-btn {
      background: #a12222;
      color: white;
      border: none;
      padding: 0.7rem 2.5rem;
      border-radius: 60px;
      font-size: 1.1rem;
      cursor: pointer;
      transition: 0.2s;
      font-family: inherit;
      margin: 0.5rem 0.3rem;
    }

    .game-btn:hover:not(:disabled) {
      background: #c03939;
      transform: scale(1.05);
    }

    .game-btn:disabled {
      opacity: 0.4;
      cursor: not-allowed;
    }

    .game-feedback {
      font-size: 1.1rem;
      margin: 1rem 0 0.5rem;
      min-height: 2.5rem;
      font-weight: 500;
    }

    .game-feedback.success {
      color: #2d7a4a;
    }

    .game-feedback.error {
      color: #a12222;
    }

    .game-score {
      color: #5a2d2d;
      font-size: 0.95rem;
      margin-top: 0.5rem;
    }

    .game-score span {
      color: #a12222;
      font-weight: bold;
      font-size: 1.2rem;
    }

    .quote-card {
      background: linear-gradient(135deg, #fff5f0, #ffe8e8);
      border-radius: 2rem;
      padding: 2rem;
      border: 2px solid #ffd9d9;
      max-width: 700px;
      margin: 0 auto;
      text-align: center;
      box-shadow: 0 8px 30px rgba(70, 20, 20, 0.08);
      position: relative;
      overflow: hidden;
    }

    .quote-card::before {
      content: '"';
      position: absolute;
      top: -10px;
      left: 20px;
      font-size: 6rem;
      color: rgba(161, 34, 34, 0.1);
      font-family: Georgia, serif;
    }

    .quote-card .quote-icon {
      font-size: 2.5rem;
      color: #a12222;
      margin-bottom: 0.5rem;
      display: block;
    }

    .quote-card .quote-text {
      font-size: 1.4rem;
      color: #2d1414;
      line-height: 1.8;
      font-style: italic;
      font-family: 'Georgia', serif;
      padding: 0.5rem 1rem;
    }

    .quote-card .quote-author {
      margin-top: 1rem;
      color: #7a4a4a;
      font-size: 0.95rem;
      font-style: normal;
    }

    .quote-card .quote-author i {
      color: #a12222;
      margin: 0 0.3rem;
    }

    .content-page {
      padding: 0.5rem 0;
    }

    .content-page h2 {
      color: #641e1e;
      text-align: center;
      font-size: 1.8rem;
      margin-bottom: 1.2rem;
    }

    .content-page h2 i {
      color: #cc3b3b;
    }

    .photo-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 1rem;
      margin: 1.2rem 0;
    }

    .photo-card {
      background: white;
      border-radius: 1.5rem;
      overflow: hidden;
      box-shadow: 0 6px 20px rgba(0,0,0,0.08);
      border: 2px solid #ffd9d9;
      transition: 0.3s;
      aspect-ratio: 1/1;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #f5e3e3;
      position: relative;
    }

    .photo-card:hover {
      transform: translateY(-5px) scale(1.02);
      box-shadow: 0 12px 30px rgba(0,0,0,0.15);
    }

    .photo-card img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .photo-card .photo-heart-overlay {
      position: absolute;
      bottom: 8px;
      right: 8px;
      font-size: 1.2rem;
      color: rgba(255, 50, 50, 0.7);
      background: rgba(255, 255, 255, 0.7);
      border-radius: 50%;
      padding: 4px 6px;
      backdrop-filter: blur(4px);
    }

    .photo-card .placeholder-img {
      font-size: 3rem;
      color: #a12222;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.3rem;
      text-align: center;
    }

    .photo-card .placeholder-img span {
      font-size: 0.8rem;
      color: #5a2d2d;
    }

    .video-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.2rem;
      margin: 1.2rem 0;
    }

    .video-card {
      background: #1a0b0b;
      border-radius: 1.5rem;
      overflow: hidden;
      border: 2px solid #ffd9d9;
      aspect-ratio: 16/9;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
    }

    .video-card video,
    .video-card iframe {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .video-placeholder {
      color: white;
      text-align: center;
      font-size: 2.5rem;
    }

    .video-placeholder i {
      display: block;
      margin-bottom: 0.3rem;
    }

    .video-placeholder span {
      font-size: 0.9rem;
      color: #ffb3b3;
    }

    .love-letter-full {
      background: #fffaf7;
      border-radius: 2rem;
      padding: 1.8rem;
      border: 2px solid #f5d0d0;
      box-shadow: inset 0 0 30px rgba(200, 120, 120, 0.05);
      max-width: 700px;
      margin: 0 auto;
      position: relative;
    }

    .love-letter-full .letter-content {
      font-size: 1.05rem;
      line-height: 1.8;
      color: #2d1414;
      font-style: italic;
      background: #fff5f0;
      padding: 1.5rem;
      border-radius: 1.5rem;
      border-left: 6px solid #e04e4e;
    }

    .love-letter-full .sig {
      margin-top: 1.2rem;
      text-align: right;
      font-weight: 600;
      color: #a12222;
    }

    .nav-controls {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 1.5rem;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .nav-btn {
      background: #a12222;
      color: white;
      border: none;
      padding: 0.6rem 1.8rem;
      border-radius: 60px;
      font-size: 1rem;
      cursor: pointer;
      transition: 0.2s;
      font-family: inherit;
    }

    .nav-btn:hover:not(:disabled) {
      background: #c03939;
      transform: scale(1.05);
    }

    .nav-btn:disabled {
      opacity: 0.3;
      cursor: not-allowed;
    }

    .page-counter {
      color: #5a2d2d;
      font-size: 0.95rem;
    }

    .footer-note {
      margin-top: 1.5rem;
      text-align: center;
      color: #4f2b2b;
      border-top: 1px solid #ecc0c0;
      padding-top: 1rem;
      font-size: 0.9rem;
    }

    .footer-note i { color: #cc3b3b; }

    .footer-note .heartbeat {
      animation: pulseHeart 1.2s ease-in-out infinite;
      display: inline-block;
    }

    @media (max-width: 768px) {
      .container { padding: 1.2rem; }
      .header h1 { font-size: 1.8rem; }
      .music-bar { 
        position: relative; 
        top: auto; 
        right: auto; 
        display: flex; 
        justify-content: center; 
        margin: 0.3rem auto 0.8rem; 
        width: fit-content;
      }
      .progress-dot { min-width: 28px; height: 28px; font-size: 0.65rem; }
      .qa-box { padding: 1.2rem; }
      .photo-grid { grid-template-columns: repeat(auto-fit, minmax(130px, 1fr)); }
      .video-grid { grid-template-columns: 1fr; }
      .scrambled-word { font-size: 2rem; letter-spacing: 5px; }
      .quote-card .quote-text { font-size: 1.1rem; }
    }

    @media (max-width: 480px) {
      .header h1 { font-size: 1.4rem; }
      .qa-box .question { font-size: 1rem; }
      .photo-grid { grid-template-columns: 1fr 1fr; }
      .nav-controls { flex-direction: column; gap: 0.5rem; }
      .progress-dot { min-width: 24px; height: 24px; font-size: 0.6rem; }
      .scrambled-word { font-size: 1.6rem; letter-spacing: 3px; }
      .game-input { width: 90%; font-size: 1rem; }
      .quote-card .quote-text { font-size: 1rem; }
    }
  </style>
</head>
<body>

<!-- ===== FLOATING HEARTS BACKGROUND ===== -->
<div class="heart-bg" id="heartBg"></div>

<!-- ===== BACKGROUND MUSIC ===== -->
<audio id="bgMusic" loop>
  <source src="your-song.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

<div class="container">
  <!-- Music Bar -->
  <div class="music-bar">
    <i class="fas fa-music"></i>
    <span id="musicLabel">🎵 our song</span>
    <i class="fas fa-play-circle" id="playBtn"></i>
  </div>

  <!-- Header -->
  <div class="header">
    <h1>
      <i class="fas fa-heart pulse-heart"></i> 
      Bindhu <i class="fas fa-heart pulse-heart"></i> Varun
      <i class="fas fa-heart pulse-heart"></i>
    </h1>
    <div class="subhead">
      <span class="names">Bindhu (19)</span> ❤️ <span class="names">Varun (23)</span>
      <br>27 Days of Our Love Story
    </div>
    <div class="special-memory">
      <i class="fas fa-train train-emoji"></i> 
      We met at <strong>Kachiguda Railway Station</strong> · <strong>Platform No. 2</strong> 
      <i class="fas fa-train train-emoji"></i>
    </div>
  </div>

  <!-- Progress Dots -->
  <div class="progress-scroll" id="progressBar"></div>

  <!-- Pages -->
  <div class="page-container" id="pageContainer"></div>

  <!-- Navigation -->
  <div class="nav-controls">
    <button class="nav-btn" id="prevBtn" disabled><i class="fas fa-arrow-left"></i> Previous</button>
    <span class="page-counter" id="pageCounter">Page 1 / 27</span>
    <button class="nav-btn" id="nextBtn">Next <i class="fas fa-arrow-right"></i></button>
  </div>

  <div class="footer-note">
    <i class="fas fa-heart heartbeat"></i> Made with all my love for you, Varun <i class="fas fa-heart heartbeat"></i>
    <br><span style="font-size: 0.8rem; color: #7a4a4a;">~ Bindhu ❤️</span>
    <br><span style="font-size: 0.7rem; color: #7a4a4a;">🚂 Kachiguda Platform No. 2 - Where our story began</span>
  </div>
</div>

<script>
  // ============================================================
  // BACKGROUND MUSIC CONTROLS
  // ============================================================
  
  const audio = document.getElementById('bgMusic');
  const playBtn = document.getElementById('playBtn');
  const musicLabel = document.getElementById('musicLabel');
  let isPlaying = false;

  // Try to autoplay
  audio.volume = 0.5;
  
  // Attempt autoplay
  audio.play().then(() => {
    isPlaying = true;
    playBtn.className = 'fas fa-pause-circle';
    musicLabel.textContent = '🎵 Playing our song';
  }).catch(() => {
    // Autoplay blocked - user needs to click
    isPlaying = false;
    playBtn.className = 'fas fa-play-circle';
    musicLabel.textContent = '🎵 Click play';
  });

  playBtn.addEventListener('click', function() {
    if (isPlaying) {
      audio.pause();
      this.className = 'fas fa-play-circle';
      musicLabel.textContent = '🎵 paused';
      isPlaying = false;
    } else {
      audio.play();
      this.className = 'fas fa-pause-circle';
      musicLabel.textContent = '🎵 Playing our song';
      isPlaying = true;
    }
  });

  // ============================================================
  // FLOATING HEARTS BACKGROUND
  // ============================================================
  
  function createFloatingHearts() {
    const container = document.getElementById('heartBg');
    const hearts = ['❤️', '💕', '💗', '💖', '♥️'];
    for (let i = 0; i < 25; i++) {
      const heart = document.createElement('div');
      heart.className = 'floating-heart';
      heart.textContent = hearts[i % hearts.length];
      heart.style.left = Math.random() * 100 + '%';
      heart.style.fontSize = (1 + Math.random() * 2) + 'rem';
      heart.style.setProperty('--delay', Math.random() * 6);
      heart.style.animationDuration = (6 + Math.random() * 6) + 's';
      container.appendChild(heart);
    }
  }
  createFloatingHearts();

  // ============================================================
  // YOUR PHOTO LINKS - Replace these with your actual direct links
  // ============================================================
  
  // Get direct links from ImgBB: Right-click photo → "Copy image address"
  const photoLinks = [
    "https://i.ibb.co/placeholder/photo1.jpg",
    "https://i.ibb.co/placeholder/photo2.jpg",
    "https://i.ibb.co/placeholder/photo3.jpg",
    "https://i.ibb.co/placeholder/photo4.jpg",
    "https://i.ibb.co/placeholder/photo5.jpg",
    "https://i.ibb.co/placeholder/photo6.jpg",
    "https://i.ibb.co/placeholder/photo7.jpg",
    "https://i.ibb.co/placeholder/photo8.jpg",
    "https://i.ibb.co/placeholder/photo9.jpg",
    "https://i.ibb.co/placeholder/photo10.jpg",
    "https://i.ibb.co/placeholder/photo11.jpg",
    "https://i.ibb.co/placeholder/photo12.jpg",
    "https://i.ibb.co/placeholder/photo13.jpg",
    "https://i.ibb.co/placeholder/photo14.jpg",
    "https://i.ibb.co/placeholder/photo15.jpg",
    "https://i.ibb.co/placeholder/photo16.jpg",
    "https://i.ibb.co/placeholder/photo17.jpg"
  ];

  // ============================================================
  // VIDEO LINKS - Replace with your video URLs
  // ============================================================
  
  const videoLinks = [
    "https://www.youtube.com/embed/VIDEO_ID_1",
    "https://www.youtube.com/embed/VIDEO_ID_2",
    "https://www.youtube.com/embed/VIDEO_ID_3",
    "https://www.youtube.com/embed/VIDEO_ID_4",
    "https://www.youtube.com/embed/VIDEO_ID_5",
    "https://www.youtube.com/embed/VIDEO_ID_6"
  ];

  // ============================================================
  // EMOTIONAL LOVE QUOTES
  // ============================================================
  
  const loveQuotes = [
    { text: "In all the world, there is no heart for me like yours. In all the world, there is no love for you like mine.", author: "– Maya Angelou" },
    { text: "I saw that you were perfect, and so I loved you. Then I saw that you were not perfect and I loved you even more.", author: "– Angelita Lim" },
    { text: "You are my heart, my life, my one and only thought.", author: "– Conan Doyle" },
    { text: "I love you not only for what you are, but for what I am when I am with you.", author: "– Elizabeth Barrett Browning" },
    { text: "You are my sun, my moon, and all my stars.", author: "– E.E. Cummings" },
    { text: "I have found the one whom my soul loves.", author: "– Song of Solomon 3:4" },
    { text: "Your love is the anchor that keeps me steady in the storms of life.", author: "– Unknown" },
    { text: "Every love story is beautiful, but ours is my favorite.", author: "– Unknown" },
    { text: "When I look into your eyes, I see my forever. When I hold your hand, I feel my home.", author: "– Bindhu ❤️" },
    { text: "I never knew what love was until I met you. You taught me that love is patient, kind, and unconditional.", author: "– Bindhu ❤️" },
    { text: "Every heartbeat of mine whispers your name, Varun. You are my first thought in the morning and my last prayer at night.", author: "– Bindhu ❤️" },
    { text: "You are not just my boyfriend. You are my best friend, my confidant, and my soulmate.", author: "– Bindhu ❤️" },
    { text: "The moment I saw you at Kachiguda Platform 2, I knew my life would never be the same.", author: "– Bindhu ❤️" },
    { text: "I love you more than all the stars in the sky, more than all the words in the world.", author: "– Bindhu ❤️" }
  ];

  // ============================================================
  // WORD SCRAMBLE WORDS
  // ============================================================
  
  const wordScrambleWords = [
    { word: "LOVE", hint: "❤️ What I feel for you" },
    { word: "HEART", hint: "💓 It beats for you" },
    { word: "KISS", hint: "💋 What I want to give you" },
    { word: "HUG", hint: "🤗 What makes me feel safe" },
    { word: "SMILE", hint: "😊 What you put on my face" },
    { word: "FOREVER", hint: "⏳ How long I'll love you" },
    { word: "DESTINY", hint: "🌟 What brought us together" },
    { word: "SOULMATE", hint: "💞 What you are to me" }
  ];

  // ============================================================
  // Q&A QUESTIONS
  // ============================================================
  
  const qaQuestions = [
    {
      question: "Where did we first meet? 💕",
      options: ["Secunderabad Station", "Kachiguda Station", "Hyderabad Station", "Nampally Station"],
      correct: 1
    },
    {
      question: "Which platform did we meet on? 🚂",
      options: ["Platform 1", "Platform 2", "Platform 3", "Platform 4"],
      correct: 1
    },
    {
      question: "What's my favorite color? 🎨",
      options: ["Blue", "Pink", "Red", "Purple"],
      correct: 2
    },
    {
      question: "What's your nickname for me? 💗",
      options: ["Baby", "Sweetie", "Cutie", "All of the above"],
      correct: 3
    },
    {
      question: "What's our favorite date activity? 🌹",
      options: ["Movies", "Candlelight Dinner", "Long Walk", "Train Ride"],
      correct: 3
    },
    {
      question: "What song reminds you of us? 🎵",
      options: ["Perfect - Ed Sheeran", "Thinking Out Loud", "All of Me", "I Love You 3000"],
      correct: 0
    },
    {
      question: "What's my favorite food? 🍕",
      options: ["Pizza", "Pasta", "Burgers", "Sushi"],
      correct: 1
    },
    {
      question: "What's your favorite thing about me? ❤️",
      options: ["My smile", "My eyes", "My laugh", "My heart"],
      correct: 0
    },
    {
      question: "What's our movie? 🎬",
      options: ["The Notebook", "Titanic", "A Star is Born", "La La Land"],
      correct: 0
    },
    {
      question: "What's the best gift I gave you? 🎁",
      options: ["Watch", "Letter", "Cake", "Teddy bear"],
      correct: 1
    }
  ];

  // ============================================================
  // PERSONALIZED LOVE MESSAGES
  // ============================================================
  
  const loveMessages = [
    "Varun, you make
