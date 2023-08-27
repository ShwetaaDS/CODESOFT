import tkinter
from tkinter import *
from PIL import Image, ImageTk
window = Tk()
#creating window
window.title("To-Do-List")
window.geometry("400x650")
window.resizable(TRUE, TRUE)
task_list = []
def addTask():
    task = task_entry.get()
    task_entry.delete(0, END)
    if task:
        with open("ss.txt", 'a') as taskfile:
            taskfile.write(f"\n{task}")
        task_list.append(task)
        lb1.insert(END, task)
def DT():
    global task_list
    task=str(lb1.get(ANCHOR))
    if  task in task_list:
        with open("ss.txt" ,'w') as taskfile:
            for task in task_list:
                taskfile.write(task+"\n")
        lb1.delete(ANCHOR)

def openTaskFile():
     try:
             global task_list
             with open("ss.txt", 'r') as taskfile:
               tasks = taskfile.readlines()
             for task in tasks:
                  if task !='\n':
                      task_list.append(task)
                      lb1.insert(END, task)
     except:
         file=open("ss.txt",'w')
         file.close()

topimg = PhotoImage(file="img.png", width=400 , height= 75)
#image_resize = topimg. resize(300, 200)
Label1 = Label(image=topimg)
Label1.pack(side=TOP,pady=0)
Label1.place(x=0, y=0)

var = StringVar()
label = Label( window, text = "TO-DO-LIST" , font="arial 25", height=1 , width= 15).place(x=50, y=15)

F1 = Frame(window, width=400, height=41, bg="white")
F1.place(x=0, y=150)
task = StringVar()
task_entry = Entry(F1, width=18, font="arial 20 ", bd=0)
task_entry.place(x=10, y=7)
task_entry.focus()

button1 = Button(window, text="ADD",  width="14", height="2 ", bg="#0000cd", fg="#fff", activebackground="#000fff000", command=addTask)
button1.place(x=290, y=150)

f2 = Frame(window,bd=3, bg="#a9a9a9", width="398", height="350")
f2.pack(pady=(160,0))
f2.place(x=0, y=191)

lb1 = Listbox(f2,font=('arial',12), width=43, height=18 , bg="#00bfff",fg="black", cursor="hand2",bd=0 , selectbackground="#5a95ff")
#lb1.pack(side=LEFT, fill=BOTH, padx=0)
lb1.place(x=0, y=1)

'''sb = Scrollbar(f2)
sb.pack(side=RIGHT, fill=Y)

lb1 = Listbox(yscrollcommand=sb.set)
sb.config(command=lb1.yview)'''

di = PhotoImage(file="di.png",width= 80, height= 80)
Button(window,image=di ,bd=0 , command=DT).pack(side=BOTTOM,pady=0)

#im = Image.open(r"C:\Users\Shweta\PycharmProjects\hey!\d.png")
'''width, height = im.size
left = 2
top = height/4
right = 2
bottom = 3* height/4
img1 = im.crop((left, top, right, bottom))
ns = (50,50)
img1 = img1.resize(ns)
img1.show()'''

#di.place(x=170, y=600)
window.mainloop()
