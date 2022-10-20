# file-handling-user-data
# file handling of multiple user data in required manner

def user(j):
    while j > 0:
        print("Enter Details of Employee[{}]".format(j))
        f = open("user.txt", "a")
        f.write("Details of Employee:{}".format(j))
        f.write("\nName: ")
        f.write(input("Enter Employee Name: "))
        f.writelines("\nId: ")
        f.write(input("Enter Employee Id: "))
        f.writelines("\nPhone No: ")
        f.write(input("Enter Employee Phone No: "))
        f.writelines("\nAddress: ")
        f.write(input("Enter Employee Address: "))
        f.writelines("\n\n")
        print("Data Updated Successfully !!!")

        f.close()

        while j != 0:
            ip = ""
            while ip != "YES" or ip != "NO":
                print("Do you want to Add more Employees Data?")
                break
            ip = input("Enter 'YES' or 'NO': ")
            if ip == "YES":
                j += 1
                user(j)
            elif ip == "NO":
                print("Do you want to DELETE all Information")
                z = input("Enter 'YES' or 'NO' : ")
                if z == "YES":
                    f = open("user.txt", "w")
                    print("All Data Deleted.")
                    break
                if z == "NO":
                    print("Thank you for Visiting!!!")
                break
        break


user(1)

