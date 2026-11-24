import random

questions = [
    {
        "question": "Which language is used for web development?",
        "options": ["A) HTML", "B) Python", "C) Both A and B", "D) None"],
        "answer": "C"
    },
    {
        "question": "What is the result of 5 + 3?",
        "options": ["A) 6", "B) 7", "C) 8", "D) 9"],
        "answer": "C"
    },
    {
        "question": "Which keyword defines a function in Python?",
        "options": ["A) function", "B) def", "C) fun", "D) define"],
        "answer": "B"
    },
    {
        "question": "Which data type stores True or False?",
        "options": ["A) str", "B) int", "C) list", "D) bool"],
        "answer": "D"
    },
    {
        "question": "Which symbol is used for comments in Python?",
        "options": ["A) //", "B) <!--", "C) #", "D) **"],
        "answer": "C"
    }
]

def play_quiz():
    score = 0
    random.shuffle(questions)

    print("\n=== PYTHON QUIZ GAME ===")
    print("Choose the correct answer: A, B, C, or D\n")

    for number, question in enumerate(questions, 1):
        print(f"{number}. {question['question']}")

        for option in question["options"]:
            print(option)

        answer = input("Your answer: ").strip().upper()

        if answer == question["answer"]:
            print("Correct!\n")
            score += 1
        else:
            print(
                f"Incorrect! Correct answer: "
                f"{question['answer']}\n"
            )

    print("=== QUIZ RESULTS ===")
    print(f"Your score: {score}/{len(questions)}")

    percentage = score / len(questions) * 100
    print(f"Accuracy: {percentage:.0f}%")

    if score == len(questions):
        print("Excellent! Perfect score!")
    elif score >= 3:
        print("Great job! Keep learning!")
    else:
        print("Keep practicing. You can do it!")

def main():
    while True:
        print("\n1. Start Quiz")
        print("2. Exit")

        choice = input("Choose an option: ")

        if choice == "1":
            play_quiz()
        elif choice == "2":
            print("Thanks for playing!")
            break
        else:
            print("Invalid choice. Try again.")

if __name__ == "__main__":
    main()
