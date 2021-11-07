class Coffeemachine():
    def __init__(self):
        self.water = 400
        self.milk = 540
        self.coffee_beans = 120
        self.cups = 9
        self.money = 550

    def action_cycle(self, action):
        self.action = action
        while True:
            if self.action == 'exit':
                break
            elif self.action == 'buy':
                self.buy()
            elif self.action == 'fill':
                self.fill()
            elif self.action == 'remaining':
                self.remaining()
            elif self.action == 'take':
                self.take()
            self.action = input('Write action (buy, fill, take, remaining, exit):')
        return

    def remaining(self):
        print(f'''The coffee machine has:
        {self.water} of water
        {self.milk} of milk
        {self.coffee_beans} of coffee beans
        {self.cups} of disposable cups
        {self.money} of money''')

    def check_supply(self):
        self.check_list = [self.water, self.milk, self.coffee_beans, self.cups, self.money]
        self.name_list = ['water', 'milk', 'coffee_beans', 'cups', 'money']
        for i in range(len(self.check_list)):
            if self.check_list[i] < 0:
                print(f'Sorry, not enough {self.name_list[i]}!')
                return False
            else:
                print('I have enough resources, making you a coffee!')
                return True

    def make_espresso(self):
        self.water -= 250
        self.coffee_beans -= 16
        self.money += 4
        self.cups -= 1
        if self.check_supply() is False:
            self.water += 250
            self.coffee_beans += 16
            self.money -= 4
            self.cups += 1
        return self.water, self.milk, self.coffee_beans, self.cups, self.money

    def make_latte(self):
        self.water -= 350
        self.coffee_beans -= 20
        self.milk -= 75
        self.money += 7
        self.cups -= 1
        if self.check_supply() is False:
            self.water += 350
            self.coffee_beans += 20
            self.milk += 75
            self.money -= 7
            self.cups += 1
        return self.water, self.milk, self.coffee_beans, self.cups, self.money

    def make_cappuccino(self):
        self.water -= 200
        self.coffee_beans -= 12
        self.milk -= 100
        self.money += 6
        self.cups -= 1
        if self.check_supply() is False:
            self.water += 200
            self.coffee_beans += 12
            self.milk += 100
            self.money -= 6
            self.cups += 1
        return self.water, self.milk, self.coffee_beans, self.cups, self.money

    def buy(self):
        self.program = (input('What do you want to buy? 1 - espresso, 2 - latte, 3 - cappuccino:'))
        if self.program.isdigit():
            self.program = int(self.program)
        if self.program == 'back':
            return self.water, self.milk, self.coffee_beans, self.cups, self.money
        elif self.program == 1:
            return self.make_espresso()
        elif self.program == 2:
            return self.make_latte()
        elif self.program == 3:
            return self.make_cappuccino()

    def fill(self):
        self.water += int(input('Write how many ml of water you want to add:'))
        self.milk += int(input('Write how many ml of milk you want to add:'))
        self.coffee_beans += int(input('Write how many grams of coffee beans you want to add:'))
        self.cups += int(input('Write how many disposable coffee cups you want to add:'))
        return self.water, self.milk, self.coffee_beans, self.cups

    def take(self):
        print(f'I gave you ${self.money}')
        self.money -= self.money
        return self.money

work = Coffeemachine()
work.action_cycle(0)



