---
Всем привет это мои практики написания красивого и легко читаемого javascript кода.

---

# h1 Хорошие практики написания javascript кода

## Фигурные скобки:
Плохой код:

    if (n < 0) {alert(`Степень ${n} не поддерживается`);}
    //или
    if (n < 0)
      alert(`Степень ${n} не поддерживается`);

Хороший код:

    if (n < 0) alert(`Степень ${n} не поддерживается`);
    или
    if (n < 0) {
      alert(`Степень ${n} не поддерживается`);
    }

## Длина строки:
Плохой код:

    Это очень длинная строка без переносов и никто не в здравом уме не захочет ее читать, так как весь текст не помещается на один экран и надо листать вправо, а потом возвращаться обратно.

Хороший код:

    Это очень длинная строка, но уже с переносами,
    ее очень удобно читать, так как весь текст на
    одном экране друг под другом.

## Горизонтальные отступы слева:
Плохой код:

    show (parameters,
    aligned,
    one,
    after,
    another
    ) {
    // ...
    }

Хороший код:

    show (parameters,
      aligned,
      one,
      after,
      another
      ) {
        // ...
      }

## Вертикальные отступы:
Плохой код:

    function1 (par1, par2){
       // some code
    }
    function2 (par1, par2){  
      // some code
    }
    function3 (par1, par2){
      // some code
    }

Хороший код:

    function1 (par1, par2){
      // some code
    }

    function2 (par1, par2){
      // some code
    }

    function3 (par1, par2){
      // some code
    }

## Горизонтальные пробелы в строке:
Плохой код:

    function1(arg1,arg2)if(i<2&&n==0)return 0;

Хороший код:

    function1 (arg1, arg2) if (i < 2 && n == 0) return 0;

## Размещение функции:
Плохой код:

    // объявление функций
    function createElement() {
      ...
    }

    function setHandler(elem) {
      ...
    }

    function walkAround() {
      ...
    }

    // код, который использует их
    let elem = createElement();
    setHandler(elem);
    walkAround(); 

Хороший код:

    // код, использующий функции
    let elem = createElement();
    setHandler(elem);
    walkAround();

    // --- вспомогательные функции ---
    function createElement() {
      ...
    }
    
    function setHandler(elem) {
      ...
    }

    function walkAround() {
      ...
    }

## Вложенность и использование break, continue, return или throw:
Плохой код:

    if (!client_agree())  {
        ...
    } else {
        find_defects();

        if (defects_found()) {
            ...
        }

        create_request();
        take_money();
        bye();
    }

Хороший код:

    if (!client_agree())  {
        ...
        return;
    } 

    find_defects();

    if (defects_found()) {
        ...
    }

    create_request();
    take_money();
    bye();

## Дробление сложных функций на отдельные функции:
Плохой код:

    do_a()
    if (check) {
        something();
    } else {
        anything();
        if (whatever()) {
            for (a in b) {
                if (good(a)) {
                    something();
                }
            }
        }
    }

Хороший код:

    procedure do_on_whatever() {
        for (a in b) {
            if (good(a)) {
                something();
            }
        }
    }

    do_a();
    if (check) {
        something();
    } else {
        anything();
        if (whatever()) {
            do_on_whatever();
        }
    }

## Объединяем вложенные if-ы:
Плохой код:

    if (a) {
        if (b) {
            do_something();
        }
    }


Хороший код:

    if (a && b) {
        do_something();
    }

## Используем тернарный оператор (a? b: c) вместо if:
Плохой код:

    if (a) {
        var1 = b;
    } else {
        var1 = c;
    } 


Хороший код:

    var1 = a ? b : c;
