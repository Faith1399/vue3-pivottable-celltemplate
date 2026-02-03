# 🧾 Vue 3 — Syncfusion PivotView cellTemplate (Vue CLI) Quick Start

This sample demonstrates using Vue 3 with Vite to integrate Syncfusion PivotView (Pivot Table) and customize pivot cells via the cellTemplate option. It includes Vite-based dev setup, examples for binding JSON or fetched data, and patterns for rendering lightweight HTML inside pivot cells (icons, badges, conditional styles). Designed as copy‑paste ready demos for dashboards and analytics UIs.

---

## 📚 Table of Contents
- [🔎 Overview](#-overview)
- [✨ Key Features](#-key-features)
- [🛠️ Requirements](#️-requirements)
- [⚙️ Installation](#️-installation)
- [🚀 Quick Start](#-quick-start)
- [🏗️ Project Structure](#️-project-structure)
- [🔧 Best Practices](#-best-practices)
- [❓ Troubleshooting](#-troubleshooting)
- [🤝 Contributing](#-contributing)
- [📜 License & Support](#-license--support)

---

## 🔎 Overview
Demonstrates integrating Syncfusion PivotView (Pivot Table) with a custom cellTemplate in a Vue 3 app (Vue CLI). Shows binding JSON data, defining row/column/value/filter fields, sizing the PivotView, and customizing cells by inserting templates.

---

## ✨ key Features
- Vue 3 SFC examples using cellTemplate
- Bind local JSON or fetched API data
- Define row/column/value/filter fields
- Cell customization: using cell template
- Performance guidance for large datasets

---

## 🛠️ Requirements
- Node.js 20+ and npm/yarn  
- Vue 3.x  
- @syncfusion/ej2-vue-pivotview and @syncfusion/ej2-pivotview (ensure license/trial)  
- Modern browser (Chrome/Edge/Firefox/Safari)

Suggested versions:
- vue: ^3.2.0  
- @syncfusion/ej2-vue-pivotview: *

---

## ⚙️ Installation
```bash
git clone https://github.com/SyncfusionExamples/vue3-pivottable-celltemplate.git
cd vue3-pivottable-celltemplate
npm install
npm run serve   # or `npm run dev` if using Vite
# open the shown localhost URL
```

---

## 🚀 Quick Start — Minimal examples

1) package.json (example)
```json
{
  "name": "vue3-pivottable-celltemplate",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "serve": "vue-cli-service serve",
    "build": "vue-cli-service build"
  },
  "dependencies": {
    "vue": "^3.2.0",
    "@syncfusion/ej2-vue-pivotview": "*"
  }
}
```

2) App.vue — cellTemplate
```vue
<template>
  <div id="app">
    <ejs-pivotview :dataSourceSettings="dataSourceSettings" height="500" :cellTemplate="cellTemplate" />
  </div>
</template>

<script setup>
import { ref } from 'vue';

const app = createApp();

  // Template declaration.
  var colVue = app.component("cellTemplate", {
    data() {
      return {
        data: {},
      };
    },
    methods: {
      getCellContent: function () {
        return '<span class="tempwrap sb-icon-neutral pv-icons"></span>';
      },
    },
    template: `<span class="template-wrap"><span class="tempwrap sb-icon-neutral pv-icons"></span></span>`,
  });

  export default {
    name: "App",
    components: {
      "ejs-pivotview": PivotViewComponent,
    },
    data() {
      return {
        dataSourceSettings: {
          dataSource:  [....]
        }
      }
    }
  } 
</script>

<style>
.cell-high { background:#e6fff2; padding:6px; }
.cell-low { background:#fff7f0; padding:6px; }
.badge { margin-left:6px; color:#f39c12; }
</style>
```

---

## 🏗️ Project Structure
- src/ — App.vue,
- public/ — static assets  
- package.json — dependencies & scripts  
- README.md, LICENSE

---

## 🔧 Best Practices
- For many cells, return sanitized HTML strings (faster than mounting components).  
- Aggregate server-side or use server-side pivoting for very large datasets.  
- Use CSS and inline SVG for small visuals (sparklines) to minimize JS overhead.  
- Avoid mounting heavy components per cell; unmount when cells are recycled.

---

## ❓ Troubleshooting
- Raw HTML displayed: ensure cellTemplate returns a string or mount safely.  
- Slow render for many cells: simplify templates or pre-aggregate.  
- Syncfusion license errors: verify package activation and matching versions.  
- CORS/API issues: enable CORS or use same-origin during testing.

---

## 🤝 Contributing
Please add CONTRIBUTING.md and CODE_OF_CONDUCT.md. Suggested minimal PR template:
```markdown
## Summary
- What changed?

## 📜 License & Support

This is a **commercial product** subject to the Syncfusion End User License Agreement (EULA).

**Free Community License** is available for qualifying users/organizations:  
- Annual gross revenue < $1 million USD  
- 5 or fewer total developers  
- 10 or fewer total employees  

The community license allows free use in both internal and commercial applications under these conditions.  
No registration or approval is required — just comply with the terms.

**Paid Licenses** are required for:  
- Larger organizations  
- Teams exceeding the community license limits  
- Priority support, custom patches, or on-premise deployment options  

Purchase options and pricing: https://www.syncfusion.com/sales/products  
30-day free trial (full features, no credit card required): https://www.syncfusion.com/downloads/essential-js2  
Community License details & FAQ: https://www.syncfusion.com/products/communitylicense  
Full EULA: https://www.syncfusion.com/eula/es/

© 2026 Syncfusion, Inc. All Rights Reserved.
