## Втора лабораториска вежба по Софтверско инженерство
# Симона Анѓелковска бр. на индекс 223080

# Control Flow Graph

![Alt text](https://github.com/AnSimona/SI_2024_lab2_223080/blob/master/final_diagram.png?raw=true)

# Цикломатска комплексност

Цикломатската комплесност на овој граф е 10, што значи дека има 10 независни патеки коишто треба да се извршат за потполно да се тестира кодот. 

Според формулата V(G)=E-N+2P

V(G)=37-29=8+2=10 Каде што 29 е бројот на јазли, 37 бројот на рабови.

Број на предикатни јазли + 1 

9+1 = 10

# Тест случаи според Every Branch:

1. if (allItems == null)
   
Празна листа

input: allItems = null, payment = 1000

output: Исклучок RuntimeException("allItems list can't be null!")


2. if (item.getName() == null || item.getName().length() == 0)
   
input: allItems = [new Item("", "12345", 100, 0)], payment = 100

output: true


3. if (item.getBarcode() != null)
   
test case: Валиден баркод

input: allItems = [new Item("Milk", "12345", 100, 0)], payment = 100

output: true

test case: Невалиден баркод

input: allItems = [new Item("Milk", null, 100, 0)], payment = 100

output: Исклучок RuntimeException("No barcode!")


4. if (item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0')

Цена над 300, со попуст и баркодот започнува со '0'

input: allItems = [new Item("Milk", "01234", 400, 0.1f)], payment = 340

output: true

Цена над 300, со попуст и баркодот не започнува со '0'

input: allItems = [new Item("Milk", "11234", 400, 0.1f)], payment = 360

output: true


5. if (sum <= payment)

test case: Сумата е помала или еднаква на плаќањето

input: allItems = [new Item("Milk", "01234", 100, 0), new Item("Bread", "56789", 150, 0.1f)], payment = 250

output: true

test case: Сумата е поголема од плаќањето

input: allItems = [new Item("Milk", "01234", 100, 0), new Item("Bread", "56789", 250, 0.1f)], payment = 300

output: false


#  Тест случаи според Multiple condition
if (item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0)== '0')

Дадениот код минимум може да помине 4 тестови за да биде исполнет. 
1. Случај е кога сите критериуми се исполнети - ТТТ
2. Доколку цената е помала од 300 и условот item.getDiscount() е исполнет
3. Кога првиот случај е исполнет, а вториот не
4. Случај кога цената е поголема, има попуст но баркодот не започнува со '0'
   

