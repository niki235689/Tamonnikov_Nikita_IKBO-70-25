# Task_1
```
# Найти папки пакета: код и dist-info
Get-ChildItem venv\Lib\site-packages | Select-String -Pattern 'matplotlib'

# Содержимое папки dist-info
Get-ChildItem venv\Lib\site-packages\matplotlib-*.dist-info

# Первые 50 строк файла METADATA
Get-Content venv\Lib\site-packages\matplotlib-*.dist-info\METADATA | Select-Object -First 50

# Фильтрация зависимостей и метаданных
Get-Content venv\Lib\site-packages\matplotlib-*.dist-info\METADATA | Select-String -Pattern '^(Requires-Python|Requires-Dist|Project-URL|Classifier: Operating)'

# Вывод файла WHEEL
Get-Content venv\Lib\site-packages\matplotlib-*.dist-info\WHEEL

# Установка пакета
pip install matplotlib

# Метаданные пакета
pip show matplotlib

# Фильтрация полей
pip show matplotlib | Select-String -Pattern '^(Name|Version|Summary|Home-page|Author|Location|Requires|Required-by):'

# Список первых 30 файлов пакета
$files = pip show -f matplotlib
$start = $false
$files | Where-Object { 
    if ($_ -match '^Files:') { $start = $true } 
    $start 
} | Select-Object -First 30

# Найти папки пакета: код и dist-info
Get-ChildItem venv\Lib\site-packages | Select-String -Pattern 'matplotlib'

# Содержимое папки dist-info
Get-ChildItem venv\Lib\site-packages\matplotlib-*.dist-info

# Первые 50 строк файла METADATA
Get-Content venv\Lib\site-packages\matplotlib-*.dist-info\METADATA | Select-Object -First 50

# Фильтрация зависимостей и метаданных
Get-Content venv\Lib\site-packages\matplotlib-*.dist-info\METADATA | Select-String -Pattern '^(Requires-Python|Requires-Dist|Project-URL|Classifier: Operating)'

# Вывод файла WHEEL
Get-Content venv\Lib\site-packages\matplotlib-*.dist-info\WHEEL
```
# Task_2
```
# Создаем рабочую папку в профиле пользователя и переходим в нее
New-Item -ItemType Directory -Force -Path "$HOME\pract2" | Out-Null
Set-Location "$HOME\pract2"

npm view express

# Создание каталога проекта и переход
New-Item -ItemType Directory -Force -Path "express_test" | Out-Null
Set-Location "express_test"
npm init -y
npm install express
npm ls --all | Select-Object -First 40

# В PowerShell Get-Content выводит содержимое файла
Get-Content node_modules\express\package.json


репозиторий напрямую:
Set-Location "$HOME\pract2"
git clone --depth 1 https://github.com/expressjs/express.git express_git
Get-ChildItem express_git
# Аналог grep -A 30 в PowerShell — утилита Select-String с параметром -Context
Get-Content express_git\package.json | Select-String -Pattern '"dependencies"' -Context 0, 30
```
# Task_3
```

```
