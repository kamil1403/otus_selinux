<p align="center">
  <img src="https://github.com/kamil1403/otus_selinux/blob/main/screenshots/selinux.jpg" alt="Banner" width="55%">
</p>

## ![Lesson](https://img.shields.io/badge/Lesson-otus__selinux-0A84FF?style=for-the-badge&logo=linux&logoColor=white&labelColor=111827)![Author](https://img.shields.io/badge/Author-Kamil%20Ibragimov-10B981?style=for-the-badge&logo=github&logoColor=white&labelColor=111827)![Date](https://img.shields.io/badge/Date-06.11.2025-F59E0B?style=for-the-badge&logo=calendar&logoColor=white&labelColor=111827)

### 📌 Задание:   
- [ ] Написать свою реализацию ps ax используя анализ /proc
      
### ✅ Результат:   
- [x] Результат ДЗ - рабочий скрипт который можно запустить. Результат см. на скриншоте 🖼️ ["my_ps.sh"](https://github.com/kamil1403/proc/blob/main/screenshots/my_ps.sh.png)        

### 🧭 Оглавление
- [📝 Содержимое скрипта](#script)

---

<a id="script"></a>
## 📝 Содержимое скрипта

```bash
#!/bin/bash

echo "PID   CMD"

for p in /proc/[0-9]*; do
    pid=$(basename "$p")
    cmd=$(cat "$p/comm" 2>/dev/null)
    echo "$pid   [$cmd]"
done | head -n 10
```

---
