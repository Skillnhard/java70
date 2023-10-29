# Задача 1.
```java
public class Test {

    public static void main(String[] args) {
        System.out.println("Привет, Пиксель!");
        System.out.println("Привет, Байт!");

        double[] feedExpensesCat = {100.50, 236.0, 510.6, 150.20, 80.0, 172.0, 135.4};
        double[] feedExpensesHamster = {70.50, 146.0, 710.6, 250.20, 83.0, 19.0, 55.4};

        double maxFeedExpenseCat = 0;
        for (int i = 0; i < feedExpensesCat.length; i++) {
            if (feedExpensesCat[i] > maxFeedExpenseCat) {
                maxFeedExpenseCat = feedExpensesCat[i];
            }
        }

        System.out.println("Твой самый дорогой корм стоил " + maxFeedExpenseCat);

        double maxFeedExpenseHamster = 0;
        for (int i = 0; i < feedExpensesHamster.length; i++) {
            if (feedExpensesHamster[i] > maxFeedExpenseHamster) {
                maxFeedExpenseHamster = feedExpensesHamster[i];
            }
        }

        System.out.println("Твой самый дорогой корм стоил " + maxFeedExpenseHamster);

        double sumFeedCat = 0;
        for (int i = 0; i < feedExpensesCat.length; i++) {
            sumFeedCat = sumFeedCat + feedExpensesCat[i];
        }

        System.out.println("Всего на корм было потрачено " + sumFeedCat);

        double sumFeedHamster = 0;
        for (int i = 0; i < feedExpensesHamster.length; i++) {
            sumFeedHamster = sumFeedHamster + feedExpensesHamster[i];
        }

        System.out.println("Всего на корм было потрачено " + sumFeedHamster);

        System.out.println("Приятного аппетита, Пиксель!");
        System.out.println("Приятного аппетита, Байт!");
    }
}
```

## Описание
Прочитайте код. Сейчас программа анализирует расходы на корм одновременно для двух питомцев: кота Пикселя и хомяка Байта — из-за этого в результатах печати можно запутаться. Декомпозируйте код — разбейте его отдельные методы: sayHello, sayEnjoyMeal, findMaxExpense и findExpensesSum. Методы с приветствием и пожеланием приятного аппетита должны быть типа void; методы, касающиеся анализа трат, должны возвращать значение. 
У всех методов должны быть параметры. Внутри главного метода main(String[] args) должны остаться массивы с тратами, вызов методов и вывод результатов трат. 
Вызовите методы так, чтобы сначала была напечатана информация про Пикселя, а потом про Байта. Порядок вывода такой: сперва приветствие, затем стоимость самого дорогого корма и общие траты на него и только потом пожелание приятного аппетита.


# Задача 2

```java

import java.util.Scanner;

public class Test {
    public static void main(String[] args) {
        double[] expenses = new double[7];

        double rateUSD = 78.5;
        double rateEUR = 85;
        double rateJPY = 0.74;

        Scanner scanner = new Scanner(System.in);

        System.out.println("Сколько денег у вас осталось до зарплаты?");
        double moneyBeforeSalary = scanner.nextDouble();

        System.out.println("Сколько дней до зарплаты?");
        int daysBeforeSalary = scanner.nextInt();

        while (true) {
            ... // Вынесите печать меню в метод printMenu, здесь останется только его вызов
            System.out.println("Что вы хотите сделать? ");
            System.out.println("1 - Конвертировать валюту");
            System.out.println("2 - Получить совет");
            System.out.println("3 - Ввести трату");
            System.out.println("4 - Показать траты за неделю");
            System.out.println("5 - Показать самую большую сумму расходов за неделю");
            System.out.println("0 - Выход");

            int command = scanner.nextInt();

            if (command == 1) {
                ... // Вынесите обработку команды в метод convert, здесь вызовите его
                System.out.println("Ваши сбережения: " + moneyBeforeSalary + " TENGE");
                System.out.println("В какую валюту хотите конвертировать? Доступные варианты: 1 - USD, 2 - EUR, 3 - JPY.");
                int currency = scanner.nextInt();
                if (currency == 1) {
                    System.out.println("Ваши сбережения в долларах: " + moneyBeforeSalary / rateUSD);
                } else if (currency == 2) {
                    System.out.println("Ваши сбережения в евро: " + moneyBeforeSalary / rateEUR);
                } else if (currency == 3) {
                    System.out.println("Ваши сбережения в иенах: " + moneyBeforeSalary / rateJPY);
                } else {
                    System.out.println("Неизвестная валюта");
                }
            } else if (command == 2) {
                ... // Вынесите обработку команды в метод getAdvice, здесь вызовите его
                if (moneyBeforeSalary < 3000) {
                    System.out.println("Сегодня лучше поесть дома. Экономьте, и вы дотянете до зарплаты!");
                } else if (moneyBeforeSalary < 10000){
                    if (daysBeforeSalary < 10) {
                        System.out.println("Окей, пора в Макдак!");
                    } else {
                        System.out.println("Сегодня лучше поесть дома. Экономьте, и вы дотянете до зарплаты!");
                    }
                } else if (moneyBeforeSalary < 30000) {
                    if (daysBeforeSalary < 10) {
                        System.out.println("Неплохо! Прикупите долларов и зайдите поужинать в классное место. :)");
                    } else {
                        System.out.println("Окей, пора в Макдак!");
                    }
                } else {
                    if (daysBeforeSalary < 10) {
                        System.out.println("Отлично! Заказывайте крабов!");
                    } else {
                        System.out.println("Неплохо! Прикупите долларов и зайдите поужинать в классное место. :)");
                    }
                }
            } else if (command == 3) {
                System.out.println("За какой день вы хотите ввести трату: 1-ПН, 2-ВТ, 3-СР, 4-ЧТ, 5-ПТ, 6-СБ, 7-ВС?");
                int day = scanner.nextInt();
                System.out.println("Введите размер траты:");
                double expense = scanner.nextDouble();
                moneyBeforeSalary = moneyBeforeSalary - expense;
                expenses[day - 1] = expenses[day - 1] + expense;
                System.out.println("Значение сохранено! Ваш текущий баланс в тенге: " + moneyBeforeSalary);
                if (moneyBeforeSalary < 1000) {
                    System.out.println("На вашем счету осталось совсем немного. Стоит начать экономить!");
                }
            } else if (command == 4) {
                for (int i = 0; i < expenses.length; i++) {
                    System.out.println("День " + (i + 1) + ". Потрачено " + expenses[i] + " тенге");
                }
            } else if (command == 5) {
                double maxExpense = 0;
                for (int i = 0; i < expenses.length; i++) {
                    if (expenses[i] > maxExpense) {
                        maxExpense = expenses[i];
                    }
                }
                System.out.println("Самая большая сумма расходов на этой неделе составила " + maxExpense + " тг.");
            } else if (command == 0) {
                System.out.println("Выход");
                break;
            } else {
                System.out.println("Извините, такой команды пока нет.");
            }
        }
    }

    // Объявите и реализуйте метод printMenu, который печатает меню
    ...
 
    // Объявите и реализуйте метод convert, который конвертирует валюты 
    ... convert(Scanner scanner, double moneyBeforeSalary) ...

    // Объявите и реализуйте метод getAdvice, который даёт совет
    ...
            
}
```

## 1 из 2

Начните декомпозицию финансового приложения. Объявите, реализуйте и вызовите следующие методы:
Метод printMenu должен печатать цифровое меню с командами и не будет ничего возвращать. Его вызов необходимо оставить в цикле while, чтобы меню выводилось перед каждой командой.
Метод convert будет использоваться для конвертации валют. Заготовку параметров для него вы найдёте в прекоде. Он должен принимать в качестве аргументов остаток денег на счету и переменную сложного типа scanner — это позволит не дублировать код для считывания выбора валюты. Также не забудьте перенести из main в метод convert те переменные, которые нужны непосредственно для его работы.
Метод getAdvice должен давать совет насчёт ужина в зависимости от того, сколько денег осталось до зарплаты. Он должен принимать два параметра moneyBeforeSalary и daysBeforeSalary (в этом порядке) и так же, как и остальные, не должен возвращать никаких значений.


## 2 из 2

Завершите декомпозицию финансового приложения — в методе main(String[] args) всё ещё сосредоточено слишком много задач. Вынесите обработку трат в отдельные методы: объявите, реализуйте и вызовите их. 
Метод saveExpense должен сохранять значение расходов, введённое пользователем, и возвращать новое значение остатка средств. У него будет три параметра: Scanner scanner — для считывания ввода из консоли, double moneyBeforeSalary — для значения суммы на счёте, double[] expenses — для массива расходов.
Метод printAllExpenses должен печатать траты пользователя. Он ничего не возвращает и имеет один параметр — массив расходов.
Метод findMaxExpense должен находить максимальное значение в списке трат за неделю и возвращать её в качестве результата при вызове. Печать максимальной траты должна остаться в главном методе. У этого метода один параметр — массив расходов.

