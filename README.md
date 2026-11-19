# vue3-ts-fsd-skills

Три независимых скилла для Codex. Можно установить весь набор или выбрать один каталог. Каждый скилл учитывает конфигурацию и соглашения проекта, в котором его вызывают.

| Скилл | Для каких задач |
| --- | --- |
| [typescript-contracts](skills/typescript-contracts/SKILL.md) | Проверить внешние данные, уточнить тип, изменить контракт и найти его потребителей |
| [vue3-composition](skills/vue3-composition/SKILL.md) | Спроектировать компонент, выбрать владельца состояния, сохранить реактивность |
| [fsd-boundaries](skills/fsd-boundaries/SKILL.md) | Выбрать слой и слайс, определить публичный API, устранить глубокий импорт или цикл |

## Установка в проект

После публикации набора выполните из корня целевого проекта в Bash или Zsh:

```sh
skills_source="$(mktemp -d)"
git clone --depth 1 https://github.com/Merriidiian/vue3-ts-fsd-skills.git "$skills_source" &&
  mkdir -p .agents/skills &&
  cp -Ri "$skills_source"/skills/* .agents/skills/
```

Для установки одного скилла замените `"$skills_source"/skills/*` на путь к его каталогу, например `"$skills_source"/skills/vue3-composition`. Если исходный репозиторий уже есть локально, укажите путь к нему в `skills_source` и выполните команды `mkdir` и `cp`. При совпадении файлов `cp -i` запросит подтверждение замены.

Добавьте выбранные каталоги из `.agents/skills/` в Git целевого проекта, чтобы набор был доступен команде. Откройте проект в новой сессии Codex и вызовите скилл по имени, например:

```text
$vue3-composition Проверь, почему список перестаёт обновляться после смены фильтра.
```

Лицензия — [MIT](LICENSE).
