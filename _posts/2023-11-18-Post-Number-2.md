---
layout: posts
title: "Turtle فرکتال درخت در کتابخانه"
---

<!-- </fontcolor> -->
<!-- </font> -->
<!-- </center> -->
<hr>
لاکپشت همون فلش ماست که در حال حرکت و رسم هست
.
از اونجایی که داریم از کتابخانه 
Turtle
از پایتون استفاده میکنیم پس اول از همه داریم
:
<pre dir="ltr">
import turtle
</pre>
یه نکته مهم اینه که لاکپشت ما به طور خودکار به سمت راست هست پس 90 درجه به چپ میپرخونیمش تا درخت رو عمودی بکشه نه افقی 
،
همچنین بهتره لاکپشتمون یکم از عقب شروع کنه به رسم تا کامل درختمون در صفحه نمایش باشه وگرنه میزنه بیرون پس یک دستور عقب گرد هم میدیم
:
<pre dir="ltr">
turtle.left(90)
turtle.backward(100)
</pre>
عمل اصلی ای که باید انجام بدیم تعریف یک تابع برای رسم درخت هست.سخت ترین بخش اینه که باید از تابع در تابع استفاده کنیم.حالا قدم به قدم بریم جلو
:
<br>
<pre dir="ltr">
def Tree(d,a,s):
</pre>
<br>
برای تابع سه متغیر در نظر گرفتیم
،
d 
یعنی طول شاخه ها
،
a
یعنی زاویه بین دو شاخه
و
s
یعنی قطر درخت ها
.
<br>
در قدم بعدی باید یک حدی تعریف کنیم که اگر اندازه شاخه ها از آن حد کوچکتر شد تابع از رسم دست بکشه
.
پس داریم
:
<br>
<pre dir="ltr">
if d<25:
    return
</pre>

عدد 25 معقول به نظر میرسید اما میشه مقدارش رو کمتر یا بیشتر هم کرد
.
<br>
در ادامه باید رسم تنه رو
(که بعدا میشه همون شاخه ی ما)
انجام بدیم
.
سایز قلممون رو هم با کد پن سایز تعیین میکنیم
،
رنگ قلممون هم باید قهوای 
("Brown")
باشه که با پن کالر این کار رو انجام میدیم
.
باید به لاکپشتمون بگیم بره جلو بعد با یک زاویه ای بچرخه و بعد صبر کنه تا ما بهش ادامه دستور رو بدیم 
:)
<pre dir="ltr"> 
turtle.pencolor("Brown")
turtle.pensize(s)    
turtle.forward(d)
turtle.left(a)

</pre>
خب حالا میخوایمم شاخه رو رسم کنه پس تابع رو داخل خودش صدا میزنیم اما طبیعتا میخوایم که اندازه شاخه ها از تنه کوچکتر باشه پس اندازه 
d 
رو متفاوت میزنیم،زاویه هم همینطور که درختمون رفته رفته باز تر بشه پس ضربدر یک عدد بین صفر و یک میکنیم زاویه رو،بدین صورت که
:
<pre dir="ltr">
Tree(d*0.7,a,s*0.7)
</pre>
باز هم میشه گفت که 0.7 عددی معقول است اما میشه عدد های دیگه مثل 0.4 هم داد ولی شکل درخت زیاد خوب در نمی آید
.
نکته سوال این جاست که لاکپشت ما بعد از رسم شاخه باید دو برابر زاویه بچرخه وگرنه شاخه ها متقارن نمیشوند
همچنین برای تنظیم سایز شاخه دوباره باید کد سایز رو بزنیم
:
<pre dir="ltr">
turtle.right(2*a)
turtle.pensize(s)
</pre>
حالا دوباره تابع رو صدا میکنیم در خودش که طرف دیگه شاخه رو رسم کنه و چون باید متقارن با شاخه قبلی باشه پس دوباره ضربدر 0.7 میکنیم و بعد میخوایم لاکپشت به زاویه اش رو درست کنه و بعد به عقب برگرده و اونقدر این کار رو ادامه بده که به حدی که ما گذاشتیم برسه
.
<pre dir="ltr">
Tree(d*0.7,a,s*0.7)
turtle.left(a)
turtle.backward(d)
</pre>
تمام
!!!!!
الان کافیه که تابع رو بیرون از تابع درخت صدا بزنیم مثلا
:
<pre dir="ltr">
Tree(150,30,9)
</pre>
در آخر برای اینکه صفحه امون بسته نشه میزنیم
:
<pre dir="ltr">
turtle.mainloop()
</pre>
پس کد ما به صورت یکجا میشه
(بهتره سعی کنیم کدی که مینویسیم خوش خوان باشه و تو هم نباشه)
:
<pre dir="ltr">
import turtle
turtle.left(90)
turtle.backward(100)

def Tree(d,a,s):
    if d<25:
        return

    turtle.pencolor("Brown")
    turtle.pensize(s)    
    turtle.forward(d)
    turtle.left(a)

    Tree(d*0.7,a,s*0.7)

    turtle.right(2*a)
    turtle.pensize(s)

    Tree(d*0.7,a,s*0.7)

    turtle.left(a)
    turtle.backward(d)

Tree(150,30,9)

turtle.mainloop()
</pre>
خروجی ما به شکل زیر میشه
:
<br>
<center>
<img src="/assets/images/Screenshot.png">
</center>
 در آخر اگه بخوایم خلاقیت نشون بدیم میتونیم مثلا برگ تعریف کنیم و به درخت اضافه کنیم که بسا درختمون زیبا تر هم میشه
اما باید یک سری تغییرات کوچیک هم انجام داد مثلا بعد رسم برگ ها باید از پن آپ و بعد از پن داون استفاده کرد
.
برای یک نمونه میتوان کد زیر را در نظر گرفت
:
<pre dir="ltr">
import turtle
turtle.speed(0)

turtle.penup()
turtle.left(90)
turtle.backward(150)
turtle.pendown()

def Leaves1(d):
    turtle.forward((2*(3**0.5))*d)
    turtle.right(150)
    turtle.forward(2*d)
    turtle.right(60)
    turtle.forward(2*d)

def Leaves2(d):
    turtle.left(60)
    turtle.backward(2*d)
    turtle.left(120)
    turtle.forward(2*d)

def Tree(d,a,s):
    turtle.pencolor("Brown")

    if d<25:
        Leaves1(d//3)
        Leaves2(d//3)
        turtle.left(390)
        turtle.backward(d)
        turtle.penup()
        return

    turtle.pensize(s)  
    turtle.forward(d)
    turtle.left(a)
      
    Tree(d*0.7,a,s*0.7)
    
    turtle.pendown()
    turtle.right(2*a)
    turtle.pensize(s)

    Tree(d*0.7,a,s*0.7)

    turtle.left(a)
    turtle.backward(d)
    

Tree(150,30,9)

turtle.mainloop()
</pre>
خروجی
:
<br>
<center>
<img src="/assets//images/Screenshot2.png">
</center>
برای دیدن فرکتال مثلث روی گزینه زیر کلیک کنید
!
<center>
    <br>
    <a href="/Post-Number-3">
        <button>فرکتال مثلث</button>
      </a>
    </center>
