# PLAYING-QUIZ-PROGRAM 
import random

# Load Quiz Questions
quiz_questions = [
    {
        "question": "What is the capital of France?",
        "answers": [
            "Paris",
            "London",
            "Berlin",
            "Rome"
        ],
        "correct_answer": 0
    },
    {
        "question": "What is the largest ocean on Earth?",
        "answers": [
            "Atlantic Ocean",
            "Indian Ocean",
            "Arctic Ocean",
            "Pacific Ocean"
        ],
        "correct_answer": 3
    },
    # Add more questions here
]

# Display Welcome Message and Rules
print("Welcome to the Quiz Game!")
print("You will be asked multiple-choice questions on various topics.")
print("Answer each question by entering the corresponding number.")
print("Good luck!\n")

def play_quiz():
    score = 0
    num_questions = len(quiz_questions)

    # Present Quiz Questions
    for question in quiz_questions:
        print(question["question"])
        for i, answer in enumerate(question["answers"]):
            print(f"{i+1}. {answer}")

        # Prompt the user to select an answer
        user_answer = int(input("\nEnter your answer (1-4): "))

        # Evaluate the User's Answer
        if user_answer - 1 == question["correct_answer"]:
            print("Correct!")
            score += 1
        else:
            print(f"Incorrect. The correct answer is: {question['answers'][question['correct_answer']]}")

        print(f"Current score: {score}/{num_questions}\n")

    # Display Final Results
    print(f"Quiz complete! Your final score is: {score}/{num_questions}")

    # Play Again
    play_again = input("Do you want to play again? (y/n) ").lower()
    if play_again == "y":
        play_quiz()
    else:
        print("Thank you for playing!")
