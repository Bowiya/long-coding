class Price:
    amount:float
    def __init__(self,amt):
        self.amount=amt
    def setAmount(self,amt:float):
        self.amount=amt
    def getAmount(self):
        return self.amount

class flavor(Price):
    name:str

    def __init__(self,Name:str,Amt:float):

        self.name= Name
        self.setAmount(Amt)
    def getName(self):
        return self.name

class ic_type(Price):
    ic_typename:str
    def __init__(self,IC_typename:str,Amt:float):
        self.ic_typename=IC_typename
        self.setAmount(Amt)
    def getName(self):
        return self.ic_typename

class menu:
    flavors=[]

    types=[]
    a:int
    b:int
    def flavorstypes(self):
        self.flavors.append(flavor("vanilla",50))
        self.flavors.append(flavor("chocolate",60))
        self.flavors.append(flavor("strawberry",100))

        self.types.append(ic_type("stick",50))
        self.types.append(ic_type("cup",60))
        self.types.append(ic_type("cone",20))

    def display(self):
        print("....................................................................................................................")
        print("\n")
        print("Icecream flavors")
        print(".....................................................................................................................")
        fl_c = 1
        if len(self.flavors) > 0:
            for flavor in self.flavors:
                print(fl_c, flavor.getName(), "[Rs.", flavor.getAmount(), "]")
                fl_c += 1
        else:
            print("sorry we haven't that flavor")
        print(".................................................................................................................")
        print("\nIcecream Types")
        print(".................................................................................................................")
        ty_c = 1
        if len(self.types) > 0:
            for type in self.types:
                print(ty_c, type.getName(), "[Rs.", type.getAmount(), "]")
                ty_c += 1
        else:
            print("sorry we haven't that type")


    def askflavorchoice(self):
        return int(input("what flavor you want purchase?"))

    def askicechoice(self):
        return int(input("what type of ice do you want?"))
    def displayquantity(self):
        print("\n")
        print(".........................................................................................................")
        print("                       ice cream quantity")
        print("...........................................................................................................")
        print("you choosen",self.askicechoice(),"type")
        print("you choosen",self.askflavorchoice(),"flavor")
    def askquantity(self):
         return int(input("how many ice creams do you want"))
    def bill(self):
        flavor_amt=self.flavors[self.askflavorchoice()-1].getAmount()
        ic_type_amt=self.types[self.askicechoice()-1].getAmount()
        return flavor_amt+ic_type_amt*askquantity()

obj = menu()
obj.flavorstypes()
obj.display()
obj.displayquantity()
obj.bill()
