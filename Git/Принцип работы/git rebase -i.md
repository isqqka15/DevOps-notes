**git rebase -i** - может быть использован для того , что бы изменить информацию о коммитах. 
```bash
# Открывает редактор текста (Nano, Vim, etc.)
git rebase -i HEAD~(ЧИСЛО) 

```

После открытия покажет, действие с коммитом (read, squash, ...), хэш и имя.
<mark style="background:#40a9ff">Все доступные действия с коммитами:</mark>

| Действие | Команда | Что произойдет |
| :--- | :--- | :--- |
| **Оставить все как есть** | `pick` | Коммит останется без изменений |
| **Переименовать** | `reword` | После сохранения Git предложит изменить сообщения |
| **Удалить** | `drop` | Коммит будет исключен из истории |
| **Поменять порядок** | (Просто переставить строки в редакторе) | Изменяет порядок коммитов |
| **Объединить с предыдущим коммитом** | `squash` | Сливается с предыдущим коммитом |
Пример вывода **git rebase -i HEAD~(ЧИСЛО)**
```bash
pick dbfb6df Релиз 1.0.
pick d90aa63 Релиз 2.0.

# Rebase d90aa63 onto 01e9c64 (2 commands)
#
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup [-C | -c] <commit> = like "squash" but keep only the previous
#                    commit's log message, unless -C is used, in which case
#                    keep only this commit's message; -c is same as -C but
#                    opens the editor
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
#         create a merge commit using the original merge commit's
#         message (or the oneline, if no original merge commit was
#         specified); use -c <commit> to reword the commit message
# u, update-ref <ref> = track a placeholder for the <ref> to be updated
#                       to this position in the new commits. The <ref> is
#                       updated at the end of the rebase
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# Если вы удалите строку здесь, то УКАЗАННЫЙ КОММИТ БУДЕТ УТЕРЯН.
#
# Но если вы удалите все, то процесс перемещения будет будет прерван.
#
```