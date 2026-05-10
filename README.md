[tony-aubrey-tracker(1).html](https://github.com/user-attachments/files/27562530/tony-aubrey-tracker.1.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tony & Aubrey ♥</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #fdf6ee;
    --blush: #f2c4b8;
    --rose: #c96b6b;
    --deep: #3b2a2a;
    --muted: #8a7070;
    --card: #fff9f5;
    --border: #ead5c8;
    --accent: #e8a598;
    --green: #7aab8a;
    --shadow: 0 4px 24px rgba(59,42,42,0.08);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--cream);
    color: var(--deep);
    font-family: 'DM Sans', sans-serif;
    min-height: 100vh;
  }

  /* Header */
  header {
    text-align: center;
    padding: 48px 24px 32px;
    position: relative;
  }

  .header-deco {
    font-family: 'Playfair Display', serif;
    font-size: 13px;
    letter-spacing: 4px;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  header h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.4rem, 6vw, 4rem);
    font-weight: 700;
    line-height: 1.1;
    color: var(--deep);
  }

  header h1 span {
    color: var(--rose);
    font-style: italic;
  }

  .header-heart {
    font-size: 1.1rem;
    margin: 0 10px;
    color: var(--rose);
  }

  .header-sub {
    margin-top: 10px;
    font-size: 14px;
    color: var(--muted);
    font-weight: 300;
    letter-spacing: 1px;
  }

  /* Stats bar */
  .stats-bar {
    display: flex;
    justify-content: center;
    gap: 0;
    max-width: 600px;
    margin: 24px auto 0;
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
    background: var(--card);
    box-shadow: var(--shadow);
  }

  .stat {
    flex: 1;
    padding: 14px 16px;
    text-align: center;
    border-right: 1px solid var(--border);
  }
  .stat:last-child { border-right: none; }

  .stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 1.6rem;
    font-weight: 700;
    color: var(--rose);
    line-height: 1;
  }

  .stat-label {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-top: 3px;
  }

  /* Main layout */
  main {
    max-width: 960px;
    margin: 0 auto;
    padding: 32px 20px 60px;
  }

  /* Controls */
  .controls {
    display: flex;
    gap: 10px;
    margin-bottom: 24px;
    flex-wrap: wrap;
    align-items: center;
  }

  .tab-group {
    display: flex;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 3px;
    gap: 2px;
  }

  .tab {
    padding: 7px 16px;
    border-radius: 9px;
    border: none;
    background: transparent;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    color: var(--muted);
    cursor: pointer;
    transition: all 0.18s;
  }
  .tab.active {
    background: var(--rose);
    color: white;
  }
  .tab:hover:not(.active) { color: var(--deep); }

  .add-btn {
    margin-left: auto;
    padding: 9px 20px;
    background: var(--rose);
    color: white;
    border: none;
    border-radius: 12px;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    cursor: pointer;
    transition: background 0.18s, transform 0.12s;
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .add-btn:hover { background: #b55c5c; transform: translateY(-1px); }
  .add-btn:active { transform: translateY(0); }

  /* Table */
  .table-wrap {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 20px;
    overflow: hidden;
    box-shadow: var(--shadow);
  }

  table {
    width: 100%;
    border-collapse: collapse;
  }

  thead {
    background: linear-gradient(90deg, #f7e8e2, #fdf0ea);
  }

  th {
    padding: 13px 16px;
    text-align: left;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--muted);
    border-bottom: 1px solid var(--border);
    white-space: nowrap;
    cursor: pointer;
    user-select: none;
  }
  th:hover { color: var(--rose); }

  td {
    padding: 12px 16px;
    font-size: 14px;
    border-bottom: 1px solid #f0e4db;
    vertical-align: middle;
  }

  tr:last-child td { border-bottom: none; }

  tr:hover td { background: #fdf0ea44; }

  .title-cell {
    font-weight: 500;
    color: var(--deep);
    max-width: 240px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  /* Badges */
  .badge {
    display: inline-block;
    padding: 3px 10px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.3px;
    white-space: nowrap;
  }

  .badges-cell { display: flex; gap: 4px; flex-wrap: nowrap; align-items: center; }

  .badge-anime { background: #e8d5f5; color: #7a4fa0; }
  .badge-movie { background: #d5e8f5; color: #2e6fa0; }
  .badge-tv    { background: #d5f5e3; color: #2a8052; }
  .badge-game  { background: #f5ead5; color: #9a6a1a; }

  /* Status */
  .status-dot {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    font-size: 12px;
    font-weight: 500;
  }
  .dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    display: inline-block;
  }
  .dot-done   { background: var(--green); }
  .dot-watch  { background: #f0c060; }
  .dot-drop   { background: #c07070; }

  .rating {
    font-size: 13px;
    font-weight: 600;
    white-space: nowrap;
  }

  /* Actions */
  .action-btn {
    background: none;
    border: none;
    cursor: pointer;
    padding: 4px 6px;
    border-radius: 6px;
    font-size: 14px;
    transition: background 0.15s;
    color: var(--muted);
  }
  .action-btn:hover { background: #f0e0d8; color: var(--rose); }

  /* Empty state */
  .empty {
    text-align: center;
    padding: 60px 20px;
    color: var(--muted);
  }
  .empty-icon { font-size: 3rem; margin-bottom: 12px; }
  .empty p { font-size: 15px; }

  /* Modal */
  .overlay {
    position: fixed; inset: 0;
    background: rgba(59,42,42,0.35);
    backdrop-filter: blur(3px);
    z-index: 100;
    display: none;
    align-items: center;
    justify-content: center;
    padding: 20px;
  }
  .overlay.open { display: flex; }

  .modal {
    background: var(--card);
    border-radius: 24px;
    padding: 32px;
    width: 100%;
    max-width: 480px;
    box-shadow: 0 20px 60px rgba(59,42,42,0.2);
    animation: slideUp 0.22s ease;
    max-height: 90vh;
    overflow-y: auto;
  }

  @keyframes slideUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .modal h2 {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem;
    margin-bottom: 24px;
    color: var(--deep);
  }

  .form-row {
    margin-bottom: 16px;
  }

  .form-row label {
    display: block;
    font-size: 12px;
    font-weight: 500;
    color: var(--muted);
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-bottom: 6px;
  }

  .form-row input,
  .form-row select,
  .form-row textarea {
    width: 100%;
    padding: 10px 14px;
    border: 1px solid var(--border);
    border-radius: 10px;
    background: white;
    font-family: 'DM Sans', sans-serif;
    font-size: 14px;
    color: var(--deep);
    transition: border-color 0.15s;
    outline: none;
  }
  .form-row input:focus,
  .form-row select:focus,
  .form-row textarea:focus {
    border-color: var(--rose);
  }

  .form-two { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }

  .star-picker {
    display: flex;
    gap: 4px;
    align-items: center;
  }
  .star-btn {
    background: none; border: none; cursor: pointer;
    font-size: 1.4rem; color: #ddd; transition: color 0.1s;
    padding: 2px;
  }
  .star-btn.lit { color: #f0a060; }

  .modal-actions {
    display: flex;
    gap: 10px;
    margin-top: 24px;
    justify-content: flex-end;
  }

  .btn-cancel {
    padding: 10px 20px;
    border: 1px solid var(--border);
    border-radius: 10px;
    background: transparent;
    font-family: 'DM Sans', sans-serif;
    font-size: 14px;
    color: var(--muted);
    cursor: pointer;
    transition: background 0.15s;
  }
  .btn-cancel:hover { background: #f5ece6; }

  .btn-save {
    padding: 10px 24px;
    background: var(--rose);
    color: white;
    border: none;
    border-radius: 10px;
    font-family: 'DM Sans', sans-serif;
    font-size: 14px;
    font-weight: 500;
    cursor: pointer;
    transition: background 0.15s;
  }
  .btn-save:hover { background: #b55c5c; }

  /* Rating color applied to star + number only */
  .rating-10 { color: #4aaa6a; }
  .rating-9  { color: #62b85a; }
  .rating-8  { color: #86c24a; }
  .rating-7  { color: #b8c840; }
  .rating-6  { color: #c8b838; }
  .rating-5  { color: #d49a38; }
  .rating-4  { color: #d07a3a; }
  .rating-3  { color: #c85a3a; }
  .rating-2  { color: #c04040; }
  .rating-1  { color: #b03030; }

  /* Multi-type toggle */
  .type-toggle-group {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
  }
  .type-toggle {
    padding: 6px 14px;
    border: 1px solid var(--border);
    border-radius: 20px;
    background: white;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    color: var(--muted);
    cursor: pointer;
    transition: all 0.15s;
  }
  .type-toggle:hover { border-color: var(--rose); color: var(--rose); }
  .type-toggle.selected { background: var(--rose); color: white; border-color: var(--rose); }
  .type-toggle[data-type="Anime"].selected   { background: #9b6bc4; border-color: #9b6bc4; }
  .type-toggle[data-type="Movie"].selected   { background: #4a8fc4; border-color: #4a8fc4; }
  .type-toggle[data-type="TV Show"].selected { background: #4aaa72; border-color: #4aaa72; }
  .type-toggle[data-type="Game"].selected    { background: #c4913a; border-color: #c4913a; }

  /* Badge tweaks for multi */
  .badges-cell { display: flex; gap: 4px; flex-wrap: wrap; }
  .deco-line {
    border: none;
    border-top: 1px solid var(--border);
    margin: 0 auto 28px;
    max-width: 120px;
    opacity: 0.6;
  }

  @media (max-width: 600px) {
    .form-two { grid-template-columns: 1fr; }
    td, th { padding: 10px 10px; font-size: 12px; }
    .title-cell { max-width: 110px; }
    .controls { gap: 8px; }
  }
</style>
</head>
<body>

<header>
  <div class="header-deco">our little log</div>
  <h1><span>Tony</span> <span class="header-heart">♥</span> <span>Aubrey</span></h1>
  <p class="header-sub">movies · shows · anime · games</p>
  <hr class="deco-line" style="margin-top:20px">

  <div class="stats-bar">
    <div class="stat">
      <div class="stat-num" id="stat-total">0</div>
      <div class="stat-label">Total</div>
    </div>
    <div class="stat">
      <div class="stat-num" id="stat-done">0</div>
      <div class="stat-label">Finished</div>
    </div>
    <div class="stat">
      <div class="stat-num" id="stat-watching">0</div>
      <div class="stat-label">In Progress</div>
    </div>
    <div class="stat">
      <div class="stat-num" id="stat-avg">—</div>
      <div class="stat-label">Avg Rating</div>
    </div>
  </div>
</header>

<main>
  <div class="controls">
    <div class="tab-group">
      <button class="tab active" onclick="filterType('all', this)">All</button>
      <button class="tab" onclick="filterType('Anime', this)">Anime</button>
      <button class="tab" onclick="filterType('Movie', this)">Movies</button>
      <button class="tab" onclick="filterType('TV Show', this)">TV</button>
      <button class="tab" onclick="filterType('Game', this)">Games</button>
    </div>
    <button class="add-btn" onclick="openModal()">
      <span>＋</span> Add Entry
    </button>
  </div>

  <div class="table-wrap">
    <table>
      <thead>
        <tr>
          <th onclick="sortBy('title')">Title ↕</th>
          <th onclick="sortBy('genre')">Genre</th>
          <th onclick="sortBy('type')">Type</th>
          <th onclick="sortBy('status')">Status</th>
          <th onclick="sortBy('dateStarted')">Started</th>
          <th onclick="sortBy('dateCompleted')">Completed</th>
          <th onclick="sortBy('rating')">Rating</th>
          <th></th>
        </tr>
      </thead>
      <tbody id="table-body">
      </tbody>
    </table>
    <div id="empty-state" class="empty" style="display:none">
      <div class="empty-icon">🎬</div>
      <p>Nothing here yet — add your first entry!</p>
    </div>
  </div>
</main>

<!-- Modal -->
<div class="overlay" id="overlay" onclick="closeModalOutside(event)">
  <div class="modal">
    <h2 id="modal-title">Add Entry</h2>
    <div class="form-row">
      <label>Title</label>
      <input type="text" id="f-title" placeholder="e.g. Your Name">
    </div>
    <div class="form-two">
      <div class="form-row">
        <label>Genre</label>
        <input type="text" id="f-genre" placeholder="e.g. Romance">
      </div>
      <div class="form-row">
        <label>Type <span style="font-size:10px;opacity:0.7">(pick all that apply)</span></label>
        <div class="type-toggle-group" id="f-type-group">
          <button type="button" class="type-toggle" data-type="Anime" onclick="toggleType(this)">Anime</button>
          <button type="button" class="type-toggle" data-type="Movie" onclick="toggleType(this)">Movie</button>
          <button type="button" class="type-toggle" data-type="TV Show" onclick="toggleType(this)">TV Show</button>
          <button type="button" class="type-toggle" data-type="Game" onclick="toggleType(this)">Game</button>
        </div>
      </div>
    </div>
    <div class="form-two">
      <div class="form-row">
        <label>Date Started</label>
        <input type="text" id="f-start" placeholder="e.g. 3/16/26">
      </div>
      <div class="form-row">
        <label>Date Completed</label>
        <input type="text" id="f-end" placeholder="e.g. 3/26/26">
      </div>
    </div>
    <div class="form-two">
      <div class="form-row">
        <label>Episodes / Progress</label>
        <input type="text" id="f-episodes" placeholder="e.g. 13/13 or N/A">
      </div>
      <div class="form-row">
        <label>Status</label>
        <select id="f-status">
          <option>Completed</option>
          <option>In Progress</option>
          <option>Dropped</option>
        </select>
      </div>
    </div>
    <div class="form-row">
      <label>Rating (out of 10)</label>
      <div class="star-picker" id="star-picker">
        <!-- filled by JS -->
      </div>
      <input type="hidden" id="f-rating" value="0">
    </div>
    <div class="modal-actions">
      <button class="btn-cancel" onclick="closeModal()">Cancel</button>
      <button class="btn-save" onclick="saveEntry()">Save ♥</button>
    </div>
  </div>
</div>

<script>
// ─── Data ────────────────────────────────────────────────
let data = JSON.parse(localStorage.getItem('ta-tracker') || '[]');
let editId = null;
let currentFilter = 'all';
let sortKey = 'dateCompleted';
let sortDir = 1;

function uid() { return Date.now().toString(36) + Math.random().toString(36).slice(2); }
function save() { localStorage.setItem('ta-tracker', JSON.stringify(data)); }

// Migrate old string `type` → array, and pre-load seed data
if (!data.length) {
  data = [
    { id: uid(), title: 'Mahou Shoujo Site', genre: 'Magical Girl', types: ['Anime'], episodes: '5/12', dateStarted: 'February', dateCompleted: 'DROPPED', status: 'Dropped', rating: 4 },
    { id: uid(), title: 'Monster', genre: 'Drama', types: ['Movie'], episodes: 'N/A', dateStarted: '2/14/26', dateCompleted: '2/14/26', status: 'Completed', rating: 7 },
    { id: uid(), title: 'Rascal Does Not Dream of Bunny Girl Senpai', genre: 'Romance/Mystery', types: ['Anime'], episodes: '13/13', dateStarted: '3/16/26', dateCompleted: '3/26/26', status: 'Completed', rating: 9 },
    { id: uid(), title: 'Rascal Does Not Dream of a Dreaming Girl', genre: 'Romance/Mystery', types: ['Anime','Movie'], episodes: 'N/A', dateStarted: 'March', dateCompleted: 'March', status: 'Completed', rating: 9 },
    { id: uid(), title: 'Rascal Does Not Dream of a Sister Venturing Out', genre: 'Romance/Mystery', types: ['Anime','Movie'], episodes: 'N/A', dateStarted: '3/28/26', dateCompleted: '3/28/26', status: 'Completed', rating: 7 },
    { id: uid(), title: 'Rascal Does Not Dream of a Knapsack Kid', genre: 'Romance/Mystery', types: ['Anime','Movie'], episodes: 'N/A', dateStarted: '3/31/26', dateCompleted: '3/31/26', status: 'Completed', rating: 7 },
    { id: uid(), title: 'Rascal Does Not Dream of Santa Claus', genre: 'Romance/Mystery', types: ['Anime'], episodes: '13/13', dateStarted: '4/8/26', dateCompleted: '4/28/26', status: 'Completed', rating: 8 },
    { id: uid(), title: 'Regular Show', genre: 'Comedy', types: ['TV Show'], episodes: '33/261', dateStarted: '5/2/26', dateCompleted: '', status: 'In Progress', rating: 0 },
    { id: uid(), title: 'Minecraft Hardcore Vanilla', genre: 'Survival', types: ['Game'], episodes: 'N/A', dateStarted: '', dateCompleted: '1/21/26', status: 'Completed', rating: 10 },
    { id: uid(), title: 'It Takes Two', genre: 'Co-op', types: ['Game'], episodes: 'N/A', dateStarted: '', dateCompleted: '2/23/26', status: 'Completed', rating: 9 },
    { id: uid(), title: 'Whisk Demo', genre: 'Co-op', types: ['Game'], episodes: 'N/A', dateStarted: '', dateCompleted: '2/28/26', status: 'Completed', rating: 8 },
    { id: uid(), title: 'Femboy Love Story', genre: 'Visual Novel', types: ['Game'], episodes: 'N/A', dateStarted: '', dateCompleted: '3/15/26', status: 'Completed', rating: 2 },
    { id: uid(), title: 'Ember Knights', genre: 'Action', types: ['Game'], episodes: 'N/A', dateStarted: '', dateCompleted: '4/13/26', status: 'Completed', rating: 8 },
    { id: uid(), title: 'StoneBlock 4', genre: 'Sandbox', types: ['Game'], episodes: 'N/A', dateStarted: '', dateCompleted: '5/1/26', status: 'Completed', rating: 7.5 },
  ];
  save();
} else {
  // migrate old string type → array
  data = data.map(r => {
    if (!r.types) r.types = r.type ? [r.type] : ['Movie'];
    delete r.type;
    return r;
  });
}

// ─── Rendering ───────────────────────────────────────────
function typeBadges(types) {
  const map = { 'Anime': 'badge-anime', 'Movie': 'badge-movie', 'TV Show': 'badge-tv', 'Game': 'badge-game' };
  return `<div class="badges-cell">${(types||[]).map(t=>`<span class="badge ${map[t]||'badge-movie'}">${t}</span>`).join('')}</div>`;
}

function statusDot(s) {
  const map = { 'Completed': 'dot-done', 'In Progress': 'dot-watch', 'Dropped': 'dot-drop' };
  return `<span class="status-dot"><span class="dot ${map[s]||'dot-watch'}"></span>${s}</span>`;
}

function ratingDisplay(r) {
  if (!r) return '<span style="color:#ccc">—</span>';
  const n = Math.round(Math.min(10, Math.max(1, r)));
  return `<span class="rating rating-${n}">★ ${r}/10</span>`;
}

function render() {
  let rows = [...data];
  if (currentFilter !== 'all') rows = rows.filter(r => (r.types||[]).includes(currentFilter));

  rows.sort((a, b) => {
    let va = a[sortKey] || '', vb = b[sortKey] || '';
    if (sortKey === 'rating') { va = +va || 0; vb = +vb || 0; }
    if (va < vb) return -sortDir;
    if (va > vb) return sortDir;
    return 0;
  });

  const tbody = document.getElementById('table-body');
  const empty = document.getElementById('empty-state');

  if (!rows.length) {
    tbody.innerHTML = '';
    empty.style.display = '';
    return;
  }
  empty.style.display = 'none';

  tbody.innerHTML = rows.map(r => `
    <tr>
      <td class="title-cell" title="${r.title}">${r.title.length > 34 ? r.title.slice(0,32)+'…' : r.title}</td>
      <td style="color:var(--muted);font-size:13px">${r.genre||'—'}</td>
      <td>${typeBadges(r.types)}</td>
      <td>${statusDot(r.status)}</td>
      <td style="color:var(--muted);font-size:13px">${r.dateStarted||'—'}</td>
      <td style="color:var(--muted);font-size:13px">${r.dateCompleted||'—'}</td>
      <td>${ratingDisplay(r.rating)}</td>
      <td>
        <button class="action-btn" onclick="editEntry('${r.id}')" title="Edit">✏️</button>
        <button class="action-btn" onclick="deleteEntry('${r.id}')" title="Delete">🗑</button>
      </td>
    </tr>
  `).join('');

  document.getElementById('stat-total').textContent = data.length;
  document.getElementById('stat-done').textContent = data.filter(r=>r.status==='Completed').length;
  document.getElementById('stat-watching').textContent = data.filter(r=>r.status==='In Progress').length;
  const rated = data.filter(r=>r.rating>0);
  const avg = rated.length ? (rated.reduce((s,r)=>s+(+r.rating),0)/rated.length).toFixed(1) : '—';
  document.getElementById('stat-avg').textContent = avg !== '—' ? avg : '—';
}

function filterType(t, btn) {
  currentFilter = t;
  document.querySelectorAll('.tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  render();
}

function sortBy(key) {
  if (sortKey === key) sortDir *= -1;
  else { sortKey = key; sortDir = 1; }
  render();
}

// ─── Star picker ─────────────────────────────────────────
let pickerVal = 0;

function buildStars(val) {
  const picker = document.getElementById('star-picker');
  picker.innerHTML = '';
  for (let i = 1; i <= 10; i++) {
    const btn = document.createElement('button');
    btn.type = 'button';
    btn.className = 'star-btn' + (i <= val ? ' lit' : '');
    btn.textContent = '★';
    btn.dataset.v = i;
    btn.onmouseenter = () => buildStars(i);
    btn.onclick = () => { pickerVal = i; document.getElementById('f-rating').value = i; buildStars(i); };
    picker.appendChild(btn);
  }
  picker.onmouseleave = () => buildStars(pickerVal);
}

// ─── Type toggles ────────────────────────────────────────
function toggleType(btn) {
  btn.classList.toggle('selected');
}

function setTypeToggles(types) {
  document.querySelectorAll('.type-toggle').forEach(btn => {
    btn.classList.toggle('selected', (types||[]).includes(btn.dataset.type));
  });
}

function getSelectedTypes() {
  return [...document.querySelectorAll('.type-toggle.selected')].map(b => b.dataset.type);
}

// ─── Modal ───────────────────────────────────────────────
function openModal() {
  editId = null;
  document.getElementById('modal-title').textContent = 'Add Entry ♥';
  document.getElementById('f-title').value = '';
  document.getElementById('f-genre').value = '';
  setTypeToggles([]);
  document.getElementById('f-start').value = '';
  document.getElementById('f-end').value = '';
  document.getElementById('f-episodes').value = '';
  document.getElementById('f-status').value = 'Completed';
  pickerVal = 0;
  buildStars(0);
  document.getElementById('overlay').classList.add('open');
}

function editEntry(id) {
  const r = data.find(x => x.id === id);
  if (!r) return;
  editId = id;
  document.getElementById('modal-title').textContent = 'Edit Entry';
  document.getElementById('f-title').value = r.title;
  document.getElementById('f-genre').value = r.genre;
  setTypeToggles(r.types || []);
  document.getElementById('f-start').value = r.dateStarted;
  document.getElementById('f-end').value = r.dateCompleted;
  document.getElementById('f-episodes').value = r.episodes;
  document.getElementById('f-status').value = r.status;
  pickerVal = +r.rating || 0;
  buildStars(pickerVal);
  document.getElementById('overlay').classList.add('open');
}

function closeModal() { document.getElementById('overlay').classList.remove('open'); }
function closeModalOutside(e) { if (e.target === document.getElementById('overlay')) closeModal(); }

function saveEntry() {
  const title = document.getElementById('f-title').value.trim();
  if (!title) { document.getElementById('f-title').focus(); return; }
  const types = getSelectedTypes();
  if (!types.length) { alert('Please pick at least one type!'); return; }
  const entry = {
    id: editId || uid(),
    title,
    genre: document.getElementById('f-genre').value.trim(),
    types,
    episodes: document.getElementById('f-episodes').value.trim(),
    dateStarted: document.getElementById('f-start').value.trim(),
    dateCompleted: document.getElementById('f-end').value.trim(),
    status: document.getElementById('f-status').value,
    rating: +document.getElementById('f-rating').value || 0,
  };
  if (editId) {
    const idx = data.findIndex(x => x.id === editId);
    if (idx !== -1) data[idx] = entry;
  } else {
    data.push(entry);
  }
  save();
  render();
  closeModal();
}

function deleteEntry(id) {
  if (!confirm('Remove this entry?')) return;
  data = data.filter(x => x.id !== id);
  save();
  render();
}

// ─── Init ────────────────────────────────────────────────
render();
</script>
</body>
</html>
