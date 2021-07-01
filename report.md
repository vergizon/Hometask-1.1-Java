# Отчёт о тестировании <Название приложения>
## Краткое описание
26.06.2021 - <Дата окончания> было проведено функциональное тестирование приложения приёма платежей с банковских карт различным организациям.

На тестирование затрачено: 3 часа

В результате тестирования выявлены следующие дефекты:

1. [Visa Card is not valid](https://github.com/vergizon/Hometask-1.1-Java/issues/1) .

2. [Discover Card is not valid](https://github.com/vergizon/Hometask-1.1-Java/issues/2) .

3. [JCB Card is not valid](https://github.com/vergizon/Hometask-1.1-Java/issues/3) .

4. [American Express Card is not valid](https://github.com/vergizon/Hometask-1.1-Java/issues/4) .

# Описание процесса тестирования
В процессе тестирования использовались следующие артефакты*:

Чек лист: https://github.com/netology-code/javaqa-homeworks/tree/master/intro



В качестве тестовых данных использовались данные:

https://www.freeformatter.com/credit-card-number-generator-validator.html ;

'''
public class Main {
  public static void main(String[] args) {
    // TODO: подставлять номер карты нужно сюда между двойными кавычками, без пробелов
    String number = "5351719427810741";
    System.out.println(String.format("Result is %s", isValidCardNumber(number) ? "OK" : "FAIL"));
  }

  public static boolean isValidCardNumber(String number) {
    if (number == null) {
      return false;
    }

    if (number.length() != 16) {
      return false;
    }

    long result = 0;
    for (int i = 0; i < number.length(); i++) {
      int digit;
      try {
        digit = Integer.parseInt(number.charAt(i) + "");
      } catch (NumberFormatException e) {
        return false;
      }

      if (i % 2 == 0) {
        digit *= 2;
        if (digit > 9) {
          digit -= 9;
        }
      }
      result += digit;
    }

    return (result != 0) && (result % 10 == 0);
  }
}'''

Тестирование производилось в следующем окружении:

версия и разрядность ОС - Windows 10 Pro x64; 
версия Java - 11.0.11;
другое ПО, при необходимости - IntelliJ IDEA version 1.20