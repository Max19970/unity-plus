# Unity Plus Template

Этот репозиторий — стартовый шаблон Unity-проекта с подготовленной структурой папок, базовыми project settings и предустановленными плагинами.

## Версия Unity

- Unity: `6000.3.1f1` (Unity 6)

## Что уже настроено

- URP (`com.unity.render-pipelines.universal` 17.3.0) как активный Render Pipeline.
- Два профиля качества и рендера:
  - `PC` -> `Assets/_System/Settings/PC_RPAsset.asset`
  - `Mobile` -> `Assets/_System/Settings/Mobile_RPAsset.asset`
- Линейное цветовое пространство (`Linear`).
- Включён новый Input System (старый Input Manager отключён).
- В Build Settings добавлена стартовая сцена:
  - `Assets/_Project/Scenes/SampleScene.unity`
- Подключены базовые Input Actions:
  - `Assets/_Project/InputSystem_Actions.inputactions`
- Подключен FMOD (плагин размещён в `Assets/_External/FMOD`).
- Настроен NuGetForUnity с установкой пакетов в:
  - `Assets/_External/NuGet/Packages`

## Структура проекта

```text
Assets/
  _Project/               # Ваш игровой код, сцены, префабы, контент проекта
    Scenes/
    InputSystem_Actions.inputactions
  _System/                # Системные настройки проекта (URP assets, volume profile и т.д.)
    Settings/
  _External/              # Внешние плагины и сторонние ресурсы
    FMOD/
    NuGet/
    TextMesh Pro/

Docs/                     # Локальные выгрузки документации по установленным пакетам
Packages/                 # manifest.json и lock-файл UPM
ProjectSettings/          # Unity project settings
```

## Предустановленные пакеты и плагины

Ключевые зависимости (часть через UPM Registry, часть через Git UPM):

- DI / Architecture: `VContainer`, `MessagePipe`, `MessagePipe.VContainer`
- Async / Reactive: `UniTask`, `R3`
- Serialization: `MemoryPack`
- Utility / Performance: `ZLinq`, `ZString`
- Tween / Animation: `LitMotion`
- Tools / Integration: `NuGetForUnity`, `Unity MCP`
- Unity stack: `URP`, `Input System`, `AI Navigation`, `Timeline`, `uGUI`, `Test Framework`
- Audio middleware: `FMOD` (в `Assets/_External/FMOD`)

Подробные версии и источники:

- `Packages/manifest.json`
- `Packages/packages-lock.json`

## Быстрый старт

1. Откройте проект в Unity Hub с версией `6000.3.1f1`.
2. Дождитесь импорта ассетов и резолва пакетов.
3. Откройте `Assets/_Project/Scenes/SampleScene.unity`.
4. Убедитесь, что проект запускается в Play Mode без ошибок.

## Системный промпт AI-агента

Системный промпт, определяющий строгие инженерные правила работы агента, перенесен в:

- `Docs/AI/SYSTEM.md`

Что закреплено на уровне системного промпта:

- Режим Unity Principal Engineer с непереговорными архитектурными требованиями.
- Строгий протокол выполнения задач: Intake -> Planning -> Implementation -> Verification Gate -> Hot-refactor -> Финальный аудит.
- Обязательная фиксация артефактов задачи:
  - `Docs/AI/TaskPlans/<task-id>.md`
  - `Docs/AI/TaskReports/<task-id>.md`
- Жесткий Definition of Done: задачу нельзя закрыть без валидации, проверок и прозрачного отчета.

Шаблоны артефактов:

- `Docs/AI/TaskPlans/_template.md`
- `Docs/AI/TaskReports/_template.md`

## Рекомендуемые шаги при создании нового проекта на основе шаблона

1. Изменить `Company Name`, `Product Name`, `Bundle Identifier` в `Project Settings > Player`.
2. Заменить `SampleScene` на вашу стартовую сцену и обновить `Build Settings`.
3. Проверить необходимость каждого внешнего пакета и удалить лишние.
4. Если используется FMOD: указать `sourceProjectPath`/пути банков и настроить загрузку банков.
5. Разнести собственный код по подпапкам внутри `Assets/_Project` (например, `Scripts`, `Prefabs`, `UI`, `Addressables`).

## Примечания

- В репозиторий обычно не коммитятся `Library/`, `Temp/`, `Logs/`, `UserSettings/` (уже учтено в `.gitignore`).
- Для воспроизводимости зависимостей используйте `Packages/packages-lock.json`.
