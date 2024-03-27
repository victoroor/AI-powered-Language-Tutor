# AI-powered-Language-Tutor
開発AI駆動の言語チューターは、ユーザーの能力に合わせてパーソナライズされたレッスンとフィードバックを提供し、言語学習を強化します。
import random

class AILanguageTutor:
    def __init__(self):
        self.lessons = {
            'beginner': ["Basic Greetings", "Numbers 1-10", "Simple Verbs"],
            'intermediate': ["Past and Future Tense", "Conditional Statements", "Complex Vocabulary"],
            'advanced': ["Subjunctive Mood", "Idiomatic Expressions", "Advanced Grammar"]
        }
        self.feedback_messages = {
            'correct': ["Great job!", "Correct answer!", "You're doing well!"],
            'incorrect': ["Try again!", "Incorrect, let's review this one.", "Keep practicing!"]
        }

    def get_user_level(self):
        level = input("What is your current language proficiency level (beginner, intermediate, advanced)? ")
        return level.lower()

    def select_lesson(self, level):
        if level in self.lessons:
            return random.choice(self.lessons[level])
        else:
            print("Invalid level. Defaulting to beginner.")
            return random.choice(self.lessons['beginner'])

    def simulate_lesson(self, lesson):
        print(f"Today's lesson is: {lesson}.")
        # Simulate a question-answer session (placeholder for actual lesson content and user interaction)
        answer = input("What is the capital of France? ").lower()
        if answer == "paris":
            feedback = random.choice(self.feedback_messages['correct'])
            print(feedback)
        else:
            feedback = random.choice(self.feedback_messages['incorrect'])
            print(feedback)

    def start_tutoring_session(self):
        user_level = self.get_user_level()
        lesson = self.select_lesson(user_level)
        self.simulate_lesson(lesson)

if __name__ == "__main__":
    tutor = AILanguageTutor()
    tutor.start_tutoring_session()
