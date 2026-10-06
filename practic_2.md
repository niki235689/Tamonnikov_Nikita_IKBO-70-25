# Task_1
```
import importlib.metadata
meta = importlib.metadata.metadata('matplotlib')
print(f"Name: {meta['Name']}")
print(f"Version: {meta['Version']}")
print(f"Summary: {meta['Summary']}")
print(f"Requires-Dist: {meta.get_all('Requires-Dist')}")

1 строчка импортирует метаданные из библиотеки
2 строчка присваивает служебные данные переменной
ласт строчка выводит имена пакета и их версию, которые требуются для работы

пряямиком: apt-get download <package_name>
```
# Task_2
```
const fs = require('fs');
const path = require('path');

// Читаем package.json прямо из директории node_modules
const pkgPath = path.join(process.cwd(), 'node_modules', 'express', 'package.json');
const pkg = JSON.parse(fs.readFileSync(pkgPath, 'utf-8'));

console.log(`Name: ${pkg.name}`);
console.log(`Version: ${pkg.version}`);
console.log(`Description: ${pkg.description}`);
console.log(`Main entry: ${pkg.main}`);
console.log(`Dependencies:`, Object.keys(pkg.dependencies || {}));

первые две строки подключают встроенные модули node.js
3 строчка формирует абсолютный путь к файлу
4 читает файл
```
# Task_3
```

```
