#SiMpLe CaLcUlAtOr

from tkinter import *
# window
root=Tk()

#Text 
e=Entry(root,width=35,borderwidth=5,font=40)
e.grid(row=0,column=0,columnspan=5)

#Button functions
def b(n):
    c=str(e.get())+str(n)
    e.delete(0,END)
    e.insert(0,c)

def add():
    f=e.get()
    global f1
    global maths
    maths='+'
    f1=float(f)
    e.delete(0,END)

def sub():
    f=e.get()
    global f1
    global maths
    maths='-'
    f1=float(f)
    e.delete(0,END)
    
def div():
    f=e.get()
    global f1
    global maths
    maths='/'
    f1=float(f)
    e.delete(0,END)
    
def mul():
    f=e.get()
    global f1
    global maths
    maths='*'
    f1=float(f)
    e.delete(0,END)

def exponential():
     f=e.get()
     global f1
     global maths
     maths='^'
     f1=float(f)
     e.delete(0,END)
    
def remainder():
     f=e.get()
     global f1
     global maths
     maths='%'
     f1=float(f)
     e.delete(0,END)
    
def factorial():
     f=e.get()
     global f1
     global maths
     maths='!'
     f1=int(f)
     s=1
     for i in range(1,f1+1):
         s*=i
     e.delete(0,END)
     e.insert(0,s)

def sqroot():
     f=e.get()
     global f1
     global maths
     maths='√'
     f1=float(f)
     import math
     from math import sqrt
     s=sqrt(f1)
     e.delete(0,END)
     e.insert(0,s)

def fun():
    def fsin():
        e.insert(0,'sin ')
        global maths
        maths='sin'
        win.quit
    win=Tk()
    win.geometry='50,50'
    b_sin=Button(win,text='sin',font=30,command=fsin)
    b_sin.pack()

    
def equal():
    s=e.get()
    if maths != 'sin':
        global s1
        s1=float(s)
    global c
    c=0
       
    if maths=='+':
        c=f1+s1
    if maths=='-':
        c=f1-s1
    if maths=='*':
        c=f1*s1
    if maths=='/':
        c=f1/s1
    if maths=='^':
        c=f1**s1
    if maths=='%':
        c=f1%s1
    if maths=='sin':
        import math
        from math import sin,degrees
        
        s=s[3:]
        s=float(s)
        s=degrees(s)
        c=sin(s)
    e.delete(0,END)
    e.insert(0,c)

def clear():
    e.delete(0,END)

#Buttons defined
b_1=Button(root, text='1',padx=40, pady=40,font=20, command=lambda:b(1))
b_2=Button(root, text='2',padx=40, pady=40,font=20, command=lambda:b(2))
b_3=Button(root, text='3',padx=40, pady=40,font=20, command=lambda:b(3))
b_4=Button(root, text='4',padx=40, pady=40,font=20, command=lambda:b(4))
b_5=Button(root, text='5',padx=40, pady=40,font=20, command=lambda:b(5))
b_6=Button(root, text='6',padx=40, pady=40,font=20, command=lambda:b(6))
b_7=Button(root, text='7',padx=40, pady=40,font=20, command=lambda:b(7))
b_8=Button(root, text='8',padx=40, pady=40,font=20, command=lambda:b(8))
b_9=Button(root, text='9',padx=40, pady=40,font=20, command=lambda:b(9))
b_0=Button(root, text='0',padx=40, pady=40,font=20, command=lambda:b(0))


b_add=Button(root, text='+',padx=40, pady=40,font=20, command=add)
b_clear=Button(root, text='Clear',padx=79, pady=40,font=20,command=clear)
b_equal=Button(root, text='=',padx=80, pady=40,font=20,command=equal)

b_subtract=Button(root, text='-',padx=41, pady=40, font=20,command=sub)
b_divide=Button(root, text='/',padx=40, pady=40, font=20,command=div)
b_multiply=Button(root, text='*',padx=40, pady=40, font=20,command=mul)

b_exponential=Button(root, text='^',padx=40, pady=40,font=20,command=exponential)
b_remainder=Button(root, text='%',padx=40, pady=40,font=20, command=remainder)
b_factorial=Button(root, text='!',padx=40, pady=40,font=20, command=factorial)


b_root=Button(root, text='√',padx=40, pady=40,font=20,command=sqroot)
b_r=Button(root, text='>',padx=40, pady=40,font=20,command=fun)


#Buttons position
b_1.grid(row=3,column=0)
b_2.grid(row=3,column=1)
b_3.grid(row=3,column=2)

b_4.grid(row=2,column=0)
b_5.grid(row=2,column=1)
b_6.grid(row=2,column=2)

b_7.grid(row=1,column=0)
b_8.grid(row=1,column=1)
b_9.grid(row=1,column=2)

b_0.grid(row=4,column=0)
b_add.grid(row=5,column=0)

b_equal.grid(row=5,column=1,columnspan=2)
b_clear.grid(row=4,column=1,columnspan=2)

b_subtract.grid(row=6,column=0)
b_divide.grid(row=6,column=1)
b_multiply.grid(row=6,column=2)

b_exponential.grid(row=1,column=4)
b_remainder.grid(row=2,column=4)
b_factorial.grid(row=3,column=4)

b_root.grid(row=4,column=4)
b_r.grid(row=5,column=4)

