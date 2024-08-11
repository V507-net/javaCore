### Задание 2.9. Калькулятор (HW-02)

<details>
  <summary>Задание</summary>

    РЕАЛИЗУЙТЕ КАЛЬКУЛЯТОР:
    Калькулятор считывает число.
    После этого считывает операцию, которую необходимо выполнить. Давайте ограничимся простыми операциями: сложение, вычитание, умножение и деление.
    Считывает второй операнд.
    После выполнения операции калькулятор выводит получившееся значение.

</details>


[Calc.java](src%2FCalc.java)

```java
import java.util.Scanner;

public class Calc {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.println("Добро пожаловать в калькулятор! Для начала расчета введиет с для выхода введите q");
        while (scanner.next().charAt(0) != 'q')
        {
            char operation;
            int operand1, operand2, result = 0;

            System.out.println("Введите первый операнд (целое число): ");
            while ( !scanner.hasNextInt() ) {
                scanner.next();
                System.out.println("Неверное число, повторите ввод");
            }
            operand1 = scanner.nextInt();

            while (true) {
                System.out.println("Введите действие (+-/*): ");
                operation = scanner.next().charAt(0);
                if (operation == '/' || operation == '*' || operation == '+' || operation == '-')
                {
                    break;
                }
                System.out.println("Повторите ввод, не известное действие");
            }

            System.out.println("Введите второй операнд (целое число): ");
            while ( !scanner.hasNextInt() ) {
                scanner.next();
                System.out.println("Неверное число, повторите ввод");
            }
            operand2 = scanner.nextInt();

            switch (operation) {
                case '/':

                    if (operand2 == 0 || operand1 == 0) {
                        System.out.println("Деление на 0 запрещено!");
                        break;
                    }
                    System.out.println("Результат вычислений: " + result);
                    break;
                case '*':
                    result = operand1 * operand2;
                    System.out.println("Результат вычислений: " + result);
                    break;
                case '+':
                    result = operand1 + operand2;
                    System.out.println("Результат вычислений: " + result);
                    break;
                case '-':
                    result = operand1 - operand2;
                    System.out.println("Результат вычислений: " + result);

            }

            System.out.println("Для продолжения введите с для выхода введите q");
        }

    }
}
```