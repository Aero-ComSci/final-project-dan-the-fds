![Screenshot 2025-05-28 112612](https://github.com/user-attachments/assets/e4fcde1b-5c01-485a-9582-84ace9ebac3d)



**Description**

This program is for an ice cream shop on the beach where people can order off of the menu and choose what they want to order off the menu. This program automates the process of ordering by asking the user what they would like to order, and how much of it they would like to order, and eventually calculating the price of what they are going to order. 

```import random

def merchandise():
    merch_items =["Ice cream shop T shirt", "Ice cream shop hat", "Beach ball", "Ice cream shop sunglasses","Ice cream shop shorts", "Ice cream shop floatie" ]
    mystery_box = random.sample(merch_items, k=3 )
    return mystery_box

mystery = input("Would you like to buy our limited edition mystery box with 3 random merchandise items for 15 dollars").lower()
if mystery == "yes":

    merchandise()
    print(merchandise())
else:
    print("Okay, continue")

while True:

    total = 0.0
    choose_icecream = True
    choose_topping = True
    choose_drink = True
    order = ["", "", "", 0]
    amount=[0,0,0,0]

    icecream_index = 0
    topping_index = 1
    drink_index= 2
    extra_scoop_index = 3

    while True:
        order[icecream_index]= input("What flavor of ice cream would you like? vanilla  $1.00, chocolate  $1.50, strawberry  $1.50").lower()
        if order[icecream_index] in ("vanilla","chocolate","strawberry"):
            break
        else:
            print("Please enter vanilla, chocolate, or strawberry.")

    while True:
        try:    
            amount[icecream_index]=int(input("How many scoops of ice cream would you like?"))
            if order[icecream_index] == "vanilla":
                total += 1.00*amount[0]
            elif order[icecream_index] == "chocolate":
                total += 1.50*amount[0]
            elif order[icecream_index] == "strawberry":
                total += 1.50*amount[0]
            break

        except ValueError:
            print("Please enter quantity")
            amount[icecream_index] = 0

    while True:
        topping = input("Would you like a topping? (yes/no)").lower()
        if topping in ("yes","no"):
            break
        else:
            print("Please enter yes or no.")

    if topping == "yes":
        while True:
            order[topping_index]= input("Choose a topping: sprinkles $0.50, chocolate chips $0.75, caramel $1.00").lower()
            if order[topping_index] in ("sprinkles","chocolate chips","caramel"):
                break
            else:
                print("Please enter sprinkles, chocolate chips, or caramel.")

        while True:
            try:
                amount[topping_index]=int(input("How many toppings would you like?"))
                if order[topping_index] == "sprinkles":
                    total += 0.50 * amount[1]
                elif order[topping_index] == "chocolate chips":
                    total += 0.50 * amount[1]
                elif order[topping_index] == "caramel":
                    total += 0.75 * amount[1]
                break
            except ValueError:
                print("Please enter quantity")
                amount[topping_index] = 0

    while True:
        drink = input("Would you like a drink? (yes/no)").lower()
        if drink in ("yes","no"):
            break
        else:
            print("Please enter yes or no.")

    if drink == "yes":
        while True:
            order[drink_index] = input("What size of drink would you like? small $1.25, medium $2.00, large $2.50").lower()
            if order[drink_index] in ("small","medium","large"):
                break
            else:
                print("Please enter small, medium, or large.")

        while True:
            try:
                amount[drink_index] = int(input("How many drinks would you like?"))
                if order[drink_index] == "small":
                    total += 1.25 * amount[2]
                elif order[drink_index] == "medium":
                    total += 2.00 * amount[2]
                elif order[drink_index] == "large":
                    total += 2.50 * amount[2]
                break
            except ValueError:
                print("Please enter quantity")
                amount[drink_index] = 0

    while True:
        extra_scoop = input("Would you like an extra scoop? It is 50 cents extra (yes/no)").lower()
        if extra_scoop in ("yes","no"):
            break
        else:
            print("Please enter yes or no.")

    if extra_scoop == "yes":
        while True:
            try:
                order[extra_scoop_index] = int(input("How many extra scoops would you like?"))
                total += 0.50 *order[3]
                amount[extra_scoop_index] = order[extra_scoop_index]
                break
            except ValueError:
                print("Please enter quantity")

    if mystery== "yes":
        total += 15.00



    print(order)
    print(amount)
    print("Total cost: $", total)

    while True:
        confirm = input("Is this your order? (yes/no)").lower()
        if confirm in ("yes","no"):
            break    
        else:  
            print("Please enter yes or no.")
    
    if confirm == "yes":
        print(order)
        print(amount)
        print("total: $", total)
        break
    elif confirm == "no":
        print("Your order is restarting.")```

