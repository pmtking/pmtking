from tkinter import *
from tkinter.font import *
from tkinter import messagebox
from unit_converter import*

def calcualte_unit():
    #print('calculating...')
    unit_from = list_box_from.get(ACTIVE)
    unit_to = list_box_to.get(ACTIVE)
    value_from = int(entry_from.get())
    my_canveter=unit_canveter(unit_from, unit_to, value_from)


    

    #messagebox.showinfo(title='result',message=result)
    entry_to.delete(0,END)
    entry_to.insert(END,my_canveter.canverter_unit())
    


window = Tk()

my_font = Font(family='Consolas' , size=18)

pad_x = 5
pad_y = 5

label_from = Label(window, text='From', font = my_font)
label_to = Label(window, text='To' , font= my_font)
label_from.grid(row=0 , column = 0,sticky=W,padx = pad_x,pady=pad_y)
label_to.grid(row=0,column=1,sticky=W,padx = pad_x,pady=pad_y)

entry_from = Entry(window , font = my_font,fg='brown')
entry_to = Entry(window , font = my_font,fg='brown')
entry_from.grid(row=1,column=0,padx = pad_x,pady=pad_y)
entry_to.grid(row=1,column=1,padx = pad_x,pady=pad_y)

list_box_from = Listbox(window,exportselection=False, font = my_font)
list_box_to = Listbox(window,exportselection=False, font = my_font)
list_box_from.grid(row=2 , column=0,padx = pad_x,pady=pad_y)
list_box_to.grid(row=2 , column=1,padx = pad_x,pady=pad_y)
list_box_from.insert(END, 'Centimeter')
list_box_from.insert(END, 'Meter')
list_box_from.insert(END, 'Kilometer')
list_box_from.insert(END, 'Mile')
list_box_from.insert(END, 'Yard')
list_box_to.insert(END, 'Centimeter')
list_box_to.insert(END, 'Meter')
list_box_to.insert(END, 'Kilometer')
list_box_to.insert(END, 'Mile')
list_box_to.insert(END, 'Yard')

button = Button(window, text='Calculate', font = my_font,command=calcualte_unit)
button.grid(row=3 , column=0 , columnspan = 2 , sticky = W+E ,padx = pad_x,pady=pad_y)


window.mainloop()


