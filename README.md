<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Profesyonel müzisyen Erkan Önay'ın resmi web sitesi. Saz, ritim ve yapay zekâ destekli müzik çalışmaları.">
  <title>Erkan Önay | Müzisyen</title>

  <!-- Google AdSense -->
  <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-3009181231099628" crossorigin="anonymous"></script>

  <style>
    :root {
      --bg1:#0f2027; --bg2:#203a43; --bg3:#2c5364;
      --accent:#e67e22; --accent-2:#d35400; --panel:#111; --muted:#ddd; --muted-2:#888;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body {
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif;
      background: linear-gradient(120deg, var(--bg1), var(--bg2), var(--bg3));
      color:#fff;
      line-height:1.6;
    }
    header{ text-align:center; padding:80px 20px 30px }
    header h1{ font-size:42px; margin:0; animation:fadeInDown 1s ease both }
    header p{ font-size:18px; margin:10px 0 0; color:var(--muted) }
    @keyframes fadeInDown{ from{opacity:0; transform:translateY(-24px)} to{opacity:1; transform:translateY(0)} }

    .topbar { display:flex; justify-content:center; align-items:center; gap:12px; margin:10px 0 0 }
    .btn { text-decoration:none; color:#fff; background:var(--accent); padding:10px 18px; border-radius:999px; transition:.25s }
    .btn:hover{ background:var(--accent-2); transform:translateY(-1px) }

    main{ max-width:960px; margin:0 auto; padding:32px 20px }
    section{ background:rgba(0,0,0,.25); backdrop-filter: blur(2px); border-radius:16px; padding:24px; margin-bottom:20px; }
    h2{ margin-top:0 }

    .adsense { text-align:center; background:var(--panel); border-radius:12px; padding:16px; color:var(--muted-2); }
    footer { text-align:center; padding:24px; background:#0a0a0a; color:#bbb; }

    /* contact form */
    form { background:var(--panel); padding:18px; border-radius:12px; display:grid; gap:10px }
    input, textarea { width:100%; padding:12px; border:none; border-radius:8px }
    button[type=submit]{ background:var(--accent); color:#fff; border:none; padding:12px 18px; border-radius:999px; cursor:pointer }
    button[type=submit]:hover{ background:var(--accent-2) }

    /* audio helper */
    .audio-ctrl{ display:inline-flex; align-items:center; gap:8px; background:transparent; border:1px solid rgba(255,255,255,.35); padding:8px 12px; border-radius:999px; color:#fff; cursor:pointer }
    .audio-ctrl:hover{ background:rgba(255,255,255,.06) }
  </style>
</head>
<body>

<!-- Arka plan müzik: bazı tarayıcılar otomatik oynatmayı engelleyebilir.
     Aşağıdaki 'Play' butonu bu durumda sesi başlatır. -->
<audio id="bgm" autoplay loop>
  <source src="background.mp3" type="audio/mpeg">
</audio>

<header>
  <h1>🎶 Erkan Önay</h1>
  <p>Saz, ritim, yapay zekâ destekli müzik & ilham dolu eserler</p>
  <div class="topbar">
    <a class="btn" href="https://youtube.com/@erkanonay" target="_blank" rel="noopener">YouTube</a>
    <a class="btn" href="https://www.instagram.com/erkanonay" target="_blank" rel="noopener">Instagram</a>
    <a class="btn" href="https://www.tiktok.com/@onaymuzik" target="_blank" rel="noopener">TikTok</a>
    <button id="playToggle" class="audio-ctrl" type="button">▶︎ Play</button>
  </div>
</header>

<main>
  <section>
    <h2>Hakkımda</h2>
    <p>Ben Erkan. Profesyonel bir müzisyenim. Saz ve ritim enstrümanlarıyla başladığım yolculuğumu yapay zekâ destekli müzik teknolojileriyle birleştirdim. Amacım; hem geleneksel müziği yaşatmak hem de geleceğin sahnesine ilham dolu eserler bırakmak.</p>
  </section>

  <section>
    <h2>Projelerim</h2>
    <ul>
      <li>🎼 Canlı Zeka: Yapay zekâ destekli müzik kayıt uygulaması</li>
      <li>🥁 Bendir ve gerçek enstrüman ritimleriyle loop çalışmaları</li>
      <li>📀 Epik ve duygusal besteler</li>
    </ul>
  </section>

  <section class="adsense">
    <!-- Reklam birimi: onay sonrasında otomatik dolar -->
    <ins class="adsbygoogle"
         style="display:block"
         data-ad-client="ca-pub-3009181231099628"
         data-ad-slot="0000000000"
         data-ad-format="auto"
         data-full-width-responsive="true"></ins>
    <script>
      (window.adsbygoogle = window.adsbygoogle || []).push({});
    </script>
    <p>Reklam Alanı (Adsense onayını takiben görünür)</p>
  </section>

  <section>
    <h2>İletişim</h2>
    <form action="mailto:erkanonay@hotmail.com" method="get" enctype="text/plain">
      <input type="text" name="isim" placeholder="Adınız" required>
      <input type="email" name="email" placeholder="Email adresiniz" required>
      <textarea name="mesaj" rows="5" placeholder="Mesajınız" required></textarea>
      <button type="submit">Gönder</button>
    </form>
  </section>
</main>

<footer>© 2025 Erkan Önay | Tüm Hakları Saklıdır.</footer>

<script>
  // Audio autoplay fallback
  const audio = document.getElementById('bgm');
  const btn = document.getElementById('playToggle');

  function updateLabel(){
    btn.textContent = audio.paused ? '▶︎ Play' : '⏸ Pause';
  }
  btn.addEventListener('click', async () => {
    try{
      if(audio.paused){ await audio.play(); } else { audio.pause(); }
      updateLabel();
    }catch(e){ console.log(e); }
  });
  document.addEventListener('visibilitychange', () => { if(document.visibilityState === 'visible') updateLabel(); });
  updateLabel();
</script>

</body>
</html>
