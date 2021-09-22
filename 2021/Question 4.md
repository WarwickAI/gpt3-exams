# Question 4 (7/20)
### 4a
4a You are working for a company developing an employment database application. The database will store information about each employee (such as their name, date of birth, contact information, etc.). Design an abstract Employee class to store the following attributes: forename, surname, age and annual salary?

```Java
public abstract class Employee {
    private String forename;
    private String surname;
    private int age;
    private double annualSalary;
    public Employee(String forename, String surname, int age, double annualSalary) {
        this.forename = forename;
        this.surname = surname;
        this.age = age;
        this.annualSalary = annualSalary;
    }
    public String getForename() {
        return forename;
    }
    public String getSurname() {
        return surname;
    }
    public int getAge() {
        return age;
    }
    public double getAnnualSalary() {
        return annualSalary;
    }
}
```

(3/3)

### 4b
4b Add methods to your Employee class from 4a to modify the attributes and additionally add an abstract method to add overtime to an employee’s monthly wage?

```Java
public abstract class Employee {
    private String forename;
    private String surname;
    private int age;
    private double annualSalary;
    public Employee(String forename, String surname, int age, double annualSalary) {
        this.forename = forename;
        this.surname = surname;
        this.age = age;
        this.annualSalary = annualSalary;
    }
    public String getForename() {
        return forename;
    }
    public String getSurname() {
        return surname;
    }
    public int getAge() {
        return age;
    }
    public double getAnnualSalary() {
        return annualSalary;
    }
    public abstract double calculateMonthlyWage();
}
```

(0/3)

### 4c
4c For an accountant in this company, overtime is equivalent to (1/1200) of their annual salary per hour if they do more than 50 hours of overtime in a month and (1/1800) of their annual salary per hour if they do up to 50 hours in a month. Design a concrete Accountant class that correctly calculates an accountant’s overtime pay when given the amount of overtime hours?

```Java
public class Accountant extends Employee {
    private double overtimeHours;
    public Accountant(String forename, String surname, int age, double annualSalary, double overtimeHours) {
        super(forename, surname, age, annualSalary);
        this.overtimeHours = overtimeHours;
    }
    public double calculateMonthlyWage() {
        double monthlyWage = 0;
        if (overtimeHours > 50) {
            monthlyWage = (annualSalary / 1200) * overtimeHours;
        } else {
            monthlyWage = (annualSalary / 1800) * overtimeHours;
        }
        return monthlyWage;
    }
}
```

(1/4) - wrong method name, overtime not given as parameter, right method though

### 4d
4d A salesperson at this company cannot work more than 25 hours of overtime, and earns it at a rate of (1/2000) of their annual salary per hour. All salespeople also have a target sales number they must meet (which is the same for everyone), and if they do they get a 500 bonus in that month, added to their overtime. Design a concrete Salesperson class that includes this information?

```Java
public class Salesperson extends Employee {
    private double overtimeHours;
    private double targetSales;
    public Salesperson(String forename, String surname, int age, double annualSalary, double overtimeHours, double targetSales) {
        super(forename, surname, age, annualSalary);
        this.overtimeHours = overtimeHours;
        this.targetSales = targetSales;
    }
    public double calculateMonthlyWage() {
        double monthlyWage = 0;
        if (overtimeHours > 25) {
            monthlyWage = annualSalary / 2000 * overtimeHours;
        } else {
            monthlyWage = annualSalary / 1800 * overtimeHours;
        }
        if (monthlyWage >= targetSales) {
            monthlyWage += 500;
        }
        return monthlyWage;
    }
}
```

(1/6) - Weird method name, overtime hours should be given as parameter, didn't understand "cannot work more than 25 hours of overtime", but had some correct code

### 4e
4e The company has a number of offices that require secure access, which requires verifying a PIN code. These offices are only used by the accountants. Furthermore, to access the building at all requires verifying an employee’s ID number. Design two interfaces (SecureAccess and BuildingAccess) which provide this access management. Then, update the class declarations of your Accountant and Salesperson classes to use these interfaces?

```Java
public interface SecureAccess {
    public boolean verifyPin(int pin);
}
public interface BuildingAccess {
    public boolean verifyId(int id);
}
public class Accountant extends Employee implements SecureAccess, BuildingAccess {
    private double overtimeHours;
    private double targetSales;
    public Accountant(String forename, String surname, int age, double annualSalary, double overtimeHours, double targetSales) {
        super(forename, surname, age, annualSalary);
        this.overtimeHours = overtimeHours;
        this.targetSales = targetSales;
    }
    public double calculateMonthlyWage() {
        double monthlyWage = 0;
        if (overtimeHours > 25) {
            monthlyWage = annualSalary / 2000 * overtimeHours;
        } else {
            monthlyWage = annualSalary / 1800 * overtimeHours;
        }
        if (monthlyWage >= targetSales) {
            monthlyWage += 500;
        }
        return monthlyWage;
    }
    public boolean verifyPin(int pin) {
        return true;
    }
    public boolean verifyId(int id) {
        return true;
    }
}
public class Salesperson extends Employee implements SecureAccess, BuildingAccess {
    private double overtimeHours;
    private double targetSales;
    public Salesperson(String forename, String surname, int age, double annualSalary, double overtimeHours, double targetSales) {
        super(forename, surname, age, annualSalary);
        this.overtimeHours = overtimeHours;
        this.targetSales = targetSales;
    }
    public double calculateMonthlyWage() {
        double monthlyWage = 0;
        if (overtimeHours > 25) {
            monthlyWage = annualSalary / 2000 * overtimeHours;
        } else {
            monthlyWage = annualSalary / 1800 * overtimeHours;
        }
        if (monthlyWage >= targetSales) {
            monthlyWage += 500;
        }
        return monthlyWage;
    }
    public boolean verifyPin(int pin) {
        return true;
    }
    public boolean verifyId(int id) {
        return true;
    }
}
```

(2/4) - given pin/id should be checked against actual

### 4f
4f In addition to the Employee abstract class, there is also a Contractor abstract class, which has additional functionality. This company only ever hires programmers as contractors, but they also need to be employees. How can we achieve this in Java?

```
We could achieve this by using the interface Employee in the Contractor class.
```

(0/2)