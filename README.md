# codealphatask1
import tkinter as tk
from tkinter import messagebox

class PhishingTrainingModule:
    def __init__(self, root):
        self.root = root
        self.root.title("Phishing Awareness Training")

        # Create GUI components
        self.create_widgets()

    def create_widgets(self):
        # Introduction
        self.intro_label = tk.Label(self.root, text="Welcome to Phishing Awareness Training!", font=("Arial", 16))
        self.intro_label.pack(pady=10)

        self.intro_text = tk.Text(self.root, height=10, wrap=tk.WORD)
        self.intro_text.insert(tk.END, "Phishing attacks are a type of social engineering attack where attackers "
                                       "deceive individuals into providing sensitive information. This training module "
                                       "will help you recognize and avoid phishing emails, websites, and social engineering "
                                       "tactics.\n\nClick 'Next' to continue.")
        self.intro_text.config(state=tk.DISABLED)
        self.intro_text.pack(pady=10, padx=10)

        self.next_button = tk.Button(self.root, text="Next", command=self.show_phishing_examples)
        self.next_button.pack(pady=10)

    def show_phishing_examples(self):
        # Clear previous widgets
        self.clear_widgets()

        # Phishing Examples
        self.example_label = tk.Label(self.root, text="Examples of Phishing Attacks", font=("Arial", 16))
        self.example_label.pack(pady=10)

        self.example_text = tk.Text(self.root, height=15, wrap=tk.WORD)
        self.example_text.insert(tk.END, "1. Phishing Email: An email that appears to be from a legitimate source asking for "
                                         "personal information. It may contain links to malicious websites.\n\n"
                                         "2. Fake Websites: Websites that mimic legitimate sites to steal login credentials.\n\n"
                                         "3. Social Engineering: Attackers impersonating trusted individuals or organizations "
                                         "to extract sensitive information.\n\nClick 'Next' to learn how to avoid phishing attacks.")
        self.example_text.config(state=tk.DISABLED)
        self.example_text.pack(pady=10, padx=10)

        self.next_button = tk.Button(self.root, text="Next", command=self.show_prevention_tips)
        self.next_button.pack(pady=10)

    def show_prevention_tips(self):
        # Clear previous widgets
        self.clear_widgets()

        # Prevention Tips
        self.tips_label = tk.Label(self.root, text="How to Avoid Phishing Attacks", font=("Arial", 16))
        self.tips_label.pack(pady=10)

        self.tips_text = tk.Text(self.root, height=15, wrap=tk.WORD)
        self.tips_text.insert(tk.END, "1. Be Skeptical: Be wary of unsolicited emails and messages asking for personal information.\n\n"
                                      "2. Verify the Source: Check the sender's email address and verify the legitimacy of the request.\n\n"
                                      "3. Look for Red Flags: Poor grammar, spelling mistakes, and urgent requests are common in phishing emails.\n\n"
                                      "4. Don't Click Links: Avoid clicking on links in unsolicited emails. Instead, visit the website directly.\n\n"
                                      "5. Use Multi-Factor Authentication (MFA): Enable MFA for an extra layer of security.\n\n"
                                      "6. Report Phishing: Report suspicious emails to your IT department or email provider.\n\n"
                                      "Click 'Finish' to complete the training.")
        self.tips_text.config(state=tk.DISABLED)
        self.tips_text.pack(pady=10, padx=10)

        self.finish_button = tk.Button(self.root, text="Finish", command=self.show_completion_message)
        self.finish_button.pack(pady=10)

    def show_completion_message(self):
        # Clear previous widgets
        self.clear_widgets()

        # Completion Message
        self.completion_label = tk.Label(self.root, text="Training Complete!", font=("Arial", 16))
        self.completion_label.pack(pady=10)

        self.completion_text = tk.Text(self.root, height=5, wrap=tk.WORD)
        self.completion_text.insert(tk.END, "Congratulations! You have completed the Phishing Awareness Training. "
                                            "Remember to stay vigilant and protect your personal information.\n\n"
                                            "Thank you for participating!")
        self.completion_text.config(state=tk.DISABLED)
        self.completion_text.pack(pady=10, padx=10)

    def clear_widgets(self):
        for widget in self.root.winfo_children():
            widget.destroy()

if __name__ == "__main__":
    root = tk.Tk()
    app = PhishingTrainingModule(root)
    root.mainloop()
