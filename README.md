# OOPs

class Employee:
    
    increment = 1.5
    no_of_emp = 0
    
    # Construction 
    def __init__(self, fname, lname, salary):
        self.fname = fname
        self.lname = lname
        self.salary = salary
        Employee.no_of_emp += 1
    
    # increse salary
    def increse(self):
        self.salary  *= self.increment
    
    # increse salary by self
    @classmethod
    def change_increse(cls, amount):
        cls.increment = amount
    
    # only one line, using split function
    @classmethod
    def frm_str(cls, emp_str):
        fname, lname, salary = emp_str.split("-")
        return cls(fname, lname, salary)
    
    # staticmethod is depend on own function
    @staticmethod
    def real_life(deserve):
        if deserve=="salman":
            return "Businesman"
        else :
            return "Job Person"
    
    # Email function (attribute)
    @property
    def email(self):
        return self.fname + self.lname + "@gmail.com"
        
    # add direct another variable    
    def __add__(self, other):
        self.salary = self.salary + other.salary
        return self.salary
    
    # Spescial Dunder method
    def __repr__(self):
        return f"Employee in repr {self.fname}, {self.lname}, {self.salary}"
    
    # Spescial Dunder method
    def __str__(self):
        return f"Employee in str {self.fname}"
    
    
if __name__ == "__main__":
        
    salman = Employee("Salman","Shaikh", 12000)
    azaz = Employee("Azaz", "Ansari", 44000)
    afjal = Employee.frm_str("Afjal-Ansari-20000")
    
    
    print(salman.salary)      # simple salary print
    Employee.change_increse(2)  # salary increse by self
    salman.increse()           # start increasing
    print(salman.salary)       # salary increased
    
    print(Employee.real_life("salman"))    # staticmethod method is depend on own function
    
    print(afjal.salary)        # using split("-") function
    
    print(salman + azaz)       # add direct another variable 
    
    print(repr(salman))        # Spescial Dunder method
    print(str(salman))         # Spescial Dunder method
    print(salman)              # by itself using str
    
    print(salman.email)        # (Property) Email function (attribute)
