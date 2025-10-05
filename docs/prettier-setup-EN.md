# 🌽 @codecorn/prettier-guide-community 🌍

> 🪶 Minimal, reliable Prettier setup for VSCode + npm + CI + Git hooks.  
> Predictable formatting, zero noise, team-friendly and community-driven. <br>
> Avoid conflicts, ignore only what’s necessary, and standardize across repos.

---

[![CODECORN - PRETTIER GUIDE](https://img.shields.io/badge/CODECORN-PRETTIER%20GUIDE-green?style=for-the-badge&logo=prettier)](#)
[![GitHub Stars](https://img.shields.io/github/stars/CodeCornTech/prettier-guide-community?style=for-the-badge&logo=github&label=stars&labelColor=000000&color=gold)](https://github.com/CodeCornTech/prettier-guide-community/stargazers)
[![Issues](https://img.shields.io/github/issues/CodeCornTech/prettier-guide-community?style=for-the-badge&logo=github&label=issues&labelColor=000000&color=orange)](https://github.com/CodeCornTech/prettier-guide-community/issues)
[![License](https://img.shields.io/github/license/CodeCornTech/prettier-guide-community?style=for-the-badge&label=license&labelColor=000000&color=gray)](./LICENSE)
![Prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=for-the-badge&logo=prettier&labelColor=000000)
![VSCode](https://img.shields.io/badge/Editor-VSCode-007ACC?style=for-the-badge&logo=visualstudiocode&labelColor=000000)

> If this guide helps you, **please leave a ⭐ star** and/or open a PR!

## TL;DR

```bash
npm i -D prettier
npm set-script format "prettier --write ."
npm set-script "format:check" "prettier --check ."
```

`.prettierrc.json`

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

`.prettierignore`

```
node_modules
dist
build
coverage
.vscode
.DS_Store
```

`.vscode/settings.json`

```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "prettier.requireConfig": true,
  "files.eol": "\n"
}
```

## Properly ignoring

- **Single line**

  ```js
  // prettier-ignore
  const x={a:1,b:2}
  ```

- **Block**

  ```js
  // prettier-ignore-start
  function demo() {
    return 1;
  }
  const x = { a: 1, b: 2 };
  // prettier-ignore-end
  ```

- **Whole file** (must be first line)

  ```js
  // prettier-ignore-file
  ```

> For JS/TS use `//` (not `/* */`). Avoid _Format Selection_ if you rely on ignores: prefer **Format on Save** / **Format Document**.

## ESLint (optional)

```bash
npm i -D eslint-config-prettier eslint-plugin-prettier
```

Minimal `.eslintrc`:

```json
{
  "extends": ["eslint:recommended", "plugin:prettier/recommended"]
}
```

## CI (GitHub Actions, optional)

`.github/workflows/prettier.yml`

```yaml
name: Prettier
on: { pull_request: {}, push: { branches: [main] } }
jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 20 }
      - run: npm ci || npm i
      - run: npm run format:check
```

## Quick troubleshooting

1. Status bar should show **Prettier** as the formatter.
2. With `prettier.requireConfig: true` you need a nearby `.prettierrc`.
3. `.editorconfig` may override EOL/indent — align or remove it.
4. Disable competing formatters (Beautify, Biome/Rome, ESLint formatter).
5. Parsers are auto-detected (JS/TS → `babel`/`babel-ts`; HTML/CSS/JSON/MD built-in).
6. Don’t format files outside workspace or in subfolders with different configs.

Happy formatting! 🚀

## 🌍 Languages

🌐 🇮🇹 IT — 🇬🇧 EN
Want to add more languages? **Contributions are welcome!**

## 📝 License

MIT © [CodeCorn™](https://codecorn.it) — Distributed under the [MIT](../LICENSE) license.

### ⭐ Support

If this was useful, **star the repo** and share it with your team.

### 🤝 Contribute

PRs welcome. Open an issue for proposals/bugs. Thanks!

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
