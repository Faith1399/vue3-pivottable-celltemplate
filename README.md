# 🧾 Vue 3 — Syncfusion PivotView cellTemplate (Vue CLI) Quick Start

[![License](https://img.shields.io/github/license/SyncfusionExamples/vue3-pivottable-celltemplate)](./LICENSE) [![Last Commit](https://img.shields.io/github/last-commit/SyncfusionExamples/vue3-pivottable-celltemplate)]() [![Top Language](https://img.shields.io/github/languages/top/SyncfusionExamples/vue3-pivottable-celltemplate)]()

_Last updated: 2026-02-03_

---

## 📚 Table of Contents
- 🔎 Overview
- ✨ Features
- 🛠️ Requirements
- ⚙️ Installation
- 🚀 Quick Start
- 🏗️ Project Structure
- 🔧 Best Practices
- ❓ Troubleshooting
- 🤝 Contributing
- 🔎 SEO & Metadata

---

## 🔎 Overview
Demonstrates integrating Syncfusion PivotView (Pivot Table) with a custom cellTemplate in a Vue 3 app (Vue CLI). Shows binding JSON data, defining row/column/value/filter fields, sizing the PivotView, and customizing cells by inserting templates.

---

## ✨ Features
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

## Checklist
- [ ] Tested locally
- [ ] Updated docs
- [ ] Linked issue (if any)
```

---

## 🔎 SEO & GitHub Metadata
Suggested repo description (<=160 chars):  
"Vue 3 demo showing Syncfusion PivotView cellTemplate usage for custom pivot cell rendering and conditional formatting."

Suggested topics:  
vue3, syncfusion, pivotview, pivot-table, cell-template, javascript, typescript, vue-cli, analytics, dashboard

Suggested hashtags:  
#VueJS #Syncfusion #PivotTable #PivotView #DataViz #Dashboard #JavaScript #TypeScript

Recommended badges:
```markdown
[![License](https://img.shields.io/github/license/SyncfusionExamples/vue3-pivottable-celltemplate)](./LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/SyncfusionExamples/vue3-pivottable-celltemplate)]()
[![Top Language](https://img.shields.io/github/languages/top/SyncfusionExamples/vue3-pivottable-celltemplate)]()
```

---

## 📌 Next steps
- Add sample dataset (JSON/CSV) and screenshots/GIFs.  
- Add CONTRIBUTING.md, CODE_OF_CONDUCT.md, CI with badge, and issue/PR templates.  
- Publish a live demo for faster adoption.
