# Описание разметки файла README.md
Для описания проектов на GitHub используется README.md, который пишется на языке разметки markdown. Что и как поддерживается расписано ниже. Также существует еще один формат - [reStructuredText](https://github.com/GnuriaN/format-README/blob/master/README.rst), описание которого вынесено в отдельный файл `README.rst`.
____
## Using эмодзи    
:white_check_mark: Это уже сделано    
:negative_squared_cross_mark: Я не буду это делать    
:black_square_button: делать или не делать, вот в чем вопрос?    
В оригинале это выглядит так (в конце строки четыре (4) пробела для того, что бы был переход на новую строку):
```
:white_check_mark: Это уже сделано    
:negative_squared_cross_mark: Я не буду это делать    
:black_square_button: делать или не делать, вот в чем вопрос?    
```

Список работающих Эмодзи находится тут -> [emoji.md](https://github.com/GnuriaN/format-README.md/blob/master/emoji.md)    
    
[:arrow_up:Оглавление](#Оглавление)
___
## Использование цитирования in text
```
> Цитата (уровень 1)    
> > Вложенная цитата (уровень 2)    
> > > Вложенная цитата (уровень 3) jkdfjkkjbv   

> > Продолжение цитаты (уровень 2)   vdrvev 

> Продолжение цитаты (уровень 1)    
```vdvfvd
> Цитата (уровень 1)    
> > Вложенная цитата (уровень 2)    
> > > Вложенная цитата (уровень 3)    

> > Продолжение цитаты (уровень 2)    

> Продолжение цитаты (уровень 1)    

Внешний вид, конечно, не очень, но может и пригодиться.

[:arrow_up:Оглавление](#Оглавление)
___
## Подсветка code

Если нужно выделить слово или фразу внутри строки, то используются одинарные обратные кавычки (`):

    Это `слово` будет выделено

Для выделения в блоки - тройные:

    ```
        Здесь может быть
        Ваша реклама
    ```

Дополнительно можно задавать язык кода внутри блока, указав его после первых трех кавычек:

    ```html
        <input type="text">
    ```

    ```css
        body {
            margin: 0;
            padding: 0;
        }
    ```

    ```php
        <?php phpinfo();?>
    ```

Пример блока для `C#`:

```C#
using MarkdownSharp;
using MarkdownSharp.Extensions.Mal;

Markdown mark = new Markdown();

// Short link for MAL - 
// http://myanimelist.net/people/413/Kitamura_Eri => mal://Kitamura_Eri
mark.AddExtension(new Articles()); 
mark.AddExtension(new Profile());

mark.Transform(text);
```

Пример блока для `Python`:
```Python
from timeit import Timer

tmp = "Python 3.2.2 (default, Jun 12 2011, 15:08:59) [MSC v.1500 32 bit (Intel)] on win32."

def case1(): # А. инкрементальные конкатенации в цикле
    s = ""
    for i in range(10000):
        s += tmp

def case2(): # Б. через промежуточный список и метод join
    s = []
    for i in range(10000):
        s.append(tmp)
    s = "".join(s)

def case3(): # В. списковое выражение и метод join
    return "".join([tmp for i in range(10000)])

def case4(): # Г. генераторное выражение и метод join
    return "".join(tmp for i in range(10000))

for v in range(1,5):
    print (Timer("func()","from __main__ import case%s as func" % v).timeit(200))
```
    
[:arrow_up:Оглавление](#Оглавление)
___
