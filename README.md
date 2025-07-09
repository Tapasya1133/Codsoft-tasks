# Codsoft-tasks
import tkinter as tk
from tkinter import messagebox

def add_task():
    task = entry.get()
    if task != "":
        listbox.insert(tk.END, task)
        entry.delete(0, tk.END)
    else:
        messagebox.showwarning("Input Error", "Please enter a task.")

def delete_task():
    try:
        selected_task = listbox.curselection()
        listbox.delete(selected_task)
    except:
        messagebox.showwarning("Selection Error", "Please select a task to delete.")

def clear_all():
    listbox.delete(0, tk.END)


root = tk.Tk()
root.title("To-Do List")
root.geometry("300x400")


entry = tk.Entry(root, width=25)
entry.pack(pady=10)


add_btn = tk.Button(root, text="Add Task", width=20, command=add_task)
add_btn.pack()


listbox = tk.Listbox(root, width=30, height=10)
listbox.pack(pady=10)


del_btn = tk.Button(root, text="Delete Task", width=20, command=delete_task)
del_btn.pack()


clear_btn = tk.Button(root, text="Clear All", width=20, command=clear_all)
clear_btn.pack(pady=10)


root.mainloop()
