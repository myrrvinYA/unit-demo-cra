## Testing

- Вызывается при PR
- Ограничение на merge если не прошли проверки

## Create release

- Вызывается при добавлении тега v<число> (например, v12 )
- Осуществляется прогон тестов схож с Testing
- Создается changelock
- Формируется issue с пометкой RELEASE. В неё сохраняться вся важная информация: автор и дата релиза, номер версии, changelog
- Eсли проверки прошли, приложение должно выкладываться на gh-pages, а запись об этом должна добавляться в реестр релизов
- После этого релизный issue автоматом закрыватся

В этом репозитории находится пример приложения с тестами:

- [e2e тесты](e2e/example.spec.ts)
- [unit тесты](src/example.test.tsx)

Для запуска примеров необходимо установить [NodeJS](https://nodejs.org/en/download/) 16 или выше.

Как запустить:

```sh
# установить зависимости
npm ci

# запустить приложение
npm start
```

Как запустить e2e тесты:

```sh
# скачать браузеры
npx playwright install

# запустить тесты
npm run e2e
```

Как запустить модульные тесты:

```sh
npm test
```
