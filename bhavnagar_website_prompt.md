# 🏛️ BHAVNAGAR DISTRICT — CITY SERVICES WEBSITE (REPLIT BUILD PROMPT)

## 🎯 PROJECT OVERVIEW

Build a complete, fully functional, visually stunning **Bhavnagar District City Services Website** — inspired by `https://bhavnagar.nic.in/` but massively upgraded with animations, modern design, multi-language support, user accounts, settings panel, theme switching, and zero-database architecture. Everything must run entirely client-side using **localStorage** for persistence.

**Tech Stack:**
- **React 18 + Vite** (preferred) OR **Single-file HTML/CSS/Vanilla JS** if Vite is unavailable
- **CSS3 Animations + Keyframes** for all transitions (NO external animation libraries needed)
- **Google Fonts** — load: `Noto Sans`, `Noto Sans Gujarati`, `Noto Sans Devanagari`, `Poppins`
- **localStorage only** — zero backend, zero database, zero API keys required
- **Weather** — use `Open-Meteo` free API (no API key needed): `https://api.open-meteo.com/v1/forecast`
  - For location lookup, use: `https://geocoding-api.open-meteo.com/v1/search`
  - Both are free, no key required

---

## 🗂️ PAGE STRUCTURE / ROUTES

Build these pages/sections (SPA with hash-router or React Router):

1. **Home** (`/` or `#home`)
2. **Services** (`#services`)
3. **Tourist Guide / Places** (`#places`)
4. **Departments** (`#departments`)
5. **Helpline** (`#helpline`)
6. **News & Updates** (`#news`)
7. **Land Records** (`#land-records`)
8. **Certificates** (`#certificates`)
9. **Public Grievance** (`#grievance`)
10. **RTI — Right to Information** (`#rti`)
11. **About Bhavnagar** (`#about`)
12. **Contact** (`#contact`)
13. **Login Page** (`#login`)
14. **Register Page** (`#register`)
15. **User Dashboard** (`#dashboard`) — visible only after login
16. **Settings Page** (`#settings`)

---

## 🌐 MULTI-LANGUAGE SYSTEM

### Languages Supported
- **English** (default)
- **Hindi** (हिन्दी)
- **Gujarati** (ગુજરાતી)

### Language Selection Flow
1. **On first visit:** Show a full-screen beautiful **Language Welcome Modal** with the Bhavnagar emblem/seal graphic (SVG), and three large buttons — English, हिन्दी, ગુજરાતી. This choice is saved in `localStorage` key `"bhavnagar_lang"`.
2. **After selection:** Modal slides away with a fade, website loads in chosen language.
3. **On every page:** Show a small **Language Switcher** in the navbar — a globe icon 🌐 with dropdown for EN / HI / GU. Switching updates all visible text instantly without reload.
4. **Mobile:** Language switcher appears as an icon button in the top bar, tapping it opens a bottom sheet.

### Translation Keys (implement these in a `translations.js` object with `en`, `hi`, `gu` keys)

```javascript
const TRANSLATIONS = {
  en: {
    siteName: "District Bhavnagar",
    tagline: "Government of Gujarat | Education City | India",
    nav_home: "Home",
    nav_services: "Services",
    nav_tourist: "Tourist Guide",
    nav_departments: "Departments",
    nav_helpline: "Helpline",
    nav_news: "News & Updates",
    nav_about: "About",
    nav_contact: "Contact",
    nav_login: "Login",
    nav_register: "Register",
    nav_logout: "Logout",
    nav_dashboard: "My Account",
    nav_settings: "Settings",
    hero_title: "Welcome to Bhavnagar District",
    hero_subtitle: "Serving 24,10,211 Citizens with Excellence",
    search_placeholder: "Search services, departments, schemes...",
    services_title: "Our Services",
    services_subtitle: "Quick access to all government services",
    helpline_title: "Emergency Helplines",
    stats_area: "District Area",
    stats_pop: "Population",
    stats_literacy: "Literacy Rate",
    stats_villages: "Villages",
    stats_blocks: "Blocks",
    stats_muni: "Municipalities",
    footer_rights: "© 2024 District Bhavnagar, Government of Gujarat",
    footer_nic: "Developed by National Informatics Centre",
    welcome_lang: "Please select your language",
    // ... (add all nav and section labels)
  },
  hi: {
    siteName: "जिला भावनगर",
    tagline: "गुजरात सरकार | शिक्षा नगर | भारत",
    nav_home: "मुख्य पृष्ठ",
    nav_services: "सेवाएं",
    nav_tourist: "पर्यटन गाइड",
    nav_departments: "विभाग",
    nav_helpline: "हेल्पलाइन",
    nav_news: "समाचार",
    nav_about: "परिचय",
    nav_contact: "संपर्क",
    nav_login: "लॉगिन",
    nav_register: "पंजीकरण",
    nav_logout: "लॉगआउट",
    nav_dashboard: "मेरा खाता",
    nav_settings: "सेटिंग्स",
    hero_title: "भावनगर जिले में आपका स्वागत है",
    hero_subtitle: "24,10,211 नागरिकों की सेवा में",
    search_placeholder: "सेवाएं, विभाग, योजनाएं खोजें...",
    services_title: "हमारी सेवाएं",
    helpline_title: "आपातकालीन हेल्पलाइन",
    stats_area: "जिला क्षेत्रफल",
    stats_pop: "जनसंख्या",
    stats_literacy: "साक्षरता दर",
    stats_villages: "गाँव",
    stats_blocks: "ब्लॉक",
    stats_muni: "नगरपालिकाएं",
    footer_rights: "© 2024 जिला भावनगर, गुजरात सरकार",
    welcome_lang: "कृपया अपनी भाषा चुनें",
    // ...
  },
  gu: {
    siteName: "જિલ્લો ભાવનગર",
    tagline: "ગુજરાત સરકાર | શિક્ષણ નગર | ભારત",
    nav_home: "મુખ્ય પૃષ્ઠ",
    nav_services: "સેવાઓ",
    nav_tourist: "પ્રવાસ માર્ગદર્શિકા",
    nav_departments: "વિભાગો",
    nav_helpline: "હેલ્પલાઇન",
    nav_news: "સમાચાર",
    nav_about: "વિશે",
    nav_contact: "સંપર્ક",
    nav_login: "લૉગઇન",
    nav_register: "નોંધણી",
    nav_logout: "લૉગઆઉટ",
    nav_dashboard: "મારું ખાતું",
    nav_settings: "સેટિંગ્સ",
    hero_title: "ભાવનગર જિલ્લામાં આપનું સ્વાગત છે",
    hero_subtitle: "24,10,211 નાગરિકોની સેવામાં",
    search_placeholder: "સેવાઓ, વિભાગો, યોજના શોધો...",
    services_title: "અમારી સેવાઓ",
    helpline_title: "કટોકટી હેલ્પલાઇન",
    stats_area: "જિલ્લો વિસ્તાર",
    stats_pop: "વસ્તી",
    stats_literacy: "સાક્ષરતા દર",
    stats_villages: "ગામો",
    stats_blocks: "બ્લૉક",
    stats_muni: "નગરપાલિકા",
    footer_rights: "© 2024 જિલ્લો ભાવનગર, ગુજરાત સરકાર",
    welcome_lang: "કૃપા કરીને તમારી ભાષા પસંદ કરો",
    // ...
  }
};
```

---

## 🎨 DESIGN SYSTEM

### Color Palette
```css
:root {
  /* Primary */
  --primary: #1A3C6E;        /* Deep Government Blue */
  --primary-light: #2A5BA8;  /* Brighter Blue */
  --accent: #F4A300;         /* Gujarat Saffron/Gold */
  --accent-light: #FFD166;   /* Light Gold */
  
  /* Backgrounds — Light Mode */
  --bg-primary: #F8F9FC;
  --bg-secondary: #FFFFFF;
  --bg-card: #FFFFFF;
  --text-primary: #1A1A2E;
  --text-secondary: #4A5568;
  --text-muted: #718096;
  --border: #E2E8F0;
  --shadow: rgba(26, 60, 110, 0.12);
  
  /* Dark Mode overrides applied via .dark-mode class on <body> */
  /* Device preference = prefers-color-scheme media query */
}

body.dark-mode {
  --bg-primary: #0D1117;
  --bg-secondary: #161B22;
  --bg-card: #21262D;
  --text-primary: #F0F6FC;
  --text-secondary: #C9D1D9;
  --text-muted: #8B949E;
  --border: #30363D;
  --shadow: rgba(0, 0, 0, 0.4);
  --primary: #58A6FF;
  --accent: #FFD166;
}
```

### Typography Scale
```css
/* Load from Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&family=Noto+Sans:wght@400;500;700&family=Noto+Sans+Gujarati:wght@400;700&family=Noto+Sans+Devanagari:wght@400;700&display=swap');

/* Apply font based on language */
body[lang="gu"] { font-family: 'Noto Sans Gujarati', 'Noto Sans', sans-serif; }
body[lang="hi"] { font-family: 'Noto Sans Devanagari', 'Noto Sans', sans-serif; }
body[lang="en"] { font-family: 'Poppins', 'Noto Sans', sans-serif; }
```

---

## 🏠 HOME PAGE — DETAILED SPEC

### 1. TOP BAR (above navbar)
```
[Left] 🇮🇳 Government of Gujarat | National Informatics Centre
[Right] 📅 Sunday, 28 June 2026  🕐 14:32:05  (LIVE — updates every second)
```
- Right side shows **full date** (Day, DD Month YYYY) + **live time** (HH:MM:SS, 12h format with AM/PM)
- Real-time clock using `setInterval` every 1000ms
- Background: `var(--primary)` with white text
- Font size: 13px, Poppins

### 2. NAVBAR
```
[Logo + Emblem SVG] [Site Name]        [Nav Links]        [🌐 Lang] [🔍 Search] [👤 Login/User]
```
- Sticky on scroll, adds box-shadow when scrolled down 50px
- On mobile: hamburger menu (☰) → slides in from left as a drawer
- Active page link has gold underline + color change
- Dropdown menu for: Services (with sub-items), Departments

### 3. HERO SECTION — FULL SCREEN SLIDER

**Background Image Carousel** (automatic, 5-second interval, with smooth CSS transition):

Use these 10 beautiful locations as background slides (use royalty-free placeholder gradient backgrounds for each if real images can't be loaded, with location name as overlay text — but structure it so real image URLs can be swapped in):

```javascript
const HERO_SLIDES = [
  {
    name_en: "Takhteshwar Temple",
    name_hi: "तख्तेश्वर मंदिर",
    name_gu: "તખ્તેશ્વર મંદિર",
    desc_en: "White marble hilltop Shiva temple, built 1893, panoramic city views",
    gradient: "linear-gradient(135deg, #667eea 0%, #764ba2 100%)",
    imgUrl: "https://images.unsplash.com/photo-1582510003544-4d00b7f74220?w=1600&q=80"
  },
  {
    name_en: "Velavadar Blackbuck National Park",
    name_hi: "वेलावदार कृष्णमृग राष्ट्रीय उद्यान",
    name_gu: "વેળાવદર કૃષ્ણમૃગ રાષ્ટ્રીય ઉદ્યાન",
    desc_en: "36 sq km wildlife sanctuary — home to blackbucks, wolves & migratory birds",
    gradient: "linear-gradient(135deg, #11998e 0%, #38ef7d 100%)",
    imgUrl: "https://images.unsplash.com/photo-1564349683136-77e08dba1ef7?w=1600&q=80"
  },
  {
    name_en: "Nilambag Palace",
    name_hi: "नीलमबाग पैलेस",
    name_gu: "નીલમ્બાગ પૅલેસ",
    desc_en: "Royal 1859 heritage palace, blend of Indian & European architecture",
    gradient: "linear-gradient(135deg, #f093fb 0%, #f5576c 100%)",
    imgUrl: "https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?w=1600&q=80"
  },
  {
    name_en: "Gopnath Beach",
    name_hi: "गोपनाथ बीच",
    name_gu: "ગોપનાથ બીચ",
    desc_en: "Pristine Gulf of Khambhat beach with limestone cliffs & Gopnath Mahadev Temple",
    gradient: "linear-gradient(135deg, #4facfe 0%, #00f2fe 100%)",
    imgUrl: "https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=1600&q=80"
  },
  {
    name_en: "Gaurishankar Lake (Bor Talav)",
    name_hi: "गौरीशंकर झील",
    name_gu: "ગૌરીશંકર સરોવર",
    desc_en: "Historic 1872 reservoir — boat rides, musical fountain & planetarium",
    gradient: "linear-gradient(135deg, #30cfd0 0%, #330867 100%)",
    imgUrl: "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=1600&q=80"
  },
  {
    name_en: "Palitana Jain Temples",
    name_hi: "पालिताना जैन मंदिर",
    name_gu: "પાલિતાણા જૈન મંદિર",
    desc_en: "863 sacred Jain temples on Shatrunjaya Hill — holiest pilgrim destination",
    gradient: "linear-gradient(135deg, #fa709a 0%, #fee140 100%)",
    imgUrl: "https://images.unsplash.com/photo-1545293527-e26058c5b48b?w=1600&q=80"
  },
  {
    name_en: "Victoria Park",
    name_hi: "विक्टोरिया पार्क",
    name_gu: "વિક્ટોરિયા પાર્ક",
    desc_en: "500-acre urban forest, 200+ bird species, established 1888 by Maharaja",
    gradient: "linear-gradient(135deg, #a8edea 0%, #fed6e3 100%)",
    imgUrl: "https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=1600&q=80"
  },
  {
    name_en: "Gandhi Smriti & Barton Museum",
    name_hi: "गांधी स्मृति एवं बार्टन संग्रहालय",
    name_gu: "ગાંધી સ્મૃતિ અને બાર્ટન મ્યુઝિયમ",
    desc_en: "1895 heritage museum housing Gandhi's relics, coins, arms & folk arts",
    gradient: "linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%)",
    imgUrl: "https://images.unsplash.com/photo-1568454537842-d933259bb258?w=1600&q=80"
  },
  {
    name_en: "Khodiyar Mata Temple",
    name_hi: "खोडियार माता मंदिर",
    name_gu: "ખોડિયાર માતા મંદિર",
    desc_en: "Royal family's Kuldevi temple on Tataniya Wali Lake banks, built 1911",
    gradient: "linear-gradient(135deg, #a18cd1 0%, #fbc2eb 100%)",
    imgUrl: "https://images.unsplash.com/photo-1577639673170-bb2e9a9ad7e5?w=1600&q=80"
  },
  {
    name_en: "Bhavnagar Lock Gate",
    name_hi: "भावनगर लॉक गेट",
    name_gu: "ભાવનગર લૉક ગેટ",
    desc_en: "Gujarat's first and only lock gate — enables ships to float at low tide",
    gradient: "linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%)",
    imgUrl: "https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=1600&q=80"
  }
];
```

**Hero Overlay Content (on top of each slide):**
```
[Dark gradient overlay from bottom]
[Slide Name] — in large bold white text with text-shadow
[Description] — smaller white text
[Animated dot indicators at bottom]
[← Prev]  [Play/Pause]  [Next →]  buttons
```

**Animation:** Use CSS `transition: opacity 0.8s ease, transform 0.8s ease` — slides cross-fade with slight Ken Burns zoom effect (`transform: scale(1.05)`).

### 4. QUICK STATS BAR
Animated count-up numbers when section enters viewport:
```
[ 7,034 Sq Km  |  24,10,211 Population  |  70.57% Literacy  |  699 Villages  |  11 Blocks  |  6 Municipalities ]
```
- Blue bar, white numbers, gold accent line
- Numbers animate from 0 to final value using `requestAnimationFrame` on IntersectionObserver trigger

### 5. SEARCH BAR (PROMINENT)
- Large centered search bar below hero
- Placeholder changes per language
- As user types: shows live filtered dropdown of matching services/departments/schemes
- Categories shown as filter chips: All | Services | Departments | Tourist | Forms | Schemes
- Keyboard-navigable results dropdown

### 6. QUICK ACCESS SERVICES GRID (on Home)

6-column responsive grid (3 on mobile, 2 on xs) with icon cards + hover animations:

```javascript
const QUICK_SERVICES = [
  { icon: "📜", label_en: "Certificates", label_hi: "प्रमाणपत्र", label_gu: "પ્રમાણપત્ર", link: "#certificates" },
  { icon: "🗺️", label_en: "Land Records", label_hi: "भूमि अभिलेख", label_gu: "જમીન નોંધ", link: "#land-records" },
  { icon: "🎓", label_en: "Student Corner", label_hi: "छात्र कोना", label_gu: "વિદ્યાર્થી ખૂણો", link: "#services" },
  { icon: "🏪", label_en: "Ration & PDS", label_hi: "राशन व PDS", label_gu: "રેશન અને PDS", link: "#services" },
  { icon: "👵", label_en: "Social Security", label_hi: "सामाजिक सुरक्षा", label_gu: "સામાજિક સુરક્ષા", link: "#services" },
  { icon: "⚖️", label_en: "Magisterial", label_hi: "मजिस्ट्रेट", label_gu: "મેજિસ્ટ્રેટ", link: "#services" },
  { icon: "📋", label_en: "Public Grievance", label_hi: "सार्वजनिक शिकायत", label_gu: "સાર્વજનિક ફરિયાદ", link: "#grievance" },
  { icon: "📂", label_en: "RTI", label_hi: "सूचना का अधिकार", label_gu: "માહિતી અધિકાર", link: "#rti" },
  { icon: "🗳️", label_en: "Census", label_hi: "जनगणना", label_gu: "વસ્તીગણતરી", link: "#about" },
  { icon: "🏛️", label_en: "Government Orders", label_hi: "सरकारी आदेश", label_gu: "સરકારી આદેશ", link: "#departments" },
  { icon: "📱", label_en: "e-Governance", label_hi: "ई-गवर्नेंस", label_gu: "ઇ-ગવર્નન્સ", link: "#services" },
  { icon: "🌿", label_en: "Tourist Guide", label_hi: "पर्यटन गाइड", label_gu: "પ્રવાસ માર્ગ", link: "#places" },
];
```
**Card hover:** lifts with `translateY(-6px)` + box-shadow expansion + icon scales to 1.15.
**Card animation on load:** staggered `fadeInUp` with 50ms delay per card.

### 7. DISTRICT COLLECTOR SECTION
```
[Photo placeholder circle with gradient]    [Name: Shri R K Mehta, IAS]
                                            [Title: District Collector, Bhavnagar]
                                            [Welcome message in active language]
```

### 8. HELPLINES STRIP (red/orange gradient)
```
🚨 EMERGENCY HELPLINES:  Citizens Call Center: 155300  |  Child Helpline: 1098  |  Women Helpline: 1091  |  Crime Stopper: 1090  |  Rescue & Relief: 1070
```
- Infinite horizontal scroll marquee animation
- Red pulse dot before "EMERGENCY"

### 9. NEWS & UPDATES SECTION (Tabs)
Two tabs: **News** and **Events**

Hardcoded mock entries (realistic, not "lorem ipsum"):
```javascript
const NEWS = [
  { id: 1, date: "2026-06-25", title_en: "Subhash Chandra Bose Aapda Prabandhan Puraskar 2023 awarded", title_hi: "सुभाष चन्द्र बोस आपदा प्रबंधन पुरस्कार 2023 प्रदान", title_gu: "સુભાષ ચન્દ્ર બોઝ આપત્તિ વ્યવસ્થાપન પુરસ્કાર 2023 એનાયત", type: "news" },
  { id: 2, date: "2026-06-20", title_en: "Covid-19: Assistance to heirs of deceased — Application process open", title_hi: "कोविड-19: दिवंगतों के वारिसों को सहायता — आवेदन प्रक्रिया खुली", title_gu: "કોવિડ-19: મૃત્યુ પામેલ વ્યક્તિઓના વારસદારોને સહાય", type: "news" },
  { id: 3, date: "2026-06-15", title_en: "Voter List Update: List of Absent/Shifted/Dead Voters published", title_hi: "मतदाता सूची अद्यतन: अनुपस्थित/स्थानांतरित/मृत मतदाताओं की सूची प्रकाशित", title_gu: "મતદાર યાદી અપડેટ: ગેરહાજર/સ્થળાંતર/મૃત મતદારોની યાદી", type: "news" },
  { id: 4, date: "2026-06-10", title_en: "Blackbuck National Park wildlife census results released", title_hi: "कृष्णमृग राष्ट्रीय उद्यान वन्यजीव गणना परिणाम जारी", title_gu: "કૃષ્ણ મૃગ રાષ્ટ્રીય ઉદ્યાન વન્ય પ્રાણી ગણના પરિણામ", type: "news" },
  { id: 5, date: "2026-07-15", title_en: "Bhavnagar District Festival — Annual Cultural Programme", title_hi: "भावनगर जिला महोत्सव — वार्षिक सांस्कृतिक कार्यक्रम", title_gu: "ભાવનગર જિલ્લા મહોત્સવ — વાર્ષિક સાંસ્કૃતિક કાર્યક્રમ", type: "event" },
  { id: 6, date: "2026-08-01", title_en: "Janmashtami Celebrations at Gopnath Beach", title_hi: "गोपनाथ बीच पर जन्माष्टमी उत्सव", title_gu: "ગોપનાથ બીચ પર જન્માષ્ટમી ઉત્સવ", type: "event" },
];
```
- Each news item has a left-border colored line, date badge, and title
- Items slide in from right on tab switch

### 10. FAMOUS PLACES GALLERY SECTION (on Home)
Title: "Discover Bhavnagar" — horizontal scroll card row (or 3-col grid)
Each card: gradient background + place name + short description + "Know More →" button
Include: Takhteshwar Temple, Gopnath Beach, Velavadar National Park, Nilambag Palace, Gaurishankar Lake, Victoria Park, Palitana, Gandhi Smriti, Khodiyar Mata Temple, Bhavnagar Lock Gate, Alang Ship Breaking Yard, Ganga Deri

### 11. PUBLIC UTILITIES SECTION
Show logos/cards for:
- Bhavnagar Municipal Corporation (BMC)
- 1 Municipal Corporation
- 1 University
- 1 Electricity Provider
- 1 Hospital network
- 6 Municipalities

---

## 📋 SERVICES PAGE — DETAILED

### Filter Tabs (category chips):
`All` | `Magisterial` | `Certificates` | `Land Records` | `Student Corner` | `Supply` | `Social Security`

### Services Data (mock but realistic — all filterable):

```javascript
const SERVICES_DATA = [
  // MAGISTERIAL
  { id: 1, cat: "Magisterial", icon: "⚖️", title_en: "Arms Licence", title_hi: "शस्त्र लाइसेंस", title_gu: "શસ્ત્ર લાઇસન્સ", desc_en: "Apply for arms license from Mamlatdar Office", fee: "₹200", time: "30 days", docs_en: ["ID Proof", "Address Proof", "Medical Certificate", "Character Certificate"] },
  { id: 2, cat: "Magisterial", icon: "🏪", title_en: "New Fair Price Shop", title_hi: "नया उचित मूल्य दुकान", title_gu: "નવી ઉચિત ભાવ દુકાન", desc_en: "Application for new Pandit Deen Dayal Upadhyaya store", fee: "₹500", time: "45 days", docs_en: ["Business Registration", "Land NOC", "ID Proof"] },
  { id: 3, cat: "Magisterial", icon: "📋", title_en: "Organization Card", title_hi: "संगठन कार्ड", title_gu: "સંગઠન કાર્ડ", desc_en: "Application for organization card from Jan Seva Kendra", fee: "₹100", time: "15 days", docs_en: ["Registration Certificate", "ID Proof", "Photo"] },
  { id: 4, cat: "Magisterial", icon: "⛽", title_en: "Petroleum Retail Licence", title_hi: "पेट्रोलियम खुदरा लाइसेंस", title_gu: "પેટ્રોલિયમ છૂટક લાઇસન્સ", desc_en: "Change of partnership for petroleum retail/wholesale", fee: "₹1000", time: "60 days", docs_en: ["Partnership Deed", "NOC", "Safety Certificate"] },
  
  // CERTIFICATES
  { id: 5, cat: "Certificates", icon: "🏠", title_en: "Domicile Certificate", title_hi: "अधिवास प्रमाणपत्र", title_gu: "રહેઠાણ પ્રમાણપત્ર", desc_en: "Certificate proving residence in Bhavnagar district", fee: "₹20", time: "7 days", docs_en: ["Ration Card", "Aadhar Card", "School Certificate"] },
  { id: 6, cat: "Certificates", icon: "💰", title_en: "Income Certificate", title_hi: "आय प्रमाणपत्र", title_gu: "આવક પ્રમાણ પત્ર", desc_en: "Certificate of annual family income for schemes", fee: "₹20", time: "7 days", docs_en: ["Salary Slip", "Aadhar", "Self Declaration"] },
  { id: 7, cat: "Certificates", icon: "👨‍👩‍👧", title_en: "Caste Certificate", title_hi: "जाति प्रमाणपत्र", title_gu: "જ્ઞાતિ પ્રમાણ પત્ર", desc_en: "SC/ST/OBC caste certificate for reservations", fee: "₹20", time: "15 days", docs_en: ["Birth Certificate", "School Certificate", "Parent's Caste Certificate"] },
  { id: 8, cat: "Certificates", icon: "📅", title_en: "Birth Certificate", title_hi: "जन्म प्रमाणपत्र", title_gu: "જન્મ પ્રમાણ પત્ર", desc_en: "Official birth registration certificate", fee: "₹15", time: "3 days", docs_en: ["Hospital Record", "Parent ID"] },
  { id: 9, cat: "Certificates", icon: "🕊️", title_en: "Death Certificate", title_hi: "मृत्यु प्रमाणपत्र", title_gu: "મૃત્યુ પ્રમાણ પત્ર", desc_en: "Official death registration certificate", fee: "₹15", time: "3 days", docs_en: ["Hospital Record", "ID Proof of Applicant"] },
  { id: 10, cat: "Certificates", icon: "💍", title_en: "Marriage Certificate", title_hi: "विवाह प्रमाणपत्र", title_gu: "લગ્ન પ્રમાણ પત્ર", desc_en: "Registered marriage certificate", fee: "₹50", time: "15 days", docs_en: ["ID Proof Both", "Photos", "Witness Details"] },
  
  // LAND RECORDS
  { id: 11, cat: "Land Records", icon: "📝", title_en: "7/12 Extract (Satbara)", title_hi: "7/12 उतारा", title_gu: "7/12 ઉતારો", desc_en: "Land ownership and cultivation record extract", fee: "₹15", time: "Instant Online", docs_en: ["Survey Number", "Applicant ID"] },
  { id: 12, cat: "Land Records", icon: "🗺️", title_en: "8-A Extract", title_hi: "8-ए उतारा", title_gu: "8-A ઉતારો", desc_en: "Record of rights for landholders", fee: "₹15", time: "Instant Online", docs_en: ["Khasra Number", "Applicant ID"] },
  { id: 13, cat: "Land Records", icon: "📐", title_en: "City Survey Map", title_hi: "शहर सर्वेक्षण मानचित्र", title_gu: "શહેર સર્વે નકશો", desc_en: "City survey plot map and record copy", fee: "₹50", time: "7 days", docs_en: ["Plot Number", "ID Proof"] },
  { id: 14, cat: "Land Records", icon: "🔄", title_en: "Mutation Entry", title_hi: "नामांतरण प्रविष्टि", title_gu: "નામ ફેર નોંધ", desc_en: "Transfer of land ownership name change", fee: "₹100", time: "30 days", docs_en: ["Sale Deed", "Old Record", "ID Proof"] },
  
  // STUDENT CORNER
  { id: 15, cat: "Student Corner", icon: "🎓", title_en: "Scholarship Application", title_hi: "छात्रवृत्ति आवेदन", title_gu: "શિષ્યવૃત્તિ અરજી", desc_en: "Apply for state and national scholarships", fee: "Free", time: "30 days", docs_en: ["Marksheet", "Caste Certificate", "Income Certificate", "Bank Details"] },
  { id: 16, cat: "Student Corner", icon: "🏫", title_en: "School Transfer Certificate", title_hi: "विद्यालय स्थानांतरण प्रमाणपत्र", title_gu: "શાળા સ્થળાંતર પ્રમાણ પત્ર", desc_en: "TC from recognized school", fee: "Free", time: "7 days", docs_en: ["Previous Marksheet", "Parent ID"] },
  { id: 17, cat: "Student Corner", icon: "📚", title_en: "Bonafide Certificate", title_hi: "बोनाफाइड प्रमाणपत्र", title_gu: "બોનાફાઇડ પ્રમાણ પત્ર", desc_en: "Student bonafide certificate for various purposes", fee: "Free", time: "3 days", docs_en: ["Enrollment Proof", "ID"] },
  
  // SUPPLY
  { id: 18, cat: "Supply", icon: "🛒", title_en: "New Ration Card", title_hi: "नया राशन कार्ड", title_gu: "નવો રેશન કાર્ડ", desc_en: "Apply for new APL/BPL ration card", fee: "₹5", time: "30 days", docs_en: ["Aadhar", "Address Proof", "Family Photos", "Income Proof"] },
  { id: 19, cat: "Supply", icon: "🔄", title_en: "Ration Card Changes", title_hi: "राशन कार्ड संशोधन", title_gu: "રેશન કાર્ડ સુધારો", desc_en: "Add/remove members or correct details", fee: "₹5", time: "15 days", docs_en: ["Existing Ration Card", "Supporting Docs"] },
  { id: 20, cat: "Supply", icon: "📱", title_en: "Aadhaar Enabled PDS", title_hi: "आधार सक्षम PDS", title_gu: "આધાર સક્ષમ PDS", desc_en: "Link Aadhaar with Public Distribution System", fee: "Free", time: "7 days", docs_en: ["Aadhaar Card", "Ration Card"] },
  
  // SOCIAL SECURITY
  { id: 21, cat: "Social Security", icon: "👴", title_en: "Old Age Pension", title_hi: "वृद्धावस्था पेंशन", title_gu: "વૃદ્ધ પેન્શન", desc_en: "Monthly pension for senior citizens above 60", fee: "Free", time: "45 days", docs_en: ["Age Proof", "Income Certificate", "Bank Details", "Aadhar"] },
  { id: 22, cat: "Social Security", icon: "♿", title_en: "Disability Pension", title_hi: "विकलांगता पेंशन", title_gu: "વિકલાંગ પેન્શન", desc_en: "Financial assistance for persons with disabilities", fee: "Free", time: "45 days", docs_en: ["Disability Certificate", "Income Proof", "Bank Details"] },
  { id: 23, cat: "Social Security", icon: "👩", title_en: "Widow Pension", title_hi: "विधवा पेंशन", title_gu: "વિધવા પેન્શન", desc_en: "Monthly assistance for widows", fee: "Free", time: "45 days", docs_en: ["Death Certificate of Spouse", "Marriage Certificate", "Bank Details"] },
];
```

**Service Card Design:** Show as grid cards with:
- Category badge (colored chip)
- Icon (large, circle background)
- Title in active language
- Fee + Processing time badge row
- "Apply Now" button → opens a modal with required documents list + Download Form link + "Submit Application" mock form
- Hover: card lifts + subtle border color glow

---

## 🏛️ DEPARTMENTS PAGE

Show as cards:

```javascript
const DEPARTMENTS = [
  { icon: "📊", name_en: "District Planning Office", name_hi: "जिला योजना कार्यालय", name_gu: "જિલ્લા આયોજન કાર્યાલય" },
  { icon: "🗺️", name_en: "Deputy Director of Land Records (DILR)", name_hi: "भूमि अभिलेख उप निदेशक", name_gu: "જમીન નોંધ નાયબ નિયામક" },
  { icon: "🏙️", name_en: "City Survey Office", name_hi: "शहर सर्वे कार्यालय", name_gu: "શહેર સર્વે ઓફિસ" },
  { icon: "🛒", name_en: "District Supply Office", name_hi: "जिला आपूर्ति कार्यालय", name_gu: "જિલ્લા પુરવઠા કાર્યાલય" },
  { icon: "🗳️", name_en: "District Election Office", name_hi: "जिला निर्वाचन कार्यालय", name_gu: "જિલ્લા ચૂંટણી કાર્યાલય" },
  { icon: "🍽️", name_en: "District MDM Office", name_hi: "जिला MDM कार्यालय", name_gu: "જિલ્લા MDM ઓફિસ" },
  { icon: "🏛️", name_en: "District Collector Office", name_hi: "जिला कलेक्टर कार्यालय", name_gu: "જિલ્લા કલેક્ટર કાર્યાલય" },
  { icon: "⚖️", name_en: "District Court", name_hi: "जिला न्यायालय", name_gu: "જિલ્લા ન્યાયાલય" },
  { icon: "🚔", name_en: "District Police", name_hi: "जिला पुलिस", name_gu: "જિલ્લા પોલીસ" },
  { icon: "🏥", name_en: "District Health Office", name_hi: "जिला स्वास्थ्य कार्यालय", name_gu: "જિલ્લા આરોગ્ય ઓફિસ" },
  { icon: "🎓", name_en: "District Education Office", name_hi: "जिला शिक्षा कार्यालय", name_gu: "જિલ્લા શિક્ષણ ઓફિસ" },
  { icon: "🌾", name_en: "District Agriculture Office", name_hi: "जिला कृषि कार्यालय", name_gu: "જિલ્લા કૃષિ ઓફિસ" },
];
```

---

## 🔴 HELPLINE PAGE

Display these as large visible cards with phone icon, number, and description:

| Helpline | Number |
|---|---|
| Citizen's Call Center | **155300** |
| Child Helpline | **1098** |
| Women Helpline | **1091** |
| Crime Stopper | **1090** |
| Commissioner of Rescue & Relief | **1070** |
| Police Control Room | **100** |
| Fire Brigade | **101** |
| Ambulance | **108** |
| Disaster Management | **1079** |
| Blood Bank | **0278-2521234** |

Each card: red/orange gradient, large number in big font, `tel:` link so mobile users can tap to call.

---

## 👤 USER AUTHENTICATION (localStorage — NO backend)

### Registration (`#register`)
Fields: Full Name, Email, Mobile Number, Password, Confirm Password, District Block (dropdown)
Validation: Email format, phone 10 digits, password min 8 chars, passwords match.
Store in localStorage: `bhavnagar_users` array as JSON, passwords stored as plain string (note: this is a demo/prototype — no real auth needed).

```javascript
// Example localStorage structure
const users = [
  { id: "u1", name: "Hiten Tadha", email: "hiten@example.com", phone: "9876543210", block: "Bhavnagar", password: "demo1234", createdAt: "2026-06-28", savedServices: [], grievances: [], applications: [] }
];
```

After registration → auto-login and redirect to dashboard.
Show success toast: "Registration successful! Welcome to Bhavnagar District Portal"

### Login (`#login`)
Fields: Email + Password. Check against `bhavnagar_users` in localStorage.
On success: set `bhavnagar_currentUser` in localStorage, redirect to dashboard.
On fail: shake animation on form, "Invalid email or password" message.
**"Forgot Password" link** → shows email field, then displays mock "Reset link sent" message.

### Logout
Clear `bhavnagar_currentUser` from localStorage. Redirect to home. Show toast: "Logged out successfully."

### User Dashboard (`#dashboard`)
Only accessible if logged in (redirect to login page if not).
Show:
- Welcome message: "Namaste, [User Name]!" (changes language)
- Profile card: Name, Email, Phone, Block
- My Applications tab: list of mock submitted applications
- My Grievances tab: list of submitted grievances with status (Pending/In Process/Resolved)
- Saved Services: starred/bookmarked services
- Edit Profile button (inline form with save)

---

## ⚙️ SETTINGS PAGE (`#settings`)

Design as a clean settings panel with sections:

### 1. APPEARANCE — Theme
Three large styled buttons with preview:
- **☀️ Light Mode** — white background preview
- **🌙 Dark Mode** — dark background preview
- **💻 Device Preference** — matches `prefers-color-scheme` automatically

Theme saved to `localStorage` key `"bhavnagar_theme"`. Apply immediately on change.
Also show a small live preview strip for each theme when hovering.

### 2. LANGUAGE
Same globe icon + 3 language buttons (English / हिन्दी / ગુજરાતી)

### 3. CURRENT WEATHER — AREA SELECTION
```
[Select your area dropdown]  →  Shows current weather card

Areas: Bhavnagar City, Palitana, Mahuva, Sihor, Ghogha, Talaja, Vallabhipur, Gariadhar, Jesar, Umrala, Botad
```
On area selection → use **Open-Meteo free API** (no API key):
1. Get lat/lon for the area from a hardcoded `AREA_COORDS` map (Gujarat cities)
2. Call: `https://api.open-meteo.com/v1/forecast?latitude={lat}&longitude={lon}&current_weather=true&hourly=temperature_2m,relativehumidity_2m,windspeed_10m`
3. Show: Temperature (°C), Weather condition (clear/cloudy/rainy), Wind speed, Humidity
4. Weather icon based on condition code (WMO codes)
5. "Last updated" timestamp

```javascript
const AREA_COORDS = {
  "Bhavnagar City": { lat: 21.7645, lon: 72.1519 },
  "Palitana": { lat: 21.5234, lon: 71.8257 },
  "Mahuva": { lat: 21.0848, lon: 71.7476 },
  "Sihor": { lat: 21.7275, lon: 71.9636 },
  "Ghogha": { lat: 21.6889, lon: 72.2738 },
  "Talaja": { lat: 21.3536, lon: 71.9181 },
  "Botad": { lat: 22.1731, lon: 71.6673 },
  "Gariadhar": { lat: 21.5322, lon: 71.5800 },
  "Umrala": { lat: 22.1002, lon: 71.7795 },
  "Jesar": { lat: 21.5000, lon: 71.6500 },
};
```

### 4. FEEDBACK
A beautifully styled textarea form:
- Subject dropdown (Website, Services, Departments, Tourist Info, Technical Issue, Other)
- Message textarea (min 20 chars)
- Submit → saves to `bhavnagar_feedback` in localStorage, shows animated success checkmark

### 5. WEBSITE RATING
5-star interactive rating widget (click stars, they fill with gold color).
After rating: show "Thank you for your feedback! [X] stars" with animated confetti burst (CSS-only).
Save to `bhavnagar_rating` in localStorage. Once rated, show "You rated us X ⭐" with option to change.

---

## 🚪 EXIT INTENT RATING POPUP

Trigger this when:
1. User moves mouse rapidly toward the top of the viewport (exit intent on desktop)
2. On mobile: when the page visibility changes (`visibilitychange` event) and user is navigating away

**Popup design:**
- Centered modal overlay with blur backdrop
- Title: "Before you go... 😊 / जाने से पहले... / જતા પહેલા..."
- Text: "How would you rate your experience today?"
- 5 interactive star buttons (large, 48px)
- [Skip] button (light text) + [Submit Rating] button (gold)
- Skip closes without action. Submit saves rating and closes with confetti burst.
- **NEVER** show as mandatory — always show Skip option
- Only show once per session (track with `sessionStorage` key `"exit_popup_shown"`)

---

## 🗺️ TOURIST GUIDE PAGE (`#places`)

### Header
Full-width hero with parallax title: "Explore Bhavnagar" with animated subtitle

### Filter Tabs
`All` | `Temples & Mandirs` | `Nature & Parks` | `Beaches` | `Historical` | `Museums` | `Near Bhavnagar`

### Places Cards Grid (3 cols desktop, 2 tablet, 1 mobile):

```javascript
const PLACES = [
  {
    id: 1, cat: "Temples & Mandirs",
    name_en: "Takhteshwar Temple", name_hi: "तख्तेश्वर मंदिर", name_gu: "તખ્તેશ્વર મંદિર",
    desc_en: "White marble hilltop Shiva temple built in 1893 by Maharaja Takhatsinhji. Offers panoramic views of the city and Gulf of Khambhat. Famous during Maha Shivratri.",
    timings: "6:00 AM - 12:00 PM, 4:00 PM - 9:00 PM",
    entry: "Free", distance: "In City Center",
    gradient: "linear-gradient(135deg, #667eea, #764ba2)"
  },
  {
    id: 2, cat: "Temples & Mandirs",
    name_en: "Gopnath Mahadev Temple", name_hi: "गोपनाथ महादेव मंदिर", name_gu: "ગોપનાથ મહાદેવ મંદિર",
    desc_en: "700-year-old temple on the coast of Gulf of Khambhat. Associated with Gopnath Beach and King Gohilvad's fort. A sacred Shiva pilgrimage site.",
    timings: "5:00 AM - 8:00 PM", entry: "Free", distance: "75 km from city",
    gradient: "linear-gradient(135deg, #f093fb, #f5576c)"
  },
  {
    id: 3, cat: "Temples & Mandirs",
    name_en: "Khodiyar Mata Temple", name_hi: "खोडियार माता मंदिर", name_gu: "ખોડિયાર માતા મંદિર",
    desc_en: "Built in 1911 by the King of Bhavnagar on the banks of Tataniya Wali Lake. Kuldevi (family deity) of the royal family. Famous for Lapsi prasad.",
    timings: "6:00 AM - 9:00 PM", entry: "Free", distance: "15 km / Rajpara 69 km",
    gradient: "linear-gradient(135deg, #a18cd1, #fbc2eb)"
  },
  {
    id: 4, cat: "Temples & Mandirs",
    name_en: "Aksharwadi Swaminarayan Temple", name_hi: "अक्षरवाडी स्वामिनारायण मंदिर", name_gu: "અક્ષરવાડી સ્વામિનારાયણ મંદિર",
    desc_en: "Magnificent Swaminarayan temple known for its ornate architecture and peaceful atmosphere. Major pilgrimage site in Bhavnagar.",
    timings: "6:00 AM - 12:00 PM, 4:00 PM - 9:00 PM", entry: "Free", distance: "In City",
    gradient: "linear-gradient(135deg, #fa709a, #fee140)"
  },
  {
    id: 5, cat: "Historical",
    name_en: "Nilambag Palace", name_hi: "नीलमबाग महल", name_gu: "નીલમ્બાગ પૅલેસ",
    desc_en: "Built in 1859 by Maharaja Takhtsinhji. Blends Indian and European architecture. Now a heritage hotel with royal gardens and peacocks.",
    timings: "Open to Hotel Guests", entry: "Heritage Stay", distance: "City Center",
    gradient: "linear-gradient(135deg, #ffecd2, #fcb69f)"
  },
  {
    id: 6, cat: "Historical",
    name_en: "Gandhi Smriti & Barton Museum", name_hi: "गांधी स्मृति व बार्टन संग्रहालय", name_gu: "ગાંધી સ્મૃતિ અને બાર્ટન મ્યુઝિયમ",
    desc_en: "1895 AD heritage building with Gandhi's relics, 40,000 books on Gandhian thought, coins, arms, sculpture and folk arts. Mahatma Gandhi studied here.",
    timings: "9:00 AM - 6:00 PM (Closed Mondays)", entry: "₹5", distance: "City Center",
    gradient: "linear-gradient(135deg, #568cd4, #8ea8d4)"
  },
  {
    id: 7, cat: "Historical",
    name_en: "Bhavnagar Lock Gate", name_hi: "भावनगर लॉक गेट", name_gu: "ભાવનગર લૉક ગેટ",
    desc_en: "Gujarat's first and only lock gate — enables ships to remain afloat at low tide. A unique maritime engineering heritage site.",
    timings: "Accessible Anytime", entry: "Free", distance: "Near Port",
    gradient: "linear-gradient(135deg, #0f0c29, #302b63)"
  },
  {
    id: 8, cat: "Historical",
    name_en: "Ganga Deri", name_hi: "गंगा देरी", name_gu: "ગંગા ડેરી",
    desc_en: "Elegant marble monument built in memory of Maharaja Takhtsinhji's queen. Showcases exquisite craftsmanship and royal heritage.",
    timings: "Sunrise to Sunset", entry: "Free", distance: "City Center",
    gradient: "linear-gradient(135deg, #c6ffdd, #f7797d)"
  },
  {
    id: 9, cat: "Nature & Parks",
    name_en: "Velavadar Blackbuck National Park", name_hi: "वेलावदार राष्ट्रीय उद्यान", name_gu: "વેળાવદર રાષ્ટ્રીય ઉદ્યાન",
    desc_en: "36 sq km grassland established 1976. India's largest blackbuck population + wolves, nilgai, jungle cats & 200+ bird species. Jeep safaris available.",
    timings: "7:00 AM - 6:00 PM (Closed monsoon)", entry: "₹20 Indians / ₹100 Foreign", distance: "50 km",
    gradient: "linear-gradient(135deg, #11998e, #38ef7d)"
  },
  {
    id: 10, cat: "Nature & Parks",
    name_en: "Victoria Park", name_hi: "विक्टोरिया पार्क", name_gu: "વિક્ટોરિયા પાર્ક",
    desc_en: "500-acre man-made tropical forest, established 1888. Over 200 bird species, nilgai, foxes, porcupines. Adjacent to Gaurishankar Lake.",
    timings: "6:00 AM - 10:00 AM, 5:00 PM - 8:00 PM", entry: "₹10", distance: "6 km",
    gradient: "linear-gradient(135deg, #56ab2f, #a8e063)"
  },
  {
    id: 11, cat: "Nature & Parks",
    name_en: "Gaurishankar Lake (Bor Talav)", name_hi: "गौरीशंकर झील", name_gu: "ગૌરીશંકર સરોવર",
    desc_en: "Historic 1872 reservoir supplying city water. Now a leisure hub: boat rides, musical fountain, planetarium, and lakeside gardens.",
    timings: "6:00 AM - 9:00 PM", entry: "Free (boat rides: ₹30)", distance: "6 km",
    gradient: "linear-gradient(135deg, #30cfd0, #330867)"
  },
  {
    id: 12, cat: "Beaches",
    name_en: "Gopnath Beach", name_hi: "गोपनाथ बीच", name_gu: "ગોપનાથ બીચ",
    desc_en: "Pristine beach on Gulf of Khambhat with dramatic limestone cliffs. Bird watchers' paradise. Summers spent here by Maharaja Krishna Kumar Singhji.",
    timings: "All day", entry: "Free", distance: "75 km",
    gradient: "linear-gradient(135deg, #4facfe, #00f2fe)"
  },
  {
    id: 13, cat: "Near Bhavnagar",
    name_en: "Palitana Jain Temples", name_hi: "पालिताना जैन मंदिर", name_gu: "પાલિતાણા જૈન મંદિર",
    desc_en: "863 Jain temples on Shatrunjaya Hill — holiest pilgrimage site for Jains. Stunning 11th–16th century architecture. World's only vegetarian town.",
    timings: "7:00 AM - 6:00 PM (Closed Monday)", entry: "₹50 (monument fee)", distance: "55 km",
    gradient: "linear-gradient(135deg, #fa709a, #fee140)"
  },
  {
    id: 14, cat: "Near Bhavnagar",
    name_en: "Alang Ship Breaking Yard", name_hi: "अलंग शिप ब्रेकिंग यार्ड", name_gu: "અળંગ શીપ બ્રેકિંગ યાર્ડ",
    desc_en: "World's largest ship recycling facility. Unique industrial tourism — watch massive ships being dismantled on the beach. Truly one-of-a-kind.",
    timings: "With Special Permission", entry: "Permit Required", distance: "50 km",
    gradient: "linear-gradient(135deg, #4b6cb7, #182848)"
  },
];
```

Each card: gradient top image area, title, category badge, description (truncated), timing & entry badges, "View Details →" button.

On card click → full detail modal with all info.

---

## 📣 PUBLIC GRIEVANCE PAGE (`#grievance`)

Form with fields:
- Grievance Type (Infrastructure / Public Services / Corruption / Health / Education / Other)
- Subject
- Description (textarea)
- Your Block/Taluka
- Contact Number
- Upload Proof (file input — store filename only in localStorage, not file content)

On Submit:
- Assign a tracking number: `GR-2026-XXXXX` (random 5-digit)
- Save to localStorage under user's account OR as guest in `bhavnagar_grievances`
- Show success modal: "Grievance submitted. Tracking Number: **GR-2026-XXXXX**. Expected resolution: 30 days."

Track Grievance section: input tracking number → show mock status:
- `GR-2026-*1` → Pending
- `GR-2026-*2` → In Process (assigned to Officer)
- `GR-2026-*3` → Resolved

---

## 📂 RTI PAGE (`#rti`)

Informational page with:
- What is RTI? (short explanation in active language)
- How to file RTI application — step-by-step with numbered visual process
- Download RTI Form (link to `#` with tooltip "Form available at Collectorate")
- RTI Officers list (mock names/positions table)
- Response timeline: 30 days (or 48hrs for life/liberty matters)

---

## 🔎 GLOBAL SEARCH FUNCTIONALITY

The search bar (in navbar and home page) should:
1. Accept text input
2. Search through: Services data, Departments, Places, Helplines, News
3. Show results grouped by category in a floating dropdown
4. Each result is clickable → navigates to relevant page + section
5. Show "No results found" with suggestion to contact helpline
6. Highlight matched text in results
7. Keyboard: Arrow keys to navigate, Enter to select, Escape to close

---

## 🎬 ANIMATIONS SPECIFICATION (CRITICAL)

### Global Animation Variables
```css
:root {
  --anim-fast: 0.2s;
  --anim-med: 0.4s;
  --anim-slow: 0.7s;
  --ease-out: cubic-bezier(0.25, 0.46, 0.45, 0.94);
  --ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1);
}
```

### Required Animations

1. **Page load:** Navbar slides down from top (0.5s), hero fades in (0.8s delay), then stats bar slides up
2. **Hero slider:** Cross-fade with Ken Burns zoom (scale 1.0 → 1.05 over 5 seconds per slide)
3. **Card hover:** `transform: translateY(-6px) scale(1.01)` + `box-shadow` expansion — 0.25s ease
4. **Count-up stats:** Number counts up from 0 when scrolled into view using IntersectionObserver
5. **Section reveal:** `@keyframes fadeInUp { from { opacity:0; transform:translateY(30px); } to { opacity:1; transform:translateY(0); } }` — triggered by IntersectionObserver on each section
6. **Staggered cards:** `animation-delay: calc(var(--i) * 0.08s)` where `--i` is card index
7. **Language modal:** Opens with `scaleIn` (0.3s spring), closes with `scaleOut` (0.2s ease)
8. **Toast notifications:** Slide in from right, auto-dismiss after 3s with fade
9. **Modal open/close:** Backdrop fades in (0.2s), modal slides up (0.35s spring)
10. **Navigation clicks:** Smooth scroll between sections with `scroll-behavior: smooth`
11. **Burger menu:** Morphs ☰ to ✕ with rotation animation; drawer slides from left
12. **Dark mode toggle:** Color transitions with `transition: background-color 0.3s, color 0.3s` on all elements
13. **Search dropdown:** Slides down with `max-height` transition from 0 to auto
14. **Star rating:** Each star fills individually on hover with gold color slide animation
15. **Form shake error:** `@keyframes shake { 0%,100%{transform:translateX(0)} 25%{transform:translateX(-8px)} 75%{transform:translateX(8px)} }` on invalid submit
16. **Helpline marquee:** Smooth infinite scroll `@keyframes marquee { from{transform:translateX(100%)} to{transform:translateX(-100%)} }`
17. **Confetti burst on rating:** Pure CSS multicolored dots explode outward with `@keyframes confetti-fall`
18. **Progress bars (in dashboard):** Animate from 0% to target width on view

### Performance Rules (CRITICAL)
- Use `will-change: transform` ONLY on actively animating elements, remove after animation
- Use `transform` and `opacity` for animations (GPU-composited — never animate width/height/top/left)
- Images: add `loading="lazy"` attribute to all non-hero images
- Hero images: preload first slide, lazy-load rest
- Use `requestAnimationFrame` for count-up animations
- Debounce search input with 300ms delay
- Use `IntersectionObserver` for scroll animations (not scroll event listener)
- Add `@media (prefers-reduced-motion: reduce)` — disable all animations for accessibility

---

## 🧩 COMPONENT SPECS

### Toast Notification System
```javascript
// Call anywhere: showToast("Message", "success" | "error" | "info" | "warning")
// Toast stack in top-right corner, max 3 visible, auto-dismiss 3s
```

### Modal System
```javascript
// Reusable modal with: openModal(title, content, actions)
// Always closeable with X button, ESC key, and clicking backdrop
// Prevent body scroll when modal is open (overflow: hidden)
```

### Navbar Active State
- Detect current hash from URL, apply `.active` class to corresponding nav link
- Listen to `hashchange` event to update active state without reload

---

## 📊 ABOUT BHAVNAGAR PAGE (`#about`)

### District Facts Section
```
Area: 7,034 Sq Km
Population: 24,10,211
Literacy Rate: 70.57%
Blocks: 11
Villages: 699
Municipalities: 6
Municipal Corporations: 1
```

### History (short paragraphs in active language):
- Founded by Bhavsinhji Gohil (Gohil dynasty from Marwar)
- First state in India to build its own railway system
- First state to join the Indian Union
- Historic port connecting Africa, Singapore, Persian Gulf

### Connectivity:
- **By Air:** Bhavnagar Airport — flights from Ahmedabad, Mumbai, Surat
- **By Rail:** Bhavnagar Railway Station — major junction
- **By Road:** Well-connected to Ahmedabad (198 km via NH), Rajkot, Surat

### Economy: Cotton trade, Alang ship recycling, Fishing, Agriculture

---

## 📬 CONTACT PAGE (`#contact`)

### Contact Cards:
```
District Collectorate, Bhavnagar - 364001, Gujarat
📞 0278-2522012
✉️ collector-bhav@gujarat.gov.in
🕐 Monday–Friday: 10:30 AM – 6:10 PM
```

### Embedded Mock Map (CSS-drawn):
Draw a simple SVG-based stylized map showing Bhavnagar location within Gujarat outline.

### Contact Form:
- Name, Email, Subject, Message
- Submit → localStorage + success toast

---

## 📱 RESPONSIVE DESIGN

### Breakpoints:
```css
/* Mobile First */
/* xs: 0-480px */
/* sm: 481-768px */
/* md: 769-1024px */
/* lg: 1025-1280px */
/* xl: 1281px+ */
```

### Mobile Specifics:
- Hamburger nav with slide-in drawer
- Hero slider dots: larger tap targets (48px)
- Service grid: 2 cols on sm, 1 col on xs
- Language switcher: bottom sheet instead of dropdown
- Stats: scroll horizontally (scroll-snap)
- Footer: stack all columns vertically

---

## 🦶 FOOTER

Three columns + bottom bar:

**Column 1 — About**
- Site logo + name
- Tagline
- Social media icons (decorative — link to `#`)

**Column 2 — Quick Links**
- Home, Services, Tourist Guide, Departments, Helpline, Contact, About

**Column 3 — Contact**
- Address, Phone, Email, Hours
- Citizen Call Center: 155300 (large, bold)

**Bottom Bar:**
```
[Left] © 2024 District Bhavnagar, Government of Gujarat | National Informatics Centre
[Right] Privacy Policy | Terms of Use | Sitemap | Accessibility
```

---

## 🧪 QUALITY CHECKLIST (Build to Pass All)

- [ ] Live clock updates every 1 second without lag
- [ ] Language switches ALL text on page instantly (no reload)
- [ ] Theme persists after page refresh
- [ ] Language choice persists after page refresh
- [ ] Login state persists after page refresh
- [ ] Exit popup never shows more than once per session
- [ ] No console errors in any page
- [ ] All modals closeable with ESC key
- [ ] All forms have proper validation with visual feedback
- [ ] Search returns results in under 100ms
- [ ] Hero slider auto-advances every 5s, pauses on hover
- [ ] All pages visible and navigable via navbar
- [ ] Dark mode applies to EVERY element (no unthemed islands)
- [ ] Weather loads and displays within 3 seconds of area selection
- [ ] Registration and login work end-to-end with localStorage
- [ ] Mobile nav works on touch devices
- [ ] Reduced motion respected (`prefers-reduced-motion`)
- [ ] No horizontal scroll at any viewport width

---

## 🚀 FINAL NOTES FOR AI/BUILDER

1. Start with the data layer (TRANSLATIONS, SERVICES_DATA, PLACES, DEPARTMENTS) in a separate `data.js` module
2. Build a global state manager: `{ lang, theme, user, currentPage }` — update and re-render reactively
3. Use CSS custom properties for ALL colors — this makes dark mode a 1-class toggle
4. Every `console.log` should be wrapped in `if (DEBUG_MODE)` — ship clean
5. Minify nothing manually — let Vite handle it
6. Test localStorage operations with try/catch — private browsing can block them; show graceful fallback
7. The entire project must work as a static site (no Node.js server at runtime — just `npm run build` output)
8. Image URLs from Unsplash CDN are used as placeholders — they require no API key for display
9. Bhavnagar coat of arms / emblem: use a golden chakra SVG or lion SVG in navbar and welcome modal as a symbol

---

**END OF PROMPT. BUILD THE COMPLETE WEBSITE AS DESCRIBED ABOVE. Do not skip any section. Prioritize: (1) correct language switching, (2) glitch-free animations, (3) localStorage persistence, (4) responsive mobile layout, (5) beautiful visual design.**
