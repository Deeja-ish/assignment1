# assignment1

Python Task: Interactive Quiz GameObjective:Create a command-line quiz game in Python that:Presents the user with a series of multiple-choice questions.Checks the user's answers.Keeps track of the user's score.Provides feedback to the user after each question.Displays the final score at the end of the quiz.Functions:You must use at least the following functions:display_question(question_data):  This function should take a dictionary containing the question, options, and correct answer, and display the question and options to the user.get_user_answer():  This function should get the user's answer from the console (e.g., using input()) and return it.check_answer(user_answer, correct_answer):  This function should take the user's answer and the correct answer as arguments, compare them, and return True if the answer is correct, and False otherwise.update_score(current_score, is_correct):  This function should take the current score and a boolean indicating whether the answer was correct.  It should return the updated score.display_feedback(is_correct): This function should display feedback to the user, such as "Correct!" or "Incorrect."display_final_score(final_score):  This function should take the final score and display it to the user at the end of the game.play_quiz(questions): This function should take a list of question dictionaries, control the flow of the quiz (calling the other functions), and return the final score.Example Question Data:questions = [
    {
        "question": "What is the capital of France?",
        "options": ["A. London", "B. Paris", "C. Rome", "D. Berlin"],
        "correct_answer": "B"
    },
    {
        "question": "What is the highest mountain in the world?",
        "options": ["A. K2", "B. Mount Kilimanjaro", "C. Mount Everest", "D. Mount Fuji"],
        "correct_answer": "C"
    },
    {
        "question": "What is the chemical symbol for water?",
        "options": ["A. H2O", "B. CO2", "C. O2", "D. NaCl"],
        "correct_answer": "A"
    }
]
Bonus:Add a timer for each question.Implement different difficulty levels.Store questions in an external file (e.g., JSON).Add a loop to allow the user to play again.
