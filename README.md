
---

### Структура проекта

```
porncombinator/
├── core.py              # Логика поиска и расчёта возбуждения
├── porncombinator.py    # CLI-интерфейс
├── rules.json           # База правил с эротическими сочетаниями
```

---

### Установка

```bash
git clone https://github.com/wakeuppls/porn-combinator.git
cd porn-combinator
python porncombinator.py --help
```

---

### Примеры использования

Найти все возбуждающие комбинации с участием ролевых игр:

```bash
python porncombinator.py --genre roleplay
```

Найти все случаи, где ролевые игры участвуют в связках, но не как основной элемент:

```bash
python porncombinator.py --genre roleplay --reverse
```

Сохранить возбуждающие сценарии в файл:

```bash
python porncombinator.py --genre roleplay --reverse --export fantasies.txt
```

Рассчитать совокупный возбуждающий эффект:

```bash
python porncombinator.py --arousal 8.1 6.7 1.5
```

---

### Пример эротического правила (`rules.json`)

```json
{
  "base_genre": "roleplay",
  "combined_with": ["bondage"],
  "goal": "Maximum immersion and tension",
  "arousal_score": 9.2,
  "description": "Combine roleplay with light bondage for heightened psychological and physical engagement."
}
```

---

### Экспорт фантазий

Флаг `--export <file>` позволяет сохранить найденные сценарии в текстовый файл — удобно для съёмок, планирования или вдохновения.

---

### Модель расчёта возбуждения

Возбуждающий эффект рассчитывается по формуле:

```
A_combo = 10 × (1 - (1 - A1/10) × (1 - A2/10) × 1/C)
```

где:

* `A1`, `A2` — индивидуальные уровни возбуждения от жанров (по шкале 0–10)
* `C` — коэффициент возбуждающего взаимодействия
