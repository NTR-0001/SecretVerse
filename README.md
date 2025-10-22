<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width,initial-scale=1"/>
  <title>SecretVerse 2.0 — Next Level</title>

  <!-- Fonts & icons -->
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600;700&family=Poppins:wght@300;400;600&family=Quicksand:wght@400;600&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css"/>

  <style>
    :root{
      --bg1:#071226; --bg2:#04182a;
      --glass: rgba(255,255,255,0.04);
      --neonA:#00e5ff; --neonB:#7b61ff; --accent:#ff6b81;
      --card: rgba(255,255,255,0.05);
      --maxw:1100px;
      --blur:12px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0; font-family:Poppins, system-ui, sans-serif; -webkit-font-smoothing:antialiased;
      background:
        radial-gradient(600px 360px at 6% 10%, rgba(0,230,255,0.06), transparent 8%),
        radial-gradient(500px 300px at 92% 86%, rgba(123,97,255,0.04), transparent 8%),
        linear-gradient(180deg,var(--bg1),var(--bg2));
      color:#eaf6ff;
      display:flex; justify-content:center; padding:28px 18px;
    }

    /* container */
    .shell{ width:100%; max-width:var(--maxw); border-radius:16px; padding:18px; backdrop-filter:blur(var(--blur));
      border:1px solid rgba(255,255,255,0.03); box-shadow:0 18px 50px rgba(2,8,20,0.6); overflow:hidden;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    }

    /* header */
    .header{ display:flex; align-items:center; justify-content:space-between; gap:12px; margin-bottom:12px }
    .brand{ display:flex; gap:12px; align-items:center }
    .logo{ width:62px; height:62px; border-radius:12px; display:grid; place-items:center; font-family:Orbitron; font-weight:700; color:#041017;
      background:linear-gradient(135deg,var(--neonA),var(--neonB)); box-shadow:0 10px 40px rgba(0,230,255,0.08); transform-origin:center; animation:logoBob 4s ease-in-out infinite; }
    @keyframes logoBob{0%{transform:translateY(0)}50%{transform:translateY(-6px) rotate(-6deg)}100%{transform:translateY(0)}}
    .brand h1{ font-family:Orbitron; font-size:20px; margin:0; background:linear-gradient(90deg,var(--neonA),var(--neonB)); -webkit-background-clip:text; -webkit-text-fill-color:transparent; }
    .brand p{ margin:0; font-size:12px; color:#bfe9f7 }

    /* nav */
    nav{ display:flex; gap:8px; align-items:center; flex-wrap:wrap }
    nav a{ padding:8px 12px; border-radius:10px; color:#cfeff6; text-decoration:none; font-weight:600; font-family:Orbitron; font-size:13px;
      border:1px solid transparent; transition:all .25s; display:inline-flex; gap:8px; align-items:center; }
    nav a.active{ background: linear-gradient(90deg, rgba(0,230,255,0.06), rgba(123,97,255,0.06)); border:1px solid rgba(255,255,255,0.03); box-shadow:0 8px 30px rgba(0,230,255,0.03) }
    nav a:hover{ transform:translateY(-4px); box-shadow:0 10px 30px rgba(0,230,255,0.02) }

    /* layout */
    .layout{ display:grid; grid-template-columns: 1fr 320px; gap:18px; align-items:start }
    @media(max-width:980px){ .layout{ grid-template-columns: 1fr; } }

    /* main column */
    .main{ min-height:320px }

    /* composer */
    .composer{ background:var(--card); padding:14px; border-radius:12px; display:flex; gap:12px; border:1px solid rgba(255,255,255,0.02); margin-bottom:14px }
    .composer textarea{ flex:1; min-height:86px; max-height:220px; resize:vertical; padding:12px; border-radius:10px; background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border:none; color:#eaf6ff; font-size:15px }
    .composer .controls{ width:140px; display:flex; flex-direction:column; gap:10px }
    .btn{ background:linear-gradient(135deg,var(--neonB),var(--neonA)); border:none; color:#02131a; padding:10px; border-radius:10px; font-weight:700; cursor:pointer; box-shadow:0 10px 30px rgba(123,97,255,0.08) }
    .btn.secondary{ background:transparent; border:1px solid rgba(255,255,255,0.03); color:#cfeff6; box-shadow:none; font-weight:600 }

    /* ad styles */
    .ad{ border-radius:12px; background: linear-gradient(90deg, rgba(255,255,255,0.02), rgba(0,0,0,0.08)); padding:10px; text-align:center; border:1px dashed rgba(255,255,255,0.03); margin:12px 0; }
    .ad .sponsor{ font-family:Orbitron; color:#bff6ff; font-weight:700; margin-bottom:6px }
    .ad .tag{ font-size:12px; color:#9fdbe8; display:block; margin-bottom:6px }
    .ad .cta{ margin-top:8px; display:inline-block; padding:8px 12px; border-radius:8px; background:linear-gradient(135deg,var(--neonA),var(--neonB)); color:#02131a; font-weight:700; text-decoration:none }

    /* posts list */
    .posts{ display:flex; flex-direction:column; gap:14px; margin-bottom:12px }
    .post{ padding:14px; border-radius:12px; background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border:1px solid rgba(255,255,255,0.02); backdrop-filter: blur(6px); position:relative }
    .post .who{ display:flex; gap:12px; align-items:center; margin-bottom:10px }
    .avatar{ width:46px; height:46px; border-radius:10px; display:grid; place-items:center; font-family:Orbitron; background:linear-gradient(135deg,var(--neonA),var(--neonB)); color:#02131a; font-weight:700 }
    .who .meta{ font-size:13px; color:#bfe9f7 }
    .post p{ font-size:15px; color:#eaf6ff; margin:0; line-height:1.5; white-space:pre-wrap; word-wrap:break-word }
    .metaRow{ display:flex; gap:8px; align-items:center; margin-top:10px }
    .react{ background:transparent; border:1px solid rgba(255,255,255,0.03); color:#bfe9f7; padding:6px 10px; border-radius:8px; cursor:pointer; font-family:Orbitron; font-weight:700 }
    .react:hover{ transform:translateY(-6px); box-shadow:0 12px 40px rgba(0,230,255,0.03) }
    .count{ margin-left:6px; color:var(--accent); font-weight:800 }

    .deleteBtn{ position:absolute; top:12px; right:12px; background:rgba(255,46,99,0.06); border:none; padding:8px; border-radius:8px; color:#ffb6c1; cursor:pointer }
    .deleteBtn:hover{ transform:scale(1.08); box-shadow:0 8px 30px rgba(255,46,99,0.06) }

    /* right sidebar */
    .side{ position:sticky; top:18px }
    .card{ background:var(--card); padding:12px; border-radius:12px; border:1px solid rgba(255,255,255,0.02); margin-bottom:12px }
    .small{ font-size:13px; color:#bfe9f7 }

    /* pages (simple) */
    .page{ display:none }
    .page.active{ display:block; animation:pageIn .45s ease both }
    @keyframes pageIn{ from{opacity:0; transform:translateY(10px)} to{opacity:1; transform:translateY(0)} }

    /* footer */
    .footer{ margin-top:14px; text-align:center; color:#9ccbd7; font-size:13px }

    /* tiny helpers & responsive */
    .muted{ color:#9ccbd7; font-size:13px }
    @media(max-width:980px){
      .layout{ grid-template-columns: 1fr; }
      .side{ position:static; top:auto }
      nav{ width:100%; overflow:auto; padding-bottom:10px }
    }
  </style>
</head>
<body>
  <div class="shell">

    <!-- header -->
    <div class="header">
      <div class="brand">
        <div class="logo">SV</div>
        <div>
          <h1>SecretVerse</h1>
          <p>Anonymous Confessions — Share freely, stay anonymous</p>
        </div>
      </div>

      <nav id="nav">
        <a href="#home" data-route="home" class="active"><i class="fa-solid fa-house"></i> Home</a>
        <a href="#trending" data-route="trending"><i class="fa-solid fa-fire"></i> Trending</a>
        <a href="#categories" data-route="categories"><i class="fa-solid fa-list"></i> Categories</a>
        <a href="#notes" data-route="notes"><i class="fa-solid fa-book"></i> Notes</a>
        <a href="#leaderboard" data-route="leaderboard"><i class="fa-solid fa-trophy"></i> Leaderboard</a>
        <a href="#about" data-route="about"><i class="fa-solid fa-circle-info"></i> About</a>
        <a href="#contact" data-route="contact"><i class="fa-solid fa-envelope"></i> Contact</a>
        <a href="#profile" data-route="profile"><i class="fa-solid fa-user"></i> Profile</a>
      </nav>
    </div>

    <div class="layout">
      <!-- MAIN -->
      <main class="main">
        <!-- TOP AD (demo) -->
        <div class="ad" id="topAd">
          <div class="sponsor">Sponsored • GlowTech</div>
          <div class="tag">AI Tools for Students — Try GlowNote Pro</div>
          <a class="cta" href="#" onclick="alert('Demo sponsor clicked')">Visit Sponsor</a>
        </div>

        <!-- PAGES -->
        <!-- HOME -->
        <section id="home" class="page active">
          <div class="composer">
            <textarea id="composerInput" placeholder="Share your secret... (anonymous)"></textarea>
            <div class="controls">
              <div class="small muted">Post anonymously</div>
              <button class="btn" id="postBtn">POST</button>
              <button class="btn secondary" id="clearBtn">Clear</button>
            </div>
          </div>

          <div id="homeAds" class="ad"></div>

          <div id="postsList" class="posts"></div>
        </section>

        <!-- TRENDING -->
        <section id="trending" class="page">
          <div class="card">
            <div class="small muted">Trending confessions — sorted by total reactions</div>
          </div>
          <div id="trendingList" class="posts"></div>
        </section>

        <!-- CATEGORIES (demo categories) -->
        <section id="categories" class="page">
          <div class="card">
            <div style="display:flex;gap:8px;flex-wrap:wrap">
              <button class="btn secondary" data-cat="crush">Crush</button>
              <button class="btn secondary" data-cat="school">School</button>
              <button class="btn secondary" data-cat="funny">Funny</button>
              <button class="btn secondary" data-cat="study">Study</button>
              <button class="btn secondary" data-cat="other">Other</button>
            </div>
          </div>
          <div id="catList" class="posts"></div>
        </section>

        <!-- NOTES -->
        <section id="notes" class="page">
          <div class="card">
            <div class="small muted">Notes / Resources — save text notes locally</div>
            <textarea id="noteInput" style="width:100%;min-height:90px;margin-top:8px;padding:10px;border-radius:8px;background:rgba(255,255,255,0.02);border:none;color:#eaf6ff"></textarea>
            <div style="display:flex;gap:8px;margin-top:8px">
              <button class="btn" id="saveNote">Save Note</button>
              <button class="btn secondary" id="clearNotes">Clear All Notes</button>
            </div>
          </div>
          <div id="notesList"></div>
        </section>

        <!-- LEADERBOARD -->
        <section id="leaderboard" class="page">
          <div class="card">
            <div class="small muted">Top creators by reactions (local device demo)</div>
          </div>
          <div id="leaderList"></div>
        </section>

        <!-- ABOUT -->
        <section id="about" class="page">
          <div class="card">
            <h3 style="margin:0 0 8px 0">About SecretVerse</h3>
            <p class="small">SecretVerse is a student-first anonymous platform to share confessions, laughs, and study life. This demo is built as a single-file app (localStorage). For multi-device sync use Firebase (I can add that for you).</p>
          </div>
        </section>

        <!-- CONTACT -->
        <section id="contact" class="page">
          <div class="card">
            <h3 style="margin:0 0 8px 0">Contact / Feedback</h3>
            <input id="contactName" placeholder="Your name (optional)" style="width:100%;padding:10px;border-radius:8px;border:none;background:rgba(255,255,255,0.02);color:#eaf6ff;margin-bottom:8px">
            <textarea id="contactMsg" placeholder="Your message..." style="width:100%;min-height:90px;padding:10px;border-radius:8px;border:none;background:rgba(255,255,255,0.02);color:#eaf6ff"></textarea>
            <div style="margin-top:8px"><button class="btn" id="sendContact">Send</button></div>
            <div id="contactResult" style="margin-top:8px;color:#9cdbe6"></div>
          </div>
        </section>

        <!-- PROFILE -->
        <section id="profile" class="page">
          <div class="card">
            <h3 style="margin:0 0 8px 0">Your Profile (local demo)</h3>
            <div class="small muted">Browser ID: <span id="browserId"></span></div>
            <div style="margin-top:8px" class="small muted">Posts created on this device: <span id="myCount">0</span></div>
            <div style="margin-top:12px"><button class="btn secondary" id="exportBtn">Export My Posts (JSON)</button></div>
          </div>
        </section>

        <!-- BOTTOM AD -->
        <div class="ad" id="bottomAd">
          <div class="sponsor">Sponsored • ChillBytes</div>
          <div class="tag">Make memes & share — Get ChillBytes tools free</div>
          <a class="cta" href="#" onclick="alert('Demo sponsor clicked')">Sponsor Link</a>
        </div>
      </main>

      <!-- SIDE (ads + small widgets) -->
      <aside class="side">
        <div class="card">
          <div class="small muted">Top Ad</div>
          <div style="height:120px;display:grid;place-items:center">
            <div style="width:100%;height:100%;border-radius:10px;background:linear-gradient(90deg,var(--neonA),var(--neonB));display:flex;align-items:center;justify-content:center;color:#02131a;font-weight:800">
              DEMO AD • Secret Sponsor
            </div>
          </div>
        </div>

        <div class="card">
          <div class="small muted">Quick Tips</div>
          <ol style="margin:8px 0 0 16px;color:#bfe9f7">
            <li>Be kind — report abuse</li>
            <li>Share posts to get friends</li>
            <li>Use Notes for study snippets</li>
          </ol>
        </div>

        <div class="card">
          <div class="small muted">Mid Ad</div>
          <div style="height:80px;display:grid;place-items:center">
            <div style="padding:10px;border-radius:8px;background:linear-gradient(135deg,rgba(255,255,255,0.02),rgba(0,0,0,0.08));width:100%;text-align:center">
              MID-FEED AD • Try GlowNote
            </div>
          </div>
        </div>
      </aside>
    </div>

    <div class="footer">© <span id="yr"></span> SecretVerse — Next Level Demo</div>
  </div>

  <script>
    // ---------- App state & storage ----------
    const YEAR = document.getElementById('yr'); YEAR.textContent = new Date().getFullYear();
    const BROWSER_KEY = 'secretverse_browser_id_v2';
    let browserId = localStorage.getItem(BROWSER_KEY);
    if(!browserId){ browserId = 'B_'+Math.random().toString(36).slice(2,9); localStorage.setItem(BROWSER_KEY,browserId); }
    document.getElementById('browserId').textContent = browserId;

    const POSTS_KEY = 'secretverse_posts_v2';
    let posts = JSON.parse(localStorage.getItem(POSTS_KEY)) || [];

    const NOTES_KEY = 'secretverse_notes_v2';
    let notes = JSON.parse(localStorage.getItem(NOTES_KEY)) || [];

    // helpers
    const esc = s => String(s).replaceAll('&','&amp;').replaceAll('<','&lt;').replaceAll('>','&gt;');

    function genUser(){
      const names = ['Whisper','Hidden','Shy','Silent','Myst','Echo','Shadow','Glimmer'];
      return names[Math.floor(Math.random()*names.length)] + '_' + Math.floor(Math.random()*9000+1000);
    }
    function timeAgo(ts){
      const s = Math.floor((Date.now() - ts)/1000);
      if(s < 60) return `${s}s ago`;
      const m = Math.floor(s/60); if(m < 60) return `${m}m ago`;
      const h = Math.floor(m/60); if(h < 24) return `${h}h ago`;
      const d = Math.floor(h/24); return `${d}d ago`;
    }

    // ---------- UI refs ----------
    const composerInput = document.getElementById('composerInput');
    const postBtn = document.getElementById('postBtn');
    const clearBtn = document.getElementById('clearBtn');
    const postsList = document.getElementById('postsList');
    const topAd = document.getElementById('topAd');
    const homeAds = document.getElementById('homeAds');
    const bottomAd = document.getElementById('bottomAd');

    // render posts with mid ad injection
    function renderPosts(){
      postsList.innerHTML = '';
      const list = document.createElement('div'); list.className='posts';
      posts.forEach((p,i)=>{
        if(i === 4){
          const ad = document.createElement('div'); ad.className='ad'; ad.innerHTML = `<div class="sponsor">Sponsored • StudyBoost</div><div class="tag">Crack exams with StudyBoost premium</div><a class="cta" href="#" onclick="alert('Demo')">Learn more</a>`;
          list.appendChild(ad);
        }
        const el = document.createElement('div'); el.className='post';
        el.innerHTML = `
          <div class="who">
            <div class="avatar">${esc(p.user.charAt(0) || 'S')}</div>
            <div>
              <div class="meta"><strong>${esc(p.user)}</strong> <div class="muted" style="display:inline-block;margin-left:6px">${timeAgo(p.created)}</div></div>
            </div>
          </div>
          <p>${esc(p.text)}</p>
          <div class="metaRow">
            <button class="react" data-id="${p.id}" data-type="heart">❤️ <span class="count">${p.reactions.heart}</span></button>
            <button class="react" data-id="${p.id}" data-type="lol">😂 <span class="count">${p.reactions.lol}</span></button>
            <button class="react" data-id="${p.id}" data-type="sad">😭 <span class="count">${p.reactions.sad}</span></button>
          </div>
        `;
        // delete if owner
        if(p.owner === browserId){
          const del = document.createElement('button'); del.className='deleteBtn'; del.innerHTML='<i class="fa-solid fa-trash-can"></i>';
          del.addEventListener('click', ()=> deletePost(p.id));
          el.appendChild(del);
        }
        // reaction handlers
        el.querySelectorAll('.react').forEach(b=>{
          b.addEventListener('click', ()=>{
            toggleReact(b.getAttribute('data-id'), b.getAttribute('data-type'));
          });
        });
        list.appendChild(el);
      });
      if(posts.length === 0){
        const empty = document.createElement('div'); empty.className='post'; empty.style.textAlign='center'; empty.innerHTML='<div class="muted">No confessions yet — be the first to share anonymously ✨</div>';
        list.appendChild(empty);
      }
      postsList.appendChild(list);
    }

    function renderTrending(){
      const el = document.getElementById('trendingList'); el.innerHTML='';
      // sort by total reactions
      const sorted = [...posts].sort((a,b)=>{
        const sa = a.reactions.heart + a.reactions.lol + a.reactions.sad;
        const sb = b.reactions.heart + b.reactions.lol + b.reactions.sad;
        return sb - sa;
      });
      const list = document.createElement('div'); list.className='posts';
      sorted.forEach(p=>{
        const item = document.createElement('div'); item.className='post';
        item.innerHTML = `<div class="who"><div class="avatar">${esc(p.user.charAt(0))}</div><div><div class="meta"><strong>${esc(p.user)}</strong> <span class="muted" style="margin-left:6px">${timeAgo(p.created)}</span></div></div></div><p>${esc(p.text)}</p><div class="metaRow"> <div class="muted">Total: ${p.reactions.heart + p.reactions.lol + p.reactions.sad}</div></div>`;
        list.appendChild(item);
      });
      el.appendChild(list);
    }

    function renderCategories(cat){
      const el = document.getElementById('catList'); el.innerHTML='';
      // category demo: filter by tag in text (crush/school/funny/study)
      const filtered = cat ? posts.filter(p => p.text.toLowerCase().includes(cat)) : posts;
      const list = document.createElement('div'); list.className='posts';
      filtered.forEach(p=>{
        const item = document.createElement('div'); item.className='post';
        item.innerHTML = `<div class="who"><div class="avatar">${esc(p.user.charAt(0))}</div><div><div class="meta"><strong>${esc(p.user)}</strong> <span class="muted" style="margin-left:6px">${timeAgo(p.created)}</span></div></div></div><p>${esc(p.text)}</p>`;
        list.appendChild(item);
      });
      el.appendChild(list);
    }

    function renderNotes(){
      const el = document.getElementById('notesList'); el.innerHTML='';
      if(notes.length === 0){ el.innerHTML = `<div class="card"><div class="muted">No notes saved yet.</div></div>`; return; }
      notes.forEach((n, i)=>{
        const c = document.createElement('div'); c.className='card'; c.innerHTML = `<div style="display:flex;justify-content:space-between;align-items:center"><div><div style="font-weight:700">${esc(n.title||'Note')}</div><div class="muted" style="font-size:13px">${new Date(n.created).toLocaleString()}</div></div><div><button class="btn secondary" data-i="${i}">Delete</button></div></div><div style="margin-top:8px">${esc(n.text)}</div>`;
        c.querySelectorAll('.btn.secondary').forEach(b=>{
          b.addEventListener('click', ()=>{
            const idx = Number(b.getAttribute('data-i')); if(!confirm('Delete this note?')) return; notes.splice(idx,1); localStorage.setItem(NOTES_KEY, JSON.stringify(notes)); renderNotes();
          });
        });
        el.appendChild(c);
      });
    }

    function renderLeaderboard(){
      const el = document.getElementById('leaderList'); el.innerHTML='';
      // aggregate by user
      const map = {};
      posts.forEach(p=>{
        if(!map[p.user]) map[p.user] = {user:p.user, score:0, posts:0};
        map[p.user].score += p.reactions.heart + p.reactions.lol + p.reactions.sad;
        map[p.user].posts += 1;
      });
      const arr = Object.values(map).sort((a,b)=>b.score - a.score);
      if(arr.length === 0){ el.innerHTML = `<div class="card"><div class="muted">No creators yet.</div></div>`; return; }
      arr.forEach(u=>{
        const c = document.createElement('div'); c.className='card'; c.innerHTML = `<div style="display:flex;justify-content:space-between;align-items:center"><div><strong>${esc(u.user)}</strong><div class="muted">Posts: ${u.posts}</div></div><div style="font-weight:800;color:var(--accent)">${u.score}</div></div>`;
        el.appendChild(c);
      });
    }

    // ---------- post actions ----------
    function savePosts(){ localStorage.setItem(POSTS_KEY, JSON.stringify(posts)); refreshAll(); }
    function createPost(text){
      const p = { id:'p_'+Date.now()+'_'+Math.random().toString(36).slice(2,6), user: genUser(), text: text, reactions:{heart:0,lol:0,sad:0}, owner: browserId, created: Date.now() };
      posts.unshift(p); savePosts();
    }
    function deletePost(id){
      const idx = posts.findIndex(x=>x.id===id); if(idx === -1) return;
      if(posts[idx].owner !== browserId){ alert('You can only delete posts created from this device.'); return; }
      if(!confirm('Delete this confession?')) return;
      posts.splice(idx,1); savePosts();
    }
    function toggleReact(id,type){
      const p = posts.find(x=>x.id===id); if(!p) return; p.reactions[type]++; savePosts();
    }

    // ---------- notes ----------
    document.getElementById('saveNote').addEventListener('click', ()=>{
      const t = document.getElementById('noteInput').value.trim();
      if(!t) return alert('Write a note first');
      notes.unshift({ title: t.slice(0,30), text:t, created: Date.now() });
      localStorage.setItem(NOTES_KEY, JSON.stringify(notes));
      document.getElementById('noteInput').value='';
      renderNotes();
      alert('Note saved locally ✅');
    });
    document.getElementById('clearNotes').addEventListener('click', ()=>{
      if(!confirm('Clear all notes?')) return; notes=[]; localStorage.setItem(NOTES_KEY, JSON.stringify(notes)); renderNotes();
    });

    // contact demo
    document.getElementById('sendContact').addEventListener('click', ()=>{
      const name = document.getElementById('contactName').value.trim();
      const msg = document.getElementById('contactMsg').value.trim();
      if(!msg) return alert('Write a message');
      document.getElementById('contactResult').textContent = 'Thanks! (This is a demo — message stored locally)';
      // store locally
      const old = JSON.parse(localStorage.getItem('secretverse_contacts_v2')||'[]'); old.unshift({name, msg, created:Date.now()}); localStorage.setItem('secretverse_contacts_v2', JSON.stringify(old));
      document.getElementById('contactMsg').value=''; document.getElementById('contactName').value='';
    });

    // export my posts
    document.getElementById('exportBtn').addEventListener('click', ()=>{
      const mine = posts.filter(p=>p.owner===browserId);
      const blob = new Blob([JSON.stringify(mine,null,2)], {type:'application/json'}); const url = URL.createObjectURL(blob);
      const a = document.createElement('a'); a.href=url; a.download='my_posts.json'; a.click(); URL.revokeObjectURL(url);
    });

    // clear composer
    clearBtn.addEventListener('click', ()=> { composerInput.value=''; });

    // post creation
    postBtn.addEventListener('click', ()=> {
      const v = composerInput.value.trim(); if(!v) return alert('Write something first!');
      createPost(v); composerInput.value=''; alert('Posted anonymously ✅');
    });
    composerInput.addEventListener('keydown', (e)=>{ if(e.key==='Enter' && (e.ctrlKey||e.metaKey)){ postBtn.click(); } });

    // clear all posts (local)
    document.getElementById('clearBtn').addEventListener('click', ()=>{
      if(!confirm('Clear all local posts? This removes posts only from this device.')) return; posts=[]; savePosts();
    });

    // ---------- routing & navigation ----------
    const pages = Array.from(document.querySelectorAll('.page'));
    const navlinks = Array.from(document.querySelectorAll('nav a'));
    function showPage(name){
      pages.forEach(p => p.classList.toggle('active', p.id === name));
      navlinks.forEach(a => a.classList.toggle('active', a.getAttribute('data-route') === name));
      // render page content if needed
      if(name === 'home') renderPosts();
      if(name === 'trending') renderTrending();
      if(name === 'categories') renderCategories();
      if(name === 'notes') renderNotes();
      if(name === 'leaderboard') renderLeaderboard();
      if(name === 'profile') document.getElementById('myCount').textContent = posts.filter(p=>p.owner===browserId).length;
    }
    function route(){
      const hash = location.hash.replace('#','') || 'home'; showPage(hash);
    }
    window.addEventListener('hashchange', route);
    // init nav clicks
    navlinks.forEach(a => a.addEventListener('click', ()=> {
      // small UX: close mobile scroll to top
      window.scrollTo({top:0, behavior:'smooth'});
    }));
    // initial
    route();

    // ---------- global refresh ----------
    function refreshAll(){
      // re-save and render necessary pieces
      localStorage.setItem(POSTS_KEY, JSON.stringify(posts));
      if(location.hash.replace('#','') === 'home' || location.hash === '') renderPosts();
      if(location.hash.replace('#','') === 'trending') renderTrending();
      renderLeaderboard();
      renderNotes();
    }

    // initial rendering
    refreshAll();

    // categories buttons
    document.querySelectorAll('[data-cat]').forEach(b=>{
      b.addEventListener('click', ()=> {
        const cat = b.getAttribute('data-cat');
        location.hash = 'categories';
        setTimeout(()=> renderCategories(cat), 120);
      });
    });

    // small keyboard shortcut: N to focus composer
    window.addEventListener('keydown', (e)=>{ if(e.key.toLowerCase()==='n' && !e.metaKey && !e.ctrlKey){ composerInput.focus(); } });

    // expose some functions for demo
    window.deletePost = deletePost;
  </script>
</body>
</html>
