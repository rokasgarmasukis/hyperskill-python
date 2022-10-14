msg_0 = "Enter an equation"
msg_1 = "Do you even know what numbers are? Stay focused!"
msg_2 = "Yes ... an interesting math operation. You've slept through all classes, haven't you?"
msg_3 = "Yeah... division by zero. Smart move..."
msg_4 = "Do you want to store the result? (y / n):"
msg_5 = "Do you want to continue calculations? (y / n):"
msg_6 = " ... lazy"
msg_7 = " ... very lazy"
msg_8 = " ... very, very lazy"
msg_9 = "You are"
msg_10 = "Are you sure? It is only one digit! (y / n)"
msg_11 = "Don't be silly! It's just one number! Add to the memory? (y / n)"
msg_12 = "Last chance! Do you really want to embarrass yourself? (y / n)"

result = 0
memory = 0.0
calculation = True


def check(v1, v2, v3):
    msg = ""
    if is_one_digit(v1) and is_one_digit(v2):
        msg = msg + msg_6
    if (v1 == 1 or v2 == 1) and v3 == "*":
        msg = msg + msg_7
    if (v1 == 0 or v2 == 0) and (v3 == "*" or v3 == "+" or v3 == "-"):
        msg = msg + msg_8
    if msg != "":
        msg = msg_9 + msg
    print(msg)


def is_one_digit(v):
    if v.is_integer() and -10 < v < 10:
        return True
    return False


while calculation:
    print(msg_0)
    calc = input().split(" ")

    x = calc[0]
    y = calc[2]

    if x == "M":
        x = memory

    if y == "M":
        y = memory

    try:
        x = float(x)
    except (TypeError, ValueError):
        print(msg_1)
        continue

    try:
        y = float(y)
    except (TypeError, ValueError):
        print(msg_1)
        continue

    operator = calc[1]

    if operator != "+" and operator != "-" and operator != "*" and operator != "/":
        print(msg_2)
        continue

    check(x, y, operator)

    if operator == "+":
        result = x + y
    if operator == "-":
        result = x - y
    if operator == "*":
        result = x * y
    if operator == "/":
        if y == 0:
            print(msg_3)
            continue
        result = x / y

    print(result)

    memory_loop = False

    while True:
        print(msg_4)
        answer = input()

        if answer == "y":
            if not is_one_digit(result):
                memory = result
                break
            memory_loop = True

            break
        elif answer == "n":
            break

    message_index = 10;

    while memory_loop:
        if message_index == 10:
            print(msg_10)
        if message_index == 11:
            print(msg_11)
        if message_index == 12:
            print(msg_12)

        answer = input()

        if answer == "y":
            if message_index < 12:
                message_index = message_index + 1
                continue
            else:
                memory = result
                break

        if answer == "n":
            break

    while True:
        print(msg_5)
        answer = input()

        if answer == "y":
            break
        elif answer == "n":
            calculation = False
            break
