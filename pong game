import turtle

wn = turtle.Screen()
wn.title("Ranajit's Pong game")
wn.bgcolor("black")
wn.setup(width = 800,height=600)
wn.tracer(0)
#score
score_a = 0
score_b= 0
# Paddle A
paddle_a = turtle.Turtle()
paddle_a.speed(0)
paddle_a.shape("square")
paddle_a.color("white")
paddle_a.shapesize(stretch_wid=5,stretch_len=1)
paddle_a.penup() #avoid's the follow line of the tirtle
paddle_a.goto(-350,0)


# Paddle B
paddle_b = turtle.Turtle()
paddle_b.speed(0)
paddle_b.shape("square")
paddle_b.color("white")
paddle_b.shapesize(stretch_wid=5,stretch_len=1)
paddle_b.penup() #avoid's the follow line of the tirtle
paddle_b.goto(350,0)

#ball
ball = turtle.Turtle()
ball.speed(0)
ball.shape("circle")
ball.color("white")
ball.penup() #avoid's the follow line of the tirtle
ball.goto(0,0)
ball.dx = 0.1 #change in x position of the ball
ball.dy = 0.1 #change in y positipon of the ball

#pen
pen = turtle.Turtle()
pen.color("white")
pen.penup()
pen.speed(0)
pen.hideturtle()
pen.goto(0,260)
pen.write("Player A: 0   Player B: 0" ,align="center", font=("Arial", 16, "normal"))

def paddle_a_up():
    y = paddle_a.ycor()
    y=y+20
    paddle_a.sety(y)

def paddle_a_down():
    y = paddle_a.ycor()
    y=y-20
    paddle_a.sety(y)

def paddle_b_up():
    y = paddle_b.ycor()
    y=y+20
    paddle_b.sety(y)

def paddle_b_down():
    y = paddle_b.ycor()
    y=y-20
    paddle_b.sety(y)

#keyboard bindings
wn.listen()
wn.onkeypress(paddle_a_up, "w")
wn.onkeypress(paddle_a_down, "s")
wn.onkeypress(paddle_b_up, "Up")
wn.onkeypress(paddle_b_down, "Down")



while True:
    wn.update()

    #Move the ball
    ball.setx(ball.xcor() + ball.dx)
    ball.sety(ball.ycor() + ball.dy)
    #border checking_upper_border
    if ball.ycor() > 290:
        ball.sety(290)
        ball.dy *= -1

    #border_cheaking_lower_border
    if ball.ycor() < -290:
        ball.sety(-290)
        ball.dy*=-1
    #bounching of the right and left border
    if ball.xcor() > 390:
        ball.goto(0,0)
        ball.dx*=-1
        score_a += 1
        pen.clear()
        pen.write("Player A: {}   Player B: {}".format(score_a,score_b), align="center", font=("Arial", 16, "normal"))

    if ball.xcor() < -390:
        ball.goto(0,0)
        ball.dx*=-1
        score_b += 1
        pen.clear()
        pen.write("Player A: {}   Player B: {}".format(score_a, score_b), align="center", font=("Arial", 16, "normal"))

    #ball bounce of paddle
    if(ball.xcor() > 340 and ball.xcor() < 350) and (ball.ycor() < paddle_b.ycor() + 40 and ball.ycor() > paddle_b.ycor() - 40 ):
        ball.setx(340)
        ball.dx*=-1

    if(ball.xcor() < -340 and ball.xcor() > -350) and (ball.ycor() < paddle_a.ycor() + 40 and ball.ycor() > paddle_a.ycor() - 40):
        ball.setx(-340)
        ball.dx*= -1

