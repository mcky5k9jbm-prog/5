<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Каталог образовательных сервисов для школьников">
    <title>Цифровой навигатор школьника</title>
    <style>
/* ===== Base & Variables ===== */
:root {
  --bg: #fdf2f8;
  --bg-card: #ffffff;
  --text: #1a2332;
  --text-muted: #6b5a6a;
  --primary: #db2777;
  --primary-dark: #be185d;
  --primary-light: #fce7f3;
  --accent: #ec4899;
  --border: #f3e8ef;
  --shadow: 0 4px 20px rgba(219, 39, 119, 0.08);
  --shadow-hover: 0 8px 30px rgba(219, 39, 119, 0.14);
  --radius: 14px;
  --font: "Segoe UI", system-ui, -apple-system, BlinkMacSystemFont, "Roboto", "Helvetica Neue", Arial, sans-serif;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: var(--font);
  background: var(--bg);
  color: var(--text);
  line-height: 1.6;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

body::before {
  content: "";
  position: fixed;
  inset: 0;
  background-image:
    radial-gradient(circle at 20% 20%, rgba(219, 39, 119, 0.05) 0%, transparent 40%),
    radial-gradient(circle at 80% 70%, rgba(236, 72, 153, 0.06) 0%, transparent 45%);
  pointer-events: none;
  z-index: -1;
}

.container {
  width: 100%;
  max-width: 960px;
  margin: 0 auto;
  padding: 0 1.25rem;
}

/* ===== Header ===== */
.site-header {
  background: linear-gradient(135deg, #9d174d 0%, #db2777 45%, #ec4899 100%);
  color: #fff;
  padding: 2.75rem 0 2.5rem;
  position: relative;
  overflow: hidden;
}

.site-header::after {
  content: "";
  position: absolute;
  bottom: -1px;
  left: 0;
  right: 0;
  height: 40px;
  background: var(--bg);
  border-radius: 50% 50% 0 0 / 100% 100% 0 0;
}

.site-header .container {
  position: relative;
  z-index: 1;
}

.eyebrow {
  display: inline-block;
  font-size: 0.8rem;
  font-weight: 600;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  background: rgba(255, 255, 255, 0.18);
  padding: 0.3rem 0.75rem;
  border-radius: 999px;
  margin-bottom: 0.9rem;
  backdrop-filter: blur(4px);
}

.site-header h1 {
  font-size: clamp(1.75rem, 4vw, 2.35rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 0.6rem;
  line-height: 1.25;
}

.subtitle {
  font-size: 1.05rem;
  opacity: 0.92;
  max-width: 540px;
  line-height: 1.55;
}

/* ===== Main ===== */
main {
  flex: 1;
  padding: 1.5rem 0 3rem;
}

.intro {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  gap: 1rem;
  margin-bottom: 1.5rem;
  flex-wrap: wrap;
}

.intro h2 {
  font-size: 1.35rem;
  font-weight: 700;
  color: var(--text);
  margin-bottom: 0.25rem;
}

.intro p {
  color: var(--text-muted);
  font-size: 0.95rem;
}

.count {
  background: var(--primary-light);
  color: var(--primary-dark);
  font-size: 0.85rem;
  font-weight: 600;
  padding: 0.35rem 0.85rem;
  border-radius: 999px;
  white-space: nowrap;
}

/* ===== Table ===== */
.table-wrapper {
  background: var(--bg-card);
  border-radius: var(--radius);
  box-shadow: var(--shadow);
  border: 1px solid var(--border);
  overflow: hidden;
}

table {
  width: 100%;
  border-collapse: collapse;
  font-size: 0.95rem;
}

thead {
  background: linear-gradient(180deg, #fdf2f8 0%, #fce7f3 100%);
}

th {
  text-align: left;
  padding: 0.95rem 1.1rem;
  font-weight: 600;
  font-size: 0.8rem;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  color: var(--text-muted);
  border-bottom: 2px solid var(--border);
}

td {
  padding: 1rem 1.1rem;
  border-bottom: 1px solid var(--border);
  vertical-align: middle;
}

tbody tr:last-child td {
  border-bottom: none;
}

tbody tr {
  transition: background 0.18s ease;
}

tbody tr:hover {
  background: #fdf2f8;
}

td:first-child {
  font-weight: 600;
  color: var(--primary);
  width: 3rem;
  text-align: center;
}

.service-name {
  font-weight: 600;
  color: var(--text);
}

a {
  color: var(--primary);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.15s ease;
  border-bottom: 1.5px solid transparent;
}

a:hover {
  color: var(--primary-dark);
  border-bottom-color: var(--primary);
}

a:focus-visible {
  outline: 2px solid var(--primary);
  outline-offset: 3px;
  border-radius: 2px;
}

td:last-child {
  color: var(--text-muted);
  font-size: 0.9rem;
  max-width: 280px;
}

/* ===== Footer ===== */
.site-footer {
  background: #831843;
  color: #f9a8d4;
  padding: 1.4rem 0;
  text-align: center;
  font-size: 0.9rem;
}

/* ===== Accessibility ===== */
.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

/* ===== Responsive: Card layout on mobile ===== */
@media (max-width: 720px) {
  .site-header {
    padding: 2.2rem 0 2.8rem;
  }

  .site-header::after {
    height: 28px;
  }

  thead {
    display: none;
  }

  table,
  tbody,
  tr,
  td {
    display: block;
    width: 100%;
  }

  tr {
    padding: 1.1rem 1.15rem;
    border-bottom: 1px solid var(--border);
  }

  tr:last-child {
    border-bottom: none;
  }

  td {
    padding: 0.3rem 0;
    border: none;
    display: flex;
    gap: 0.5rem;
  }

  td:first-child {
    width: auto;
    text-align: left;
    font-size: 0.8rem;
    color: var(--text-muted);
    margin-bottom: 0.15rem;
  }

  td:first-child::before {
    content: attr(data-label) ": ";
    font-weight: 500;
  }

  td:not(:first-child)::before {
    content: attr(data-label);
    font-weight: 600;
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.03em;
    color: var(--text-muted);
    min-width: 5.5rem;
    flex-shrink: 0;
  }

  .service-name {
    font-size: 1.05rem;
  }

  td:last-child {
    max-width: none;
    margin-top: 0.25rem;
  }

  .intro {
    margin-bottom: 1.25rem;
  }
}

@media (max-width: 400px) {
  td:not(:first-child) {
    flex-direction: column;
    gap: 0.15rem;
  }

  td:not(:first-child)::before {
    min-width: auto;
  }
}
    </style>
</head>
<body>
    <header class="site-header">
        <div class="container">
            <p class="eyebrow">Полезные ресурсы для учёбы</p>
            <h1>Цифровой навигатор школьника</h1>
            <p class="subtitle">
                Подборка онлайн-сервисов для школьников: электронные журналы,
                подготовка к ОГЭ и ЕГЭ, интерактивные курсы и онлайн-школы.
            </p>
        </div>
    </header>

    <main class="container">
        <section class="intro" aria-labelledby="services-title">
            <div>
                <h2 id="services-title">Сервисы для школьников</h2>
                <p>Нажмите на название сервиса, чтобы открыть его сайт.</p>
            </div>
            <span class="count">7 сервисов</span>
        </section>

        <div class="table-wrapper">
            <table>
                <caption class="visually-hidden">Список образовательных сервисов, ссылки и их назначение</caption>
                <thead>
                    <tr>
                        <th scope="col">№</th>
                        <th scope="col">Сервис</th>
                        <th scope="col">Ссылка</th>
                        <th scope="col">Назначение</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td data-label="№">1</td>
                        <td data-label="Сервис" class="service-name">ЦОП ХМАО</td>
                        <td data-label="Ссылка">
                            <a href="https://cop-admhmao.ru/" target="_blank" rel="noopener noreferrer">
                                cop-admhmao.ru
                            </a>
                        </td>
                        <td data-label="Назначение">Электронный журнал ХМАО</td>
                    </tr>
                    <tr>
                        <td data-label="№">2</td>
                        <td data-label="Сервис" class="service-name">Решу ОГЭ</td>
                        <td data-label="Ссылка">
                            <a href="https://oge.sdamgia.ru/" target="_blank" rel="noopener noreferrer">
                                oge.sdamgia.ru
                            </a>
                        </td>
                        <td data-label="Назначение">Подготовка к ОГЭ, генератор вариантов</td>
                    </tr>
                    <tr>
                        <td data-label="№">3</td>
                        <td data-label="Сервис" class="service-name">Решу ЕГЭ</td>
                        <td data-label="Ссылка">
                            <a href="https://rus-ege.sdamgia.ru/" target="_blank" rel="noopener noreferrer">
                                rus-ege.sdamgia.ru
                            </a>
                        </td>
                        <td data-label="Назначение">Подготовка к ЕГЭ, генератор вариантов</td>
                    </tr>
                    <tr>
                        <td data-label="№">4</td>
                        <td data-label="Сервис" class="service-name">Учи.ру</td>
                        <td data-label="Ссылка">
                            <a href="https://uchi.ru/" target="_blank" rel="noopener noreferrer">
                                uchi.ru
                            </a>
                        </td>
                        <td data-label="Назначение">
                            Образовательная онлайн-платформа для школьников, их родителей и учителей,
                            интерактивные курсы
                        </td>
                    </tr>
                    <tr>
                        <td data-label="№">5</td>
                        <td data-label="Сервис" class="service-name">Умскул</td>
                        <td data-label="Ссылка">
                            <a href="https://umschool.net/" target="_blank" rel="noopener noreferrer">
                                umschool.net
                            </a>
                        </td>
                        <td data-label="Назначение">Онлайн-школа</td>
                    </tr>
                    <tr>
                        <td data-label="№">6</td>
                        <td data-label="Сервис" class="service-name">ЦОС «Моя школа»</td>
                        <td data-label="Ссылка">
                            <a href="https://www.gosuslugi.ru/myschool" target="_blank" rel="noopener noreferrer">
                                gosuslugi.ru/myschool
                            </a>
                        </td>
                        <td data-label="Назначение">
                            Государственный сервис, электронный дневник, расписание,
                            домашние задания, успеваемость
                        </td>
                    </tr>
                    <tr>
                        <td data-label="№">7</td>
                        <td data-label="Сервис" class="service-name">Егэленд</td>
                        <td data-label="Ссылка">
                            <a href="https://el-ed.ru/" target="_blank" rel="noopener noreferrer">
                                el-ed.ru
                            </a>
                        </td>
                        <td data-label="Назначение">Онлайн-школа для подготовки к ЕГЭ и ОГЭ</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </main>

    <footer class="site-footer">
        <div class="container">
            <p>Образовательные сервисы &copy; 2026</p>
        </div>
    </footer>
</body>
</html>