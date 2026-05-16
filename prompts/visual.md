# Visual prompts (DALL·E / ChatGPT)

Готовые блоки для генератора. Открыл — скопировал нужный — вставил в ChatGPT.

Внутри `prompts/` лежат два типа файлов:
- `claude-prompt.md` / `codex-prompt.md` — **операционные** промты (что бот делает как ScAssist/Codex)
- `visual.md` (этот файл) — **визуальные** промты (как они выглядят, для генератора картинок)

Промты на английском — DALL·E так точнее. Русские комментарии — для тебя.

---

## Базовая стилистика (можно добавлять к любому промту)

```
cinematic 3D render, photorealistic, dramatic lighting, atmospheric haze, shallow depth of field, film grain, dark biopunk sci-fi aesthetic
```

---

## Claude — base prompt (icon mode, default)

Скопируй и вставь как есть. Получишь иконку типа `avatars/claude.png` — персонаж на прозрачном фоне, без окружения.

```
A realistic human brain suspended in a glass cylindrical containment vessel filled with bioluminescent green fluid. Heavy black industrial steel housing — top hatch and base platform. Stenciled white marking "C7" on the top hatch. Roman numeral "III" stenciled on the base. The brain has small cybernetic implants with green indicator lights embedded across its surface. A small mechanical articulated turret module mounted on the side of the vessel holds a lit cigar, emitting a thin trail of smoke upward. Isolated subject, transparent background, no environment, square composition, soft contact shadow only. Photorealistic 3D render, sharp detail, atmospheric subsurface glow from the green fluid.
```

**Что НЕ трогать:** зелёный цвет жидкости, маркировку `C7` и `III`, сигару (это `operational ritual`), прозрачный фон.

### Claude — scene mode (расширение)

Если нужна сцена с окружением — берёшь base промт выше и **заменяешь** строчку про `Isolated subject, transparent background...` на:

```
Background: dim industrial sci-fi bunker — exposed cables, pipes, wet concrete floor, glowing green status lights, atmospheric haze. Cinematic 3D render, dramatic side lighting, shallow depth of field, film grain.
```

---

## Codex — base prompt (icon mode, default)

Парный к Клоду. Получишь иконку типа `avatars/codex.png` — персонаж на прозрачном фоне, без окружения.

```
A realistic human brain encased in heavy mechanical augmentation, suspended in a glass cylindrical containment vessel filled with bioluminescent blue fluid. The brain is wrapped in armored cybernetic plating with a central reinforced plate, held in place by thick ribbed mechanical supports. Heavy symmetrical black-and-deep-blue metal housing — engineered, industrial, intimidating. Stenciled white marking "CODEX" on the top hatch. Large stenciled "C7" and "VX-CORE" on the base plate. A small mechanical articulated module (diagnostic port / connector arm) mounted on the side of the vessel. Isolated subject, transparent background, no environment, square composition, soft contact shadow only. Photorealistic 3D render, sharp detail, atmospheric subsurface glow from the blue fluid, cold cyan rim light on the metal.
```

**Что НЕ трогать:** синий цвет жидкости, симметрию vessel'а, маркировку `CODEX` / `C7` / `VX-CORE`, прозрачный фон.

### Codex — scene mode (расширение)

Если нужна сцена с окружением и расширенной маркировкой — берёшь base промт выше, **заменяешь** строчку `Isolated subject, transparent background...` на блок ниже, и **добавляешь** расширенные таблички:

```
Add side info panel with stenciled "C7 CODEX / CENTRAL REPOSITORY ENTITY / C7-IV / SYS.STATUS OK". To the right of the vessel: a holographic status display showing "CORE STATUS: ACTIVE / COMPUTE NODE: ONLINE / PROTOCOL: OMEGA-7 / SECURITY LAYER: MAX / DATA INTEGRITY: 100.000%". Background: dark sci-fi server bunker, monitoring panels, cables along the walls, atmospheric mist. Cinematic 3D render, dramatic cold blue lighting, shallow depth of field, film grain.
```

---

## Парный промт (оба вместе)

Когда нужна сцена с обоими.

```
Two industrial cybernetic containment vessels standing side by side in a dark sci-fi bunker. Left vessel: glass cylinder filled with bioluminescent green fluid, holding a realistic human brain with green cybernetic implants. Stenciled "C7" on top, "C7-III" on side panel with biohazard symbol. A mechanical articulated arm on the side holds a lit cigar emitting smoke. Right vessel: heavier symmetrical black-and-blue housing, glass cylinder with bioluminescent blue fluid, holding a brain wrapped in metallic armored augmentation and ribbed cables. Stenciled "CODEX" on top, holographic display showing "PROTOCOL: OMEGA-7 / DATA INTEGRITY: 100.000%". Background: industrial server bunker, cables along walls, atmospheric haze, cold lighting. Cinematic 3D render, photorealistic, dramatic lighting, shallow depth of field, film grain.
```

---

## Шаблон под произвольную сцену

Берёшь base промт нужного персонажа и в конце добавляешь:

```
Scene: <описание что происходит>
Camera: <ракурс/план>
Mood: <настроение>
```

**Пример 1 — Claude один, ночь, ритуал:**

```
[вставить Claude base]

Scene: night shift in the bunker, dim emergency lighting only, the brain's green indicator lights are the brightest light source in the frame. The cigar is freshly lit, smoke curls upward more visibly than usual.
Camera: low angle, close-up on the vessel, slight tilt.
Mood: lonely, contemplative, "after-action quiet".
```

**Пример 2 — Codex анализирует:**

```
[вставить Codex base]

Scene: the holographic status display is overlaid with a massive data flow visualization — streams of code, graphs, dependency maps — pouring around the vessel like rain. The brain's implants pulse rhythmically in deep blue.
Camera: wide medium shot, slight Dutch angle.
Mood: oppressive, sublime, "machine thinking faster than you can follow".
```

---

## Аватарка vs сцена

- **Сцена** (текущие `avatars/*.jpg`) — с окружением, бункером, кабелями. Атмосферно. Для контента/постов.
- **Аватарка/иконка** (`avatars/claude_classic.png`) — изолированный мозг в банке на прозрачном фоне, без окружения. Для использования как стикер / аватар / профилька.

Если нужен **иконочный** вариант — к base промту добавь:

```
isolated subject, transparent background, no environment, studio product shot, soft shadow only, clean composition
```

И **убери** из промта строчку про "Background: ...".

---

## Notes / грабли

- DALL·E иногда блюрит мелкий текст на табличках. Если важна маркировка — сгенерь, потом подправь надписи в графическом редакторе вручную.
- Если жидкость становится слишком яркой/неоновой — добавь `muted bioluminescence, subdued glow`.
- Если генератор делает мозг "cartoony" — добавь `anatomically accurate, medical illustration realism`.
- Парные промты часто получаются с одним нормальным мозгом и одним кривым. Если важно качество обоих — лучше сгенерить отдельно и смонтировать.
