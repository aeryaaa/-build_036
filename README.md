# Janawaaz
A multilingual civic issue reporting and tracking platform where citizens can report problems, upload photos and track complaints.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>JanAwaaz | Your City, Your Voice</title>

<style>
:root {
  --navy: #102a43;
  --teal: #087e8b;
  --orange: #f59e0b;
  --bg: #f4f7fb;
  --muted: #64748b;
  --white: #fff;
  --border: #e2e8f0;
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: Arial, sans-serif;
  background: var(--bg);
  color: var(--navy);
}

button, input, select, textarea { font: inherit; }
button { cursor: pointer; }

header {
  background: white;
  padding: 17px 6%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  position: sticky;
  top: 0;
  z-index: 10;
  box-shadow: 0 3px 15px #102a4310;
}

.logo {
  font-size: 25px;
  font-weight: 900;
  color: var(--teal);
  white-space: nowrap;
}

.logo span { color: var(--orange); }

nav {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}

nav button {
  border: 0;
  background: transparent;
  color: var(--navy);
  font-weight: bold;
}

nav button:hover { color: var(--teal); }

.hero {
  padding: 75px 7%;
  color: white;
  background:
    radial-gradient(circle at 85% 20%, #ffffff20 0 100px, transparent 102px),
    linear-gradient(125deg, #102a43, #087e8b);
  display: grid;
  grid-template-columns: 1.4fr 1fr;
  gap: 40px;
  align-items: center;
}

.eyebrow {
  color: #ffd27a;
  font-weight: bold;
  letter-spacing: 2px;
  font-size: 13px;
  margin-bottom: 18px;
}

.hero h1 {
  font-size: clamp(38px, 5vw, 62px);
  line-height: 1.08;
  margin-bottom: 20px;
}

.hero p {
  color: #dceaf2;
  line-height: 1.7;
  font-size: 17px;
  max-width: 580px;
}

.actions {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin-top: 28px;
}

.btn {
  border: 0;
  padding: 13px 19px;
  border-radius: 10px;
  font-weight: bold;
}

.btn-primary {
  background: var(--orange);
  color: #182c3d;
}

.btn-light {
  background: white;
  color: var(--navy);
}

.btn-teal {
  background: var(--teal);
  color: white;
}

.hero-art {
  background: #ffffff12;
  border: 1px solid #ffffff35;
  border-radius: 24px;
  padding: 28px;
}

.hero-art .big-icon {
  font-size: 76px;
  text-align: center;
  padding: 15px;
}

.mini-report {
  background: white;
  color: var(--navy);
  border-radius: 13px;
  padding: 15px;
  margin-top: 12px;
  display: flex;
  justify-content: space-between;
  gap: 10px;
}

.pill {
  display: inline-block;
  background: #e0f2f1;
  color: #087e8b;
  border-radius: 30px;
  padding: 6px 10px;
  font-size: 12px;
  font-weight: bold;
}

main {
  max-width: 1180px;
  margin: auto;
  padding: 40px 22px 70px;
}

.section-head {
  display: flex;
  justify-content: space-between;
  align-items: end;
  gap: 20px;
  margin-bottom: 22px;
}

.section-head h2 {
  font-size: 27px;
  margin-bottom: 8px;
}

.section-head p { color: var(--muted); line-height: 1.5; }

.stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
  margin-bottom: 45px;
}

.stat {
  background: white;
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 22px;
}

.stat-icon { font-size: 25px; }
.stat-number { font-size: 30px; font-weight: 900; margin: 12px 0 5px; }
.stat-label { color: var(--muted); font-size: 14px; }

.issue-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 18px;
  margin-bottom: 48px;
}

.issue-card {
  background: white;
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 22px;
  transition: transform .2s, box-shadow .2s;
}

.issue-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 28px #102a4310;
}

.issue-emoji { font-size: 34px; margin-bottom: 15px; }
.issue-card h3 { margin-bottom: 9px; }
.issue-card p { color: var(--muted); line-height: 1.5; font-size: 14px; }

.panel {
  background: white;
  border: 1px solid var(--border);
  border-radius: 18px;
  padding: 28px;
  margin-bottom: 35px;
  box-shadow: 0 5px 20px #102a4308;
}

.panel h2 { margin-bottom: 8px; }
.panel-intro { color: var(--muted); margin-bottom: 24px; line-height: 1.5; }

.form-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 18px;
}

.field { margin-bottom: 18px; }
.field.full { grid-column: 1 / -1; }

label {
  display: block;
  font-weight: bold;
  font-size: 14px;
  margin-bottom: 8px;
}

input, select, textarea {
  width: 100%;
  border: 1px solid #cbd5e1;
  border-radius: 9px;
  padding: 13px;
  background: white;
  color: var(--navy);
}

textarea { min-height: 110px; resize: vertical; }

input:focus, select:focus, textarea:focus {
  outline: 2px solid #8bd3d8;
  border-color: var(--teal);
}

.upload-box {
  background: #f6fbfc;
  border: 2px dashed #a5cbd1;
  border-radius: 13px;
  padding: 22px;
  text-align: center;
}

.upload-box p { color: var(--muted); margin-bottom: 13px; }

#preview {
  display: none;
  max-width: 100%;
  max-height: 280px;
  margin: 15px auto 0;
  border-radius: 10px;
}

.notice {
  background: #fff7e6;
  border: 1px solid #f5d69a;
  padding: 13px;
  border-radius: 9px;
  font-size: 13px;
  color: #80550a;
  line-height: 1.5;
  margin-top: 18px;
}

#success {
  display: none;
  background: #e6f7ee;
  border: 1px solid #9bd8b5;
  border-radius: 12px;
  padding: 18px;
  margin-top: 20px;
  line-height: 1.7;
  overflow-wrap: anywhere;
}

.track-row {
  display: flex;
  gap: 10px;
  margin: 18px 0;
}

.track-row input { flex: 1; }

#trackingResult { display: none; margin-top: 20px; }

.timeline {
  border-left: 3px solid #cbd5e1;
  margin: 20px 0 5px 8px;
  padding-left: 22px;
}

.timeline-step {
  position: relative;
  margin-bottom: 20px;
  color: var(--muted);
}

.timeline-step::before {
  content: "";
  position: absolute;
  left: -30px;
  top: 3px;
  width: 12px;
  height: 12px;
  background: #cbd5e1;
  border-radius: 50%;
}

.timeline-step.done { color: var(--teal); font-weight: bold; }
.timeline-step.done::before { background: var(--teal); }

.filters {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  margin: 20px 0;
}

.filters select { width: auto; min-width: 150px; }

.report-list { display: grid; gap: 14px; }

.report-item {
  border: 1px solid var(--border);
  border-radius: 13px;
  padding: 18px;
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 15px;
}

.report-item h3 { margin-bottom: 8px; }
.report-item p { color: var(--muted); line-height: 1.5; font-size: 14px; }

.report-item img {
  width: 100px;
  height: 85px;
  object-fit: cover;
  border-radius: 9px;
  margin-top: 10px;
}

.report-actions {
  display: flex;
  flex-direction: column;
  gap: 8px;
  min-width: 145px;
}

.report-actions select { padding: 9px; }

.small-btn {
  border: 0;
  border-radius: 8px;
  background: #e0f2f1;
  color: #075b63;
  padding: 10px;
  font-weight: bold;
}

.empty {
  color: var(--muted);
  padding: 25px;
  background: #f8fafc;
  border-radius: 12px;
  text-align: center;
}

footer {
  background: var(--navy);
  color: #dceaf2;
  text-align: center;
  padding: 30px 20px;
  line-height: 1.8;
}

footer strong { color: #ffd27a; }

@media(max-width: 800px) {
  .hero { grid-template-columns: 1fr; padding: 50px 7%; }
  .hero-art { max-width: 500px; }
  .issue-grid { grid-template-columns: repeat(2, 1fr); }
}

@media(max-width: 560px) {
  header { align-items: flex-start; flex-direction: column; }
  nav { gap: 13px; }
  .stats, .issue-grid, .form-grid { grid-template-columns: 1fr; }
  .field.full { grid-column: auto; }
  .panel { padding: 20px; }
  .section-head { align-items: flex-start; flex-direction: column; }
  .track-row { flex-direction: column; }
  .report-item { grid-template-columns: 1fr; }
  .report-actions { min-width: 0; }
}
</style>
</head>

<body>

<header>
  <div class="logo">Jan<span>Awaaz</span></div>
  <nav>
    <button onclick="goTo('home')">Home</button>
    <button onclick="goTo('report')">Report Issue</button>
    <button onclick="goTo('track')">Track Complaint</button>
    <button onclick="goTo('dashboard')">Dashboard</button>
  </nav>
</header>

<section class="hero" id="home">
  <div>
    <div class="eyebrow">YOUR CITY. YOUR VOICE.</div>
    <h1>Let's make our city better, together.</h1>
    <p>
      Spotted a pothole, leaking water pipe, garbage pile,
      or broken streetlight? Report it, track it, and help
      your community get heard.
    </p>
    <div class="actions">
      <button class="btn btn-primary" onclick="goTo('report')">
        + Report an Issue
      </button>
      <button class="btn btn-light" onclick="goTo('track')">
        Track a Complaint
      </button>
    </div>
  </div>

  <div class="hero-art">
    <div class="big-icon">🏙️</div>
    <div class="mini-report">
      <div>
        <strong>Community reports</strong>
        <p style="color:#64748b;margin-top:5px;font-size:13px">
          Give local issues a voice
        </p>
      </div>
      <span class="pill">Together</span>
    </div>
    <div class="mini-report">
      <strong>📍 Local issues</strong>
      <span>🔎</span>
    </div>
    <div class="mini-report">
      <strong>📋 Complaint tracking</strong>
      <span>✓</span>
    </div>
  </div>
</section>

<main>
  <section>
    <div class="section-head">
      <div>
        <h2>Our community at a glance</h2>
        <p>Reports created in this browser's demo.</p>
      </div>
    </div>
    <div class="stats">
      <div class="stat">
        <div class="stat-icon">📋</div>
        <div class="stat-number" id="totalCount">0</div>
        <div class="stat-label">Total reports</div>
      </div>
      <div class="stat">
        <div class="stat-icon">⏳</div>
        <div class="stat-number" id="pendingCount">0</div>
        <div class="stat-label">Pending reports</div>
      </div>
      <div class="stat">
        <div class="stat-icon">✅</div>
        <div class="stat-number" id="resolvedCount">0</div>
        <div class="stat-label">Marked resolved</div>
      </div>
    </div>
  </section>

  <section>
    <div class="section-head">
      <div>
        <h2>What can you report?</h2>
        <p>Choose a category to get started.</p>
      </div>
    </div>

    <div class="issue-grid">
      <div class="issue-card">
        <div class="issue-emoji">🛣️</div>
        <h3>Road damage</h3>
        <p>Potholes, broken roads, and unsafe road surfaces.</p>
      </div>
      <div class="issue-card">
        <div class="issue-emoji">💧</div>
        <h3>Water leakage</h3>
        <p>Leaking pipes, water supply problems, and wastage.</p>
      </div>
      <div class="issue-card">
        <div class="issue-emoji">🗑️</div>
        <h3>Garbage</h3>
        <p>Overflowing bins, litter, and waste collection issues.</p>
      </div>
      <div class="issue-card">
        <div class="issue-emoji">💡</div>
        <h3>Streetlights</h3>
        <p>Broken lights and dark public areas.</p>
      </div>
      <div class="issue-card">
        <div class="issue-emoji">🌧️</div>
        <h3>Drainage</h3>
        <p>Blocked drains and waterlogging.</p>
      </div>
      <div class="issue-card">
        <div class="issue-emoji">🏘️</div>
        <h3>Other civic issues</h3>
        <p>Report another problem affecting your neighborhood.</p>
      </div>
    </div>
  </section>

  <section class="panel" id="report">
    <h2>📝 Report a civic issue</h2>
    <p class="panel-intro">
      Add the details and a photo if you have one.
      Fields marked * are required.
    </p>

    <form id="issueForm">
      <div class="form-grid">
        <div class="field">
          <label for="issueType">Issue category *</label>
          <select id="issueType" required>
            <option value="">Choose category</option>
            <option>Road damage / Pothole</option>
            <option>Water leakage</option>
            <option>Garbage / Waste</option>
            <option>Broken streetlight</option>
            <option>Drainage / Waterlogging</option>
            <option>Other civic issue</option>
          </select>
        </div>

        <div class="field">
          <label for="zone">Zone *</label>
          <select id="zone" required>
            <option value="">Choose zone</option>
            <option>Zone 1</option><option>Zone 2</option>
            <option>Zone 3</option><option>Zone 4</option>
            <option>Zone 5</option><option>Zone 6</option>
            <option>Zone 7</option><option>Zone 8</option>
            <option>Zone 9</option><option>Zone 10</option>
            <option>Other / Not sure</option>
          </select>
        </div>

        <div class="field full">
          <label for="location">Location or landmark *</label>
          <input id="location" required maxlength="180"
            placeholder="e.g. Ashi Nagar, near the bus stop">
        </div>

        <div class="field full">
          <label for="description">Describe the issue *</label>
          <textarea id="description" required maxlength="1500"
            placeholder="What happened? How long has it been happening?"></textarea>
        </div>

        <div class="field full">
          <label for="photo">Upload photo (optional)</label>
          <div class="upload-box">
            <p>📷 Choose a photo of the issue (maximum 5 MB).</p>
            <input id="photo" type="file"
              accept="image/png,image/jpeg,image/webp">
            <img id="preview" alt="Selected issue photo preview">
          </div>
        </div>
      </div>

      <button class="btn btn-teal" type="submit">
        Submit demo report →
      </button>
    </form>

    <div id="success" role="status" aria-live="polite"></div>

    <div class="notice">
      Demo notice: reports are saved only in this browser.
      They are not sent to a municipal department.
      Avoid entering private or sensitive personal information.
    </div>
  </section>

  <section class="panel" id="track">
    <h2>🔎 Track your complaint</h2>
    <p class="panel-intro">
      Enter the tracking ID shown after you submit a demo report.
    </p>

    <div class="track-row">
      <input id="trackingInput" placeholder="e.g. JA-12345678">
      <button class="btn btn-teal" onclick="trackReport()">Track</button>
    </div>

    <div id="trackingResult"></div>
  </section>

  <section class="panel" id="dashboard">
    <h2>📊 Community dashboard</h2>
    <p class="panel-intro">
      View and filter demo reports. You can change their status
      to test the workflow.
    </p>

    <div class="filters">
      <select id="filterType" onchange="renderReports()">
        <option value="">All categories</option>
        <option>Road damage / Pothole</option>
        <option>Water leakage</option>
        <option>Garbage / Waste</option>
        <option>Broken streetlight</option>
        <option>Drainage / Waterlogging</option>
        <option>Other civic issue</option>
      </select>

      <select id="filterStatus" onchange="renderReports()">
        <option value="">All statuses</option>
        <option>Submitted</option>
        <option>Assigned</option>
        <option>In progress</option>
        <option>Resolved</option>
        <option>Reopened</option>
      </select>
    </div>

    <div id="reportList" class="report-list"></div>
  </section>
</main>

<footer>
  <strong>JanAwaaz</strong><br>
  Your City. Your Voice.<br>
  <span style="font-size:13px">
    A civic issue reporting and tracking prototype.
  </span>
</footer>

<script>
const STORAGE_KEY = "janawaaz_demo_reports_v1";
let reports = loadReports();
let photoData = "";

function loadReports() {
  try {
    const saved = localStorage.getItem(STORAGE_KEY);
    return saved ? JSON.parse(saved) : [];
  } catch {
    return [];
  }
}

function saveReports() {
  try {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(reports));
    return true;
  } catch {
    alert("Could not save this report in browser storage. Try a smaller photo.");
    return false;
  }
}

function goTo(id) {
  document.getElementById(id).scrollIntoView({
    behavior: "smooth",
    block: "start"
  });
}

function makeId() {
  let id;
  do {
    id = "JA-" + Math.floor(10000000 + Math.random() * 90000000);
  } while (reports.some(r => r.id === id));
  return id;
}

const photoInput = document.getElementById("photo");
const preview = document.getElementById("preview");

photoInput.addEventListener("change", function() {
  const file = this.files[0];
  photoData = "";
  preview.style.display = "none";
  preview.removeAttribute("src");

  if (!file) return;

  const allowed = ["image/jpeg", "image/png", "image/webp"];

  if (!allowed.includes(file.type)) {
    alert("Please choose a JPG, PNG, or WebP image.");
    this.value = "";
    return;
  }

  if (file.size > 5 * 1024 * 1024) {
    alert("Please choose an image smaller than 5 MB.");
    this.value = "";
    return;
  }

  const reader = new FileReader();

  reader.onload = function() {
    photoData = reader.result;
    preview.src = photoData;
    preview.style.display = "block";
  };

  reader.onerror = function() {
    alert("Could not read that image. Please try another.");
    photoData = "";
    photoInput.value = "";
  };

  reader.readAsDataURL(file);
});

document.getElementById("issueForm").addEventListener("submit", function(event) {
  event.preventDefault();

  const report = {
    id: makeId(),
    type: document.getElementById("issueType").value,
    zone: document.getElementById("zone").value,
    location: document.getElementById("location").value.trim(),
    description: document.getElementById("description").value.trim(),
    status: "Submitted",
    department: "Not assigned",
    photo: photoData,
    createdAt: new Date().toLocaleString()
  };

  reports.unshift(report);

  if (!saveReports()) {
    reports.shift();
    return;
  }

  const success = document.getElementById("success");
  success.replaceChildren();

  const heading = document.createElement("h3");
  heading.textContent = "🎉 Demo report created!";

  const idLine = document.createElement("p");
  idLine.textContent = "Tracking ID: " + report.id;

  const detail = document.createElement("p");
  detail.textContent = report.type + " · " + report.zone;

  const note = document.createElement("p");
  note.textContent =
    "Save your tracking ID. This report is stored only in this browser; it has not been sent to officials.";

  const trackButton = document.createElement("button");
  trackButton.className = "btn btn-teal";
  trackButton.textContent = "Track this report";
  trackButton.style.marginTop = "12px";
  trackButton.onclick = function() {
    document.getElementById("trackingInput").value = report.id;
    trackReport();
    goTo("track");
  };

  success.append(heading, idLine, detail, note, trackButton);
  success.style.display = "block";

  this.reset();
  photoData = "";
  preview.style.display = "none";
  preview.removeAttribute("src");

  updateStats();
  renderReports();
  success.scrollIntoView({ behavior: "smooth", block: "center" });
});

function updateStats() {
  document.getElementById("totalCount").textContent = reports.length;
  document.getElementById("pendingCount").textContent =
    reports.filter(r => r.status !== "Resolved").length;
  document.getElementById("resolvedCount").textContent =
    reports.filter(r => r.status === "Resolved").length;
}

function trackReport() {
  const id = document.getElementById("trackingInput").value.trim().toUpperCase();
  const result = document.getElementById("trackingResult");
  result.replaceChildren();
  result.style.display = "block";

  const report = reports.find(r => r.id === id);

  if (!report) {
    const message = document.createElement("p");
    message.className = "empty";
    message.textContent = "No matching report found in this browser. Check the ID or submit a demo report first.";
    result.append(message);
    return;
  }

  const title = document.createElement("h3");
  title.textContent = "Report " + report.id;

  const details = document.createElement("p");
  details.textContent = report.type + " · " + report.location;

  const status = document.createElement("p");
  status.style.marginTop = "10px";
  status.textContent = "Current status: " + report.status;

  const timeline = document.createElement("div");
  timeline.className = "timeline";

  const stages = ["Submitted", "Assigned", "In progress", "Resolved"];
  const currentIndex = stages.indexOf(report.status);

  stages.forEach((stage, index) => {
    const item = document.createElement("div");
    item.className = "timeline-step" +
      (currentIndex >= index ? " done" : "");
    item.textContent = stage;
    timeline.append(item);
  });

  result.append(title, details, status, timeline);

  if (report.status === "Resolved") {
    const confirm = document.createElement("p");
    confirm.textContent =
      "Demo: The report is marked resolved. In a real system, citizens would be able to confirm or dispute the closure.";
    result.append(confirm);
  }
}

function renderReports() {
  const list = document.getElementById("reportList");
  list.replaceChildren();

  const type = document.getElementById("filterType").value;
  const status = document.getElementById("filterStatus").value;

  const filtered = reports.filter(report =>
    (!type || report.type === type) &&
    (!status || report.status === status)
  );

  if (filtered.length === 0) {
    const empty = document.createElement("div");
    empty.className = "empty";
    empty.textContent = reports.length === 0
      ? "No demo reports yet. Submit one above to see it here!"
      : "No reports match these filters.";
    list.append(empty);
    updateStats();
    return;
  }

  filtered.forEach(report => {
    const card = document.createElement("article");
    card.className = "report-item";

    const info = document.createElement("div");

    const title = document.createElement("h3");
    title.textContent = report.type;

    const id = document.createElement("p");
    id.textContent = report.id + " · " + report.createdAt;

    const location = document.createElement("p");
    location.textContent = "📍 " + report.location + " · " + report.zone;

    const desc = document.createElement("p");
    desc.textContent = report.description;

    const dept = document.createElement("p");
    dept.textContent = "Department: " + report.department;

    info.append(title, id, location, desc, dept);

    if (report.photo) {
      const image = document.createElement("img");
      image.src = report.photo;
      image.alt = "Issue photo";
      info.append(image);
    }

    const actions = document.createElement("div");
    actions.className = "report-actions";

    const statusSelect = document.createElement("select");
    ["Submitted", "Assigned", "In progress", "Resolved", "Reopened"]
      .forEach(value => {
        const option = document.createElement("option");
        option.value = value;
        option.textContent = value;
        option.selected = report.status === value;
        statusSelect.append(option);
      });

    statusSelect.setAttribute("aria-label", "Change report status");

    statusSelect.addEventListener("change", function() {
      report.status = this.value;
      saveReports();
      updateStats();
      renderReports();
    });

    const deptSelect = document.createElement("select");
    deptSelect.setAttribute("aria-label", "Assign department");

    [
      "Not assigned",
      "Municipal Corporation",
      "Water Department",
      "Roads Department",
      "Waste Management",
      "Streetlight Department",
      "Drainage Department"
    ].forEach(value => {
      const option = document.createElement("option");
      option.value = value;
      option.textContent = value;
      option.selected = report.department === value;
      deptSelect.append(option);
    });

    deptSelect.addEventListener("change", function() {
      report.department = this.value;
      if (this.value !== "Not assigned" && report.status === "Submitted") {
        report.status = "Assigned";
      }
      saveReports();
      updateStats();
      renderReports();
    });

    const trackBtn = document.createElement("button");
    trackBtn.className = "small-btn";
    trackBtn.textContent = "View tracking";
    trackBtn.onclick = function() {
      document.getElementById("trackingInput").value = report.id;
      trackReport();
      goTo("track");
    };

    actions.append(statusSelect, deptSelect, trackBtn);
    card.append(info, actions);
    list.append(card);
  });

  updateStats();
}

updateStats();
renderReports();
</script>

</body>
</html>
