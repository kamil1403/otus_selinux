<p align="center">
  <img src="https://github.com/kamil1403/otus_selinux/blob/main/screenshots/selinux.jpg" alt="Banner" width="55%">
</p>

## ![Lesson](https://img.shields.io/badge/Lesson-otus__selinux-0A84FF?style=for-the-badge&logo=linux&logoColor=white&labelColor=111827)![Author](https://img.shields.io/badge/Author-Kamil%20Ibragimov-10B981?style=for-the-badge&logo=github&logoColor=white&labelColor=111827)![Date](https://img.shields.io/badge/Date-06.11.2025-F59E0B?style=for-the-badge&logo=calendar&logoColor=white&labelColor=111827)

### 📌 Задание:  
Запустить nginx на нестандартных портах 3-мя способами:
- [ ] Переключатели setsebool;
- [ ] Добавление нестандартного порта в имеющийся тип;
- [ ] Формирование и установка модуля SELinux (audit2allow).

Обеспечить работоспособность приложения при включенном SELnux:
- [ ] Развернуть приложенный стенд https://github.com/mbfx/otus-linux-adm/tree/master/selinux_dns_problems;
- [ ] Найти причину отказа обновления зоны;
- [ ] Реализовать и обосновать решение.
      
### ✅ Результат:   
- [x] Результат задания 1 - Все 3 способа для nginx реализованы. Результат см. на скриншоте 🖼️ ["my_ps.sh"](https://github.com/kamil1403/proc/blob/main/screenshots/my_ps.sh.png)
- [x] Результат задания 2 - Стенд selinux_dns_problems развернут, решена через setsebool. Результат см. на скриншоте 🖼️ ["my_ps.sh"](https://github.com/kamil1403/proc/blob/main/screenshots/my_ps.sh.png)
  

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
