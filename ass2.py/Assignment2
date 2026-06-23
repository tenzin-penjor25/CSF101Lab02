
# Task 1: Input Validation


def get_valid_number():
    """
    Repeatedly prompt the user until a valid integer between 3 and 9
    (inclusive) is entered.
    Time complexity : O(k) where k is the number of invalid attempts
    Space complexity: O(1)
    """
    while True:
        try:
            n = int(input("Enter a number between 3 and 9: "))
            if 3 <= n <= 9:
                return n
            else:
                print("Invalid input. Please enter a number between 3 and 9.")
        except ValueError:
            print("Invalid input. Please enter a whole number between 3 and 9.")



# Task 2: Generate Personal Code


def generate_personal_code(student_id, keyword):
    """
    Build a personal code: <first_letter>-<student_id>-<last_letter>
    Letters are converted to uppercase for consistency.

    Time complexity : O(1)  – only the first and last characters are accessed
    Space complexity: O(1)
    """
    first = keyword[0].upper()
    last  = keyword[-1].upper()
    return f"{first}-{student_id}-{last}"



# Task 3: Character Frequency Using Dictionary


def count_character_frequency(name):
    """
    Count occurrences of each alphabetic character in *name*.
    - Spaces are ignored.
    - Case is ignored (all converted to lowercase).

    Returns a dict mapping character -> count.

    Time complexity : O(n) where n = len(name)
    Space complexity: O(a) where a = number of distinct characters (≤ 26)
    """
    frequency = {}
    for ch in name.lower():
        if ch == ' ':       # skip spaces
            continue
        if ch.isalpha():    # only count letters
            frequency[ch] = frequency.get(ch, 0) + 1
    return frequency



# Task 4: Unique Vowels and Consonants


def find_unique_vowels_consonants(text):
    """
    Scan *text* (name + keyword combined) and return two sorted lists:
      - unique vowels
      - unique consonants
    Case is ignored; non-alphabetic characters are skipped.

    Time complexity : O(n) where n = len(text)
    Space complexity: O(a) where a = number of distinct alphabetic characters
    """
    vowels_set     = set()
    consonants_set = set()
    vowel_letters  = set('aeiou')

    for ch in text.lower():
        if not ch.isalpha():
            continue
        if ch in vowel_letters:
            vowels_set.add(ch)
        else:
            consonants_set.add(ch)

    return sorted(vowels_set), sorted(consonants_set)



# Task 5: Stack-Based Bracket Checker


def check_balanced_brackets(expression):
    """
    Use a list as a stack to verify that every opening bracket in
    *expression* is closed correctly and in the right order.

    Supported pairs: () [] {}

    Returns True if balanced, False otherwise.

    Time complexity : O(n) where n = len(expression)
    Space complexity: O(n) in the worst case (all openers)
    """
    stack    = []                              # list used as a stack
    matching = {')': '(', ']': '[', '}': '{'}
    openers  = set('([{')

    for ch in expression:
        if ch in openers:
            stack.append(ch)                   # push onto stack
        elif ch in matching:
            if not stack or stack[-1] != matching[ch]:
                return False                   # unmatched closer
            stack.pop()                        # pop matched opener

    return len(stack) == 0                     # True only if stack is empty



# Task 6: Queue-Based Task Simulation


def process_keyword_queue(keyword):
    """
    Build a FIFO queue (list) of tasks – one per character in *keyword* –
    then process (dequeue) them in order, printing each task.

    Time complexity : O(n) to build + O(n) to process = O(n)
                      where n = len(keyword)
    Space complexity: O(n) for the queue
    """
    # Enqueue phase – build the queue
    queue = []
    for ch in keyword:
        queue.append(f"Analyse {ch}")          # append = enqueue (O(1))

    # Dequeue phase – process in FIFO order
    print("\nQueue Processing:")
    while queue:
        task = queue.pop(0)                    # pop(0) = dequeue front
        print(f"  Processing: {task}")



# Task 7: Number Pattern Using Loops


def print_number_pattern(number):
    """
    Print a right-angled number triangle with *number* rows.

    Row i (1-indexed) prints: 1  2  3  …  i

    Time complexity : O(k²) where k = number
                      (total numbers printed = k*(k+1)/2)
    Space complexity: O(1) – no additional storage needed
    """
    print("\nNumber Pattern:")
    for row in range(1, number + 1):           # outer loop: rows
        line = ""
        for col in range(1, row + 1):          # inner loop: columns
            line += str(col) + " "
        print(" ", line.strip())



# Task 8: Recursive Digit Sum


def recursive_digit_sum(student_id):
    """
    Recursively sum every digit in *student_id* (treated as a string).

    Base case : only one digit remains → return int value.
    Recursive : first digit + recursive_digit_sum(remaining digits).

    Time complexity : O(d) where d = number of digits in student_id
    Space complexity: O(d) for the call stack
    """
    sid = str(student_id)
    if len(sid) == 1:
        return int(sid)
    return int(sid[0]) + recursive_digit_sum(sid[1:])



# Summary Display


def display_summary(student_id, full_name, keyword, number,
                    bracket_expr, personal_code, freq,
                    vowels, consonants, balanced, digit_sum):
    """
    Print all results in a well-formatted summary report.
    """
    print("\n" + "=" * 45)
    print("           RESULTS SUMMARY")
    print("=" * 45)

    # Personal Code
    print(f"\nPersonal Code: {personal_code}")

    # Character Frequency
    print("\nCharacter Frequency:")
    for ch, count in freq.items():
        print(f"  {ch} : {count}")

    # Unique Vowels & Consonants
    print(f"\nUnique Vowels    : {', '.join(vowels)}")
    print(f"Unique Consonants: {', '.join(consonants)}")

    # Bracket Check
    print(f"\nBalanced Brackets: {'Yes' if balanced else 'No'}")

    # Queue Processing is printed inside process_keyword_queue()

    # Number Pattern is printed inside print_number_pattern()

    # Recursive Digit Sum
    print(f"\nRecursive Digit Sum of Student ID ({student_id}): {digit_sum}")

    print("\n" + "=" * 45)



# Main Program


def main():
    print("=" * 45)
    print("      Personal Pattern Toolkit")
    print("=" * 45)

    # ── Collect inputs ──────────────────────────
    student_id   = input("\nEnter Student ID  : ").strip()
    full_name    = input("Enter Full Name   : ").strip()
    keyword      = input("Enter Keyword     : ").strip()
    number       = get_valid_number()
    bracket_expr = input("Enter bracket expression: ").strip()

    # ── Task 2: Personal Code ───────────────────
    personal_code = generate_personal_code(student_id, keyword)

    # ── Task 3: Character Frequency ─────────────
    freq = count_character_frequency(full_name)

    # ── Task 4: Unique Vowels & Consonants ──────
    combined_text = full_name + keyword
    vowels, consonants = find_unique_vowels_consonants(combined_text)

    # ── Task 5: Bracket Checker ─────────────────
    balanced = check_balanced_brackets(bracket_expr)

    # ── Task 6: Queue Processing ─────────────── (prints inline)
    process_keyword_queue(keyword)

    # ── Task 7: Number Pattern ───────────────── (prints inline)
    print_number_pattern(number)

    # ── Task 8: Recursive Digit Sum ─────────────
    digit_sum = recursive_digit_sum(student_id)

    # ── Display full summary ─────────────────────
    display_summary(
        student_id, full_name, keyword, number,
        bracket_expr, personal_code, freq,
        vowels, consonants, balanced, digit_sum
    )


# Entry point
if __name__ == "__main__":
    main()