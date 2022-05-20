# Как создать nestjs+react проект

1. Создаем проект nestjs. Он будет основой для нашего проекта.
  * Правим форматирование
    * `.eslintrc.js` добавляем правила
      ```json
      'semi': [2, 'never'],
      'quotes': [2, "single"],
      'comma-dangle': ["error", "always-multiline"],
      ```
    * `.prettierrc` содержимое:
    ```json
    {
      "singleQuote": true,
      "trailingComma": "all",
      "semi": false,
      "bracketSameLine": true
    }
    ```
  * Освобождаем имя под `tsconfig.json`
    * Переименовываем `tsconfig.json` -> `tsconfig.back.json`
    * В `tsconfig.build.json` правим extend
  * Правим команду **lint** в `package.json` на поддержку jsx
  * Добавляем исключения в `tsconfig.build.json`
    * `src/front`
    * `src/index.tsx`
2. Отдельно создаем реакт приложение `npx superplate-cli имя`
3. Копируем из реакт приложения в наш комбинированный проект
   * Зависимости. В папке проекта реакт запускаем
     ```shell
     node -e "console.log(Object.keys(require('./package.json').dependencies).join(' '))"
     ```
     Получаем зависимости через пробел, добавляем в наш комбинированный проект
   * Копируем **browserslist** в `package.json`
   * Копируем команды в `package.json`. Для конфликтующих добавляем суффикс `:f`
   * Копируем файлы из директории `src` в `src/front`
     * Переносим файл `src/front/index.tsx` в `src/index.tsx`
     * Правим пути подключения библиотек в файлах фронтенд проекта
