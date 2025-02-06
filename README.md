import tkinter as tk
def on_button_click(value):
current_text = entry_var.get()
if value == "c":
entry_var.set("")
elif value == "=":
try:
entry_var.set(eval(current_text))
except:
entry_var.set("Error")
else:
entry_var.set(current_text + value)
root = tk.Tk()
root.title("calcualtor")
root.geometry("300*400)
entry_var = tk.StringVar()
entry = tk.Entry(root,textvariable=entry_var,
font=("Arial",20),justify="right", bd=10,
relief=tk.SUNKEN)
entry.gride(row=0, column=0, columnspan=4,
ipadx=8, ipady=8)

buttons = [
("7", "8", "9", "/"),
("4", "5", "6", "*"),
("1", "2", "3", "-"),
("c", "0", "=", "+"),

for r, row in enumerate(buttons, start=1):
for c char in enumarate(row):
tk.button(
root, text=char, font=("Arial",
20),width=5, height=2,
command=lambda ch=char:
on_button_click(ch)
).grid(row=r, column=c, padx=5,
pady=5)
root.mainloop()



