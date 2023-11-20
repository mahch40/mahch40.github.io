---
layout: posts
title: "Turtle فرکتال جنگل در کتابخانه"
---
<div
dir="rtl"
style="font-style:Tahoma">
تو پست زیر فهمیدیم چجوری یه درخت بکشیم
:
<center>

<br>

<a 
href="/Post-Number-2">
    <button>فرکتال درخت
    </button>

  </a>

</center>  
حالا می خوایم یک جنگل بکشیم
!
کار سختی نیست فقط باید چند مرحله رو انجام بدیم
:
1-زاویه و طول و قطز شاخه های درخت مون رو رندوم
(شانسی)
بکنیم
.
2-یه تابع تعریف کنیم که یه تعدادی درخت رسم کنه در مکان های رندوم
.
<br>
چون میخوایم از اعداد رندوم استفاده کنیم میزنیم
:
<pre>
import random
</pre>
مرحله اول
:
به طور کلی برای مرحله اول و دوم تفییر رو در ضربی که در اندازه درخت کردیم انجام می دیم
.
چجوری؟
d
(
یعنی طول شاخه
)
رو بجای ضرب در یک عدد مثل 0.7
در یک عدد رندوم ضرب میکنیم که دستورش رو در پایین میبینیم برای زاویه و قطر هم همین کار رو میکنیم
پس کد درخت ما در اصل به صورت زیر در میاد
:
(تقسیم بر دو بعلاوه یک عدد برای اینه که اندازه بین صفر و یک باشه)
<pre>
def Tree(d,r,s):
    turtle.pencolor("Brown")
    if d<10:
        turtle.pensize(5)
        turtle.penup()
        return
    turtle.pensize(s)
    turtle.forward(d)
    turtle.left(r)
    Tree(d*(random.random()/2+0.5),r*(random.random()/2+0.7),s*(random.random()/2+0.5)) 
    turtle.pendown()
    turtle.right(2*r)
    Tree(d*(random.random()/2+0.5),r*(random.random()/2+0.7),s*(random.random()/2+0.5))
    turtle.left(r)
    turtle.backward(d)
</pre>
مرحله دوم
:
حالا تابع دوم
.
من اسمش رو گذاشتم 
make jungle
.
در این تابع ابتدا یک مکان اولیه برای شروع رسم میدیم یعنی داریم
(عدد هایی که من دادم قابلیت تغییر به دلخواه دارن فقط به گونه ای نباشه که از کادر بزنه بیرون)
:
x=-700
y=-100
<br>
بعد یک حلفه می زنیم تا برای تعدادی دفعه درخت رسم کنه من تعداد درخت ها رو 35 دادم ولی هر تعدادی بسته به شلوغی یا خلوتی جنگل متفاوته
.
زیر حلفه اول باید کاری کنیم که رندوم مختصات بده به درخت و وقتی میره به اون مقصد چیزی رسم نکنه یعنی پن آپ و پن داون.همچنین با دستور 
(turtle.setpos(x,y))
مکانش رو تعیین می کنیم
و میگیم هربار 
x 
یعنی مکان افقی رو با یه عدد رندوم بین 0 و 150 جمع بزنه و رسم کنه 
و 
y 
یعنی مکان عمودی رو هربار یک عدد رندوم بین 0 و 150 قرار بده
،
و بعد تابع درخت رو صدا می زنیم
.
داریم
:
<pre>
def make_jungle():
    x=-700
    y=-100
    for _ in range(35):
        turtle.penup()
        x+=random.randint(0,100)
        y=random.randint(0,150)
        turtle.setpos(x,y)
        turtle.pendown()
        Tree(50,15,10.5) 
</pre>
حالا همانطور که در رسم درخت توضیح دادم باید بگیم لاکپشتمون نود درجه به چپ بچرخه 
و بعد تابع رو رسم کنه 
.
برای افزایش سرعت میتونیم از دستور
(turtle.speed(0))
استفاده کنیم که لاکپشتمون با سرعت بالا رسم میکنه
(لاکپشت با سرعت بالا تضاد جالبیه مگه نه؟)
در آخر از دو دستور هاید ترتل و مین لوپ غافل نشیم
<br>
پس صورت کلی کد ما به صورت زیر میشه
:
<pre>
import turtle
import random

def Tree(d,r,s):
    turtle.pencolor("Brown")
    if d<10:
        turtle.pensize(5)
        turtle.penup()
        return
    turtle.pensize(s)
    turtle.forward(d)
    turtle.left(r)
    Tree(d*(random.random()/2+0.5),r*(random.random()/2+0.7),s*(random.random()/2+0.5)) 
    turtle.pendown()
    turtle.right(2*r)
    Tree(d*(random.random()/2+0.5),r*(random.random()/2+0.7),s*(random.random()/2+0.5))
    turtle.left(r)
    turtle.backward(d)

def make_jungle():
    x=-700
    y=-100
    for _ in range(35):
        turtle.penup()
        x+=random.randint(0,100)
        y=random.randint(0,150)
        turtle.setpos(x,y)
        turtle.pendown()
        Tree(50,15,10.5) 
turtle.tracer(0)
turtle.left(90)
turtle.hideturtle()
make_jungle()
turtle.update()
turtle.mainloop()
</pre>
خروجی
:
<br>

<center>

<img 

src="/assets/images/Screenshot4.png">

</center>
و با کمی خلاقیت میشه جنگل های زیبایی درست کرد.چیزی که من درست کردم به صورت زیر شد کد و خروجیش
:
<pre>
import turtle
import random
import time

turtle.hideturtle()
turtle.right(90)
color=turtle.pencolor()

def Sea():
    z=0
    
    for _ in range(4):
        z+=-70
        turtle.pencolor("Turquoise")
        turtle.pensize(10)
        turtle.penup()
        turtle.setpos(1000,z)
        turtle.pendown()
        turtle.forward(5000)
        time.sleep(0.1)

        turtle.pencolor("Turquoise")
        turtle.pensize(10)
        turtle.penup()
        turtle.setpos(1000,z-10)
        turtle.pendown()
        turtle.forward(5000)
        time.sleep(0.1)

        turtle.pencolor("Cyan")
        turtle.pensize(10)
        turtle.penup()
        turtle.setpos(1000,z-20)
        turtle.pendown()
        turtle.forward(5000)
        time.sleep(0.1)

        turtle.pencolor("Cyan")
        turtle.pensize(10)
        turtle.penup()
        turtle.setpos(1000,z-30)
        turtle.pendown()
        turtle.forward(5000)
        time.sleep(0.1)

        turtle.pencolor("Blue")
        turtle.pensize(10)
        turtle.penup()
        turtle.setpos(1000,z-40)
        turtle.pendown()
        turtle.forward(5000)
        time.sleep(0.1)

        turtle.pencolor("Blue")
        turtle.pensize(10)
        turtle.penup()
        turtle.setpos(1000,z-50)
        turtle.pendown()
        turtle.forward(5000)
        time.sleep(0.1)

        turtle.pencolor("Cyan")
        turtle.pensize(10)
        turtle.penup()
        turtle.setpos(1000,z-60)
        turtle.pendown()
        turtle.forward(5000)

def Leaves1(d):
    turtle.pencolor("light Green")
    turtle.fillcolor("Light Green")
    turtle.begin_fill()
    turtle.forward((2*(3**0.5))*d)
    turtle.right(150)
    turtle.forward(2*d)
    turtle.right(60)
    turtle.forward(2*d)
    turtle.end_fill()

def Leaves2(d):
    turtle.pencolor("Green")
    turtle.fillcolor("Light Green")
    turtle.begin_fill()
    turtle.left(60)
    turtle.backward(2*d)
    turtle.left(120)
    turtle.forward(2*d)
    turtle.left(30)
    turtle.end_fill()
    turtle.backward((2*(3**0.5))*d)

def Tree(d,r,s):
    turtle.pencolor("Brown")
    if d<10:
        turtle.pensize(5)
        Leaves1(d/3)
        Leaves2(d/3)
        turtle.penup()
        return
    turtle.pensize(s)
    turtle.forward(d)
    turtle.left(r)
    Tree(d*(random.random()/2+0.5),r*(random.random()/2+0.7),s*(random.random()/2+0.5)) 
    turtle.pendown()
    turtle.right(2*r)
    Tree(d*(random.random()/2+0.5),r*(random.random()/2+0.7),s*(random.random()/2+0.5))
    turtle.left(r)
    turtle.backward(d)
    turtle.pencolor(color)
turtle.left(90)

def setup_screen(width,height):
    turtle.screensize(width,height)

def Bush(a,b,c):
        turtle.pencolor("Green")
        
        if a<1:
            turtle.penup()
            return

        turtle.pensize(c)
        turtle.forward(a)
        turtle.left(b)
        Bush(a *(random.random()/2+0.5),b*(random.random()/2+0.7),c*(random.random()/2+0.5)) 
        turtle.pendown()
        turtle.right(2*b)
        Bush(a*(random.random()/2+0.5),b*(random.random()/2+0.7),c*(random.random()/2+0.5))
        turtle.left(b)
        turtle.backward(a)
        turtle.pencolor(color)
turtle.left(90)


width=2500
height=3000
x=-width/2 + 150
y=-height/2 -100
setup_screen(width,height)

turtle.left(90)
turtle.speed(0)
Sea()
turtle.right(90)

for _ in range(35):
    turtle.penup()
    x+=random.randint(0,100)
    y=random.randint(0,150)
    turtle.setpos(x,y)
    turtle.pendown()
    turtle.tracer(0)
    Tree(50,15,10.5) 
    turtle.update()
    time.sleep(0.3)

x=-width/2 + 150

for _ in range(random.randint(30,40)):
    turtle.penup()
    x+=random.randint(0,100)
    y=random.randint(0,20)
    turtle.setpos(x,y)
    turtle.pendown()
    turtle.tracer(0)
    Tree(30,15,10.5) 
    turtle.update()
    time.sleep(0.3)

x=-width/2 + 150

for _ in range(3):

    for _ in range(100):
        turtle.pencolor("Green")
        turtle.penup()
        x+=20
        y=5
        turtle.setpos(x,y-50)
        turtle.pendown()
        turtle.tracer(0)
        Bush(12,120,5.5) 
        turtle.update()
        time.sleep(0.3)
    x=-1100
    y+=16

turtle.mainloop()
</pre>
<br>
<center>

<img 

src="/assets/images/Screenshot5.png">

</center>

