# Mutual-Fund-Analysis-portfolio-Dasboard

A mutual funds analysis portfolio dashboard offers a comprehensive overview, including fund performance against benchmarks, asset and sector allocation breakdowns, risk metrics like volatility, and details on fund holdings and characteristics such as expense ratio and manager tenure. Additionally, it tracks fund flows and provides ratings from agencies to aid investors in assessing performance, risk, and alignment with their investment objectives.

def mfn(x,y):
    e1=x[x.Category==y]
    a=[]
    for f in e1.index:
        a.append(f)
    
    abc=sample(a,3)

    e2=x.iloc[abc]
    display(e2)

    print('press y to choose specific AMC')
    print('press n to continue')
    choice = input('please enter your choice:')


    if choice.lower()=='y':
        var =df.AmcName.unique()
        print(var)

        userchoice=input('enter the amc you want:')
        print('userchoice=',userchoice)
        

        df3= df.loc[(df['AmcName']==userchoice)&(df['Category']==y)]
        

        display(df3)
        xyz = df3.index.tolist()
        print(xyz)

        while(True):
            choice = input("Enter your choice: ")
            if choice.isnumeric():
                b=int(choice)
                if b in xyz:
                    temp = x.loc[b]
                    display(temp)
                    break
                else:
                    print('Choice not in options')

            else:
                print("invalid")


                break

    elif choice.lower ()=='n':
        while(True):
            choice = input("Enter Fundrating wise Choice: ")
            if choice.isnumeric():
                b=int(choice)
                if b in abc:
                    display(x.loc[b])
                    break
                else:
                    print('Choice not in options')

            else:
                print("invalid")
    
    else:
        ('please correct choice')


    
    return

    def mfn(x,y):
    e1=x[x.Category==y]
    a=[]
    for f in e1.index:
        a.append(f)
    
    abc=sample(a,3)

    e2=x.iloc[abc]
    display(e2)


    while(True):
        print('press y to choose specific AMC')
        print('press n to continue')
        choice = input('please enter your choice:')
    
        if choice.lower()=='y':
            var =df.AmcName.unique()
            print(var)

            userchoice=input('enter the amc you want:')
            print('userchoice=',userchoice)


            df3= df.loc[(df['AmcName']==userchoice)&(df['Category']==y)]


            display(df3)
            xyz = df3.index.tolist()
            print(xyz)
            while(True):
                choice = input("Enter your choice: ")
                if choice.isnumeric():
                    b=int(choice)
                    if b in xyz:
                        temp = x.loc[b]
                        display(temp)
                        return b
                    else:
                        print('Choice not in options')

                else:
                    print("invalid")
                    break
            break



        elif choice.lower()=='n':
            while(True):
                choice = input("Enter your choice: ")
                if choice.isnumeric():
                    b=int(choice)
                    if b in abc:
                        temp = x.loc[b]
                        display(temp)
                        return b
                    else:
                        print('Choice not in options')

                else:
                    print("invalid")
                    break
            break
        else:
            print('Incorrect Option')

        def mfnrating(x,y, z):
    e1=x[(x.Category==y) & (x.Fundrating == z)]
    a=[]
    for f in e1.index:
        a.append(f)
    
    abc=sample(a,3)

    e2=x.iloc[abc]
    display(e2)


    while(True):
        print('press y to choose specific AMC')
        print('press n to continue')
        choice = input('please enter your choice:')
    
        if choice.lower()=='y':
            var =df.AmcName.unique()
            print(var)

            userchoice=input('enter the amc you want:')
            print('userchoice=',userchoice)


            df3= df.loc[(df['AmcName']==userchoice)&(df['Category']==y)]


            display(df3)
            xyz = df3.index.tolist()
            print(xyz)
            while(True):
                choice = input("Enter your choice: ")
                if choice.isnumeric():
                    b=int(choice)
                    if b in xyz:
                        temp = x.loc[b]
                        display(temp)
                        break
                    else:
                        print('Choice not in options')

                else:
                    print("invalid")
                    break
            break 



        elif choice.lower()=='n':
            while(True):
                choice = input("Enter your choice: ")
                if choice.isnumeric():
                    b=int(choice)
                    if b in abc:
                        temp = x.loc[b]
                        display(temp)
                        break
                    else:
                        print('Choice not in options')

                else:
                    print("invalid")
                    break
            break
        else:
            print('Incorrect Option')

        #CALCULATOR PROGRAMING
        def calculator(investment, r, years):
    #Returns Calculator

    months = years * 12

    #Compound Interest Formula
    i = r/100/12

    #Seperate Calculation for FV
    a = (1+i)**months-1
    b = (1+i)/i
    
    #Final Future Value Calculation
    FV = investment * a * b
    #print(FV)
    
    return FV

    def calculate(df, amount, age, row):
    print("\nFollowing are the Funds you have chosen: ")
    display(df.loc[row])
    
    if amount <= 5000:
        if age <= 18:
            equity = amount

            a = df.loc[row[0]]
            rate = a.Return_1Yr
            equity1 = calculator(equity, rate, 1)

            rate = a.Return_3Yr
            equity3 = calculator(equity, rate, 3)

            rate = a.Return_5Yr
            equity5 = calculator(equity, rate, 5)

            #Calculating Returns
            
            ## for 1 year
            print("Returns for 1 Year \n")
            totalinv = amount * 12
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            equity1 = float(equity1)
            print('Total Portfolio Value = {value:.2f}'.format(value=equity1))
            
            totalgain = equity1 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 3 years
            print('\nReturns for 3 Years\n')
            totalinv = amount * 36
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            equity3 = float(equity3)
            print('Total Portfolio Value = {value:.2f}'.format(value=equity3))
            
            totalgain = equity3 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 5 years
            print('\nReturns for 5 Years\n')
            totalinv = amount * 60
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            equity5 = float(equity5)
            print('Total Portfolio Value = {value:.2f}'.format(value=equity5))
            
            totalgain = equity5 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))

        else:
            var = 100 - age
            per = var/100
            equity = amount * per
            hybrid = amount - equity
            
            #For Equity
            a = df.loc[row[0]]
            rate = a.Return_1Yr
            equity1 = calculator(equity, rate, 1)
            
            rate = a.Return_3Yr
            equity3 = calculator(equity, rate, 3)

            rate = a.Return_5Yr
            equity5 = calculator(equity, rate, 5)
            
            #For Hybrid
            a = df.loc[row[1]]
            rate = a.Return_1Yr
            hybrid1 = calculator(hybrid, rate, 1)

            rate = a.Return_3Yr
            hybrid3 = calculator(hybrid, rate, 3)

            rate = a.Return_5Yr
            hybrid5 = calculator(hybrid, rate, 5)
            
            #Calculating Returns
            
            ## for 1 year
            print("Returns for 1 Year \n")
            totalinv = amount * 12
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year1 = float(equity1) + float(hybrid1)
            print('Total Portfolio Value = {value:.2f}'.format(value=Year1))
            
            totalgain = Year1 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 3 years
            print('\nReturns for 3 Years\n')
            totalinv = amount * 36
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year3 = float(equity3) + float(hybrid3)
            print('Total Portfolio Value = {value:.2f}'.format(value=Year3))
            
            totalgain = Year3 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 5 years
            print('\nReturns for 5 Years\n')
            totalinv = amount * 60
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year5 = float(equity5) + float(hybrid5)
            print('Total Portfolio Value = {value:.2f}'.format(value=Year5))
            
            totalgain = Year5 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
    elif amount > 5000 and amount <= 10000:
        if age <= 18:
            amount1 = amount/2
            amount2 = amount/2

            a = df.loc[row[0]]
            rate = a.Return_1Yr
            equity1 = calculator(amount1, rate, 1)

            rate = a.Return_3Yr
            equity3 = calculator(amount1, rate, 3)

            rate = a.Return_5Yr
            equity5 = calculator(amount1, rate, 5)
            
            b = df.loc[row[1]]
            rate = b.Return_1Yr
            equity21 = calculator(amount2, rate, 1)
            
            rate = b.Return_3Yr
            equity23 = calculator(amount2, rate, 3)

            rate = b.Return_5Yr
            equity25 = calculator(amount2, rate, 5)


            #Calculating Returns
            
            ## for 1 year
            print("Returns for 1 Year \n")
            totalinv = amount * 12
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year1 = equity1 + equity21
            print('Total Portfolio Value = {value:.2f}'.format(value=Year1))
            
            totalgain = Year1 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 3 years
            print('\nReturns for 3 Years\n')
            totalinv = amount * 36
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year3 = equity3 + equity23
            print('Total Portfolio Value = {value:.2f}'.format(value=Year3))
            
            totalgain = Year3 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 5 years
            print('\nReturns for 5 Years\n')
            totalinv = amount * 60
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year5 = equity5 + equity25
            print('Total Portfolio Value = {value:.2f}'.format(value=Year5))
            
            totalgain = Year5 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))

        else:
            var = 100 - age
            per = var/100
            equity = amount * per
            var2 = amount - equity
            hybrid = var2 / 2
            debt = var2 / 2
            
            #for equity funds
            fund1 = equity/2
            fund2 = equity/2
            
            #For Equity Fund 1
            a = df.loc[row[0]]
            rate = a.Return_1Yr
            equity1 = calculator(fund1, rate, 1)
            
            rate = a.Return_3Yr
            equity3 = calculator(fund1, rate, 3)

            rate = a.Return_5Yr
            equity5 = calculator(fund1, rate, 5)

            #For Equity Fund 2
            a = df.loc[row[1]]
            rate = a.Return_1Yr
            equity21 = calculator(fund2, rate, 1)
            
            rate = a.Return_3Yr
            equity23 = calculator(fund2, rate, 3)

            rate = a.Return_5Yr
            equity25 = calculator(fund2, rate, 5)
            
            
            #For Hybrid
            a = df.loc[row[2]]
            rate = a.Return_1Yr
            hybrid1 = calculator(hybrid, rate, 1)

            rate = a.Return_3Yr
            hybrid3 = calculator(hybrid, rate, 3)

            rate = a.Return_5Yr
            hybrid5 = calculator(hybrid, rate, 5)

            #For Debt
            a = df.loc[row[3]]
            rate = a.Return_1Yr
            debt1 = calculator(debt, rate, 1)

            rate = a.Return_3Yr
            debt3 = calculator(debt, rate, 3)

            rate = a.Return_5Yr
            debt5 = calculator(debt, rate, 5)
            
            
            #Calculating Returns
            
            ## for 1 year
            print("Returns for 1 Year \n")
            totalinv = amount * 12
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year1 = equity1 + equity21 + hybrid1 + debt1
            print('Total Portfolio Value = {value:.2f}'.format(value=Year1))
            
            totalgain = Year1 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 3 years
            print('\nReturns for 3 Years\n')
            totalinv = amount * 36
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year3 = equity3 + equity23 + hybrid3 + debt3
            print('Total Portfolio Value = {value:.2f}'.format(value=Year3))
            
            totalgain = Year3 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 5 years
            print('\nReturns for 5 Years\n')
            totalinv = amount * 60
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year5 = equity5 + equity25 + hybrid5 + debt5
            print('Total Portfolio Value = {value:.2f}'.format(value=Year5))
            
            totalgain = Year5 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
    
    elif amount > 10000:
        if age <= 18:
            amount1 = amount/3
            amount2 = amount/3
            amount3 = amount/3

            a = df.loc[row[0]]
            rate = a.Return_1Yr
            equity1 = calculator(amount1, rate, 1)

            rate = a.Return_3Yr
            equity3 = calculator(amount1, rate, 3)

            rate = a.Return_5Yr
            equity5 = calculator(amount1, rate, 5)
            
            b = df.loc[row[1]]
            rate = b.Return_1Yr
            equity21 = calculator(amount2, rate, 1)
            
            rate = b.Return_3Yr
            equity23 = calculator(amount2, rate, 3)

            rate = b.Return_5Yr
            equity25 = calculator(amount2, rate, 5)

            c = df.loc[row[2]]
            rate = c.Return_1Yr
            equity31 = calculator(amount3, rate, 1)
            
            rate = c.Return_3Yr
            equity33 = calculator(amount3, rate, 3)

            rate = c.Return_5Yr
            equity35 = calculator(amount3, rate, 5)
            

            #Calculating Returns
            
            ## for 1 year
            print("Returns for 1 Year \n")
            totalinv = amount * 12
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year1 = equity1 + equity21 + equity31
            print('Total Portfolio Value = {value:.2f}'.format(value=Year1))
            
            totalgain = Year1 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 3 years
            print('\nReturns for 3 Years\n')
            totalinv = amount * 36
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year3 = equity3 + equity23 + equity33
            print('Total Portfolio Value = {value:.2f}'.format(value=Year3))
            
            totalgain = Year3 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 5 years
            print('\nReturns for 5 Years\n')
            totalinv = amount * 60
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year5 = equity5 + equity25 + equity35
            print('Total Portfolio Value = {value:.2f}'.format(value=Year5))
            
            totalgain = Year5 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))

        else:
            var = 100 - age
            per = var/100
            equity = amount * per
            var2 = amount - equity
            hybrid = var2 / 2
            debt = var2 / 2
            
            #for equity funds
            fund1 = equity/3
            fund2 = equity/3
            fund3 = equity/3
            
            #For Equity Fund 1
            a = df.loc[row[0]]
            rate = a.Return_1Yr
            equity1 = calculator(fund1, rate, 1)
            
            rate = a.Return_3Yr
            equity3 = calculator(fund1, rate, 3)

            rate = a.Return_5Yr
            equity5 = calculator(fund1, rate, 5)

            #For Equity Fund 2
            a = df.loc[row[1]]
            rate = a.Return_1Yr
            equity21 = calculator(fund2, rate, 1)
            
            rate = a.Return_3Yr
            equity23 = calculator(fund2, rate, 3)

            rate = a.Return_5Yr
            equity25 = calculator(fund2, rate, 5)

            #For Equity Fund 3
            c = df.loc[row[2]]
            rate = c.Return_1Yr
            equity31 = calculator(fund3, rate, 1)
            
            rate = c.Return_3Yr
            equity33 = calculator(fund3, rate, 3)

            rate = c.Return_5Yr
            equity35 = calculator(fund3, rate, 5)
            
            
            #For Hybrid
            a = df.loc[row[3]]
            rate = a.Return_1Yr
            hybrid1 = calculator(hybrid, rate, 1)

            rate = a.Return_3Yr
            hybrid3 = calculator(hybrid, rate, 3)

            rate = a.Return_5Yr
            hybrid5 = calculator(hybrid, rate, 5)

            #For Debt
            a = df.loc[row[4]]
            rate = a.Return_1Yr
            debt1 = calculator(debt, rate, 1)

            rate = a.Return_3Yr
            debt3 = calculator(debt, rate, 3)

            rate = a.Return_5Yr
            debt5 = calculator(debt, rate, 5)
            
            
            #Calculating Returns
            
            ## for 1 year
            print("Returns for 1 Year \n")
            totalinv = amount * 12
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year1 = (equity1 + equity21 + equity31 + hybrid1 + debt1)
            print('Total Portfolio Value = {value:.2f}'.format(value=Year1))
            
            totalgain = Year1 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 3 years
            print('\nReturns for 3 Years\n')
            totalinv = amount * 36
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year3 = equity3 + equity23 + equity33 + hybrid3 + debt3
            print('Total Portfolio Value = {value:.2f}'.format(value=Year3))
            
            totalgain = Year3 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))
            
            ## for 5 years
            print('\nReturns for 5 Years\n')
            totalinv = amount * 60
            print('Total Amount Invested = {value:.2f}'.format(value=totalinv))
            
            Year5 = float(equity5) + float(equity25) + float(equity35) + float(hybrid5) + float(debt5)
            print('Total Portfolio Value = {value:.2f}'.format(value=Year5))
            
            totalgain = Year5 - totalinv
            print('Net Profit = {value:.2f}'.format(value=totalgain))
            
            gainper = totalgain/totalinv*100
            print('Percentage Gained = {value:.2f}'.format(value=gainper))

            #DASH BOARD
            while (True):
    age =input("Enter your age: ")
    if age.isnumeric():
        age = int(age)
        
        if age <=18:
            per1 = 1
            break
        elif  (age) <=100:
            per = 100-age
            per1 = per/100
            break

        else:
            print( "\n Invalid entry")




while(True):
    amt = input("Enter your amount: ")
    if amt.isnumeric():
        amt = float(amt)
    
        if amt >= 1000 and amt <=5000:
            if age <= 18:
                equity = amt * per1
                print("Equity =",equity)
                row = []
                abc = mfn(df,"Equity")
                row.append(abc)
                
                calculate(df, amt, age, row)
                break
            
            else:
                Equity = amt* per1
                Hybrid = amt-Equity
                print("Equity:",Equity, "\nHybrid:",Hybrid)
                row = []
                abc = mfn(df,"Equity")
                row.append(abc)
                
                abc = mfn(df,"Hybrid")
                row.append(abc)
                
                calculate(df, amt, age, row)
                break

        elif amt>5000 and amt<=10000:
            if age <= 18:
                equity = amt * per1
                print("Equity =",equity)
                row = []
                abc=mfnrating(df,"Equity", 5.0)
                row.append(abc)
                row = []
                abc=mfnrating(df,"Equity", 4.0)
                row.append(abc)
                break
            else:
                Equity = amt* per1
                c = amt - Equity
                Hybrid = c/2
                Dbet = c/2
                print("Equity:",Equity, "\nHybrid:",Hybrid,"\nDbet:",Dbet)
                mfnrating(df,"Equity", 5.0)
                mfnrating(df,"Equity", 4.0)
                
                mfn(df,"Hybrid")
                
                mfn(df,"Debt")
                
                break
            

        elif amt>10000:
            if age <= 18:
                equity = amt * per1
                print("Equity =",equity)
                mfnrating(df,"Equity", 5.0)
                mfnrating(df,"Equity", 4.0)
                mfnrating(df,"Equity", 3.0)
                break
            else:
                Equity = amt* per1
                c = amt - Equity
                Hybrid = c/2
                Dbet = c/2
                print("Equity:",Equity, "\nHybrid:",Hybrid,"\nDbet:",Dbet)
                
                mfnrating(df,"Equity", 5.0)
                mfnrating(df,"Equity", 4.0)
                mfnrating(df,"Equity", 3.0)
                
                mfn(df,"Hybrid")
                
                mfn(df,"Debt")
                
                break
            
        else:
            print("Invalid entry")
            
