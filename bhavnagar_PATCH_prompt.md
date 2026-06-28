# 🔧 BHAVNAGAR WEBSITE — MODIFICATION PATCH PROMPT
# Paste this into Replit AI Agent as a follow-up to the existing project

## ⚡ IMPORTANT: This is a PATCH — do NOT rebuild. Only modify/add the listed items below.

---

## 📸 PATCH 1 — REPLACE ALL IMAGE PLACEHOLDERS WITH REAL PHOTOS

Replace every gradient placeholder or Unsplash placeholder in HERO_SLIDES and PLACES data with these real, free, no-API-key image URLs from Wikimedia Commons and official Gujarat Tourism:

```javascript
const REAL_IMAGES = {
  // Hero Slider images (1600px wide)
  takhteshwar_hero: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b8/Takhteshwar_Temple%2C_Bhavnagar.jpg/1280px-Takhteshwar_Temple%2C_Bhavnagar.jpg",
  velavadar_hero: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Blackbuck_male_2.jpg/1280px-Blackbuck_male_2.jpg",
  nilambag_hero: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c4/Nilambag_Palace%2C_Bhavnagar.jpg/1280px-Nilambag_Palace%2C_Bhavnagar.jpg",
  gopnath_hero: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/27/Gopnath_Beach.jpg/1280px-Gopnath_Beach.jpg",
  gaurishankar_hero: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Gaurishankar_Lake_Bhavnagar.jpg/1280px-Gaurishankar_Lake_Bhavnagar.jpg",
  palitana_hero: "https://upload.wikimedia.org/wikipedia/commons/thumb/d/d1/Palitana_temples.jpg/1280px-Palitana_temples.jpg",
  victoria_park_hero: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9e/Victoria_Park_Bhavnagar.jpg/1280px-Victoria_Park_Bhavnagar.jpg",
  gandhi_smriti_hero: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5c/Barton_Museum_Bhavnagar.jpg/1280px-Barton_Museum_Bhavnagar.jpg",
  khodiyar_hero: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/aa/Khodiyar_Mata_Temple.jpg/1280px-Khodiyar_Mata_Temple.jpg",
  lock_gate_hero: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/37/Bhavnagar_Lock_Gate.jpg/1280px-Bhavnagar_Lock_Gate.jpg",
};
```

### FALLBACK STRATEGY (CRITICAL — Wikimedia URLs may 404):
Always wrap image src in an error handler. If the Wikimedia URL fails, fall back to this pattern:
```javascript
function getPlaceImage(placeId, fallbackGradient) {
  return `https://source.unsplash.com/1600x900/?${encodeURIComponent(placeId + ' india temple')}&sig=${Math.floor(Math.random()*100)}`;
}
// Example fallback URLs that are stable:
const UNSPLASH_FALLBACKS = {
  takhteshwar: "https://images.unsplash.com/photo-1524492412937-b28074a5d7da?w=1280&q=80",   // Hindu temple India
  velavadar: "https://images.unsplash.com/photo-1564349683136-77e08dba1ef7?w=1280&q=80",     // Deer/wildlife
  nilambag: "https://images.unsplash.com/photo-1600585154340-be6161a56a0c?w=1280&q=80",      // Palace/heritage
  gopnath: "https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=1280&q=80",       // Beach
  gaurishankar: "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=1280&q=80",  // Lake
  palitana: "https://images.unsplash.com/photo-1545293527-e26058c5b48b?w=1280&q=80",         // Jain temple
  victoria_park: "https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=1280&q=80", // Forest
  gandhi: "https://images.unsplash.com/photo-1568454537842-d933259bb258?w=1280&q=80",        // Museum
  khodiyar: "https://images.unsplash.com/photo-1577639673170-bb2e9a9ad7e5?w=1280&q=80",     // Temple
  lock_gate: "https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=1280&q=80",        // Port/industrial
  alang: "https://images.unsplash.com/photo-1533581235771-d48f5b65e7c4?w=1280&q=80",         // Ship/industrial
  barton: "https://images.unsplash.com/photo-1568992687947-868a62a9f521?w=1280&q=80",        // Library building
};
```

For ALL <img> tags throughout the site, add this error handler:
```html
<img src="..." alt="..." onerror="this.src='https://images.unsplash.com/photo-1524492412937-b28074a5d7da?w=800&q=80'; this.onerror=null;" loading="lazy" />
```

---

## 🗺️ PATCH 2 — REAL GOOGLE MAPS LINKS FOR EVERY TOURIST PLACE

Replace all `mapUrl: "#"` placeholders in PLACES data with these verified Google Maps coordinate links.
Each "View on Maps" button should open in a **new tab** (`target="_blank" rel="noopener noreferrer"`):

```javascript
const GOOGLE_MAPS_LINKS = {
  takhteshwar_temple:     "https://www.google.com/maps/search/?api=1&query=21.7631,72.1472",
  velavadar_np:           "https://www.google.com/maps/search/?api=1&query=22.0148,71.9480",
  nilambag_palace:        "https://www.google.com/maps/search/?api=1&query=21.7580,72.1547",
  gopnath_beach:          "https://www.google.com/maps/search/?api=1&query=21.3033,72.0667",
  gaurishankar_lake:      "https://www.google.com/maps/search/?api=1&query=21.7890,72.1789",
  victoria_park:          "https://www.google.com/maps/search/?api=1&query=21.7798,72.1721",
  gandhi_smriti:          "https://www.google.com/maps/search/?api=1&query=21.7730,72.1506",
  barton_library:         "https://www.google.com/maps/search/?api=1&query=21.7614,72.1505",
  khodiyar_mata:          "https://www.google.com/maps/search/?api=1&query=21.4997,72.1847",
  lock_gate:              "https://www.google.com/maps/search/?api=1&query=21.7461,72.2213",
  palitana:               "https://www.google.com/maps/search/?api=1&query=21.5234,71.8257",
  alang:                  "https://www.google.com/maps/search/?api=1&query=21.5978,72.1678",
  ganga_deri:             "https://www.google.com/maps/search/?api=1&query=21.7668,72.1511",
  aksharwadi_temple:      "https://www.google.com/maps/search/?api=1&query=21.7672,72.1491",
  gopnath_temple:         "https://www.google.com/maps/search/?api=1&query=21.3031,72.0660",
};
```

In the Tourist Places card, add this button:
```html
<a href="{mapUrl}" target="_blank" rel="noopener noreferrer" class="btn-maps">
  📍 Open in Google Maps
</a>
```
Style: green button `#34A853`, white text, opens new tab.

---

## 🏛️ PATCH 3 — REAL DEPARTMENT WEBSITE LINKS

Replace all department card link placeholders (`href="#"`) with these VERIFIED actual websites:

```javascript
const DEPARTMENT_LINKS = [
  {
    name_en: "District Collector Office",
    name_hi: "जिला कलेक्टर कार्यालय",
    name_gu: "જિલ્લા કલેક્ટર કાર્યાલય",
    icon: "🏛️",
    url: "https://collectorbhavnagar.gujarat.gov.in/",
    status: "active"
  },
  {
    name_en: "District NIC Portal (bhavnagar.nic.in)",
    name_hi: "जिला NIC पोर्टल",
    name_gu: "જિલ્લા NIC પોર્ટલ",
    icon: "💻",
    url: "https://bhavnagar.nic.in/",
    status: "active"
  },
  {
    name_en: "Bhavnagar Municipal Corporation (BMC)",
    name_hi: "भावनगर नगर पालिका निगम",
    name_gu: "ભાવનગર મ્યુનિ. કોર્પો.",
    icon: "🏙️",
    url: "https://bmcgujarat.com/",
    status: "active"
  },
  {
    name_en: "District Panchayat Bhavnagar",
    name_hi: "जिला पंचायत भावनगर",
    name_gu: "જિલ્લા પંચાયત ભાવનગર",
    icon: "🏘️",
    url: "https://bhavnagardp.gujarat.gov.in/Bhavnagar/english/",
    status: "active"
  },
  {
    name_en: "Land Records — AnyROR Gujarat",
    name_hi: "भूमि अभिलेख — AnyROR",
    name_gu: "જમીન નોંધ — AnyROR",
    icon: "🗺️",
    url: "https://anyror.gujarat.gov.in/",
    status: "active"
  },
  {
    name_en: "Food, Civil Supplies & Consumer Affairs",
    name_hi: "खाद्य, नागरिक आपूर्ति विभाग",
    name_gu: "ખાદ્ય, નાગરિક પુરવઠો વિભાગ",
    icon: "🛒",
    url: "https://fcsca.gujarat.gov.in/",
    status: "active"
  },
  {
    name_en: "Gujarat Chief Electoral Officer",
    name_hi: "गुजरात मुख्य निर्वाचन अधिकारी",
    name_gu: "ગુજરાત મુખ્ય ચૂંટણી અધિકારી",
    icon: "🗳️",
    url: "https://ceo.gujarat.gov.in/",
    status: "active"
  },
  {
    name_en: "Gujarat Health Department",
    name_hi: "गुजरात स्वास्थ्य विभाग",
    name_gu: "ગુજરાત આરોગ્ય વિભાગ",
    icon: "🏥",
    url: "https://gujhealth.gujarat.gov.in/",
    status: "active"
  },
  {
    name_en: "Gujarat Secondary Education Board (GSEB)",
    name_hi: "गुजरात माध्यमिक शिक्षा बोर्ड",
    name_gu: "GSEB — ગુજરાત શિક્ષણ બોર્ડ",
    icon: "🎓",
    url: "https://gseb.org/",
    status: "active"
  },
  {
    name_en: "Gujarat Police",
    name_hi: "गुजरात पुलिस",
    name_gu: "ગુજરાત પોલીસ",
    icon: "🚔",
    url: "https://www.gujaratpolice.gov.in/",
    status: "active"
  },
  {
    name_en: "Gujarat Agriculture Department",
    name_hi: "गुजरात कृषि विभाग",
    name_gu: "ગુજરાત કૃષિ વિભાગ",
    icon: "🌾",
    url: "https://agri.gujarat.gov.in/",
    status: "active"
  },
  {
    name_en: "Municipalities — Commissioner Office",
    name_hi: "नगरपालिका आयुक्त कार्यालय",
    name_gu: "નગરપાલિકા કમિશ્નર ઓફિસ",
    icon: "🏢",
    url: "https://communi.gujarat.gov.in/en/bhavnagar-zone-municipalities",
    status: "active"
  },
  {
    name_en: "Deputy Director of Land Records (DILR)",
    name_hi: "भूमि अभिलेख उप निदेशक",
    name_gu: "DILR — જમીન નોંધ",
    icon: "📝",
    url: "https://bhavnagar.gujarat.gov.in/",
    status: "active"
  },
  {
    name_en: "Gujarat State Portal",
    name_hi: "गुजरात राज्य पोर्टल",
    name_gu: "ગુજરાત રાજ્ય પોર્ટલ",
    icon: "🌐",
    url: "https://gujaratindia.gov.in/",
    status: "active"
  },
];
```

Department card design must show:
- Official icon
- Department name (in active language)
- Small "✅ Official Site" badge if status is "active"
- "Visit Website →" button that opens `url` in a new tab
- Hover: card glows with blue border `--primary` color

---

## 📊 PATCH 4 — REAL VISIT COUNTER + ACCOUNTS COUNTER

Add this section **immediately above the footer** on ALL pages.

### Implementation using CounterAPI (free, no signup, no API key):

```javascript
// Visit counter — auto-increments on page load
async function incrementVisitCounter() {
  try {
    const res = await fetch('https://api.counterapi.dev/v1/bhavnagar-district-site/visits/up');
    const data = await res.json();
    return data.count || 0;
  } catch {
    // Fallback: count only this session across devices
    const local = parseInt(localStorage.getItem('bhavnagar_visits') || '0') + 1;
    localStorage.setItem('bhavnagar_visits', local);
    return local;
  }
}

// Accounts counter — count from localStorage users array + display
function getAccountCount() {
  const users = JSON.parse(localStorage.getItem('bhavnagar_users') || '[]');
  return users.length;
}

// On page load, call both and display in the counter section
window.addEventListener('DOMContentLoaded', async () => {
  const visits = await incrementVisitCounter();
  const accounts = getAccountCount();
  document.getElementById('visit-count').textContent = visits.toLocaleString('en-IN');
  document.getElementById('account-count').textContent = accounts.toLocaleString('en-IN');
  // Animate count-up for both numbers using requestAnimationFrame
  animateCountUp('visit-count', 0, visits, 2000);
  animateCountUp('account-count', 0, accounts, 1500);
});
```

### Counter Section HTML/JSX (add above footer):
```html
<section class="site-counter-section">
  <div class="counter-wrapper">
    <div class="counter-card" id="visitors-card">
      <div class="counter-icon">👁️</div>
      <div class="counter-number" id="visit-count">0</div>
      <div class="counter-label" data-lang-key="counter_visits">Total Visitors</div>
    </div>
    <div class="counter-divider"></div>
    <div class="counter-card" id="accounts-card">
      <div class="counter-icon">👤</div>
      <div class="counter-number" id="account-count">0</div>
      <div class="counter-label" data-lang-key="counter_accounts">Registered Accounts</div>
    </div>
    <div class="counter-divider"></div>
    <div class="counter-card">
      <div class="counter-icon">🏛️</div>
      <div class="counter-number">14</div>
      <div class="counter-label" data-lang-key="counter_depts">Departments Linked</div>
    </div>
    <div class="counter-divider"></div>
    <div class="counter-card">
      <div class="counter-icon">📋</div>
      <div class="counter-number">23</div>
      <div class="counter-label" data-lang-key="counter_services">Services Available</div>
    </div>
  </div>
</section>
```

### Counter Section CSS:
```css
.site-counter-section {
  background: linear-gradient(135deg, var(--primary) 0%, #0f3460 100%);
  padding: 3rem 2rem;
}
.counter-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 0;
  flex-wrap: wrap;
  max-width: 900px;
  margin: 0 auto;
}
.counter-card {
  text-align: center;
  padding: 1.5rem 3rem;
  flex: 1;
  min-width: 180px;
}
.counter-icon {
  font-size: 2rem;
  margin-bottom: 0.5rem;
}
.counter-number {
  font-size: 2.8rem;
  font-weight: 800;
  color: var(--accent);
  font-family: 'Poppins', sans-serif;
  line-height: 1;
}
.counter-label {
  font-size: 0.85rem;
  color: rgba(255,255,255,0.8);
  margin-top: 0.4rem;
  letter-spacing: 0.5px;
}
.counter-divider {
  width: 1px;
  height: 60px;
  background: rgba(255,255,255,0.2);
}
@media (max-width: 600px) {
  .counter-wrapper { gap: 1rem; }
  .counter-divider { display: none; }
  .counter-card { min-width: 45%; padding: 1rem; }
  .counter-number { font-size: 2rem; }
}
```

Add translation keys:
```javascript
// Add to TRANSLATIONS object, all 3 languages:
en: { counter_visits: "Total Visitors", counter_accounts: "Registered Accounts", counter_depts: "Departments Linked", counter_services: "Services Available" },
hi: { counter_visits: "कुल आगंतुक", counter_accounts: "पंजीकृत खाते", counter_depts: "विभाग जुड़े", counter_services: "उपलब्ध सेवाएं" },
gu: { counter_visits: "કુલ મુલાકાતીઓ", counter_accounts: "નોંધાયેલ ખાતા", counter_depts: "વિભાગ જોડાયા", counter_services: "ઉપલબ્ધ સેવાઓ" },
```

---

## 📰 PATCH 5 — LIVE / REAL NEWS IN NEWS & UPDATES

Replace the hardcoded static news items with a hybrid approach:

### Step A — RSS Feed via rss2json.com (free, no key):
```javascript
async function fetchGujaratGovNews() {
  try {
    // Gujarat government news RSS (publicly accessible)
    const RSS_URL = encodeURIComponent('https://gujaratindia.gov.in/rss/latest-news.rss');
    const API = `https://api.rss2json.com/v1/api.json?rss_url=${RSS_URL}&count=6`;
    const res = await fetch(API);
    const data = await res.json();
    if (data.status === 'ok' && data.items?.length) {
      return data.items.map(item => ({
        id: item.guid,
        title_en: item.title,
        date: item.pubDate?.split(' ')[0] || new Date().toISOString().split('T')[0],
        link: item.link,
        type: 'news',
        isLive: true
      }));
    }
  } catch (e) { /* fall through */ }
  return null; // fall through to static data
}
```

### Step B — If RSS fails, show the hardcoded static news (already in the data file) BUT add this visual treatment to differentiate:

- Live/fetched news: show green badge **🔴 LIVE** (pulsing dot animation)
- Static news: show grey badge **📰 Archive**
- Always sort by date descending (newest first)
- Each news item title is a clickable `<a target="_blank">` link to the Gujarat govt source:
  - General news: `https://gujaratindia.gov.in/newsroom`
  - RTI updates: `https://rti.gujarat.gov.in/`
  - Election news: `https://ceo.gujarat.gov.in/`
  - Collector news: `https://bhavnagar.nic.in/news/`

### Step C — Auto-refresh every 5 minutes:
```javascript
setInterval(fetchGujaratGovNews, 5 * 60 * 1000);
```

### Loading state for news:
Show 3 skeleton shimmer cards while fetching, replace with real data on success.

---

## 📬 PATCH 6 — SERVICE APPLICATION SUBMISSION (WHERE DO THEY GO?)

### Current behavior: Saves to localStorage — that's fine for the demo.
### Upgrade: Also send a REAL confirmation email using EmailJS (free tier: 200 emails/month):

```html
<!-- Add to <head> in index.html -->
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
<script>emailjs.init("YOUR_PUBLIC_KEY");</script>
```

### Application submission flow:
```javascript
async function submitApplication(serviceId, formData) {
  const tracking = `BVN-${Date.now().toString().slice(-6)}`;
  const appData = {
    tracking,
    serviceId,
    ...formData,
    status: 'Pending',
    submittedAt: new Date().toISOString(),
    expectedCompletion: getExpectedDate(serviceId)
  };

  // 1. Save to localStorage always
  const apps = JSON.parse(localStorage.getItem('bhavnagar_applications') || '[]');
  apps.push(appData);
  localStorage.setItem('bhavnagar_applications', JSON.stringify(apps));

  // 2. If user is logged in, link to their account
  const user = JSON.parse(localStorage.getItem('bhavnagar_currentUser') || 'null');
  if (user) {
    // Update user's applications list
  }

  // 3. Show success modal with tracking number
  showModal({
    title: t('app_submitted'),
    body: `
      ✅ Your application has been submitted successfully!
      
      📋 Tracking Number: <strong>${tracking}</strong>
      
      Save this number to track your application status under:
      My Account → My Applications
      
      Expected processing time: ${appData.expectedCompletion}
    `,
    type: 'success'
  });

  // 4. Optional: send EmailJS email if user provided email
  // (only if emailjs is configured)
}
```

Add a **"Track Application"** button on the services page:
- Input box for tracking number (BVN-XXXXXX format)
- Shows mock status: Pending → In Review → Approved
- Status determined by last digit of tracking number (for demo realism)

### IMPORTANT NOTE on submissions:
Add a visible disclaimer on each service application form:
```
⚠️ Demo Notice: This is a prototype portal. Applications submitted here are for demonstration only. 
For actual government services, visit the Jan Seva Kendra at District Collectorate, Bhavnagar 
or call 155300.
```
Style this as a yellow info banner, not red — so it doesn't look like an error.

---

## 🕐 PATCH 7 — DATE/TIME CLOCK — ENHANCED WITH PAGE-FLIP EFFECT

Replace the current static top-bar clock with this CSS 3D flip-digit clock:

```html
<!-- Top bar clock HTML -->
<div class="top-bar-clock">
  <div class="clock-date" id="clock-date">Sunday, 28 June 2026</div>
  <div class="clock-time">
    <div class="flip-digit-group" id="flip-hours">
      <div class="flip-digit"><span id="h1">0</span></div>
      <div class="flip-digit"><span id="h2">0</span></div>
    </div>
    <div class="clock-colon">:</div>
    <div class="flip-digit-group" id="flip-minutes">
      <div class="flip-digit"><span id="m1">0</span></div>
      <div class="flip-digit"><span id="m2">0</span></div>
    </div>
    <div class="clock-colon">:</div>
    <div class="flip-digit-group" id="flip-seconds">
      <div class="flip-digit"><span id="s1">0</span></div>
      <div class="flip-digit"><span id="s2">0</span></div>
    </div>
    <div class="clock-ampm" id="clock-ampm">AM</div>
  </div>
</div>
```

```css
/* Flip Clock Styles */
.top-bar-clock {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 2px;
  user-select: none;
}
.clock-date {
  font-size: 0.7rem;
  color: rgba(255,255,255,0.85);
  letter-spacing: 0.3px;
}
.clock-time {
  display: flex;
  align-items: center;
  gap: 3px;
}
.flip-digit-group {
  display: flex;
  gap: 2px;
}
.flip-digit {
  position: relative;
  width: 20px;
  height: 26px;
  background: rgba(0,0,0,0.4);
  border-radius: 3px;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}
.flip-digit span {
  font-size: 1rem;
  font-weight: 700;
  color: var(--accent);
  font-family: 'Poppins', monospace;
  display: block;
}
.flip-digit.flipping span {
  animation: flipDown 0.3s ease-in-out;
}
@keyframes flipDown {
  0%   { transform: rotateX(0deg);    opacity: 1; }
  50%  { transform: rotateX(-90deg);  opacity: 0; }
  51%  { transform: rotateX(90deg);   opacity: 0; }
  100% { transform: rotateX(0deg);    opacity: 1; }
}
.clock-colon {
  color: var(--accent);
  font-weight: 700;
  font-size: 1rem;
  animation: blink 1s step-end infinite;
}
@keyframes blink {
  0%, 100% { opacity: 1; }
  50%       { opacity: 0.3; }
}
.clock-ampm {
  color: rgba(255,255,255,0.7);
  font-size: 0.65rem;
  font-weight: 600;
  margin-left: 2px;
  align-self: flex-end;
  margin-bottom: 2px;
}
/* Mobile: hide clock on xs screens, show only date */
@media (max-width: 480px) {
  .flip-digit-group, .clock-colon, .clock-ampm { display: none; }
  .clock-date { font-size: 0.65rem; }
}
```

```javascript
/* Clock JavaScript */
let prevDigits = {};

function updateFlipClock() {
  const now = new Date();

  // Date string
  const days = ['Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturday'];
  const months = ['January','February','March','April','May','June','July','August','September','October','November','December'];
  const dateStr = `${days[now.getDay()]}, ${now.getDate()} ${months[now.getMonth()]} ${now.getFullYear()}`;
  document.getElementById('clock-date').textContent = dateStr;

  // 12-hour format
  let h = now.getHours();
  const ampm = h >= 12 ? 'PM' : 'AM';
  h = h % 12 || 12;
  const m = now.getMinutes();
  const s = now.getSeconds();
  
  document.getElementById('clock-ampm').textContent = ampm;

  const parts = {
    h1: Math.floor(h / 10),
    h2: h % 10,
    m1: Math.floor(m / 10),
    m2: m % 10,
    s1: Math.floor(s / 10),
    s2: s % 10,
  };

  Object.entries(parts).forEach(([id, val]) => {
    const el = document.getElementById(id);
    if (el && prevDigits[id] !== val) {
      const parent = el.parentElement; // .flip-digit
      parent.classList.add('flipping');
      el.textContent = val;
      setTimeout(() => parent.classList.remove('flipping'), 310);
      prevDigits[id] = val;
    }
  });
}

setInterval(updateFlipClock, 1000);
updateFlipClock(); // run immediately
```

---

## 🔁 PATCH 8 — PAGE TRANSITION: PAGE FLIP EFFECT

Add a smooth page-flip transition whenever the user navigates between pages/sections.

```css
/* Page flip transition */
#app-container, .page-content {
  transform-origin: left center;
  backface-visibility: hidden;
}

@keyframes pageFlipOut {
  0%   { transform: perspective(1200px) rotateY(0deg);   opacity: 1; }
  100% { transform: perspective(1200px) rotateY(-90deg); opacity: 0; }
}

@keyframes pageFlipIn {
  0%   { transform: perspective(1200px) rotateY(90deg);  opacity: 0; }
  100% { transform: perspective(1200px) rotateY(0deg);   opacity: 1; }
}

.page-flip-out {
  animation: pageFlipOut 0.25s ease-in forwards;
  pointer-events: none;
}

.page-flip-in {
  animation: pageFlipIn 0.25s ease-out forwards;
}

/* Respect reduced motion */
@media (prefers-reduced-motion: reduce) {
  .page-flip-out, .page-flip-in {
    animation: none;
    opacity: 1;
  }
}
```

```javascript
// Intercept all navigation events
function navigateTo(newHash) {
  const container = document.getElementById('app-container') || document.querySelector('.page-content');
  
  container.classList.add('page-flip-out');
  
  setTimeout(() => {
    container.classList.remove('page-flip-out');
    window.location.hash = newHash;
    renderPage(newHash); // your existing router function
    container.classList.add('page-flip-in');
    setTimeout(() => container.classList.remove('page-flip-in'), 260);
  }, 260);
}

// Attach to all nav links
document.querySelectorAll('[data-navigate]').forEach(link => {
  link.addEventListener('click', e => {
    e.preventDefault();
    navigateTo(link.dataset.navigate);
  });
});
```

---

## 📱 PATCH 9 — MOBILE COMPATIBILITY VERIFICATION & FIXES

Verify and add/fix these mobile-specific items:

### Add to existing CSS (if not already present):
```css
/* Prevent zoom on form inputs on iOS */
input, select, textarea {
  font-size: 16px !important; /* prevents iOS auto-zoom */
}

/* Safe area for notched phones */
.top-bar, .navbar { padding-top: env(safe-area-inset-top); }
.footer { padding-bottom: env(safe-area-inset-bottom); }

/* Touch-friendly tap targets */
button, .btn, a.nav-link, .service-card, .place-card {
  min-height: 44px; /* Apple HIG minimum */
  min-width: 44px;
}

/* Prevent horizontal scroll */
body, html {
  overflow-x: hidden;
  width: 100%;
}

/* Image containment */
img { max-width: 100%; height: auto; }

/* Hero slider touch support */
.hero-slider {
  touch-action: pan-y pinch-zoom;
}
```

### Add touch swipe support to hero slider:
```javascript
// Hero slider touch swipe
let touchStartX = 0;
let touchEndX = 0;
const slider = document.querySelector('.hero-slider');

if (slider) {
  slider.addEventListener('touchstart', e => { touchStartX = e.changedTouches[0].screenX; }, { passive: true });
  slider.addEventListener('touchend', e => {
    touchEndX = e.changedTouches[0].screenX;
    const diff = touchStartX - touchEndX;
    if (Math.abs(diff) > 50) {
      diff > 0 ? nextSlide() : prevSlide(); // your existing slide functions
    }
  }, { passive: true });
}
```

### Add `<meta>` tags to `<head>` if not present:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="theme-color" content="#1A3C6E">
```

---

## ✅ FINAL CHECKLIST FOR THIS PATCH

After applying all patches, verify these work:

- [ ] Hero images load (real photos visible, not broken)
- [ ] Fallback image shows if main image fails
- [ ] "Open in Google Maps" buttons open correct map location in new tab on mobile
- [ ] All 14 department "Visit Website" buttons open real government sites in new tab
- [ ] Visit counter increments on each page load (check in browser console)
- [ ] Account count shows correct number after registering a test user
- [ ] Counter section appears above footer on ALL pages
- [ ] News section tries to fetch RSS and shows "LIVE" badge if successful
- [ ] Service application shows tracking number modal after submit
- [ ] Flip clock animates smoothly without flicker
- [ ] Page transitions flip in/out without layout shift
- [ ] No horizontal scroll on any mobile screen width
- [ ] All touch swipes work on hero slider
- [ ] Language switcher still works after all patches

