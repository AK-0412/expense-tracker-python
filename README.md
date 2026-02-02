#Expense tracker

expensesList = []
print("WELCOME TO EXPENSE TRACKER")

while True:
    print("====Menu====")
    print("1. Add Expense")
    print("2. View All Expenses")
    print("3. View Total Expense")
    print("4. Exit")

    choice= int(input("Please Enter Your Choice : "))

#Add expense
    if(choice ==1) :
        date= input("Enter your date?: ")
        category= input("On what you have spent your money?: ")
        description= input("Give a short note on what you have spent yoour money: ")
        amount= float(input("Enter the amount: "))

        expense= {
            "date": date,
            "category": category,
            "description": description,
            "amount": amount,
        }

        expensesList.append(expense)
        print("\n Done. Expense is added succesfully")

#2. VIEW ALL EXPENSES
    elif(choice == 2):
        if(len(expensesList)==0):
            print("No Expenses Added.")
        else:
            print("====Your expenses====")
            count= 1
            for eachexpense in expensesList:
               print(f"Expense Number {count} -> {eachexpense["date"]}, {eachexpense["category"]}, {eachexpense["description"]}, {eachexpense["amount"]} ")
               count= count+1


#3. View Total spending
    elif(choice == 3):
        total= 0
        for eachexpense in expensesList:
            total = total + eachexpense["amount"]

        print("\n TOTAL EXPENSES = ",total)

#4. EXIT
    elif (choice == 4 ):
       print("ThanYOU ")
       break

    else:
       print("INVALID CHOICE. TRY AGAIN")
