# ATM_Simulator

# atm_simulator.py

class ATM:
    def __init__(self, initial_balance=0):
         self.balance = initial_balance

    def check_balance(self):
        return self.balance

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            return f"Deposited {amount}. New balance is {self.balance}."
        else:
            return "Deposit amount must be positive."

    def withdraw(self, amount):
        if 0 < amount <= self.balance:
            self.balance -= amount
            return f"Withdrew {amount}. New balance is {self.balance}."
        elif amount > self.balance:
            return "Insufficient funds."
        else:
            return "Withdrawal amount must be positive."

        
        from atm_simulator import ATM

if __name__ == "__main__":
    my_atm = ATM(100)
    
    # Initial balance is 100
    print(my_atm.check_balance())  # Should print 100
    
    print(my_atm.deposit(50))  # Should print "Deposited 50. New balance is 150."
    
    print(my_atm.withdraw(30))  # Should print "Withdrew 30. New balance is 120."
    
    print(my_atm.withdraw(200))  # Should print "Insufficient funds."
    
    print(my_atm.check_balance())  # Should print 120
