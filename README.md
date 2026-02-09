---
title: "Такса — роскошь в миниатюре"
description: "Стильная одностраничная markdown-страница в чёрно‑золотых тонах про такс."
---

<!--
  Черно‑золотая "lux" тема в одном .md файле.
  Подходит для GitHub Pages, Obsidian, mkdocs-material, Docusaurus (MD/MDX) и большинства рендереров,
  которые разрешают HTML внутри Markdown. Если ваш рендерер запрещает <style>, перенесите CSS в отдельный файл.
-->

<style>
  :root{
    --bg-0:#050506;
    --bg-1:#0b0b10;
    --ink:#f3f2f6;
    --muted:#b9b7c3;
    --gold:#d7b35a;
    --gold-2:#f6e27a;
    --line:rgba(215,179,90,.22);
    --glass:rgba(255,255,255,.03);
    --shadow: 0 18px 60px rgba(0,0,0,.55);
    --radius: 18px;
  }

  /* базовая типографика */
  body{
    background: radial-gradient(1200px 800px at 15% 0%, rgba(215,179,90,.10), transparent 60%),
                radial-gradient(1000px 700px at 95% 15%, rgba(246,226,122,.08), transparent 55%),
                linear-gradient(180deg, var(--bg-0), var(--bg-1));
    color: var(--ink);
  }

  /* контейнер */
  .lux-wrap{
    max-width: 980px;
    margin: 0 auto;
    padding: 28px 18px 60px;
    font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, "Helvetica Neue", Arial;
    line-height: 1.6;
  }

  /* карточки */
  .lux-card{
    background: linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,.02));
    border: 1px solid var(--line);
    border-radius: var(--radius);
    box-shadow: var(--shadow);
    padding: 22px 22px;
  }

  /* header */
  .lux-hero{
    position: relative;
    overflow: hidden;
    padding: 28px 26px 24px;
  }
  .lux-hero::before{
    content:"";
    position:absolute; inset:-2px;
    background:
      radial-gradient(800px 320px at 20% 10%, rgba(215,179,90,.18), transparent 60%),
      radial-gradient(700px 260px at 85% 30%, rgba(246,226,122,.10), transparent 55%),
      linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,0));
    filter: blur(.2px);
    z-index:0;
  }
  .lux-hero > *{ position: relative; z-index:1; }

  .lux-topline{
    display:flex;
    gap:10px;
    align-items:center;
    justify-content:space-between;
    flex-wrap:wrap;
    margin-bottom: 10px;
  }
  .lux-badge{
    display:inline-flex;
    gap:10px;
    align-items:center;
    border: 1px solid var(--line);
    padding: 8px 12px;
    border-radius: 999px;
    background: rgba(0,0,0,.35);
    color: var(--muted);
    font-size: 13px;
    letter-spacing: .28px;
    text-transform: uppercase;
  }
  .lux-badge b{
    color: var(--gold);
    font-weight: 700;
    letter-spacing:.35px;
  }

  h1,h2,h3{
    margin: 0.2em 0 0.4em;
    line-height: 1.15;
    letter-spacing: .2px;
  }
  h1{
    font-size: clamp(34px, 4vw, 48px);
  }
  h2{
    margin-top: 26px;
    font-size: 22px;
    color: var(--gold-2);
  }
  h3{
    font-size: 16px;
    color: var(--gold);
    margin-top: 0;
  }

  .lux-subtitle{
    margin-top: 8px;
    color: var(--muted);
    font-size: 16px;
    max-width: 70ch;
  }

  /* разделитель */
  .lux-rule{
    height:1px;
    background: linear-gradient(90deg, transparent, rgba(215,179,90,.55), transparent);
    margin: 18px 0 6px;
  }

  /* сетки */
  .grid-2{
    display:grid;
    grid-template-columns: 1.2fr .8fr;
    gap: 14px;
  }
  .grid-3{
    display:grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
  }
  @media (max-width: 860px){
    .grid-2{ grid-template-columns: 1fr; }
    .grid-3{ grid-template-columns: 1fr; }
  }

  /* мини‑карточки */
  .mini{
    background: rgba(0,0,0,.35);
    border: 1px solid var(--line);
    border-radius: 16px;
    padding: 16px;
  }
  .mini p{ margin: 0.35em 0; color: var(--muted); }

  /* цитаты */
  blockquote{
    border-left: 3px solid var(--gold);
    margin: 16px 0;
    padding: 10px 14px;
    background: rgba(0,0,0,.28);
    border-radius: 12px;
    color: var(--muted);
  }
  blockquote strong{ color: var(--gold-2); }

  /* таблица */
  table{
    width:100%;
    border-collapse: collapse;
    margin: 10px 0 0;
    overflow:hidden;
    border-radius: 14px;
    border:1px solid var(--line);
    background: rgba(0,0,0,.25);
  }
  th, td{
    padding: 10px 12px;
    border-bottom: 1px solid rgba(215,179,90,.16);
    vertical-align: top;
  }
  th{
    color: var(--gold-2);
    text-align:left;
    background: rgba(215,179,90,.06);
    letter-spacing:.2px;
  }
  tr:last-child td{ border-bottom:none; }

  /* ссылки */
  a{ color: var(--gold-2); text-decoration: none; border-bottom: 1px dashed rgba(246,226,122,.45); }
  a:hover{ opacity: .9; border-bottom-style: solid; }

  /* кнопки‑ссылки */
  .cta{
    display:flex; gap:10px; flex-wrap:wrap;
    margin-top: 14px;
  }
  .cta a{
    border: 1px solid rgba(246,226,122,.35);
    border-radius: 999px;
    padding: 10px 14px;
    background: rgba(0,0,0,.35);
    color: var(--ink);
    text-decoration:none;
  }
  .cta a.primary{
    background: linear-gradient(180deg, rgba(215,179,90,.22), rgba(215,179,90,.08));
    border-color: rgba(215,179,90,.55);
  }

  /* футер */
  .lux-footer{
    margin-top: 18px;
    padding-top: 14px;
    color: var(--muted);
    font-size: 13px;
    border-top: 1px solid rgba(215,179,90,.18);
  }

  /* маленькие "иконки" (pure text) */
  .dot{
    display:inline-block;
    width:10px; height:10px;
    border-radius:999px;
    background: radial-gradient(circle at 30% 30%, var(--gold-2), var(--gold));
    box-shadow: 0 0 0 3px rgba(215,179,90,.18);
  }
</style>

<div class="lux-wrap">

<div class="lux-card lux-hero">

<div class="lux-topline">
  <span class="lux-badge"><span class="dot"></span> коллекция: <b>BLACK&nbsp;×&nbsp;GOLD</b></span>
  <span class="lux-badge">герой страницы: <b>такса</b> 🐾</span>
</div>

# Такса — роскошь в миниатюре

<p class="lux-subtitle">
Длинное тело, короткие лапы и безупречная уверенность в своей правоте. Такса умеет выглядеть аристократично даже в момент,
когда она упрямо «обсуждает» с вами правила прогулки.
</p>

<div class="lux-rule"></div>

<div class="grid-2">
  <div class="mini">
    <h3>Почему такса — это характер</h3>
    <p><b>Смелость.</b> Внутри — охотник, снаружи — дизайнерская форма.</p>
    <p><b>Ум.</b> Быстро учится… и ещё быстрее учится вас дрессировать.</p>
    <p><b>Чувство собственности.</b> Ваш плед, ваш диван, ваша подушка — теперь её.</p>
  </div>

  <div class="mini">
    <h3>Факт‑карточка</h3>
    <p><b>Энергия:</b> высокая</p>
    <p><b>Контактность:</b> привязывается крепко</p>
    <p><b>Комфорт:</b> любит тепло и мягкое</p>
    <p><b>Суперсила:</b> «уговаривать» взглядом</p>
  </div>
</div>

</div>

## Портрет породы

<div class="lux-card">
<div class="grid-3">
  <div class="mini">
    <h3>Элегантная геометрия</h3>
    <p>Такса — это идеально вытянутый силуэт и плавная линия спины. В движении она выглядит как уверенный штрих золотым пером.</p>
  </div>
  <div class="mini">
    <h3>Темперамент</h3>
    <p>Любопытная, настойчивая, иногда драматичная. Она не «просит» — она ведёт переговоры.</p>
  </div>
  <div class="mini">
    <h3>Верность</h3>
    <p>Такса часто выбирает «своего» человека и держится рядом, как личная охрана с хвостом.</p>
  </div>
</div>

<blockquote>
<strong>Золотое правило:</strong> такса маленькая только по размерам — по характеру она всегда «большая собака».
</blockquote>
</div>

## Уход и комфорт в стиле люкс

<div class="lux-card">

<table>
  <thead>
    <tr>
      <th>Зона</th>
      <th>Что важно</th>
      <th>Мини‑совет</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Спина</b></td>
      <td>Беречь от резких прыжков и лишнего веса.</td>
      <td>Пандус/ступеньки к дивану — это не каприз, а инвестиция.</td>
    </tr>
    <tr>
      <td><b>Прогулки</b></td>
      <td>Регулярные, с нюхательными «пауэр‑сетами».</td>
      <td>Лучше 2–3 коротких выхода, чем один «марафон без смысла».</td>
    </tr>
    <tr>
      <td><b>Ум</b></td>
      <td>Нужны задачи и игра, иначе «придумает» сама.</td>
      <td>Пищевые головоломки и поиск игрушки по запаху.</td>
    </tr>
    <tr>
      <td><b>Тепло</b></td>
      <td>Таксы часто обожают пледы и одежду по сезону.</td>
      <td>Зимой — комбинезон; дома — мягкая лежанка в тихом углу.</td>
    </tr>
  </tbody>
</table>

<div class="cta">
  <a class="primary" href="#мини-гайд-на-7-дней">Открыть мини‑гид</a>
  <a href="#характер-и-общение">Читать про характер</a>
  <a href="#блэк--голд-эстетика">Скачать палитру</a>
</div>

</div>

## Характер и общение

<div class="lux-card">

<div class="grid-2">
  <div class="mini">
    <h3>Как она «разговаривает»</h3>
    <p>Такса умеет выражать мнение: взгляд, поза, вздох, «комментарий» голосом. Это не конфликт — это коммуникация.</p>
    <p><b>Ключ:</b> спокойные правила + короткие повторения + похвала за правильный выбор.</p>
  </div>
  <div class="mini">
    <h3>Чего избегать</h3>
    <p>Грубости, хаотичных запретов и «то можно, то нельзя».</p>
    <p><b>Лучше:</b> чёткие границы и понятная система наград.</p>
  </div>
</div>

</div>

## Мини‑гайд на 7 дней

<div class="lux-card" id="мини-гайд-на-7-дней">

<div class="grid-3">
  <div class="mini">
    <h3>День 1–2</h3>
    <p>Режим: прогулка → корм → отдых.</p>
    <p>10 минут обучения: «ко мне», «сидеть».</p>
  </div>
  <div class="mini">
    <h3>День 3–4</h3>
    <p>Добавьте нюх‑игры: поиск лакомства в комнате.</p>
    <p>Тренируйте «нельзя» без крика.</p>
  </div>
  <div class="mini">
    <h3>День 5–7</h3>
    <p>Сложнее: выдержка 3–5 секунд, затем награда.</p>
    <p>Игра на перетяжку — только с правилом «отдай».</p>
  </div>
</div>

<blockquote>
<strong>Принцип:</strong> у таксы отлично работает «коротко, часто, вкусно» — небольшие тренировки, но регулярно.
</blockquote>

</div>

## Блэк × голд эстетика

<div class="lux-card" id="блэк--голд-эстетика">

<div class="grid-2">
  <div class="mini">
    <h3>Палитра</h3>
    <ul>
      <li><b>Black Velvet:</b> <code>#050506</code></li>
      <li><b>Night Ink:</b> <code>#0b0b10</code></li>
      <li><b>Gold:</b> <code>#d7b35a</code></li>
      <li><b>Gold Light:</b> <code>#f6e27a</code></li>
    </ul>
  </div>
  <div class="mini">
    <h3>Готовый блок-стикер</h3>
    <p>Скопируйте куда угодно:</p>
<pre><code>🐾 Такса: маленькая по росту, большая по характеру.
🖤 Цвет: ночь. ✨ Настроение: золото.
</code></pre>
  </div>
</div>

</div>

<div class="lux-footer">
  Сделано в Markdown + встроенный CSS. Если ваш рендерер не поддерживает <code>&lt;style&gt;</code>, вынесите CSS в отдельный файл и подключите его темой.
</div>

</div>
