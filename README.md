# Function-5
def calculate_tuition_owed(credit_hours, district_code):
    in_district_rate = 250.00
    out_of_district_rate = 550.00

    if district_code == 'I':
        return credit_hours * in_district_rate
    elif district_code == 'O':
        return credit_hours * out_of_district_rate
    else:
        return 0.0

def main():
    total_tuition_owed = 0.0

    try:
        while True:
            # User input for student information
            last_name = input("Enter student's last name (Ctrl+Z to stop): ")
            credit_hours = int(input("Enter credit hours: "))
            district_code = input("Enter district code (I or O): ")

            # Calculate tuition owed
            tuition_owed = calculate_tuition_owed(credit_hours, district_code)

            # Display student name and tuition owed
            print(f"{last_name}'s Tuition Owed: ${tuition_owed:.2f}")

            # Update total tuition owed
            total_tuition_owed += tuition_owed

    except EOFError:
        # Display the total of all tuition owed
        print(f"\nTotal Tuition Owed: ${total_tuition_owed:.2f}")

if __name__ == "__main__":
    main()
