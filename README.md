# Python-OS-test-0.1
Lol it's an OS on Python(Only interface, not a full OS now.).
So, here is OS
import tkinter as tk
from tkinter import messagebox, Text, filedialog
import random

def open_text_editor():
    editor_window = tk.Toplevel(root)
    editor_window.title("Текстовый Редактор")
    editor_window.attributes("-topmost", True)

    text_area = Text(editor_window, wrap='word')
    text_area.pack(expand=True, fill='both')

    def save_file():
        file_content = text_area.get("1.0", tk.END)
        file_path = filedialog.asksaveasfilename(defaultextension=".txt",
                                                   filetypes=[("Text files", "*.txt"), ("All files", "*.*")])
        if file_path:
            with open(file_path, "w") as file:
                file.write(file_content)
            messagebox.showinfo("Информация", f"Файл сохранен как '{file_path}'")

    def open_file():
        file_path = filedialog.askopenfilename(filetypes=[("Text files", "*.txt"), ("All files", "*.*")])
        if file_path:
            with open(file_path, "r") as file:
                file_content = file.read()
                text_area.delete("1.0", tk.END)
                text_area.insert("1.0", file_content)

    save_button = tk.Button(editor_window, text="Сохранить", command=save_file)
    save_button.pack(pady=10)

    open_button = tk.Button(editor_window, text="Открыть", command=open_file)
    open_button.pack(pady=10)

def start_guessing_game():
    random_number = random.randint(1, 100)  # Загадать число от 1 до 100
    attempts = 0

    def check_guess():
        nonlocal attempts
        user_guess = entry.get()
        attempts += 1
        if not user_guess.isdigit():
            messagebox.showwarning("Предупреждение", "Введите правильное число!")
            return
        user_guess = int(user_guess)

        if user_guess < random_number:
            messagebox.showinfo("Результат", "Загаданное число больше!")
        elif user_guess > random_number:
            messagebox.showinfo("Результат", "Загаданное число меньше!")
        else:
            messagebox.showinfo("Поздравляем!", f"Вы угадали число {random_number} за {attempts} попыток!")
            guess_window.destroy()  # Закрыть окно после удачного угадывания

    guess_window = tk.Toplevel(root)
    guess_window.title("Игра: Угадай число")
    guess_window.attributes("-topmost", True)

    label = tk.Label(guess_window, text="Угадайте число от 1 до 100:")
    label.pack(pady=10)

    entry = tk.Entry(guess_window)
    entry.pack(pady=10)

    check_button = tk.Button(guess_window, text="Проверить", command=check_guess)
    check_button.pack(pady=10)

def show_info():
    messagebox.showinfo("Информация", "Это простая операционная система на Tkinter!")

# Создание главного окна
root = tk.Tk()
root.title("Python OS test 0.1")
root.geometry("650x650")

# Создание меню
menu = tk.Menu(root)
root.config(menu=menu)

def kill():
    root.destroy()
def Browser():
    print()

# Добавление элементов в меню
file_menu = tk.Menu(menu)
menu.add_cascade(label='Файл', menu=file_menu)
file_menu.add_command(label='Открыть текстовый редактор', command=open_text_editor)
file_menu.add_separator()
file_menu.add_command(label='Выход', command=kill)
file_menu.add_command(label='Открыть Браузер', command=Browser)

game_menu = tk.Menu(menu)
menu.add_cascade(label='Игры', menu=game_menu)
game_menu.add_command(label='Угадай число', command=start_guessing_game)

help_menu = tk.Menu(menu)
menu.add_cascade(label='Справка', menu=help_menu)
help_menu.add_command(label='Информация', command=show_info)
def start_guessing_game():
    random_number = random.randint(1, 100)  # Загадать число от 1 до 100
    attempts = 0

    def check_guess():
        nonlocal attempts
        user_guess = entry.get()
        attempts += 1
        if not user_guess.isdigit():
            messagebox.showwarning("Предупреждение", "Введите правильное число!")
            return
        user_guess = int(user_guess)

        if user_guess < random_number:
            messagebox.showinfo("Результат", "Загаданное число больше!")
        elif user_guess > random_number:
            messagebox.showinfo("Результат", "Загаданное число меньше!")
        else:
            messagebox.showinfo("Поздравляем!", f"Вы угадали число {random_number} за {attempts} попыток!")
            guess_window.destroy()  # Закрыть окно после удачного угадывания

    guess_window = tk.Toplevel(root)
    guess_window.title("Игра: Угадай число")
    guess_window.geometry("400x300")  # Увеличиваем размер окна до 400x300 пикселей
    
    label = tk.Label(guess_window, text="Угадайте число от 1 до 100:", font=("Helvetica", 16))
    label.pack(pady=20)

    entry = tk.Entry(guess_window, font=("Helvetica", 16))
    entry.pack(pady=10)

    check_button = tk.Button(guess_window, text="Проверить", command=check_guess, font=("Helvetica", 16))
    check_button.pack(pady=20)
def start_guessing_game():
    random_number = random.randint(1, 100)  # Загадать число от 1 до 100
    attempts = 0

    def check_guess():
        nonlocal attempts
        user_guess = entry.get()
        attempts += 1
        if not user_guess.isdigit():
            messagebox.showwarning("Предупреждение", "Введите правильное число!")
            return
        user_guess = int(user_guess)

        if user_guess < random_number:
            messagebox.showinfo("Результат", "Загаданное число больше!")
        elif user_guess > random_number:
            messagebox.showinfo("Результат", "Загаданное число меньше!")
        else:
            messagebox.showinfo("Поздравляем!", f"Вы угадали число {random_number} за {attempts} попыток!")
            guess_window.destroy()  # Закрыть окно после удачного угадывания

    guess_window = tk.Toplevel(root)
    guess_window.title("Игра: Угадай число")
    guess_window.geometry("400x600")  # Увеличиваем размер окна до 400x300 пикселей
    guess_window.attributes('-topmost', True)  # Делаем окно всегда поверх других

    label = tk.Label(guess_window, text="Угадайте число от 1 до 100:", font=("Helvetica", 16))
    label.pack(pady=20)

    entry = tk.Entry(guess_window, font=("Helvetica", 16))
    entry.pack(pady=10)

    check_button = tk.Button(guess_window, text="Проверить", command=check_guess, font=("Helvetica", 16))
    guess_window = tk.Toplevel(root)
    guess_window = tk.Toplevel(root)
    guess_window.title("Игра: Угадай число")
    guess_window.attributes('-topmost', True)
# Запуск главного цикла приложения
root.mainloop()
#copy this lol
