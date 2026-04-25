# 🔑 Password Strength Checker

A Python security tool that checks how strong or weak any password is and gives tips to improve it.

---

## 📌 About This Project

Weak passwords are one of the biggest causes of cyber attacks.
This tool helps users understand how strong their password is and what they can do to make it stronger — just like a real security awareness tool!

---

## ⚙️ How It Works

The tool checks the password against 6 security rules:

| Rule | Points |
|---|---|
| Length 12+ characters | 3 points |
| Length 8-11 characters | 2 points |
| Has uppercase letters (A-Z) | 2 points |
| Has lowercase letters (a-z) | 1 point |
| Has numbers (0-9) | 2 points |
| Has special characters (!@#$) | 2 points |

### Strength Labels
| Score | Strength |
|---|---|
| 0-2 | 🔴 Very Weak |
| 3-4 | 🟠 Weak |
| 5-6 | 🟡 Moderate |
| 7-8 | 🟢 Strong |
| 9-10 | 💪 Very Strong |

---

## 🛠️ Technologies Used

- **Language:** Python 3
- **Library:** re — Regular Expressions (built-in)
- **Concept:** Password Security, Pattern Matching

---

## ▶️ How to Run

1. Make sure Python is installed
2. Run the script:
```bash
python password_checker.py
```
3. Type any password when prompted
4. See the score and feedback instantly!
5. Type `quit` to exit

---

## 📸 Output Example

```
Enter password: harsh123
------------------------------------------
  Password  : ********
  Score     : 4 / 10
  Strength  : 🟠 WEAK
------------------------------------------
  Feedback:
    ✅ Has numbers (0-9)
    ✅ Has lowercase letters (a-z)
    ❌ Add uppercase letters (A-Z)
    ❌ Add special characters (!@#$...)
    ⚠️  Use 12+ characters for better security
------------------------------------------
```

---

## 📚 What I Learned

- Python regex (regular expressions)
- Password security concepts
- Input validation techniques
- Security awareness tool development

---

## 👨‍💻 Author

**Harsh Patel**
BSc IT Student — GLS University, Ahmedabad
GitHub: github.com/harshpatel-15
