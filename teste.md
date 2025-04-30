
# 📘 Resumo de Comandos Git

## ✅ 1. Configuração Inicial (Setup)

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
git init
git clone <url>
```

- `--global`: aplica a todos os repositórios.
- `git init`: cria um repositório local vazio.
- `git clone`: clona um repositório remoto.

---

## ✅ 2. Estados e Áreas

- **Working Directory**: arquivos sendo editados.
- **Staging Area (Index)**: arquivos prontos para commit.
- **Repository (HEAD)**: commits confirmados.

---

## ✅ 3. Registro de Mudanças (Histórico)

```bash
git status
git add <arquivo>
git commit -m "mensagem"
git commit --amend
git log
git log --oneline
git diff
```

---

## ✅ 4. Branches e Navegação

```bash
git branch
git branch <nome>
git checkout <branch>
git checkout -b <nova-branch>
git switch <branch>
git branch -d <branch>
```

---

## ✅ 5. Mesclagem (Merge)

```bash
git merge <branch>
git merge -X ours
git merge -X theirs
```

- Estratégias:
  - `ours`: prioriza a branch atual.
  - `theirs`: prioriza a branch a ser mesclada.

---

## ✅ 6. Colaboração Remota

```bash
git remote add origin <url>
git push origin <branch>
git fetch
git pull
```

---

## ✅ 7. Marcação e Versionamento

```bash
git tag v1.0.0
git tag -a v1.0.0 -m "Versão 1.0"
git push --tags
```

---

## ✅ 8. Reversões e Correções

```bash
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
git revert <commit>
git restore <arquivo>
```

---

## ✅ 9. Ferramentas Avançadas

```bash
git rebase <branch>
git cherry-pick <commit>
git stash
git stash apply
git stash pop
git bisect start
git bisect good <commit>
git bisect bad <commit>
```

---

## ✅ 10. Utilidades

```bash
git reflog
git blame <arquivo>
git gc --prune=now
```

---
