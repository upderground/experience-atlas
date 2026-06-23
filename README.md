# Атлас опыта · Experience Atlas

Помощник для людей, которые **долго работали в одной компании** и **давно не искали работу**: вспомнить забытые кейсы, разложить их по **грейду** желаемой роли и собрать **базу для портфолио**, собеседований и сайта.

Не шаблон «красивого PDF». Ядро — **recall + упаковка под матрицу компетенций**, один вопрос за раз.

---

## Для кого

- 3+ лет в одной компании, «в голове много, на бумаге — ноль»
- Смена роли (например UX → PM) без переписывания фактов
- Подготовка к **middle / senior** без навыка «составлять портфолио»
- Нужна **JSON-база**, из которой потом: сайт, PDF, отклик под JD, mock interview

---

## Как это работает

1. Найди или собери **описание грейдов** по целевой профессии (markdown из компании, внутренняя матрица, публичный гайд).
2. Укажи **целевой грейд** (junior / middle / senior …).
3. Открой чат с AI (Cursor, Claude, ChatGPT) и вставь промпт из [`prompts/session-start.md`](prompts/session-start.md), приложив файл грейдов.
4. Агент ведёт **по одному вопросу**, помогает достать «мелочи», которые ты не считаешь кейсом.
5. После каждого блока — **`cases/*.json`** (STAR + framing для найма), обновление **`_coverage_map.md`**.
6. В конце — индекс outcomes, пробелы, промпт на сайт [`prompts/site-build.md`](prompts/site-build.md).

```
grade-matrix.md + target grade
        ↓
   coverage map (есть / частично / нет)
        ↓
   recall loop (1 вопрос → 1 кейс)
        ↓
   cases/*.json + outcomes index
        ↓
   сайт / PDF / отклик под вакансию
```

---

## Быстрый старт

```bash
git clone https://github.com/YOUR_USER/experience-atlas.git
cd experience-atlas
cp -r template/ ~/my-career-session/
# Положи в ~/my-career-session/ свой grade-matrix.md
# Открой prompts/session-start.md в AI-чате
```

В Cursor: скопируй [`SKILL.md`](SKILL.md) в `.cursor/skills/experience-atlas/SKILL.md` или подключи папку как skill.

---

## Структура репозитория

| Путь | Назначение |
|------|------------|
| `SKILL.md` | Инструкции для AI-агента |
| `prompts/session-start.md` | Стартовый промпт пользователя |
| `prompts/site-build.md` | Промпт сборки сайта из базы |
| `schema/case.schema.json` | Схема JSON-кейса |
| `template/` | Пустая сессия для копирования |
| `examples/` | Анонимный пример одного кейса |

---

## Принципы

- **Один вопрос за ход** — не перегружать память.
- **Не выдумывать метрики** — неизвестное в `_deferred_facts.md`.
- **Честные negative results** — сильный сигнал для senior/middle.
- **Readonly источники** — правки только в рабочей папке сессии.
- **Reframe, не fiction** — смена роли = другая линза, те же факты.

---

## Experience Atlas (EN)

Open-source skill + template for **recovering forgotten work stories** and mapping them to a **target job grade**. Outputs structured JSON cases for portfolios, interviews, and static sites. Built for long-tenure, single-company careers in product, UX, and adjacent roles.

---

## License

MIT — see [LICENSE](LICENSE).
