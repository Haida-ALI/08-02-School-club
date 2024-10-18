# School club program

# -------------------------
# Subprograms
# -------------------------
def add_student():
    club = input('Clubs available: programming, football or drama\nEnter the name of the club: ')
    while club not in ['programming','football','drama']:
      club = input('enter the name of the club: ')
    student = input("Enter your name to sign up for the club: ")
    student = student + "\n"
    file = open(club+'.txt','a')
    file.write (student)
    file.close()
    print("You have been signed up", student)


def show_students():
    club = input('Clubs available: programming, football or drama\nEnter the name of the club: ')
    while club not in ['programming','football','drama']:
      club = input('enter the name of the club: ')
    print("Students that signed up for the programming club:")
    file = open(club+'.txt')
    for student in file:
        student = student.strip()
        print(student)
    file.close()
    
    
def menu():
    print("1. Sign up")
    print("2. Show students")
    choice = ""
    while choice not in ["1", "2"]:
        choice = input("Enter choice: ")
    match choice:
        case "1":
            add_student()
        case "2":
            show_students()
            
            
# -------------------------
# Main program
# -------------------------
menu()
