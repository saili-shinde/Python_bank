# Python_bank
basic bank operation project using basic python 
## Code
`class python_bank:`
    `def __init__(self,bank_accounts,acc_no):`
        `self.bank_accounts=bank_accounts`
        `self.acc_no=acc_no;`
        `self.name=self.bank_accounts[self.acc_no][0]`
        `self.pin=self.bank_accounts[self.acc_no][1]`
        `self.balance=self.bank_accounts[self.acc_no][2]`

    `def change(self):`
        `self.bank_accounts.update({self.acc_no:[self.name,self.pin,self.balance]})`
    
    `def change_pass(self):`
        `check_id=int(input('enter your account number'))`
        `check_name=input('enter your account name')`
        `if check_id==self.acc_no and check_name==self.name:`
            `self.pin=input('enter your new pin')`
            `user.change()`
        
    `def check_pin(self):`
        `check_pin=input('enter your pin \n')`
        `if check_pin==self.pin:`
            `print('welcome to python bank!! \n')`
            `while True:`
                `print('please enter your choice \n')`
                `choice=int(input("1.deposite \n 2.withdraw \n 3.change pin \n 4.exit \n"))`
                `if choice==1:`
                    `print(user.deposite())`
                `elif choice==2:`
                    `print(user.withdraw())`
                `elif choice==3:`
                    `user.change_pin()`
                `elif choice==4:`
                    `break;`
                `else:`
                    `print('wrong choice!!!')`
        `else:`
            `print('wrong pass!! \n')`
            `print('forgot pass?? \n ')`
            `change_pass=int(input('1.yess \n 2.no \n'))`
            `if change_pass==1:`
                `user.change_pass()`
            `elif change_pass==2:`
                `print('please try signing in again..thankyou \n')`
            `else:`
                `print('please select from given list of choice \n')`
                
    
    `def check_balance(self):`
            `return self.balance`

    `def deposite(self):`
            `deposite=int(input('enter your amout to be deposited \n'))`
            `self.balance+=deposite`
            `if self.balance >200:`
                `user.change()`
                `user.check_balance()`
            `else:`
                `new.change()`
                `new.check_balance()`

    `def withdraw(self):`
            `withdraw=int(input('enter your amount to withdaw \n'))`
            `check_bal=self.balance-withdraw`
            `if check_bal>200:`
                `self.balance=check_bal`
                `user.change()`
                `user.check_balance()`
        

`if __name__=="__main__":`
    `bank_accounts={1:['akash','aka123',200000],2:['saili','sill34',30000]}`
    `acc_no=int(input("enter your account number : \n"))`
    `if acc_no in bank_accounts:`
        `user = python_bank(bank_accounts,acc_no)`
        `user.check_pin()`
    `else:`
        `print('please your check your account number again \n')`
        `print('are you new user? \n')`
        `print('do you want to create new id? \n')`
        `new_user=int(input('1.yess \n 2.noo \n'))`
        `if new_user==1:`
            `acc_no=len(bank_accounts)+1`
            `name=input('enter your name \n ')`
            `pin=input('enter pin \n ')`
            `balance=0`
            `bank_accounts.update({acc_no:[name,pin,balance]})`
            `new = python_bank(bank_accounts,acc_no)`
            `balance=new.deposite()`
            `if int(balance)>200:`
                `bank_accounts.update({acc_no:[name,pin,balance]})`
                `print('account created suscessfully')`
            `else:`
                `bank_accounts.popitem()`
                `print('not enogh balance, process failed..thankyou ')`
            
        `elif new_user==2:`
            `print('please try signing in again..thankyou \n')`
        `else:`
            `print('please select from given choices')`
    
