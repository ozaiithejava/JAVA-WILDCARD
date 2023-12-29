# JAVA-WILDCARD
wildcard usage in java


## Usage:
```Java
import java.util.ArrayList;
import java.util.List;

public class WildcardExample {

    // Generic metot örneği
    public static <T> void printData(List<T> dataList) {
        for (T data : dataList) {
            System.out.println(data);
        }
    }

    // Wildcard parametreli metot örneği
    public static void processList(List<?> dataList) {
        for (Object data : dataList) {
            System.out.println(data);
        }
    }

    // Upper bound wildcard örneği
    public static void processNumbers(List<? extends Number> numbers) {
        for (Number number : numbers) {
            System.out.println(number);
        }
    }

    // Lower bound wildcard örneği
    public static void processIntegers(List<? super Integer> integers) {
        for (Object integer : integers) {
            System.out.println(integer);
        }
    }

    public static void main(String[] args) {
        // Generic metot kullanımı
        List<String> stringList = List.of("Java", "C++", "Python");
        List<Integer> integerList = List.of(1, 2, 3);

        System.out.println("Generic Metot Kullanımı:");
        printData(stringList);
        printData(integerList);

        // Wildcard parametreli metot kullanımı
        List<Double> doubleList = List.of(1.1, 2.2, 3.3);

        System.out.println("\nWildcard Parametreli Metot Kullanımı:");
        processList(stringList);
        processList(integerList);
        processList(doubleList);

        // Upper bound wildcard kullanımı
        List<Integer> intList = List.of(10, 20, 30);
        List<Double> doubleList2 = List.of(4.4, 5.5, 6.6);

        System.out.println("\nUpper Bound Wildcard Kullanımı:");
        processNumbers(intList);
        processNumbers(doubleList2);

        // Lower bound wildcard kullanımı
        List<Number> numberList = new ArrayList<>();
        numberList.add(100);
        numberList.add(200);

        System.out.println("\nLower Bound Wildcard Kullanımı:");
        processIntegers(numberList);
    }
}
```
