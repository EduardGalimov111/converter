# converter
converter
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Объединить JPG онлайн — бесплатно</title>

    <style>
        /* ---------- Глобальные стили ---------- */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
            background: #f8fafc;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 1.5rem 1rem 3rem;
            color: #0f172a;
        }

        .container {
            max-width: 960px;
            width: 100%;
            background: white;
            border-radius: 2rem;
            padding: 1.8rem 2rem 3rem;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.06);
        }

        /* ---------- Шапка / Меню ---------- */
        .header {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 1.8rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #e2e8f0;
        }

        .logo {
            font-size: 1.6rem;
            font-weight: 700;
            letter-spacing: -0.02em;
            display: flex;
            align-items: center;
            gap: 0.4rem;
        }

        .nav {
            display: flex;
            align-items: center;
            gap: 1.2rem;
            flex-wrap: wrap;
        }

        .nav a {
            color: #1e293b;
            text-decoration: none;
            font-weight: 500;
            font-size: 0.95rem;
            cursor: pointer;
            padding: 0.3rem 0.6rem;
            border-radius: 0.5rem;
            transition: background 0.15s;
        }

        .nav a:hover {
            background: #f1f5f9;
        }

        .lang-switch {
            display: flex;
            gap: 0.3rem;
            background: #f1f5f9;
            padding: 0.2rem;
            border-radius: 2rem;
        }

        .lang-btn {
            border: none;
            background: transparent;
            padding: 0.3rem 0.9rem;
            border-radius: 2rem;
            font-weight: 600;
            font-size: 0.85rem;
            cursor: pointer;
            transition: background 0.15s, color 0.15s;
            color: #475569;
        }

        .lang-btn.active {
            background: white;
            color: #0f172a;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
        }

        .lang-btn:hover:not(.active) {
            background: rgba(255, 255, 255, 0.5);
        }

        /* ---------- Заголовок ---------- */
        h1 {
            font-size: 2.2rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 0.3rem;
            letter-spacing: -0.02em;
        }

        .subhead {
            text-align: center;
            color: #475569;
            margin-bottom: 2rem;
            font-size: 1.05rem;
        }

        /* ---------- Зона загрузки ---------- */
        .drop-zone {
            border: 2.5px dashed #cbd5e1;
            border-radius: 1.5rem;
            padding: 3rem 1.5rem;
            text-align: center;
            cursor: pointer;
            transition: border-color 0.2s, background 0.2s;
            background: #fafcff;
            position: relative;
        }

        .drop-zone:hover,
        .drop-zone.drag-over {
            border-color: #3b82f6;
            background: #eff6ff;
        }

        .drop-zone .icon {
            font-size: 3.2rem;
            margin-bottom: 0.5rem;
        }

        .drop-zone p {
            font-size: 1.1rem;
            color: #334155;
            margin: 0.2rem 0;
        }

        .drop-zone .hint {
            font-size: 0.9rem;
            color: #94a3b8;
            margin-top: 0.3rem;
        }

        #fileInput {
            display: none;
        }

        /* ---------- Панель управления ---------- */
        .controls {
            display: flex;
            flex-wrap: wrap;
            gap: 1.5rem 2rem;
            margin: 1.8rem 0 2rem;
            padding: 1.2rem 1.5rem;
            background: #f1f5f9;
            border-radius: 1.2rem;
            align-items: center;
            justify-content: center;
        }

        .control-group {
            display: flex;
            align-items: center;
            gap: 0.6rem;
            flex-wrap: wrap;
        }

        .control-group label {
            font-weight: 500;
            font-size: 0.95rem;
            color: #1e293b;
        }

        .control-group select,
        .control-group input[type="number"],
        .control-group input[type="color"] {
            padding: 0.4rem 0.8rem;
            border: 1px solid #cbd5e1;
            border-radius: 0.6rem;
            background: white;
            font-size: 0.95rem;
            outline: none;
            transition: 0.15s;
        }

        .control-group select:focus,
        .control-group input:focus {
            border-color: #3b82f6;
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.15);
        }

        .control-group input[type="color"] {
            width: 44px;
            height: 44px;
            padding: 3px;
            border-radius: 50%;
            cursor: pointer;
        }

        .btn {
            padding: 0.6rem 1.8rem;
            border: none;
            border-radius: 2rem;
            font-weight: 600;
            font-size: 1rem;
            background: #3b82f6;
            color: white;
            cursor: pointer;
            transition: background 0.15s, transform 0.1s;
        }

        .btn:hover {
            background: #2563eb;
        }

        .btn:active {
            transform: scale(0.97);
        }

        .btn-danger {
            background: #ef4444;
        }

        .btn-danger:hover {
            background: #dc2626;
        }

        .btn-success {
            background: #22c55e;
        }

        .btn-success:hover {
            background: #16a34a;
        }

        /* ---------- Инструкция ---------- */
        .instructions {
            margin: 1.5rem 0 2rem;
            padding: 1.5rem;
            background: #f8fafc;
            border-radius: 1.2rem;
            border: 1px solid #e2e8f0;
            display: none; /* по умолчанию скрыта, показывается по клику */
        }

        .instructions.visible {
            display: block;
        }

        .instructions h3 {
            margin-bottom: 0.8rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .instructions ol {
            padding-left: 1.5rem;
            margin: 0.5rem 0;
            color: #1e293b;
        }

        .instructions ol li {
            margin-bottom: 0.4rem;
            line-height: 1.5;
        }

        /* ---------- Галерея превью ---------- */
        .preview-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
            margin: 1.2rem 0 1.8rem;
            justify-content: center;
            min-height: 80px;
            padding: 0.5rem;
            border-radius: 1rem;
            background: #fafcff;
            border: 1px solid #e2e8f0;
        }

        .preview-item {
            position: relative;
            width: 100px;
            height: 100px;
            border-radius: 0.8rem;
            overflow: hidden;
            border: 2px solid #e2e8f0;
            background: #f1f5f9;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: 0.15s;
        }

        .preview-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .preview-item .remove-btn {
            position: absolute;
            top: -6px;
            right: -6px;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            border: none;
            background: #ef4444;
            color: white;
            font-weight: 700;
            font-size: 14px;
            line-height: 1;
            cursor: pointer;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
            transition: 0.1s;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .preview-item .remove-btn:hover {
            background: #dc2626;
            transform: scale(1.05);
        }

        .preview-item .drag-handle {
            position: absolute;
            top: 4px;
            left: 4px;
            background: rgba(0, 0, 0, 0.5);
            color: white;
            border-radius: 4px;
            padding: 2px 6px;
            font-size: 12px;
            cursor: grab;
            user-select: none;
        }

        .preview-item.dragging {
            opacity: 0.4;
            border-color: #3b82f6;
        }

        .empty-preview {
            color: #94a3b8;
            padding: 1.5rem 0;
            font-size: 0.95rem;
        }

        /* ---------- Результат ---------- */
        .result-area {
            margin-top: 2rem;
            text-align: center;
            display: none;
        }

        .result-area.visible {
            display: block;
        }

        .result-area img {
            max-width: 100%;
            max-height: 70vh;
            border-radius: 1rem;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
            border: 1px solid #e2e8f0;
        }

        .result-actions {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin-top: 1.2rem;
            flex-wrap: wrap;
        }

        /* ---------- Адаптивность ---------- */
        @media (max-width: 640px) {
            .container {
                padding: 1.2rem;
            }
            h1 {
                font-size: 1.6rem;
            }
            .controls {
                flex-direction: column;
                align-items: stretch;
            }
            .control-group {
                justify-content: center;
            }
            .preview-item {
                width: 72px;
                height: 72px;
            }
            .header {
                flex-direction: column;
                align-items: stretch;
                gap: 0.8rem;
            }
            .nav {
                justify-content: space-between;
            }
        }
    </style>
</head>

<body>

    <div class="container">

        <!-- Шапка с меню -->
        <header class="header">
            <div class="logo">🖼️ <span data-i18n="title">Объединить JPG</span></div>
            <nav class="nav">
                <a id="instructionsToggle" data-i18n="menu.instructions">Инструкция</a>
                <div class="lang-switch">
                    <button class="lang-btn active" data-lang="ru">RU</button>
                    <button class="lang-btn" data-lang="en">EN</button>
                </div>
            </nav>
        </header>

        <h1 data-i18n="title">Объединить JPG</h1>
        <p class="subhead" data-i18n="subtitle">Загрузите несколько изображений и объедините их в один файл</p>

        <!-- Зона загрузки -->
        <div class="drop-zone" id="dropZone">
            <div class="icon">📤</div>
            <p data-i18n="dropZone"><strong>Перетащите файлы</strong> или кликните для выбора</p>
            <p class="hint" data-i18n="dropHint">Поддерживаются JPG, PNG, WEBP, GIF</p>
            <input type="file" id="fileInput" multiple accept="image/*" />
        </div>

        <!-- Блок инструкции -->
        <div class="instructions" id="instructionsBlock">
            <h3 data-i18n="instructions.title">📖 Как пользоваться</h3>
            <ol>
                <li data-i18n="instructions.step1">Загрузите изображения — перетащите файлы или кликните по области загрузки.</li>
                <li data-i18n="instructions.step2">Измените порядок — перетаскивайте миниатюры в галерее.</li>
                <li data-i18n="instructions.step3">Настройте макет, цвета и отступы.</li>
                <li data-i18n="instructions.step4">Нажмите «Объединить» и скачайте результат.</li>
            </ol>
        </div>

        <!-- Панель управления -->
        <div class="controls" id="controls">
            <div class="control-group">
                <label for="layoutSelect" data-i18n="controls.layout">Макет</label>
                <select id="layoutSelect">
                    <option value="horizontal" data-i18n="controls.horizontal">Горизонтальный</option>
                    <option value="vertical" data-i18n="controls.vertical">Вертикальный</option>
                </select>
            </div>

            <div class="control-group">
                <label for="borderColor" data-i18n="controls.borderColor">Цвет рамки</label>
                <input type="color" id="borderColor" value="#000000" />
            </div>

            <div class="control-group">
                <label for="borderWidth" data-i18n="controls.borderWidth">Толщина рамки (px)</label>
                <input type="number" id="borderWidth" value="2" min="0" max="50" step="1" />
            </div>

            <div class="control-group">
                <label for="spacing" data-i18n="controls.spacing">Отступ (px)</label>
                <input type="number" id="spacing" value="4" min="0" max="100" step="1" />
            </div>

            <button class="btn btn-success" id="mergeBtn" data-i18n="controls.merge">▶ Объединить</button>
            <button class="btn btn-danger" id="clearBtn" data-i18n="controls.clear">✕ Очистить</button>
        </div>

        <!-- Превью загруженных изображений -->
        <div class="preview-grid" id="previewGrid">
            <span class="empty-preview" data-i18n="preview.empty">Нет загруженных изображений</span>
        </div>

        <!-- Результат -->
        <div class="result-area" id="resultArea">
            <h3 style="margin-bottom: 0.8rem;" data-i18n="result.title">✅ Готово!</h3>
            <img id="resultImage" alt="Результат объединения" />
            <div class="result-actions">
                <button class="btn" id="downloadBtn" data-i18n="result.download">⬇ Скачать JPG</button>
                <button class="btn btn-danger" id="resetBtn" data-i18n="result.reset">↺ Начать заново</button>
            </div>
        </div>

    </div>

    <script>
        (function() {
            'use strict';

            // ----- ПЕРЕВОДЫ -----
            const translations = {
                ru: {
                    title: "Объединить JPG",
                    subtitle: "Загрузите несколько изображений и объедините их в один файл",
                    dropZone: "<strong>Перетащите файлы</strong> или кликните для выбора",
                    dropHint: "Поддерживаются JPG, PNG, WEBP, GIF",
                    controls: {
                        layout: "Макет",
                        horizontal: "Горизонтальный",
                        vertical: "Вертикальный",
                        borderColor: "Цвет рамки",
                        borderWidth: "Толщина рамки (px)",
                        spacing: "Отступ (px)",
                        merge: "▶ Объединить",
                        clear: "✕ Очистить"
                    },
                    preview: {
                        empty: "Нет загруженных изображений"
                    },
                    result: {
                        title: "✅ Готово!",
                        download: "⬇ Скачать JPG",
                        reset: "↺ Начать заново"
                    },
                    alerts: {
                        noImages: "Загрузите хотя бы 2 изображения для объединения.",
                        invalidFiles: "Пожалуйста, загрузите изображения в формате JPG, PNG, WEBP или GIF.",
                        mergeError: "Ошибка при объединении: ",
                        noResult: "Сначала объедините изображения."
                    },
                    instructions: {
                        title: "📖 Как пользоваться",
                        step1: "Загрузите изображения — перетащите файлы или кликните по области загрузки.",
                        step2: "Измените порядок — перетаскивайте миниатюры в галерее.",
                        step3: "Настройте макет, цвета и отступы.",
                        step4: "Нажмите «Объединить» и скачайте результат."
                    },
                    menu: {
                        instructions: "Инструкция"
                    }
                },
                en: {
                    title: "Merge JPG",
                    subtitle: "Upload several images and merge them into one file",
                    dropZone: "<strong>Drag & drop files</strong> or click to select",
                    dropHint: "Supports JPG, PNG, WEBP, GIF",
                    controls: {
                        layout: "Layout",
                        horizontal: "Horizontal",
                        vertical: "Vertical",
                        borderColor: "Border color",
                        borderWidth: "Border width (px)",
                        spacing: "Spacing (px)",
                        merge: "▶ Merge",
                        clear: "✕ Clear"
                    },
                    preview: {
                        empty: "No images uploaded"
                    },
                    result: {
                        title: "✅ Done!",
                        download: "⬇ Download JPG",
                        reset: "↺ Start over"
                    },
                    alerts: {
                        noImages: "Please upload at least 2 images to merge.",
                        invalidFiles: "Please upload images in JPG, PNG, WEBP or GIF format.",
                        mergeError: "Error while merging: ",
                        noResult: "Please merge images first."
                    },
                    instructions: {
                        title: "📖 How to use",
                        step1: "Upload images — drag & drop or click the upload area.",
                        step2: "Change order — drag thumbnails in the gallery.",
                        step3: "Adjust layout, colors and spacing.",
                        step4: "Click «Merge» and download the result."
                    },
                    menu: {
                        instructions: "Instructions"
                    }
                }
            };

            // ----- ТЕКУЩИЙ ЯЗЫК -----
            let currentLang = 'ru';

            // ----- ФУНКЦИЯ ПЕРЕВОДА -----
            function t(key) {
                const keys = key.split('.');
                let val = translations[currentLang];
                for (const k of keys) {
                    if (val && val[k] !== undefined) {
                        val = val[k];
                    } else {
                        return key;
                    }
                }
                return val;
            }

            // ----- ПРИМЕНЕНИЕ ПЕРЕВОДОВ НА СТРАНИЦУ -----
            function applyTranslations() {
                // Все элементы с data-i18n
                document.querySelectorAll('[data-i18n]').forEach(el => {
                    const key = el.getAttribute('data-i18n');
                    // Проверяем, является ли элемент input или select с option
                    if (el.tagName === 'INPUT' && el.type === 'button') {
                        // кнопки обрабатываем отдельно
                    } else if (el.tagName === 'OPTION') {
                        el.textContent = t(key);
                    } else if (el.tagName === 'BUTTON' && !el.classList.contains('lang-btn')) {
                        // обычные кнопки (не переключатели языка)
                        el.textContent = t(key);
                    } else if (el.tagName === 'LABEL') {
                        // label
                        el.textContent = t(key);
                    } else if (el.tagName === 'A') {
                        el.textContent = t(key);
                    } else {
                        // Для всех остальных (div, p, span, h1, h3, li)
                        el.innerHTML = t(key);
                    }
                });

                // Особые случаи: placeholder для инпутов? Нет.
                // Обновляем кнопки переключения языка (они не имеют data-i18n, но их текст фиксирован)
                // Также обновляем заголовок страницы
                document.title = t('title') + ' — бесплатно';

                // Обновить текст в пустом превью (если оно отображается)
                const emptyPreview = document.querySelector('.empty-preview');
                if (emptyPreview && document.querySelectorAll('.preview-item').length === 0) {
                    emptyPreview.innerHTML = t('preview.empty');
                }
            }

            // ----- ПЕРЕКЛЮЧЕНИЕ ЯЗЫКА -----
            function setLanguage(lang) {
                if (!translations[lang]) return;
                currentLang = lang;
                // Обновить активную кнопку
                document.querySelectorAll('.lang-btn').forEach(btn => {
                    btn.classList.toggle('active', btn.dataset.lang === lang);
                });
                // Применить переводы
                applyTranslations();
                // Сохранить в localStorage
                localStorage.setItem('lang', lang);
            }

            // ----- ИНИЦИАЛИЗАЦИЯ ЯЗЫКА -----
            function initLanguage() {
                // Проверяем localStorage
                let saved = localStorage.getItem('lang');
                if (saved && translations[saved]) {
                    setLanguage(saved);
                    return;
                }
                // Определяем язык браузера
                const browserLang = navigator.language.split('-')[0];
                if (browserLang === 'ru') {
                    setLanguage('ru');
                } else {
                    setLanguage('en');
                }
            }

            // ----- DOM-ссылки -----
            const dropZone = document.getElementById('dropZone');
            const fileInput = document.getElementById('fileInput');
            const previewGrid = document.getElementById('previewGrid');
            const mergeBtn = document.getElementById('mergeBtn');
            const clearBtn = document.getElementById('clearBtn');
            const resetBtn = document.getElementById('resetBtn');
            const downloadBtn = document.getElementById('downloadBtn');
            const resultArea = document.getElementById('resultArea');
            const resultImage = document.getElementById('resultImage');

            const layoutSelect = document.getElementById('layoutSelect');
            const borderColorInput = document.getElementById('borderColor');
            const borderWidthInput = document.getElementById('borderWidth');
            const spacingInput = document.getElementById('spacing');

            const instructionsToggle = document.getElementById('instructionsToggle');
            const instructionsBlock = document.getElementById('instructionsBlock');

            // ----- Состояние -----
            let imageFiles = [];
            let imageUrls = [];
            let mergedBlob = null;

            // ----- Вспомогательные функции -----
            function updatePreview() {
                previewGrid.innerHTML = '';
                if (imageFiles.length === 0) {
                    const empty = document.createElement('span');
                    empty.className = 'empty-preview';
                    empty.setAttribute('data-i18n', 'preview.empty');
                    empty.innerHTML = t('preview.empty');
                    previewGrid.appendChild(empty);
                    return;
                }

                imageFiles.forEach((file, index) => {
                    const url = imageUrls[index];
                    const div = document.createElement('div');
                    div.className = 'preview-item';
                    div.draggable = true;
                    div.dataset.index = index;

                    const img = document.createElement('img');
                    img.src = url;
                    img.alt = file.name;
                    div.appendChild(img);

                    const removeBtn = document.createElement('button');
                    removeBtn.className = 'remove-btn';
                    removeBtn.textContent = '×';
                    removeBtn.type = 'button';
                    removeBtn.addEventListener('click', (e) => {
                        e.stopPropagation();
                        removeImage(index);
                    });
                    div.appendChild(removeBtn);

                    const handle = document.createElement('span');
                    handle.className = 'drag-handle';
                    handle.textContent = '⠿';
                    div.appendChild(handle);

                    // Drag & Drop
                    div.addEventListener('dragstart', (e) => {
                        e.dataTransfer.setData('text/plain', index);
                        div.classList.add('dragging');
                    });
                    div.addEventListener('dragend', () => {
                        div.classList.remove('dragging');
                    });
                    div.addEventListener('dragover', (e) => {
                        e.preventDefault();
                    });
                    div.addEventListener('drop', (e) => {
                        e.preventDefault();
                        const fromIndex = parseInt(e.dataTransfer.getData('text/plain'), 10);
                        if (fromIndex !== index && !isNaN(fromIndex)) {
                            reorderImages(fromIndex, index);
                        }
                    });

                    previewGrid.appendChild(div);
                });
            }

            function removeImage(index) {
                if (index < 0 || index >= imageFiles.length) return;
                if (imageUrls[index]) {
                    URL.revokeObjectURL(imageUrls[index]);
                }
                imageFiles.splice(index, 1);
                imageUrls.splice(index, 1);
                updatePreview();
                hideResult();
            }

            function reorderImages(from, to) {
                if (from === to) return;
                const [file] = imageFiles.splice(from, 1);
                const [url] = imageUrls.splice(from, 1);
                imageFiles.splice(to, 0, file);
                imageUrls.splice(to, 0, url);
                updatePreview();
                hideResult();
            }

            function hideResult() {
                resultArea.classList.remove('visible');
                mergedBlob = null;
                resultImage.src = '';
            }

            function clearAll() {
                imageUrls.forEach(url => URL.revokeObjectURL(url));
                imageFiles = [];
                imageUrls = [];
                updatePreview();
                hideResult();
            }

            // ----- Загрузка файлов -----
            function handleFiles(files) {
                const allowed = ['image/jpeg', 'image/png', 'image/webp', 'image/gif'];
                const validFiles = [];
                for (const file of files) {
                    if (allowed.includes(file.type)) {
                        validFiles.push(file);
                    }
                }
                if (validFiles.length === 0) {
                    alert(t('alerts.invalidFiles'));
                    return;
                }
                for (const file of validFiles) {
                    imageFiles.push(file);
                    imageUrls.push(URL.createObjectURL(file));
                }
                updatePreview();
                hideResult();
            }

            // ----- События загрузки -----
            dropZone.addEventListener('click', () => fileInput.click());

            dropZone.addEventListener('dragover', (e) => {
                e.preventDefault();
                dropZone.classList.add('drag-over');
            });

            dropZone.addEventListener('dragleave', () => {
                dropZone.classList.remove('drag-over');
            });

            dropZone.addEventListener('drop', (e) => {
                e.preventDefault();
                dropZone.classList.remove('drag-over');
                if (e.dataTransfer.files.length) {
                    handleFiles(e.dataTransfer.files);
                }
            });

            fileInput.addEventListener('change', () => {
                if (fileInput.files.length) {
                    handleFiles(fileInput.files);
                }
                fileInput.value = '';
            });

            // ----- Очистка -----
            clearBtn.addEventListener('click', clearAll);

            // ----- Объединение -----
            async function mergeImages() {
                if (imageFiles.length < 2) {
                    alert(t('alerts.noImages'));
                    return;
                }

                mergeBtn.disabled = true;
                mergeBtn.textContent = currentLang === 'ru' ? '⏳ Обработка...' : '⏳ Processing...';

                try {
                    const layout = layoutSelect.value;
                    const borderColor = borderColorInput.value;
                    const borderWidth = parseInt(borderWidthInput.value, 10) || 0;
                    const spacing = parseInt(spacingInput.value, 10) || 0;

                    const images = await Promise.all(imageFiles.map((file) => loadImage(file)));

                    let totalWidth, totalHeight;
                    if (layout === 'horizontal') {
                        const totalImgWidth = images.reduce((sum, img) => sum + img.width, 0);
                        const totalSpacing = spacing * (images.length - 1);
                        totalWidth = totalImgWidth + totalSpacing + borderWidth * 2;
                        totalHeight = Math.max(...images.map(img => img.height)) + borderWidth * 2;
                    } else {
                        const totalImgHeight = images.reduce((sum, img) => sum + img.height, 0);
                        const totalSpacing = spacing * (images.length - 1);
                        totalHeight = totalImgHeight + totalSpacing + borderWidth * 2;
                        totalWidth = Math.max(...images.map(img => img.width)) + borderWidth * 2;
                    }

                    const canvas = document.createElement('canvas');
                    canvas.width = totalWidth;
                    canvas.height = totalHeight;
                    const ctx = canvas.getContext('2d');

                    ctx.fillStyle = borderColor;
                    ctx.fillRect(0, 0, totalWidth, totalHeight);

                    let x = borderWidth;
                    let y = borderWidth;

                    for (let i = 0; i < images.length; i++) {
                        const img = images[i];
                        if (layout === 'horizontal') {
                            ctx.drawImage(img, x, y + (totalHeight - borderWidth * 2 - img.height) / 2);
                            x += img.width + spacing;
                        } else {
                            ctx.drawImage(img, x + (totalWidth - borderWidth * 2 - img.width) / 2, y);
                            y += img.height + spacing;
                        }
                    }

                    mergedBlob = await new Promise((resolve) => {
                        canvas.toBlob((blob) => resolve(blob), 'image/jpeg', 0.92);
                    });

                    const url = URL.createObjectURL(mergedBlob);
                    resultImage.src = url;
                    resultArea.classList.add('visible');

                } catch (err) {
                    console.error(err);
                    alert(t('alerts.mergeError') + err.message);
                } finally {
                    mergeBtn.disabled = false;
                    mergeBtn.textContent = t('controls.merge');
                }
            }

            function loadImage(file) {
                return new Promise((resolve, reject) => {
                    const img = new Image();
                    img.onload = () => resolve(img);
                    img.onerror = () => reject(new Error(`Не удалось загрузить ${file.name}`));
                    img.src = URL.createObjectURL(file);
                    img.addEventListener('load', () => {
                        URL.revokeObjectURL(img.src);
                    }, { once: true });
                });
            }

            mergeBtn.addEventListener('click', mergeImages);

            // ----- Скачивание -----
            downloadBtn.addEventListener('click', () => {
                if (!mergedBlob) {
                    alert(t('alerts.noResult'));
                    return;
                }
                const link = document.createElement('a');
                link.href = URL.createObjectURL(mergedBlob);
                link.download = 'merged.jpg';
                document.body.appendChild(link);
                link.click();
                document.body.removeChild(link);
                setTimeout(() => URL.revokeObjectURL(link.href), 100);
            });

            // ----- Сброс -----
            resetBtn.addEventListener('click', () => {
                clearAll();
                window.scrollTo({ top: 0, behavior: 'smooth' });
            });

            // ----- Инструкция (показать/скрыть) -----
            let instructionsVisible = false;
            instructionsToggle.addEventListener('click', (e) => {
                e.preventDefault();
                instructionsVisible = !instructionsVisible;
                instructionsBlock.classList.toggle('visible', instructionsVisible);
                // Обновим текст ссылки? Не обязательно.
            });

            // ----- Переключение языка (кнопки) -----
            document.querySelectorAll('.lang-btn').forEach(btn => {
                btn.addEventListener('click', () => {
                    const lang = btn.dataset.lang;
                    setLanguage(lang);
                    // Обновить текст кнопок "Объединить", "Очистить", т.к. они меняют текст при обработке
                    // Но они обновятся через applyTranslations
                    // Также обновить текст кнопок в результате
                });
            });

            // ----- Инициализация -----
            initLanguage();
            updatePreview();

            // Для корректного обновления текста в кнопках после переключения языка
            // уже сделано в applyTranslations

            console.log('🖼️ JPG Merger готов к работе!');

        })();
    </script>

</body>
</html>
