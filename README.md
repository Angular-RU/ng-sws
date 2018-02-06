# NgSws

* Это проект для разработки библиотек Angular 4\5
* Цель данного проекта - создание и тестирование библиотек Angular, которые соответствуют стандарту [Angular Package Format](https://docs.google.com/document/d/1CZC2rcpxffTDfRDs6p1cfbmKNLA6x5O-NtkJglDaBVs/preview), с дальнейшей их публикацией на NPM.

## Ход создания и публикации библиотеки
1. В папке libs необходимо создать папку с названием создаваемой библиотеки.
2. В ней необходимо создать package.json (по примеру с sws-loading)
3. В папке src создать модуль\компоненты\сервисы и т.д. (как и в обычном проекте)
4. В папке src создать файл public_api.ts, в котором указать пути к компонентам\модулям\сервисам, которые были созданы.
5. В package.json, относящегося ко всему проекту, прописать дополнитульную команду (по примеру с sws-loading): 
    "build:название_библиотеки": "rimraf dist && ng-packagr -p libs/название_библиотеки/package.json",
6. В корневом каталоге всего проекта запустить команду npm run build:название_библиотеки
7. После того, как библиотека будет собрана, необходимо войти в личный кабинет npm.
8. Перейти в корневой каталог собранной библиотеки (libs\dist\название_библиотеки) и прописать npm publish 
9. Изменения запушить на git, при изменении в существующих библиотеках необходимо поднимать версию библиотеки npm (https://docs.npmjs.com/cli/version)

## Доп. информация

* Стили для компонентов пишутся в их локальных файлах (название_библиотеки.component.css\scss). 
* Для более подробной инйформации: [git проекта на основании котрого был сделан данный](https://github.com/dherges/ng-packagr), [доп. статья](https://medium.com/@nikolasleblanc/building-an-angular-4-component-library-with-the-angular-cli-and-ng-packagr-53b2ade0701e) 
