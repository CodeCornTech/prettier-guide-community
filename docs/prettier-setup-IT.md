# Guida Prettier — Setup Pulito e Affidabile (IT)

> Configurazione minimale, prevedibile e coerente per Prettier (VSCode + npm + CI).<br>
> Evita conflitti, ignora solo ciò che serve e standardizza tra i repo.

---

[![CODECORN - PRETTIER GUIDE](https://img.shields.io/badge/CODECORN-PRETTIER%20GUIDE-green?style=for-the-badge&logo=prettier)](#)
[![GitHub Stars](https://img.shields.io/github/stars/fgirolami29/prettier-guide-community?style=for-the-badge&logo=github)](https://github.com/fgirolami29/prettier-guide-community/stargazers)
[![Open Issues](https://img.shields.io/github/issues/fgirolami29/prettier-guide-community?style=for-the-badge&logo=github)](https://github.com/fgirolami29/prettier-guide-community/issues)
[![License](https://img.shields.io/github/license/fgirolami29/prettier-guide-community?style=for-the-badge)](../LICENSE)
![Prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=for-the-badge&logo=prettier&labelColor=000000)
![VSCode](https://img.shields.io/badge/Editor-VSCode-007ACC?style=for-the-badge&logo=visualstudiocode&labelColor=000000)

---

> Se la guida ti è utile, **lascia una ⭐** e/o apri una PR!

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

## Come ignorare (correttamente)

- **Una riga**

  ```js
  // prettier-ignore
  const x={a:1,b:2}
  ```

- **Un blocco**

  ```js
  // prettier-ignore-start
  function demo() {
    return 1;
  }
  const x = { a: 1, b: 2 };
  // prettier-ignore-end
  ```

- **Tutto il file** (prima riga assoluta)

  ```js
  // prettier-ignore-file
  ```

> In JS/TS usa `//` (non `/* */`). Evita _Format Selection_ se vuoi rispettare gli ignore: usa **Format on Save** / **Format Document**.

## ESLint (opzionale)

```bash
npm i -D eslint-config-prettier eslint-plugin-prettier
```

`.eslintrc` minimale:

```json
{
  "extends": ["eslint:recommended", "plugin:prettier/recommended"]
}
```

## CI (GitHub Actions, opzionale)

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

## Troubleshooting rapido

1. In basso a destra devi vedere **Prettier** come formatter.
2. `prettier.requireConfig: true` → serve una `.prettierrc` vicina.
3. `.editorconfig` può sovrascrivere EOL/indent: allinealo o rimuovilo.
4. Disattiva altri formatter concorrenti (Beautify, Biome/Rome, ESLint formatter).
5. Parser auto: JS/TS → `babel`/`babel-ts`; HTML/CSS/JSON/MD built-in.
6. Non formattare file fuori workspace o in subfolder con altre config.

Buon lavoro! 🚀

## 🌍 Lingue

🌐 🇮🇹 IT — 🇬🇧 EN
Vuoi aggiungere altre lingue? **Contribuisci con una PR!**

## 📝 Licenza

MIT © [CodeCorn™](https://codecorn.it) — Distribuito sotto licenza [MIT](../LICENSE).

### ⭐ Supporto

Se la guida ti è stata utile, **metti una stella** e condividila con il tuo team.

### 🤝 Contribuire

## PR benvenute. Apri una issue per proposte/bug. Grazie!

[![GitHub Stars](https://img.shields.io/github/stars/CodeCornTech/prettier-guide-community?style=for-the-badge&logo=github&label=stars&labelColor=000000&color=gold)](https://github.com/CodeCornTech/prettier-guide-community/stargazers)
[![Forks](https://img.shields.io/github/forks/CodeCornTech/prettier-guide-community?style=for-the-badge&logo=github&label=forks&labelColor=000000&color=blue)](https://github.com/CodeCornTech/prettier-guide-community/fork)

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
