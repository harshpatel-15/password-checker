# password-checker
import re

# ─────────────────────────────────────
# STEP 1: List of most common passwords
# These are instantly rejected as weak
# ─────────────────────────────────────
common_passwords = [
    "password", "123456", "password123", "admin",
    "qwerty", "abc123", "letmein", "welcome",
    "monkey", "iloveyou", "1234567890", "000000"
]


# ─────────────────────────────────────
# STEP 2: Function to check password strength
# Returns a score and list of feedback
# ─────────────────────────────────────
def check_password(password):

    score    = 0        # Score out of 10
    feedback = []       # List of tips for user

    # ── Rule 1: Check common passwords ──
    if password.lower() in common_passwords:
        return 0, ["❌ This is a very common password. Never use this!"]

    # ── Rule 2: Length check ──
    if len(password) >= 12:
        score += 3
        feedback.append("✅ Good length (12+ characters)")
    elif len(password) >= 8:
        score += 2
        feedback.append("⚠️  Okay length (8-11 characters). Use 12+ for better security")
    else:
        score += 0
        feedback.append("❌ Too short! Use at least 8 characters")

    # ── Rule 3: Uppercase letters check ──
    if re.search(r'[A-Z]', password):
        score += 2
        feedback.append("✅ Has uppercase letters (A-Z)")
    else:
        feedback.append("❌ Add uppercase letters (A-Z)")

    # ── Rule 4: Lowercase letters check ──
    if re.search(r'[a-z]', password):
        score += 1
        feedback.append("✅ Has lowercase letters (a-z)")
    else:
        feedback.append("❌ Add lowercase letters (a-z)")

    # ── Rule 5: Numbers check ──
    if re.search(r'[0-9]', password):
        score += 2
        feedback.append("✅ Has numbers (0-9)")
    else:
        feedback.append("❌ Add numbers (0-9)")

    # ── Rule 6: Special characters check ──
    if re.search(r'[!@#$%^&*(),.?":{}|<>]', password):
        score += 2
        feedback.append("✅ Has special characters (!@#$...)")
    else:
        feedback.append("❌ Add special characters (!@#$...)")

    return score, feedback


# ─────────────────────────────────────
# STEP 3: Function to get strength label
# Converts score number to a label
# ─────────────────────────────────────
def get_strength_label(score):
    if score <= 2:
        return "🔴 VERY WEAK"
    elif score <= 4:
        return "🟠 WEAK"
    elif score <= 6:
        return "🟡 MODERATE"
    elif score <= 8:
        return "🟢 STRONG"
    else:
        return "💪 VERY STRONG"


# ─────────────────────────────────────
# STEP 4: Main program
# Keeps asking until user types 'quit'
# ─────────────────────────────────────
def run_checker():
    print("=" * 45)
    print("   PASSWORD STRENGTH CHECKER - Security Tool")
    print("=" * 45)
    print("Type your password to check its strength.")
    print("Type 'quit' to exit.\n")

    while True:
        # Ask user to enter password
        password = input("Enter password: ")

        # Exit if user types quit
        if password.lower() == "quit":
            print("Goodbye!")
            break

        # Check the password
        score, feedback = check_password(password)
        strength        = get_strength_label(score)

        # Show results
        print("\n" + "-" * 45)
        print(f"  Password  : {'*' * len(password)}")   # Hide password
        print(f"  Score     : {score} / 10")
        print(f"  Strength  : {strength}")
        print("-" * 45)
        print("  Feedback:")
        for tip in feedback:
            print(f"    {tip}")
        print("-" * 45 + "\n")


# ─────────────────────────────────────
# STEP 5: Run the program
# ─────────────────────────────────────
run_checker()
Python password strength checker tool
