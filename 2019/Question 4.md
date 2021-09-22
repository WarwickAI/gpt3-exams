# Question 4 (8/20) or (11/20)
### 4a
Explain the need for constructors in a class definition. When do we not need constructors?

```
Constructors are used to initialize the instance variables of a class. Constructors are called when an object of a class is created.
If a class does not contain a constructor, then the compiler will generate a default constructor.
```

(1/4) - Partially explained need for constructors. Explained what happens when constructors aren't defined, but didn't explain why you might not need to define one.

With $T=0.4$ and $n=2$, we get:

```
Constructors are called when an object is created. It is used to initialize the instance variables of the class. We do not need constructors when we do not need to initialize the instance variables of the class.
```

(3/4)

### 4b
Explain inheritance of constructs from parent class to child class. What is the reason we use super in Java?

```
Inheritance is a feature of object-oriented programming in which a class inherits the members of another class. The members of the parent class are inherited by the child class. The child class can access all the members of the parent class.
The super keyword is used to call the constructor of the parent class.
```

(1/4) - Didn't explain inheritance of constructs

### 4c
You are asked to design an application where users can create new money pots and add money into any pot, but only users who enter a passcode generated when a pot is created can view and reduce the balance stored in any particular pot. (Assume very simple security: the passcode is a short integer and a simple check suffices.) Write down the classes, methods and data fields needed, to ensure security. You do not need to code the methods in detail?

```Java
class MoneyPot {
    private int balance;
    private int passcode;
    private String owner;
    public MoneyPot(int passcode, String owner) {
        this.balance = 0;
        this.passcode = passcode;
        this.owner = owner;
    }
    public int getBalance() {
        return balance;
    }
    public void addMoney(int amount) {
        if(passcode == passcode) {
            balance += amount;
        }
    }
    public void removeMoney(int amount) {
        if(passcode == passcode) {
            balance -= amount;
        }
    }
}

class User {
    private String name;
    private int passcode;
    public User(String name, int passcode) {
        this.name = name;
        this.passcode = passcode;
    }
    public void addMoney(MoneyPot moneyPot, int amount) {
        if(passcode == moneyPot.getPasscode()) {
            moneyPot.addMoney(amount);
        }
    }
    public void removeMoney(MoneyPot moneyPot, int amount) {
        if(passcode == moneyPot.getPasscode()) {
            moneyPot.removeMoney(amount);
        }
    }
}
```

(6/12) - Codex does not like to give short answers. Missing method on User to create MoneyPot object. MoneyPot has no getPasscode() method. Passcode should be generated rather than given. MoneyPot object checks for passcode too much.

With $T=0.4$ and $n=4$:

```Java
class User {
    private int id;
    private String name;
    private String passcode;
    private MoneyPot[] pots;
    public User(int id, String name, String passcode) {
        this.id = id;
        this.name = name;
        this.passcode = passcode;
        this.pots = new MoneyPot[0];
    }
    public int getId() {
        return id;
    }
    public String getName() {
        return name;
    }
    public String getPasscode() {
        return passcode;
    }
    public MoneyPot[] getPots() {
        return pots;
    }
    public void addPot(MoneyPot pot) {
        MoneyPot[] newPots = new MoneyPot[pots.length + 1];
        for (int i = 0; i < pots.length; i++) {
            newPots[i] = pots[i];
        }
        newPots[pots.length] = pot;
        pots = newPots;
    }
}
class MoneyPot {
    private int id;
    private int balance;
    private String passcode;
    private String owner;
    public MoneyPot(int id, int balance, String passcode, String owner) {
        this.id = id;
        this.balance = balance;
        this.passcode = passcode;
        this.owner = owner;
    }
    public int getId() {
        return id;
    }
    public int getBalance() {
        return balance;
    }
    public String getPasscode() {
        return passcode;
    }
    public String getOwner() {
        return owner;
    }
    public void addMoney(int amount) {
        balance += amount;
    }
    public void removeMoney(int amount) {
        balance -= amount;
    }
}
```

(7/12) - Still missing password generation, and has added passcode to User object.