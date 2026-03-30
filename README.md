<div align="center">
  <br />
  <img src="./assets/images/logo-placeholder.svg" alt="MEDFIND Logo" width="200"/>
  <h1>🏥 MEDFIND</h1>
  <p><strong>Your Comprehensive Healthcare Discovery Platform</strong></p>
  <p>A modern, feature-rich hospital and healthcare service finder application connecting patients with doctors, labs, and medical facilities.</p>

  <!-- Badges -->
  <p>
    <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"/>
    <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"/>
    <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript"/>
    <img src="https://img.shields.io/badge/Font_Awesome-6.4.0-528DD7?style=for-the-badge&logo=fontawesome&logoColor=white" alt="FontAwesome"/>
    <img src="https://img.shields.io/badge/Responsive-Mobile_First-brightgreen?style=for-the-badge" alt="Responsive"/>
    <img src="https://img.shields.io/badge/Status-Development-yellow?style=for-the-badge" alt="Status"/>
  </p>
</div>

<hr />

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [✨ Key Features](#-key-features)
- [🏗️ Technology Stack](#️-technology-stack)
- [📁 Project Structure](#-project-structure)
- [🎨 Design & Architecture](#-design--architecture)
- [🚀 Getting Started](#-getting-started)
- [🧩 Module Breakdown](#-module-breakdown)
- [🔮 Production Readiness](#-production-readiness)
- [📱 Viva Guide](#-viva-guide)
- [📄 License & Contact](#-license--contact)

---

## 🔍 Project Overview

**MEDFIND** is a comprehensive web application designed to simplify healthcare discovery and management. Inspired by platforms like `bddoctors.com`, it serves as a centralized healthcare ecosystem where users can:

- 🔎 Find hospitals, doctors, and diagnostic labs based on location
- 👤 View detailed profiles with specialties, ratings, and availability
- 📅 Book appointments seamlessly with real-time slot selection
- 📊 Access medical history, reports, and prescriptions
- 🏥 Manage hospital operations (Admin, Pharmacy, Lab, Billing)

The platform features **six distinct portals** (Patient, Doctor, Admin, Pharmacy, Lab, Billing) ensuring tailored experiences for every user role. Built with vanilla HTML, CSS, and JavaScript, it demonstrates a modular, scalable, and production-ready frontend architecture.

---

## ✨ Key Features

### 🎯 Core Functionality
- **Location-Based Search:** Intelligent city/area selection with geolocation support
- **Advanced Filtering:** Filter by specialty, rating, facilities, and distance
- **Role-Based Dashboards:** Dedicated interfaces for all user types
- **Appointment Management:** End-to-end booking flow with confirmation

### 🏥 Module Highlights
- **Patient Portal:** Medical history, prescriptions, appointment tracking
- **Admin Panel:** User management, hospital verification, system reports
- **Pharmacy Module:** Medicine inventory with expiry alerts
- **Laboratory System:** Test tracking and report uploads
- **Billing Suite:** OPD/IPD billing with multiple payment options
- **Ward Management:** Bed availability (ICU/General/Cabin)

### 🎨 UI/UX Excellence
- **Mobile-First Design:** Flawless experience across all devices
- **Smooth Animations:** Hover effects, modal transitions, loading states
- **Toast Notifications:** Real-time feedback system
- **Accessibility:** Semantic HTML, ARIA labels, keyboard navigation

---

## 🏗️ Technology Stack

| Category | Technologies |
|----------|-------------|
| **Frontend** | HTML5, CSS3, JavaScript (Vanilla ES6+) |
| **Icons & Fonts** | Font Awesome 6.4.0, Google Fonts |
| **Styling** | CSS Custom Properties, Flexbox, CSS Grid |
| **Architecture** | Modular, Component-Based, Mobile-First |
| **State Management** | localStorage, Session Storage |
| **Performance** | Lazy Loading, Optimized Assets |

---

## 📁 Project Structure

```
medfind/
├── assets/
│   ├── images/
│   │   └── logo-placeholder.svg
│   ├── css/
│   │   ├── base.css
│   │   ├── layout.css
│   │   ├── components.css
│   │   ├── animations.css
│   │   └── responsive.css
│   └── js/
│       ├── main.js
│       ├── auth.js
│       ├── location.js
│       └── notification.js
├── pages/
│   ├── patient/
│   ├── doctor/
│   ├── admin/
│   ├── pharmacy/
│   ├── lab/
│   └── billing/
└── index.html
```

---

## 🎨 Design & Architecture

### CSS Architecture (Modular Approach)

```css
/* base.css - Global Foundation */
:root {
    --primary-color: #2c3e50;
    --secondary-color: #3498db;
    --success-color: #27ae60;
    --error-color: #e74c3c;
    --font-main: 'Inter', sans-serif;
    --transition-speed: 0.3s;
}

/* layout.css - Structural Layouts */
.container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
}

/* components.css - Reusable UI Elements */
.card {
    background: white;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    transition: transform var(--transition-speed);
}

.card:hover {
    transform: translateY(-5px);
}

/* animations.css - Dynamic Effects */
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
}

/* responsive.css - Breakpoints */
@media (max-width: 768px) {
    .grid { grid-template-columns: 1fr; }
}
```

### JavaScript Architecture (ES6 Modules)

```js
// main.js - Application Core
import { initLocation }    from './location.js';
import { initAuth }        from './auth.js';
import { showNotification } from './notification.js';

document.addEventListener('DOMContentLoaded', () => {
    initLocation();
    initAuth();
    setupEventListeners();
});

// location.js - Location Management
export function initLocation() {
    const citySelect = document.getElementById('city');
    const areaSelect = document.getElementById('area');

    citySelect.addEventListener('change', async (e) => {
        const areas = await fetchAreas(e.target.value);
        populateAreas(areas);
        localStorage.setItem('selectedCity', e.target.value);
    });
}

// notification.js - Toast System
export function showNotification(message, type = 'info') {
    const toast = document.createElement('div');
    toast.className = `toast toast-${type}`;
    toast.textContent = message;
    toast.style.animation = 'slideIn 0.3s ease';
    document.body.appendChild(toast);
    setTimeout(() => toast.remove(), 3000);
}
```

### UI/UX Principles

- **Consistency:** Unified color palette and spacing via CSS Custom Properties
- **Feedback:** Every user action receives immediate visual feedback (toasts, loaders)
- **Progressive Disclosure:** Complex flows broken into simple, guided steps
- **Accessibility:** Semantic HTML5 elements and ARIA labels throughout

---

## 🚀 Getting Started

### Prerequisites

- A modern web browser (Chrome, Firefox, Edge, Safari)
- Python 3 (or any static file server) for local development

### Installation

```bash
git clone https://github.com/yourusername/medfind.git
cd medfind/frontend
```

### Usage

```bash
# Start a local development server
python -m http.server 8000

# Then open your browser and visit:
# http://localhost:8000
```

---

## 🧩 Module Breakdown

### Public Pages
- **Home (`index.html`):** Location-based search, featured hospitals, and quick links
- **Hospital Listing:** Filterable list of hospitals by city, area, and specialty
- **Hospital Detail:** Tabbed view with Doctors, Lab, Pharmacy, and Ward sections
- **Doctor Profile:** Full profile with schedule, ratings, and booking flow

### Core Modules
| Module | Description |
|--------|-------------|
| **Patient Portal** | Dashboard, appointments, prescriptions, medical history |
| **Doctor Portal** | Schedule management, patient queue, consultation notes |
| **Admin Panel** | User management, hospital verification, analytics |
| **Pharmacy** | Inventory management, expiry alerts, sales tracking |
| **Laboratory** | Test orders, result uploads, report management |
| **Billing** | OPD/IPD billing, payment processing, invoice generation |

---

## 🔮 Production Readiness

To evolve MEDFIND into a production system, the following enhancements are recommended:

- **Backend Integration:** REST API (Node.js/Django) with a relational database (PostgreSQL)
- **Authentication:** JWT-based auth with role-based access control (RBAC)
- **Real-Time Features:** WebSockets for live appointment updates and chat
- **Testing:** Unit tests (Jest) and end-to-end tests (Playwright/Cypress)
- **CI/CD:** Automated deployment pipeline via GitHub Actions
- **Performance:** Code splitting, service workers, and CDN asset delivery

---

## 📱 Viva Guide

Key talking points for demonstrating MEDFIND:

1. **Architecture Decision:** Why vanilla JS over a framework — zero build overhead, demonstrates core web fundamentals
2. **Modular CSS:** How CSS Custom Properties enable consistent theming across all modules
3. **Role Separation:** How the portal structure isolates concerns between user types
4. **Scalability Path:** How the module structure maps directly onto future REST API endpoints
5. **Accessibility:** Point to semantic HTML and ARIA usage in forms and modals

---

## 📄 License & Contact

This project is for academic/demonstration purposes.

For questions or contributions, please open an issue on the [GitHub repository](https://github.com/yourusername/medfind).
