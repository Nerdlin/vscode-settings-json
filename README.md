<div align="center">

<img src="art.svg" alt="Стек технологий" width="620"/>

# 🌑 vscode-settings-json

**Тёмная минималистичная настройка VS Code**
`settings.json` · кастомный CSS · кастомный JS

![VS Code](https://img.shields.io/badge/VS%20Code-minimal-5D6E7A?logo=visualstudiocode&logoColor=white)
![Шрифт](https://img.shields.io/badge/шрифт-Geist%20Mono-bc9abc)
![Экран](https://img.shields.io/badge/экран-2560%C3%971440-008c7d)
![Платформы](https://img.shields.io/badge/Windows%20%7C%20macOS%20%7C%20Linux-4f5971)

</div>

---

## ✨ Что получится

- 🔤 **Типографика** — `Geist Mono` везде, комментарии курсивом в `Monaspace Radon`.
- 🗂️ **Сайдбар справа**, панель действий сверху, выбранный файл подсвечен, заголовки в сиреневых тонах.
- 🔍 **Палитра команд** со стеклянным градиентом, скруглениями и размытием фона.
- 💬 **Подсказки при наведении** — без рамок, с мягким градиентом.
- 🖼️ **Пустой экран** — крупный арт [`art.svg`](art.svg) вместо логотипа VS Code.
- 🔇 **«Тишина» интерфейса** — без минимапы, номеров строк, breadcrumbs, лампочек и лишних подсветок.
- 🖥️ **Подогнано под 2560×1440 (100%)** — размеры заданы в `px`.

## 📦 Что в репозитории

| Файл | Назначение |
| :-- | :-- |
| [`settings.json`](settings.json) | Пользовательские настройки VS Code |
| [`custom-vscode.css`](custom-vscode.css) | Стили интерфейса |
| [`vscode-script.js`](vscode-script.js) | Размытие фона при открытии палитры команд |
| [`art.svg`](art.svg) | Арт для пустого экрана редактора |

> [!NOTE]
> Расширение **Custom CSS and JS Loader** меняет файлы самого VS Code. Подробности для разных ОС — в [документации расширения](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css).

## 🚀 Установка

**1. Установите расширение и шрифты**
[Custom CSS and JS Loader](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css) (`be5invis.vscode-custom-css`), [Geist Mono](https://vercel.com/font) и [Monaspace Radon](https://monaspace.githubnext.com/).

**2. Скопируйте настройки**
Перенесите нужные строки из [`settings.json`](settings.json) в свой: `Ctrl+Shift+P` → *Preferences: Open User Settings (JSON)*.

**3. Укажите пути к CSS и JS**
Положите `custom-vscode.css` и `vscode-script.js` в домашнюю папку и добавьте в настройки:

```jsonc
// Windows
"vscode_custom_css.imports": [
    "file:///C:/Users/ВАШЕ_ИМЯ/custom-vscode.css",
    "file:///C:/Users/ВАШЕ_ИМЯ/vscode-script.js"
]

// macOS / Linux
// "vscode_custom_css.imports": [
//     "file:///Users/ВАШЕ_ИМЯ/custom-vscode.css",
//     "file:///Users/ВАШЕ_ИМЯ/vscode-script.js"
// ]
```

**4. Права на файлы VS Code**
- *Windows* — запустите VS Code от имени администратора, если он установлен в защищённую папку.
- *macOS / Linux* — выдайте себе права на папку приложения (путь замените на свой):

  ```bash
  sudo chown -R $(whoami) "/Applications/Visual Studio Code.app/Contents/Resources/app/out"
  ```

**5. Включите расширение**
`Ctrl+Shift+P` → **Enable Custom CSS and JS**

**6. Подправьте под себя** *(по желанию)*
Размеры шрифтов и логотипа лежат в конце `custom-vscode.css`, в блоке `Scaling for 2560x1440`:

```css
.monaco-workbench .part.statusbar { font-size: 13px !important; }
.letterpress { width: min(1100px, 80%) !important; }  /* размер арта на пустом экране */
```

**7. Перезагрузите**
`Ctrl+Shift+P` → **Reload Custom CSS and JS**

> [!TIP]
> После каждого обновления VS Code шаг 7 нужно повторить. Сообщение «установка повреждена» — ожидаемо, его можно закрыть.

## 🧩 Как это работает

- CSS переопределяет внутренние классы Workbench и Monaco, поэтому после крупных обновлений VS Code часть селекторов может устареть.
- Арт на пустом экране — класс `.letterpress` со вшитым SVG. Чтобы заменить, подставьте свой SVG в `background-image`.
- `vscode-script.js` следит за `.quick-input-widget` и добавляет или убирает слой `#command-blur`.
- Расширения из `settings.json` (Prettier, Tailwind CSS, Intelephense, Vetur, Material Icon Theme, CodeSnap) нужно ставить отдельно.

---

<div align="center">

Сделано с ♥ · [@Nerdlin](https://github.com/Nerdlin)

</div>
