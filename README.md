# Instructions

> **NOTE:** Подробности для разных ОС смотрите в документации расширения [Custom CSS and JS Loader](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css).

VS Code settings JSON, CSS и JS для минималистичной IDE. Настроено под экран 2560×1440 (100%).

1. Установите расширение **Custom CSS and JS Loader** (`be5invis.vscode-custom-css`) и шрифты [Geist Mono](https://vercel.com/font) и [Monaspace Radon](https://monaspace.githubnext.com/).
2. Скопируйте нужные строки из [`settings.json`](settings.json) в свой `settings.json` (`Ctrl+Shift+P` → *Preferences: Open User Settings (JSON)*).
3. Добавьте массив `vscode_custom_css.imports` с путями к файлам [`custom-vscode.css`](custom-vscode.css) и [`vscode-script.js`](vscode-script.js):

   ```jsonc
   // For Windows
   "vscode_custom_css.imports": [
       "file:///C:/Users/YOUR_NAME/custom-vscode.css",
       "file:///C:/Users/YOUR_NAME/vscode-script.js"
   ]

   // For Mac or Linux
   // "vscode_custom_css.imports": [
   //     "file:///Users/YOUR_NAME/custom-vscode.css",
   //     "file:///Users/YOUR_NAME/vscode-script.js"
   // ]
   ```

4. Если VS Code установлен в защищённую папку, запустите его от администратора (Windows). На Mac и Linux выдайте себе права на папку с VS Code:

   ```bash
   sudo chown -R $(whoami) "/Applications/Visual Studio Code.app/Contents/Resources/app/out"
   ```

   Замените путь на свой, если VS Code стоит в другом месте.
5. Включите расширение: `Ctrl+Shift+P` → **Enable Custom CSS and JS**.
6. При желании подправьте CSS и JS под себя. Размеры шрифтов и логотипа для своего разрешения лежат в конце `custom-vscode.css` (блок `Scaling for 2560x1440`).
7. Перезагрузите: `Ctrl+Shift+P` → **Reload Custom CSS and JS**. После каждого обновления VS Code это нужно повторять. Сообщение «установка повреждена» ожидаемо, его можно закрыть.

`art.svg` — арт, который показывается на пустом экране редактора (внутри CSS он вшит в `.letterpress`).
