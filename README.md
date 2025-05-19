# assignment1
Python Task: Interactive Quiz GameObjective:Create a command-line quiz game in Python that:Presents the user with a series of multiple-choice questions.Checks the user's answers.Keeps track of the user's score.Provides feedback to the user after each question.Displays the final score at the end of the quiz.Functions:You must use at least the following functions:display_question(question_data): This function should take a dictionary containing the question, options, and correct answer, and display the question and options to the user.get_user_answer(): This function should get the user's answer from the console (e.g., using input()) and return it.check_answer(user_answer, correct_answer): This function should take the user's answer and the correct answer as arguments, compare them, and return True if the answer is correct, and False otherwise.update_score(current_score, is_correct): This function should take the current score and a boolean indicating whether the answer was correct. It should return the updated score.display_feedback(is_correct): This function should display feedback to the user, such as "Correct!" or "Incorrect."display_final_score(final_score): This function should take the final score and display it to the user at the end of the game.play_quiz(questions): This function should take a list of question dictionaries, control the flow of the quiz (calling the other functions), and return the final score.Example Question Data:questions = [
    {
        "question": "What is the capital of France?",
        "options": ["A. London", "B. Paris", "C. Rome", "D. Berlin"],
        "correct_answer": "B",
    },
    {
        "question": "What is the highest mountain in the world?",
        "options": ["A. K2", "B. Mount Kilimanjaro", "C. Mount Everest", "D. Mount Fuji"],
        "correct_answer": "C",
    },
    {
        "question": "What is the chemical symbol for water?",
        "options": ["A. H2O", "B. CO2", "C. O2", "D. NaCl"],
        "correct_answer": "A",
    },
]
Code:def display_question(question_data):
    """
    Displays a question and its options to the user.

    Args:
        question_data (dict): A dictionary containing the question, options,
                            and correct answer.
    """
    print(question_data["question"])
    for option in question_data["options"]:
        print(option)


def get_user_answer():
    """
    Gets the user's answer from the console.

    Returns:
        str: The user's answer (e.g., "A", "B", "C", or "D").
    """
    return input("Enter your answer (A, B, C, or D): ").upper()


def check_answer(user_answer, correct_answer):
    """
    Checks if the user's answer is correct.

    Args:
        user_answer (str): The user's answer.
        correct_answer (str): The correct answer.

    Returns:
        bool: True if the answer is correct, False otherwise.
    """
    return user_answer == correct_answer


def update_score(current_score, is_correct):
    """
    Updates the user's score based on whether the answer was correct.

    Args:
        current_score (int): The current score.
        is_correct (bool): True if the answer was correct, False otherwise.

    Returns:
        int: The updated score.
    """
    if is_correct:
        return current_score + 1
    else:
        return current_score


def display_feedback(is_correct):
    """
    Displays feedback to the user (e.g., "Correct!" or "Incorrect.").

    Args:
        is_correct (bool): True if the answer was correct, False otherwise.
    """
    if is_correct:
        print("Correct!")
    else:
        print("Incorrect.")


def display_final_score(final_score):
    """
    Displays the final score to the user.

    Args:
        final_score (int): The final score.
    """
    print(f"Your final score is: {final_score}")


def play_quiz(questions):
    """
    Controls the flow of the quiz game.

    Args:
        questions (list): A list of question dictionaries.

    Returns:
        int: The final score.
    """
    score = 0
    for question_data in questions:
        display_question(question_data)
        user_answer = get_user_answer()
        is_correct = check_answer(user_answer, question_data["correct_answer"])
        display_feedback(is_correct)
        score = update_score(score, is_correct)
    display_final_score(score)
    return score


if __name__ == "__main__":
    questions = [
        {
            "question": "What is the capital of France?",
            "options": ["A. London", "B. Paris", "C. Rome", "D. Berlin"],
            "correct_answer": "B",
        },
        {
            "question": "What is the highest mountain in the world?",
            "options": ["A. K2", "B. Mount Kilimanjaro", "C. Mount Everest", "D. Mount Fuji"],
            "correct_answer": "C",
        },
        {
            "question": "What is the chemical symbol for water?",
            "options": ["A. H2O", "B. CO2", "C. O2", "D. NaCl"],
            "correct_answer": "A",
        },
    ]
    play_quiz(questions)



