##  ✅ Case 1: Undo last commit BUT keep your changes (safest)

git reset --soft HEAD~1

👉 What happens:

- Last commit is removed
- Your files stay as edited (unstaged)

If you already pushed to GitHub:

git push -f

---

## ✅ Case 2: Undo last commit AND delete changes

git reset --hard HEAD~1  
git push -f

👉 What happens:

- Last commit removed
- Changes are permanently deleted ❌

