### 1. Представим, что у нас есть данные, которые мы очень часто читаем по сравнению с другими(например словарь стран). Как можно это оптимизировать?
Кеширование (требуется оперативная память), можно по разном реализовать: отдельный сервер словарей, где в ОП все хранится; использовать inMemeryDB (H2)
+: высокая скорость для чтения

### 2. Что можно сделать, если таблица вакансий стала слишком большой? Какие есть решения на уровне текущей базы данных? Можно ли ее чем то заменить?
1. Проверить нормализованна ли БД
2. Вертикальное масштабирование - наращиваем мощность ОП и процессора
3. Горизонтальное масштабирование, например: шардирование
4. Использовать распределенную NoSQL СУБД (это может подойти, если не нужна целостность данных, также требуется миграция данных)
5. Разбить таблицу по временным диапазонам (но это нарушает нормальную форму)

### 3. Какие вы видите узкие места, возможно неправильно выбранные технологии в текущей схеме(можно рассмотреть как “нашу” схему, так и схему настоящего hh.ru)
1. добавить кеширующий сервис
2. шардирование postgres
3. уменьшить связность компонентов
