# 🌽 @codecorn/prettier-guide-community 🌍

> Minimal, reliable Prettier setup for VSCode + npm + CI + Git hooks.  
> Keep it predictable, avoid noisy configs, and share with your team/community.

---

[![CODECORN - PRETTIER GUIDE](https://img.shields.io/badge/CODECORN-PRETTIER%20GUIDE-green?style=for-the-badge&logo=prettier)](#)
[![GitHub Stars](https://img.shields.io/github/stars/CodeCornTech/prettier-guide-community?style=for-the-badge&logo=github&label=stars&labelColor=000000&color=gold)](https://github.com/CodeCornTech/prettier-guide-community/stargazers)
[![Issues](https://img.shields.io/github/issues/CodeCornTech/prettier-guide-community?style=for-the-badge&logo=github&label=issues&labelColor=000000&color=orange)](https://github.com/CodeCornTech/prettier-guide-community/issues)
[![License](https://img.shields.io/github/license/CodeCornTech/prettier-guide-community?style=for-the-badge&label=license&labelColor=000000&color=gray)](./LICENSE)
![Prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=for-the-badge&logo=prettier&labelColor=000000)
![VSCode](https://img.shields.io/badge/Editor-VSCode-007ACC?style=for-the-badge&logo=visualstudiocode&labelColor=000000)

---

> ## [🇮🇹 Italiano](./docs/prettier-setup-IT.md) · [🇬🇧 English](./docs/prettier-setup-EN.md)

> If this guide helps you, **please leave a ⭐ star** and/or open a PR!  
> Se ti è utile, **lascia una ⭐** e/o proponi una PR!

---

## Quick Start

```bash
npm i -D prettier
npm set-script format "prettier --write ."
npm set-script "format:check" "prettier --check ."
```

Create `.prettierrc.json`:

```json
{
  "$schema": "https://json.schemastore.org/prettierrc",
  "tabWidth": 2,
  "useTabs": false,
  "printWidth": 100,
  "singleQuote": false,
  "trailingComma": "es5",
  "semi": true,
  "endOfLine": "lf"
}
```

VSCode (workspace): `.vscode/settings.json`

```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "prettier.requireConfig": true,
  "files.eol": "\n"
}
```

---

## 🌍 Languages / Lingue

🌐 🇮🇹 IT — 🇬🇧 EN
Want to add more languages? **Contributions are welcome!**

---

## 📝 License

MIT © [CodeCorn™](https://codecorn.it) — Distributed under the [MIT](./LICENSE) license.

---

### ⭐ Support the Project

If this guide helped you, **leave a star ⭐ on GitHub** and help us grow the CodeCorn community!

[![GitHub Stars](https://img.shields.io/github/stars/CodeCornTech/prettier-guide-community?style=for-the-badge&logo=github&label=stars&labelColor=000000&color=gold)](https://github.com/CodeCornTech/prettier-guide-community/stargazers)
[![Forks](https://img.shields.io/github/forks/CodeCornTech/prettier-guide-community?style=for-the-badge&logo=github&label=forks&labelColor=000000&color=blue)](https://github.com/CodeCornTech/prettier-guide-community/fork)

---

## 🧭 Maintainer

<div style="display: flex; justify-content: space-between; align-items: center;"> 
  <div> 
    <p><strong>👨‍💻 Federico Girolami</strong></p> 
    <p><strong>Full Stack Developer</strong> | <strong>System Integrator</strong> | <strong>Digital Solution Architect</strong> 🚀</p> 
    <p>📫 <strong>Get in Touch</strong></p> 
    <p>🌐 <strong>Website</strong>: <a href="https://codecorn.it">codecorn.it</a> *(Under Construction)*</p> 
    <p>📧 <strong>Email</strong>: <a href="mailto:f.girolami@codecorn.it">f.girolami@codecorn.it</a></p> 
    <p>🐙 <strong>GitHub</strong>: <a href="https://github.com/fgirolami29">github.com/fgirolami29</a></p> 
  </div> 
  <div style="text-align: center;">
    <a href="https://www.codecorn.it"> 
      <img src="https://codecorn.it/wp-content/uploads/2025/05/CODECORN-trasp-qhite.png" alt="Code Corn Logo"  width="250px" height="90px" style="margin-top:0;margin-bottom:20px;"/>
    </a> 
    <a href="https://github.com/fgirolami29"> 
      <img src="https://avatars.githubusercontent.com/u/68548715?s=200&v=4" alt="Federico Girolami Avatar" style="border-radius: 50%; width: 125px; height: 125px;border: 5px solid gold" /> 
    </a> 
  </div> 
</div>
