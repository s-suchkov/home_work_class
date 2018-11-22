# home_work_class
class animals:
  feed = 1000 # единиц
  
class geese(animals):
  vote = 'ga-ga'
  eggs = 20
  def __init__(self, name: str, weight: float):
    self.name = name
    self.weight = weight
  def collect_eggs(self, collect):
    self.eggs -= collect
  def eat(self, corn):
    self.feed -= corn
  def __radd__(self, other):
    if isinstance(other, float) or isinstance(other, int):
      return self.weight + other
  def __gt__(self, other):
    if isinstance(other, animals):
      return self.weight > other.weight
  def __it__(self, other):
    if isinstance(other, animals):
      return self.weight < other.weight
geese_white = geese('white', 8)
geese_grey = geese('grey', 12)
geese_white.eat(10)
geese_white.collect_eggs(5)
print(geese_white.name)
print(geese_grey.name)

class cow(animals):
  vote = 'mu-mu'
  milk = 0
  def __init__(self, name: str, weight: float):
    self.name = name
    self.weight = weight
  def moloko(self, collect_milk):
    self.milk += collect_milk
  def eat(self, hay):
    self.feed -= hay
  def __radd__(self, other):
    if isinstance(other, float) or isinstance(other, int):
      return self.weight + other
  def __gt__(self, other):
    if isinstance(other, animals):
      return self.weight > other.weight
  def __it__(self, other):
    if isinstance(other, animals):
      return self.weight < other.weight
cow_1 = cow('Манька', 120)
cow_1.eat(50)
print(cow_1.name)

class sheeps(animals):
  vote = 'be-be'
  hair = 100
  def __init__(self, name: str, weight: float):
    self.name = name
    self.weight = weight
  def wool(self, cut):
    self.hair -= cut
  def __radd__(self, other):
    if isinstance(other, float) or isinstance(other, int):
      return self.weight + other
  def __gt__(self, other):
    if isinstance(other, animals):
      return self.weight > other.weight
  def __it__(self, other):
    if isinstance(other, animals):
      return self.weight < other.weight
sheeps_1 = sheeps('Барашек', 55)
sheeps_2 = sheeps('Кудрявый', 60)
sheeps_1.wool(45)
print(sheeps_1.name)
print(sheeps_2.name)
class goats(cow):
  vote = 'adfsad'
goats_1 = goats('Рога', 30)
goats_2 = goats('Копыта', 42)
print(goats_1.name)
print(goats_2.name)

class chikens(geese):
  vote = 'ko-ko'
  eggs = 50
chiken_1 = chikens('ко-ко', 1.5)
chiken_2 = chikens('кукареку', 2)
chiken_1.collect_eggs(20)
print(chiken_1.name)
print(chiken_2.name)

class duck(geese):
  vote = 'krya-krya'
  eggs = 10
duck_1 = duck('Кряква', 4)
duck_1.collect_eggs(2)
print(duck_1.name)

weight_list = list()    
weight_list.append(geese_white)
weight_list.append(geese_grey)
weight_list.append(cow_1)
weight_list.append(sheeps_1)
weight_list.append(sheeps_2)
weight_list.append(goats_1)
weight_list.append(goats_2)
weight_list.append(chiken_1)
weight_list.append(chiken_2)
weight_list.append(duck_1)

weight = 0
big_weight = 0
for  i in weight_list:
  weight += i
weight_list.sort()
print(weight_list)
print(weight_list[-1].name, weight_list[-1].weight)
