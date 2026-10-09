# RESQNET — Climate Aware Emergency Response Network 🚨
**Problem Statement ID:** HC-05 (*"Climate Aware Emergency Response Network"*)  
**Team Name:** Endless Coders  
**Target Platform:** Mobile-First Progressive Web App (PWA) for India (optimized for 360px+ viewport)

---

## 🌟 Executive Summary
When natural disasters, urban flash floods, or cyclones strike India, cell towers get congested, arterial roads submerge in water, and lives are lost simply because people cannot signal their location, locate a usable road, or find the nearest functioning trauma center.

**RESQNET** is an offline-first, mobile-first emergency response network that:
1. **Warns citizens of climate hazards** using real-time Open-Meteo precipitation and flood risk models.
2. **Shows which roads are usable** via community-verified road reports with auto-expiring TTLs.
3. **Guides victims to the nearest open hospitals** with turn-by-turn routing that actively routes around flooded checkpoints.
4. **Triggers instant emergency SOS in 1 tap**, generating WhatsApp/SMS alerts with live Google Maps coordinates and medical triage cards.
5. **Works seamlessly offline** with pre-cached Indian national helplines (112, 101, 108, 1091, 181), medical profiles, and app shell.

---

## 🛠️ Zero-Cost Tech Stack (No Paid API Keys Required)
- **Frontend & App Shell:** React 19 + TypeScript + Vite 8
- **Styling & Aesthetics:** Tailwind CSS v4, Dark Navy Emergency Theme (`#0B132B`, `#1C2541`, `#EF4444`)
- **Interactive Emergency Map:** Leaflet + OpenStreetMap + CartoDB Dark Voyager Tiles
- **Weather & Climate Intelligence:** Open-Meteo Forecast API & Flood Risk API (100% Free & Open)
- **Healthcare Infrastructure:** Overpass API (OpenStreetMap nodes) + Verified Indian Fallback Registry
- **Route Navigation:** Open Source Routing Machine (OSRM) Public API
- **Offline & PWA:** Service Worker (Vite PWA / Workbox), IndexedDB, LocalStorage
- **Audio & Accessibility:** Web Audio API (Synthesized Siren & Countdown Beeps), Web Speech API (TTS Readout in English, Hindi, and Marathi)
- **Deployment:** Vercel

---

## 🎯 Core Features Implemented

| Feature | Description | Offline Ready? |
| :--- | :--- | :---: |
| **1. Emergency SOS** | Large 1-tap SOS button with 5-second cancel countdown, siren alarm, Web Audio beeps, and auto-dispatch to WhatsApp/SMS with Google Maps GPS link & Medical Card payload. Instant "Call 112" link always present. | ✅ Yes |
| **2. National Helplines** | Direct tap-to-call directory: 112 (National Emergency), 101 (Fire & Rescue), 108 (Ambulance), 1091 (Women in Distress), 181 (Crisis Helpline), 1070 (SDMA), 1077 (District Control Room), 102 (Maternal). | ✅ 100% Offline |
| **3. Hyperlocal Climate Risk** | Low / Medium / High / Severe flood & heavy-rain risk badges computed from live Open-Meteo precipitation models, 24h & 72h accumulation forecast, and hourly trend visualizer. | ✅ Cached Fallback |
| **4. Live Emergency Map** | Interactive Leaflet dark map with user GPS position beacon, hospital markers, community road hazard pins, and dynamic flood risk circles. Category filters for fast triage. | ✅ Yes |
| **5. Road Blockage Reports** | Citizens report flooded roads, fallen trees, landslides, or submerged bridges with severity and passability status. Community "Still Blocked?" verification upvotes with automatic TTL expiration. | ✅ Persistent Storage |
| **6. Nearby Hospitals & Routing** | Live Overpass query for emergency hospitals and trauma centers sorted by distance. 1-tap call and OSRM turn-by-turn navigation designed to circumvent flooded roads. | ✅ Verified Fallback |
| **7. Emergency Message Presets** | 5 pre-configured one-tap distress templates (Flood, Fire, Accident, Medical, Trapped) with live GPS coordinates and medical triage payload. | ✅ Yes |
| **8. Emergency Medical Card** | Blood group, allergies, chronic conditions, and primary/secondary emergency contacts stored strictly on the user's phone for privacy and zero-connectivity access. | ✅ 100% Offline |
| **9. Offline-First PWA Engine** | Service worker precaches app shell and emergency assets. Prominent "Offline: showing last updated data" banner with sync timestamp. Standalone installable PWA. | ✅ Yes |
| **10. Multilingual & Accessibility** | Full UI translation for English, Hindi (हिंदी), and Marathi (मराठी). Web Speech API read-aloud alert reader, large 48px+ touch targets, and High Contrast mode toggle. | ✅ Yes |

---

## 💻 Local Setup Instructions

### Prerequisites
- Node.js v18+ (tested on Node v24.21.0)
- npm or pnpm

### Quick Start
```bash
# 1. Clone or navigate to the repository
cd "c:\Users\hp\ResQNet 5"

# 2. Install dependencies
npm install

# 3. Start development server
npm run dev

# 4. Open in browser
http://localhost:5173
```

### Production Build
```bash
npm run build
npm run preview
```

---

## 🚀 Deployment to Vercel

RESQNET is pre-configured with `vercel.json` for seamless zero-config deployment:

1. Push your repository to GitHub or GitLab.
2. Go to [vercel.com](https://vercel.com) and click **"Add New Project"**.
3. Import this repository.
4. Framework Preset will auto-detect as **Vite**.
5. Build Command: `npm run build`
6. Output Directory: `dist`
7. Click **Deploy**.

---

## ⏱️ 2-Minute Winning Hackathon Pitch Script (For Judges)

### **[0:00 - 0:25] The Problem & Hook**
> *"Respected judges, during the Mumbai floods, Chennai deluges, and Delhi Yamuna breaches, people die not because rescue services don't exist, but because communication collapses. Power lines go down, roads get submerged without warning, and cell networks crawl. How do you call for help when you don't even know which road is safe? This is problem statement HC-05, and we are Team Endless Coders. Meet RESQNET."*

### **[0:25 - 0:55] Innovation & Live Demo: SOS & Offline Resilience**
> *"RESQNET is a mobile-first Progressive Web App built specifically for India. Look at this interface—calibrated for a high-stress 360-pixel phone screen.  
Watch what happens when I tap the Emergency SOS button. [Tap SOS]  
A 5-second audio-visual countdown begins with an oscillating emergency siren and haptic pulse. If it's a false alarm, I can cancel. When it triggers, it automatically packages my exact Google Maps GPS coordinates, my blood group, allergies, and emergency contact into a prefilled WhatsApp or SMS message. In one tap, my family and first responders know exactly where I am. And if I need immediate government dispatch, 'Call 112' is right there."*

### **[0:55 - 1:25] Climate Risk & Intelligent Road Navigation**
> *"Now look at our climate intelligence. RESQNET queries real-time Open-Meteo global meteorological data without any expensive paid API keys. Right now, for our selected location, it calculates a live Disaster Threat Index, shows rainfall for the next 24 and 72 hours, and draws flood risk hazard zones directly on our Leaflet map.  
Switching to the Map and Hospitals tab: RESQNET pulls real emergency hospitals from OpenStreetMap Overpass API, sorts them by distance, and calculates OSRM driving routes. Notice this warning: the route actively alerts users to avoid reported roadblocks like the submerged Hindmata Flyover."*

### **[1:25 - 1:45] Community Crowdsourcing & Multilingual Accessibility**
> *"Under the Report tab, citizens report blocked roads, fallen trees, and water levels. Other users confirm with 'Still Blocked?', and reports automatically expire using TTL countdowns.  
Most importantly, disasters don't wait for good network: RESQNET is 100% PWA-installable, caches all 8 Indian emergency numbers offline, supports English, Hindi, and Marathi, and speaks alerts aloud using voice synthesis."*

### **[1:45 - 2:00] Conclusion & Impact**
> *"Zero paid APIs, 100% offline-ready, designed for every citizen across India. RESQNET bridges the gap between climate forecasting and life-saving action. Thank you, and we're ready for your questions!"*
