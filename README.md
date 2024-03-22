
QUESTION ONE ANSWER

echo "enter employees name"
read name
echo "enter hours worked"
read hours
echo "enter rate per work"
read rate
basic_pay=$(($hours * $rate)) 
clear
echo -e "\033[1;4mHere is the employee $name's Working record\033[0m"
echo ""
echo "Employee's name is $name"
echo "Employee's worked hours is $hours hours"
echo "Employee's work rate is Ksh $rate"
echo "Employee's basic pay is :Ksh $basic_pay"
if [ $basic_pay -gt 70000 ];then tax_rate=25;elif [ $basic_pay -gt 15000 ]&&[ $basic_pay -le 70000 ];then tax_rate=15; else tax_rate=0
fi
tax=$(($tax_rate * $basic_pay/100 ));
echo "The employee is taxed :Ksh $tax"
echo "The tax rate used for taxing the employee is :$tax_rate %"
salary=$(($basic_pay - $tax));
echo "Employee's Salary after being taxed is:Ksh $salary"


                QUESTION TWO ANSWER
                                                 
#!/bin/bash
# Prompt the user to enter CustomerID, CustomerName, and UnitConsumed
read -p "Enter CustomerID: " customer_id
read -p "Enter CustomerName: " customer_name
read -p "Enter UnitConsumed: " units_consumed

# Define charging rates
charge_1=120
charge_2=150
charge_3=180
charge_4=200

# Calculate charges based on the given conditions
if [ "$units_consumed" -lt 200 ]; then
    total_charge=$((units_consumed * charge_1))
elif [ "$units_consumed" -ge 200 ] && [ "$units_consumed" -lt 400 ]; then
    total_charge=$((units_consumed * charge_2))
elif [ "$units_consumed" -ge 400 ] && [ "$units_consumed" -lt 600 ]; then
    total_charge=$((units_consumed * charge_3))
else
    total_charge=$((units_consumed * charge_4))
fi
clear
charges=$(( total_charge/units_consumed))
# Display the total bill
echo -e "\033[1;4mHere is the customer $customer_name's electricity charges and consumption record\033[0m"
echo ""
echo "CustomerID: $customer_id"
echo "CustomerName: $customer_name"
echo "Units Consumed: $units_consumed units"
echo "charges per unit:$charges"
echo "Total Bill: $total_charge Ksh"


                            QUESTION THREE ANSWER

#include <stdio.h>
int main() {
    // File pointer to represent the file
    FILE *file;

    // Open a file in write mode ("w")
    file = fopen("question2.txt", "w");

    // Check if the file was opened successfully
    if (file == NULL) {
        perror("Error opening the file");
        return 1; // Exit the program with an error code
    }

    // Write content to the file
    fprintf(file, "This is Prof Wawire Ngao Kevin's work. Any modification or alteration by anybody will face impersonation charges in the rule of law.");

    // Close the file after writing
    fclose(file);

    // Open the file in read mode ("r")
    file = fopen("question2.txt", "r");

    // Check if the file was opened successfully
    if (file == NULL) {
        perror("Error opening the file");
        return 1; // Exit the program with an error code
    }

    // Read content from the file
    char content[120]; // Assuming the content size is not more than 120 characters
    if (fgets(content, sizeof(content), file) == NULL) {
        perror("Error reading from the file");
        fclose(file); // Don't forget the semicolon here
        return 1;
    }

    // Print the read content
    printf("Content read from the file: %s\n", content);

    // Close the file after reading
    fclose(file); 
    return 0; // Exit the program successfully
}
