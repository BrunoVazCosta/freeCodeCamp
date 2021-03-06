---
title: Erlang
localeTitle: Erlang
---
## Erlang

Erlang - это функциональный язык программирования, разработанный Ericsson для использования в телекоммуникационных приложениях. Поскольку они чувствовали, что для телекоммуникационной системы неприемлемо иметь какое-либо существенное время простоя, Эрланг был построен, среди прочего:

*   распределенной и отказоустойчивой _(часть неисправного программного обеспечения или аппаратного обеспечения не должна приводить систему к работе)_
*   _(он может генерировать множество процессов, каждый из которых выполняет небольшую и четко определенную часть работы и изолируется друг от друга, но может общаться через обмен сообщениями)_
*   с возможностью горячей замены _(код можно поменять местами в системе во время работы, что приведет к высокой доступности и минимальному простому простоя системы)_

### Синтаксис

Эрланг сильно использует **рекурсию** . Поскольку данные в Erlang неизменяемы, использование `while` и `for` циклов (где переменная должно продолжать изменять свое значение) недопустимо.

Ниже приведен пример рекурсии, показывающий, как функция повторно накладывает первую букву с начала имени и печатает ее, только останавливаясь при обнаружении последней буквы.

```erlang
-module(name). 
 
 -export([print_name/1]). 
 
 print_name([RemainingLetter | []]) -> 
  io:format("~c~n", [RemainingLetter]); 
 print_name([FirstLetter | RestOfName]) -> 
  io:format("~c~n", [FirstLetter]), 
  print_name(RestOfName). 
```

Вывод:
```
> name:print_name("Mike"). 
 M 
 i 
 k 
 e 
 ok 
```

Также большое внимание уделяется **сопоставлению шаблонов** , что часто устраняет необходимость в структуре `if` или `case` . В следующем примере есть два соответствия для конкретных имен, за которыми следует catch-all для любых других имен.

```erlang
-module(greeting). 
 
 -export([say_hello/1]). 
 
 say_hello("Mary") -> 
  "Welcome back Mary!"; 
 say_hello("Tom") -> 
  "Howdy Tom."; 
 say_hello(Name) -> 
  "Hello " ++ Name ++ ".". 
```

Вывод:
```
> greeting:say_hello("Mary"). 
 "Welcome back Mary!" 
 > greeting:say_hello("Tom"). 
 "Howdy Tom." 
 > greeting:say_hello("Beth"). 
 "Hello Beth." 
```

### Попробуйте

Существуют веб-сайты, на которых вы можете попробовать запустить команды Erlang без необходимости устанавливать что-либо локально, например:

*   [Попробуй! (практический учебник)](http://www.tryerlang.org/)
*   [TutorialsPoint CodingGround](https://www.tutorialspoint.com/compile_erlang_online.php)

Если вы хотите установить его на свою (или виртуальную) машину, вы можете найти установочные файлы на [Erlang.org](https://www.erlang.org/downloads) или в [Erlang Solutions](https://www.erlang-solutions.com/resources/download.html) .

#### Дополнительная информация:

*   [Информация о Эрланге](https://www.erlang.org/about)
*   [Узнай, что у тебя есть Эрланг!](http://learnyousomeerlang.com/)
*   [Порожденный укрытие!](http://spawnedshelter.com/) _(сборник статей, видеороликов и книг для изучения Эрланг)_
*   [Эрланг (язык программирования)](https://en.wikipedia.org/wiki/Erlang_(programming_language))