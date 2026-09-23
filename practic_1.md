# Task_1
```
localhost:/etc# cut -d: -f1 passwd | sort
```
# Task_2
```
localhost:/etc# awk '!/^#/ && NF {print $2, $1}' protocols | sort -rn | head -5
```
# Task_3
```
#!/bin/bash
text="$*"
length=${#text}
border=$(printf '%*s' $((length + 2)) '' | tr ' ' '-')
echo "+$border+"
echo "| $text |"
echo "+$border+"
```
# Task_4
```
#!/bin/bash
grep -oE '\b[A-Za-z_][A-Za-z0-9_]*\b' "$1" | sort -u | tr '\n' ' '
echo
```
# Task_5
```
#!/bin/bash
if [ $# -ne 1 ]; then
        exit 1
fi
if [ ! -f "$1" ]; then
        echo "Файл '$1' не найден"
        exit 1
fi
 
chmod 755 "$1"
cp "$1" /usr/local/bin
```
# Task_6
```
#!/bin/bash
for file in "$@"; do
        case "$file" in
        *.c|*.js)
                comment='//'
                ;;
        *.py)
                comment='*'
                ;;
        esac
        first_line=$(head -n 1 "$file")
        if [[ "$first_line" == "$comment"* ]] then
                echo "$file: комментарий есть"
        else
                echo "$file: комментария нет"
        fi
done
```

# Task_7
```
#!/bin/bash
if [ $# -ne 1 ]; then
        exit 1
fi
if [ ! -d "$1" ]; then
        echo "'$1' не является директорией"
        exit 1
fi
find "$1" -type f -exec md5sum {} \; | sort | uniq -w32 -D
```
# Task_8
```
#!/bin/bash
if [ $# -ne 2 ]; then
    exit 1
fi
if [ ! -d "$1" ]; then
    echo "'$1' не является директорией"
    exit 1
fi
dir="$1"
ext="$2"
find "$dir" -type f -name "*.$ext" > files.txt
if [ ! -s files.txt ]; then
    echo "Файлы с расширением .$ext не найдены"
    rm -f files.txt
    exit 1
fi
tar -cf archive.tar -T files.txt
rm -f files.txt
```
# Task_9
```
#!/bin/bash
if [ $# -ne 2 ]; then
    exit 1
fi
if [ ! -f "$1" ]; then
    echo "'$1' не найден"
    exit 1
fi
sed 's/    /\t/g' "$1" > "$2"
```
# Task_10
```
#!/bin/bash
if [ $# -ne 1 ]; then
    exit 1
fi
if [ ! -d "$1" ]; then
    echo "'$1' не является директорией"
    exit 1
fi
find "$1" -maxdepth 1 -type f -size 0 -name "*.txt" -print
```
