from IPython.core.display import clear_output

userList = []

while True: #This loop will run the main menu
  print("\nWelcome to your list!\n")
  print(" ")
  print("Your list: ",userList)
  print(" ")
  print("\nAdd items"," ","Remove items", " ","Replace items"," ","View sorted list\n")
  print(" ")
  print("Exit Program\n")
  userInput = input()

  if userInput == "Exit" or userInput == "Exit Program":
    clear_output()
    print("Closing program...")
    break

  if userInput == "View":
    clear_output()
    print("Alphabetically sorted list: \n")
    userList.sort()

    for i, item in enumerate(userList):
      print(i,":",item)
      print(" ")

    print("Exit\n")
    userInput = input()
    clear_output()

  #This provides a different menu for when the user wants to add an item
  if userInput == "Add Items" or userInput == "Add":
    clear_output()
    print("What would you like to add?\n")
    print("Exit\n")

    while True:
      userInput = input()

      if userInput == "Exit":
        clear_output()
        break
      else:

        # This checks to see if the user inputted a number, and if so, it will
        # run the print statement untill the user inputs a string
        while userInput.isdigit():
          clear_output()
          print("\nType an item, not integer\n")
          userInput = input()

        userList.append(userInput)
        clear_output()
        print(" ")                      #Untill the user inputs a number or wants to exit,
        print("Your list: ",userList)   #these functions will add the inputted string into the list.
        print(" \n")
        print("What else would you like to add?\n")
        print("Exit\n")

  #This provides a different menu for when the user wants to remove an item
  if userInput == "Remove items" or userInput == "Remove":

    if len(userList) == 0:    #If the user has nothing in their list and
      clear_output()          #wants to remove an item, the program will not let them.
      print("You have nothing, so you can't remove anything!\n")
      print("Exit\n")
      userInput = input()

      if userInput == "Exit":
        clear_output()

    while len(userList) > 0:
      clear_output()
      print("Your list: ")

      for i, item in enumerate(userList):
        print(" ")
        print(i,":",item)

      print("\nWhat would you like to remove? Type the assigned number value\n")
      print("Exit\n")

      while True:
        userInput = input()

        if userInput == "Exit":
          clear_output()
          break
        else:

          while not userInput.isdigit: #Checks to see if the user inputted a string instead of a number
            clear_output()
            print(" ")
            print("Type a place value, not letter")
            print(" ")
            userInput = input()

          if len(userList) > 0:
            index = int(userInput)
            userList.pop(index)
            clear_output()                  #Untill the user has nothing in their list,
            print("Your list: \n")          #this function will keep removing items

            for j, item in enumerate(userList):
              print(j,":",item)
              print(" ")

            print("What else would you like to remove?\n")
            print("Exit\n")

          if userInput == "Exit":
            clear_output()
            break

          if len(userList) == 0:
            clear_output()
            print("You have nothing to remove!\n")
            print("Your list: ",userList)             #If the user is done removing and has nothing left,
            print(" ")                                #this function will tell them to go back to the main menu
            print("Exit to main menu\n")
            userInput = input()

            if userInput == "Exit":
              clear_output()
              break

  #This provides a different menu for when the user wants to replace an item
  if userInput == "Replace items" or userInput == "Replace":
    clear_output()
    print("Your list: ",userList)
    print(" ")
    print("What would you like to replace?\n")
    print("Exit\n")

    while True:
      userInput = input()

      if userInput == "Exit":
        clear_output()
        break
      else:

        while userInput.isdigit():
          print(" ")
          print("Type an item, not integer")
          print(" ")
          userInput = input()

        for i, item in enumerate(userList):
          if userInput == userList[i]:          #If the user inputs an item that is in the list,
            clear_output()                      #it will replace it with another string that the user inputs
            print("Replacing:", userList[i])
            print("\nWhat would you like to replace it with?\n")
            userInput = input()
            userList[i] = userInput
            break

        else:
          clear_output()
          print("You can only replace something that is inside of your list\n")
          print(userList)
          print(" ")                                  #If the user doesn't input something that is in the list,
          print("What would you like to replace?")    #then this warning will print out
          userList[i] = input()
          clear_output()
          print("Replacing:", userList[i])
          print("\nWhat would you like to replace it with?\n")
          userInput = input()

          userList[i] = userInput
        while userInput.isdigit():
          print(" ")
          print("Type an item, not integer")
          print(" ")
          userInput = input()

        clear_output()
        print("Your new list: ",userList)
        print(" ")                          #Prints the user a fresh list and loops
        print("Replace another item\n")     #the replacement functions untill the user exits
        print("Exit")

        if userInput == "Exit":
          clear_output()

        if userInput == "Replace":
          clear_output()
          print("Your list: ",userList)
          print(" ")
          print("What would you like to replace?\n")
          print("Exit\n")
