## Lambda

[1. Что такое lambda-выражение?](#1-Что-такое-lambda-выражение)

[2. Что такое функциональные интерфейсы?](#2-Что-такое-функциональные-интерфейсы)

[3. Перечислите функциональные интерфейсы из пакета java.util.function.](#3-Перечислите-функциональные-интерфейсы-из-пакетаjava-util-function)

[4. Что такое функции высшего порядка?](#4-Что-такое-функции-высшего-порядка)

[5. Какие функциональные интерфейсы из пакета java.util.function поддерживают функции высшего порядка?](#5-Какие-функциональные-интерфейсы-из-пакета-java-util-function-поддерживают-функции-высшего-порядка)

[6. Что такое ссылки на методы?](#6-Что-такое-ссылки-на-методы)

[7. Что такое ссылки на конструкторы?](#7-Что-такое-ссылки-на-конструкторы)

[8. Расскажите о зоне видимости переменных в lambda - выражениях?](#8-Расскажите-о-зоне-видимости-переменных-в-lambda-выражениях)

[9. Как быть в ситуации, если внутри lambda - выражения операторы могут выкинуть исключение?](#9-Как-быть-в-ситуации-если-внутри-lambda-выражения-операторы-могут-выкинуть-исключение)

[10. Что такое Stream API?](#10-Что-такое-Stream-API)

[11. Расскажите, какие шаблоны проектирования используются внутри Stream API? (Builder, Strategy, Decorator, Factory Method, Pipeline).](#11-Расскажите-какие-шаблоны-проектирования-используются-внутри-Stream-API-Builder-Strategy-Decorator-Factory-Method-Pipeline)

[12. Объясните, где они используются в Stream API.](#12-Объясните-где-они-используются-в-Stream-API)

[13. Что такое конвейерные и терминальные операции?](#13-Что-такое-конвейерные-и-терминальные-операции)

[14. Перечислите конвейерные (промежуточные) методы Stream API.](#14-Перечислите-конвейерные-промежуточные-методы-Stream-API)

[15. Перечислите терминальные методы Stream API.](#15-Перечислите-терминальные-методы-Stream-API)

[16. Что такое отложенный выполнение lamdba?](#16-Что-такое-отложенный-выполнение-lamdba)

[17. Что делает метод filter()?](#17-Что-делает-метод-filter)

[18. Что делает метод map()?](#18-Что-делает-метод-map)

[19. Что делает метод flatMap()?](#19-Что-делает-метод-flatMap)

[20. Что делает метод collect?](#20-Что-делает-метод-collect)

[21. Что делает метод findFirst?](#21-Что-делает-метод-findFirst)

[22. Что делает метод reduce?](#22-Что-делает-метод-reduce)

[23. Что делают методы min и max?](#23-Что-делают-методы-min-и-max)

[24. Что делают методы count, sum, average?](#24-Что-делают-методы-count-sum-average)

[25. Что делают методы forEach и peek?](#25-Что-делают-методы-forEach-и-peek)

[26. Что делают методы skip и limit?](#26-Что-делают-методы-skip-и-limit)

[27. Что делают методы allMatch(), noneMatch() и anyMatch()?](#27-Что-делают-методы-allMatch-noneMatch-и-anyMatch)

[28. Что делают методы mapToInt(), flatMapToInt(), mapToObj()?](#28-Что-делают-методы-mapToInt-flatMapToInt-mapToObj)

[29. Что такое числовой поток?](#29-Что-такое-числовой-поток)

[30. Чем отличается Stream<Integer> от IntStream<int>?](#30-Чем-отличается-Stream-Integer-от-IntStream-int)

[31. Что делает метод boxed?](#31-Что-делает-метод-boxed)

[32. Возможно ли прервать выполнение потока по аналогии с break?](#32-Возможно-ли-прервать-выполнение-потока-по-аналогии-с-break)

[33. Возможно ли пропустить элемент потока по аналогии с continue?](#33-Возможно-ли-пропустить-элемент-потока-по-аналогии-с-continue)

[34. Что такое Optional?](#34-Что-такое-Optional)

[35. Перечислите методы Optional.](#35-Перечислите-методы-Optional)

[36. Расскажите про фабричные методы List.of, Set.of, Map.of?](#36-Расскажите-про-фабричные-методы-List-of-Set-of-Map-of)

[37. Для чего используется var?](#37-Для-чего-используется-var)

[38. В каких случаях можно использовать var?](#38-В-каких-случаях-можно-использовать-var)

## 1. Что такое lambda-выражение?

Лямбда представляет собой набор инструкций, которые можно выделить в отдельную
переменную и затем многократно вызвать в различных местах программы.
Основу лямбда-выражения составляет лямбда-оператор, который представляет стрелку `->`.
Этот оператор разделяет лямбда-выражение на две части: левая часть содержит список
параметров выражения, а правая представляет тело лямбда-выражения, где выполняются
все действия.
Лямбда-выражение не выполняется само по себе, а образует реализацию метода,
определенного в функциональном интерфейсе. При этом важно, что функциональный
интерфейс должен содержать только один единственный метод без реализации.
По факту лямбда-выражения являются в некотором роде сокращенной формой внутренних
анонимных классов.

[К оглавлению](#Lambda)

## 2. Что такое функциональные интерфейсы?

Функциональный интерфейс - это интерфейс, который содержит только один абстрактный метод. Абстрактный метод - это метод
в котором нет реализации. Основное назначение – использование в лямбда выражениях, method reference или ссылок на
конструкторы. Функциональный интерфейс может содержать так же default и static методы.

[К оглавлению](#Lambda)

## 3. Перечислите функциональные интерфейсы из пакета java.util.function.

Supplier (поставщик) используется для создания какого-либо объекта и при этом ему не требуется входной параметр.

```java

@FunctionalInterface
public interface Supplier<T> {
    T get();
}
```

Consumer (потребитель) используется в том случае, если нам нужно применить какое-то действие или операцию к параметру (
для BiConsumer два параметра) и при этом у метода нет возвращаемого значения. Два интерфейса отличаются только одним –
количеством параметров, которые принимает метод в этом интерфейсе. Параметры в Biconsumer могут быть разных типов.

```java

@FunctionalInterface
public interface Consumer<T> {
    void accept(T t);
}

@FunctionalInterface
public interface BiConsumer<T, U> {
    void accept(T t, U u);
}
```

Predicate (утверждение) наиболее часто применяется в фильтрах и сравнении. В метод test() передается один или два
параметра, в зависимости от функционального интерфейса и возвращает логическое значение true или false.

```java

@FunctionalInterface
public interface Predicate<T> {
    boolean test(T t);
}

@FunctionalInterface
public interface BiPredicate<T, U> {
    boolean test(T t, U u);
}
```

Function используется для преобразования входного параметра или двух параметров (для Bi-формы этого функционального
интерфейса) в какое-либо значение, тип возвращаемого значения может не совпадать с типом входных параметров. Все три
типа в обобщениях в BiFunction могут быть разными: принимает на вход 2 разных типа и возвращает третий тип.

```java

@FunctionalInterface
public interface Function<T, R> {
    R apply(T t);
}

@FunctionalInterface
public interface BiFunction<T, U, R> {
    R apply(T t, U u);
}
```

UnaryOperator и BinaryOperator – это разновидность Function, в которых входные и выходные обобщенные параметры должны
совпадать.

```java

@FunctionalInterface
public interface UnaryOperator<T> extends Function<T, T> {
}

@FunctionalInterface
public interface BinaryOperator<T> extends BiFunction<T, T, T> {
}
```

Помимо абстрактных методов функциональные интерфейсы могут иметь целый набор статических методов или методы по
умолчанию.

[К оглавлению](#Lambda)

## 4. Что такое функции высшего порядка?

Функции высшего порядка - это функции, зависящие от других функций. Функции высшего порядка принимают другие функции в
качестве своих параметров или возвращают другие функции в качестве своих результатов. В программировании функции высшего
порядка описываются через композицию. Композиция - объект А не может существовать без объекта B.

[К оглавлению](#Lambda)

## 5. Какие функциональные интерфейсы из пакета java.util.function поддерживают функции высшего порядка?

- Consumer - принимает один аргумент
- Function - принимает один аргумент и возвращает значение
- Predicate - принимает один аргумент и возвращает булево значение
- Supplier - не принимает аргументов и возвращает значение
- UnaryOperator - принимает один аргумент и возвращает тот же тип
- BinaryOperator - принимает два аргумента и возвращает тот же тип
- Comparator

[К оглавлению](#Lambda)

## 6. Что такое ссылки на методы?

Ссылки на методы (Method References) – это компактные лямбда выражения для методов у которых уже есть имя. Такая ссылка
позволяет обращаться к методу, не вызывая его. Для создания ссылки на метод служит следующая общая форма:
`имя_класса :: имя_метода`

Было:

```java
Consumer<String> consumer=str->System.out.println(str);
```

Стало:

```java
Consumer<String> consumer=System.out::println;
```

Вызов метода println идет через двойное двоеточие (::), а не через точку (.)

[К оглавлению](#Lambda)

## 7. Что такое ссылки на конструкторы?

Аналогично ссылкам на методы, ссылки также можно объявлять и на конструкторы.

`ИмяКласса::new`

Такую ссылку можно присвоить любой ссылке на функциональный интерфейс, где определяется метод, совместимый с
конструктором. При этом "ИмяКласса" не может быть интерфейсом или абстрактным классом. При использовании конструкторов
методы функционального интерфейса должны принимать тот же список параметров, что и конструкторы класса, и должны
возвращать объект данного класса.

[К оглавлению](#Lambda)

## 8. Расскажите о зоне видимости переменных в lambda - выражениях?

Лямбда-выражения имеют доступ к переменным в области видимости, в которой их определили. Но доступ возможен только при
условии, что переменные являются effective final, то есть либо явно имеют модификатор final, либо не меняют своего
значения после инициализации (константы). Если переменной присваивается значение во 2й раз, то лямбда-выражение вызовет
ошибку компиляции. Можно ссылаться на:

- effective final локальные переменные;
- поля примитивных типов;
- статические переменные.

[К оглавлению](#Lambda)

## 9. Как быть в ситуации, если внутри lambda - выражения операторы могут выкинуть исключение?

Лямбда-выражение может генерировать исключение.

- если тело лямбда-выражения может бросить проверяемое checked исключение, то оно должно быть объявлено в абстрактном
  методе целевого функционального интерфейса в выражении throws.
- либо должно быть обработано внутри лямбда-выражения с помощью конструкции try-catch-finally.


Как известно из функциональных интерфейсов в Stream API нельзя выбрасывать контролируемые исключения. Если по каким-то
причинам это необходимо (например, работа с файлами, базами данных или по сети), приходится оборачивать их в
RuntimeException.

[К оглавлению](#Lambda)

## 10. Что такое Stream API?

Stream API - это поток данных. Это эффективный инструмент для обработки коллекций в функциональном стиле. Stream API
работает совместно с лямбда-выражениями.

[К оглавлению](#Lambda)

## 11. Расскажите, какие шаблоны проектирования используются внутри Stream API? (Builder, Strategy, Decorator, Factory Method, Pipeline).

Builder, Strategy, Decorator, Factory Method, Pipeline

[К оглавлению](#Lambda)

## 12. Объясните, где они используются в Stream API.

- Для построения потоков при работе со Stream используется шаблон проектирования Builder
- Шаблон “Pipeline” состоит из нескольких компонентов, которые соединяются друг с другом в цепочку. Каждый компонент
  принимает на вход данные, выполняет над ними определенную операцию и передает результат следующему компоненту. Таким
  образом, результат выполнения всей цепочки операций равен результату выполнения всей операции над исходными данными.
- Декоратор - позволяет добавлять новые функции к уже существующим объектам без изменения их исходного кода.
- Фабричный метод - используется для создания объектов на основе их типов, а не на основе их конкретных классов.

[К оглавлению](#Lambda)

## 13. Что такое конвейерные и терминальные операции?

- Промежуточные (конвейерные). Преобразовывают элементы потока, возвращая новый преобразованный поток. Методов данного
  типа может быть сколько угодно в цепочке преобразований элементов потока. Данные методы ленивы, то есть отрабатывают
  только когда для потока вызван конечный метод. Промежуточных методов у потока может и не быть. Промежуточные операции
  не выполняются без конечных! Промежуточные методы ленивы - они начинают вычисляться только когда начнется терминальная
  операция, то есть вычисление происходит только тогда, когда оно нужно.


- Конечные (терминальные). Метод данного типа всегда один, располагается в конце цепочки промежуточных методов (если
  они есть). Данный метод возвращает другой тип объекта (например, Optional, коллекцию и т.д.). То есть конечный
  метод собирает результаты обработки элементов потока и возвращает единый результат. Конечный метод для завершения
  потока обязателен.

[К оглавлению](#Lambda)

## 14. Перечислите конвейерные (промежуточные) методы Stream API.

- filter() - фильтрует элементы потока, возвращая только элементы, удовлетворяющие условию.
- map() - преобразует каждый элемент потока.
- mapToInt() - тот же map(), но возвращает поток примитивов int (также есть соответствующие mapToDouble() и
  mapToLong()).
- flatMap() - трансформирует каждый объект потока в поток других объектов, то есть все элементы коллекции коллекций или
  потока потоков трансформирует в единый поток. (также поддерживает возврат потоков примитивов с помощью методов
  flatMapToInt(), flatMapToDouble(), flatMapToLong()). Может преобразовывать элементы, применяя указанную функцию к
  каждому элементу.
- peek() - применяет функцию Consumer к каждому элементу потока.
- sorted() - сортирует элементы потока по возрастанию. Возможна сортировка по убыванию при передаче соответствующего
  компаратора.
- skip() - пропускает указанное число элементов с начала потока.
- limit() - делает выборку первых элементов из родного потока в указанном количестве (отбирает элементы из потока, пока
  не достигнет указанного количества).
- distinct() - убирает дубликаты из потока.
- mapToObj() - трансформирует числовой поток в объектный.

[К оглавлению](#Lambda)

## 15. Перечислите терминальные методы Stream API.

- forEach() - применяет функцию к каждому элементу потока.
- collect() - собирает все элементы потока в структуру данных.
- toArray() - собирает элементы потока в массив.
- count() - возвращает количество элементов в потоке.
- min() - возвращает минимальный элемент (условие передается в компараторе).
- max() - возвращает максимальный элемент (условие передается в компараторе).
- sum() - возвращает сумму всех элементов потока (только для числовых потоков).
- average() - возвращает среднее арифметическое всех элементов потока (только для числовых потоков).
- allMatch() - возвращает true, если все элементы удовлетворяют условию.
- noneMatch() - возвращает true, если все элементы не удовлетворяют условию.

[К оглавлению](#Lambda)

## 16. Что такое отложенный выполнение lamdba?

Лямбда обладает свойством отложенного выполнения. Отложенное выполнение начинает вычисление только тогда, когда
пользователь запросил его результат.

[К оглавлению](#Lambda)

## 17. Что делает метод filter()?

Используется для фильтрации элементов в коллекции. Он принимает функцию-предикат в качестве аргумента и возвращает новую
коллекцию, содержащую только те элементы, для которых функция-предикат возвращает истину.

[К оглавлению](#Lambda)

## 18. Что делает метод map()?

Метод map() принимает в качестве аргумента функциональный интерфейс Function, задающий преобразование, применяемое к
каждому элементу. Возвращаемый поток содержит преобразованные элементы.
Метод map() возвращает новый поток. Он не изменяет исходный поток и коллекцию. Обычно он используется для выполнения
операций, таких как преобразование элементов из одного типа в другой.

[К оглавлению](#Lambda)

## 19. Что делает метод flatMap()?

Метод flatMap() используется для создания одного потока из множества потоков. Он принимает функцию в качестве аргумента,
которая применяется к каждому элементу исходного потока. Эта функция принимает элемент исходного потока и возвращает
новый поток.

Разница между map() и flatMap()
Метод map() преобразует элемент исходного потока из одного типа в другой. В отличие от этого, метод flatMap()
позволяет получить новый поток из элементов коллекций, которые были внутри элементов первого потока.

[К оглавлению](#Lambda)

## 20. Что делает метод collect?

Используется для сбора элементов в коллекции с использованием заданной функции. Он принимает функцию в качестве
аргумента и применяет ее к каждому элементу коллекции, собирая результаты в новую коллекцию.

[К оглавлению](#Lambda)

## 21. Что делает метод findFirst?

Метод findFirst в Java предназначен для поиска первого элемента в коллекции, удовлетворяющего заданному условию. Он
принимает предикат в качестве параметра и возвращает первый элемент коллекции, для которого предикат вернет true. Если
такого элемента не существует, метод бросает исключение NoSuchElementException.

[К оглавлению](#Lambda)

## 22. Что делает метод reduce?

Метод reduce() применяется для комбинирования элементов потока в одно значение. Он отличается от метода collect() тем,
что использует ассоциативную функцию, принимающую два значения и объединяющую их в одно. Например, метод reduce() можно
использовать для суммирования чисел или для нахождения максимального или минимального числа.

[К оглавлению](#Lambda)

## 23. Что делают методы min и max?

- min() - возвращает минимальный элемент потока. Наименьший элемент определяется с помощью компаратора, который
  передается в параметр метода.
- max() - возвращает максимальный элемент потока. Наибольший элемент определяется с помощью компаратора, который
  передается в параметр метода.

[К оглавлению](#Lambda)

## 24. Что делают методы count, sum, average?

- count() - возвращает число элементов в потоке.
- sum() - суммирует все элементы потока. Применяется только к числовым потокам.
- average() - возвращает среднее арифметическое всех элементов потока. Применяется только к числовым потокам.

[К оглавлению](#Lambda)

## 25. Что делают методы forEach и peek?

- peek() - это промежуточная операция. Выполняет действие для каждого элемента потока, возвращая поток, состоящий из
  измененных элементов.
- forEach() - это конечная операция. Выполняет действие для каждого элемента потока, завершая поток.

peek() чаще используется в отладочных целях для вывода состояния элемента в потоке, нежели для каких-либо
преобразований.

[К оглавлению](#Lambda)

## 26. Что делают методы skip и limit?

- skip(n) - промежуточная операция, пропускает первые n элементов с начала потока. То есть задает начальную границу
  диапазона перебираемых элементов. Параметром нельзя задать отрицательное число, а если заданное значение параметра
  равно или превышает число элементов в исходной структуре данных, то будет возвращен пустой поток.
- limit(n) - промежуточная операция, возвращает новый поток, содержащий только первые n элементов из исходного потока,
  то есть задает конечную границу диапазона перебираемых элементов. Нельзя задать отрицательное значение параметра. Этот
  метод перебирает элементы, пока не накопит указанное количество элементов, после чего завершает перебор исходной
  структуры данных и возвращает новый поток из собранных элементов.

[К оглавлению](#Lambda)

## 27. Что делают методы allMatch(), noneMatch() и anyMatch()?

Это методы проверки элементов на соответствие заданному условию. Все эти методы принимают Predicate в качестве
параметра (условия для проверки). Также все 3 метода являются конечными (терминальными).

- noneMatch() - возвращает true, если ни один из элементов потока не удовлетворяет условию.
- anyMatch() - возвращает true, если как минимум один из элементов потока удовлетворяет условию.
- allMatch() - возвращает true, если все элементы потока удовлетворяют условию.

[К оглавлению](#Lambda)

## 28. Что делают методы mapToInt(), flatMapToInt(), mapToObj()?

Это методы преобразования потока объектов в поток примитивов и преобразования потока примитивов обратно в поток
объектов.

- mapToInt() - преобразовывает поток объектов в поток примитивных чисел типа int. Является промежуточной операцией.
  Применяется, если исходящий поток состоит из элементов-объектов, а в результате их обработки будет получен примитивный
  тип int. Метод mapToInt возвращает объект интерфейса IntStream (числовой поток), который в дальнейшем обрабатывается
  как поток примитивных чисел. Класс Stream помимо метода mapToInt() также имеет аналогичные ему методы mapToDouble() и
  mapToLong(), работающие с Double и Long типами соответственно.
- flatMapToInt() - трансформирует поток массивов в поток примитивных чисел int. flatMapToInt() последовательно запускает
  поток из каждого массива исходящего потока, в результате чего все элементы этих массивов объединяются в один общий
  поток примитивных чисел int.
- mapToObj() - преобразует поток примитивных чисел в поток объектов. Является промежуточной операцией.

[К оглавлению](#Lambda)

## 29. Что такое числовой поток?

Поток примитивных типов данных. Для работы с числовым потоком реализуем интерфейс IntStream

[К оглавлению](#Lambda)

## 30. Чем отличается Stream<Integer> от IntStream<int>?

- Stream<Integer> - это поток объектов типа Integer. Он используется для обработки коллекций объектов Integer.
- IntStream<int> - это поток целых чисел. Он используется для работы с коллекциями целых чисел.

[К оглавлению](#Lambda)

## 31. Что делает метод boxed?

Метод оборачивает элементы примитивных типов в тип Integer, после чего собирает их в коллекцию.

[К оглавлению](#Lambda)

## 32. Возможно ли прервать выполнение потока по аналогии с break?

С помощью метода .takeWhile() - позволяет получать поток данных до тех пор, пока условие истина.

[К оглавлению](#Lambda)

## 33. Возможно ли пропустить элемент потока по аналогии с continue?

Можно использовать filter - промежуточная операция, фильтрует элементы по условию или return.

```java
    public static void main(String[]args){
        ArrayList<String> stringList=new ArrayList<>();
        stringList.add("a");
        stringList.add("b");
        stringList.add("c");
        stringList.stream().forEach(str->{
        if(str.equals("b"))return; // only skips this iteration.
        System.out.println(str); // a c
        });
        }
```

[К оглавлению](#Lambda)

## 34. Что такое Optional?

Опциональное значение Optional – это контейнер для объекта, который может содержать
или не содержать значение null. Такая обертка является удобным средством
предотвращения NullPointerException, т. к. имеет некоторые функции высшего порядка,
избавляющие от добавления повторяющихся проверок if null/notNull.

[К оглавлению](#Lambda)

## 35. Перечислите методы Optional.

- Optional.empty() - возвращает Optional с null внутри.
- Optional.of(T value) - возвращает Optional с not null значением внутри.
- Optional.ofNullable(T value) - возвращает Optional который может содержать null значение внутри.

Методы конкретного объекта Optional:

- filter(Predicate<? super T> predicate) - дает возможность отфильтровать значение опционального типа. Мы передаем ему в
  параметр Predicat (это стандартный функциональный интерфейс), он возвращает булево значение. Если значение true, то
  возвращается этот же option, если значение false, то возвращается пустой option Optional.empty().
- flatMap() применяется для изменения значения установленного в option. Функция,
  которая передается в метод flatMap должна возвращать option. Если значение не установлено, вернется Optional.empty().
- get() - возвращает значение из объекта Optional. Нужно аккуратно использовать этот метод, т.к. он может бросить
  исключение NoSuchElementException, если значение в option равно null. Чтобы безопасно использовать этот метод, перед
  его
  вызовом надо вызвать метод isPresent().
- isPresent() - возвращает булево значение true, если в option значение есть и возвращает false, если в option
  значение null.
- orElse(T other) - используется для того, чтобы установить значение по-умолчанию в том случае, если значение в option
  отсутствует.
- orElseGet(Supplier<? extends T> other) - это аналог метода orElse, только принимает в себя функциональный интерфейс,
  который должен вернуть значение.
- orElseThrow(Supplier<? extends X> exceptionSupplier) - используется для того, чтобы бросить исключение, которое
  передается в метод orElseThrow, если значения в option не установлено.
- ifPresent(Consumer<? super T> consumer) - исполняет функциональный интерфейс Consumer, если значение в option
  присутствует. Т.е. в ifPresent передается функция, которая принимает один параметр - значение из Optional.

[К оглавлению](#Lambda)

## 36. Расскажите про фабричные методы List.of, Set.of, Map.of?

Методы получения списка из набора элементов. .of() возвращает коллекцию, которую можно прочитать, но нельзя изменять или
добавлять элементы.

[К оглавлению](#Lambda)

## 37. Для чего используется var?

var - это ограниченный идентификатор, который упрощает создание переменных. Стоит подчеркнуть важную особенность - var не является ключевым словом согласно спецификации языка. Соответственно var можно использовать в качестве имени переменной. var может использоваться только в сочетании с данными, var можно использовать в циклах.

Нельзя использовать var без самого значения, потому что JDK нужно знать тип переменной, а тип можно извлечь только из значения.

[К оглавлению](#Lambda)

## 38. В каких случаях можно использовать var?

Var может использоваться только в сочетании с данными, т.е. нужно обязательно инициализировать переменную. Компилятору
нужно знать тип переменной, а тип можно извлечь только из значения.

[К оглавлению](#Lambda)



