Wirth-A-DS
==========

Assignments from the book "Algorithms and Data Structures", performed on the Component Pascal (BlackBox Component Builder)
59 / 274 pages
0 / 7 issues

1.1. Обозначим мощности стандартных типов INTEGER, REAL и CHAR как Cint, Creal и Cchar. Каковы мощности следующих типов даных, определенных в этой главе в качестве примеров: Complex, Date, Person, Row, Card, Name?
1.2. Какие последовательности машинных инструкций соответсвуют следующим операциям:
а) чтение и запись для элементов упакованных записей и массивов;
б) операции для множеств, включая проверку принадлежности числа множеству?
1.3. Каковы могут быть аргументы в пользу определения некоторых наборов данных в виде последовательностей, а не массивов?
1.4. Пусть дано ежедневное железнодорожное расписание для поездов на нескольких линиях. Найдите такое представление данных в виде массивов, записей или последовательностей, которое было бы удобно для определения времени прибытия и отправления для заданных станций и направления поезда.
1.5. Пусть даны текст Т, представленный последовательностью, а также списки небольшого числа слов в виде двух массивов A и B. Предположим, что слова являются короткими массивами литер небольшой фиксированной максимальной длины. Напишите программу, преобразующую текст T в текст S заменой каждого вхождения слова Ai соответсвующим словом Bi.
1.6. Сравните следующие три варианта поиска делением пополам с тем, который был дан в основном тексте. Какие из трех программ правильны? Определите соответствующие инварианты. Какие варианты более эффективны? Предполагается, что определены константа N>0 и следующие переменные:
VAR i, j, k, x: INTEGER;
a: ARRAY OF INTEGER;

Программа A:
	i := 0; j := N - 1;
	REPEAT
		k:=(i + j) DIV 2;
		IF a[k] < x THEN i := k ELSE j := k END
	UNTIL (a[k] = x) OR (i > j)

Программа B:
	i := 0; j := N - 1;
	REPEAT
		k:=(i + j) DIV 2;
		IF x < a[k] THEN j := k - 1 END:
		IF a[k] < x THEN i := k + 1 END:
	UNTIL i > j

Программа C:
	i := 0; j := N - 1;
	REPEAT
		k:=(i + j) DIV 2;
		IF x < a[k] THEN j := k ELSE i := k + 1 END
	UNTIL i > j

Подсказка: Все программы должны заканчиваться с ak = x, если такой  элемент присутствует, или ak <> x, если элемента со значением x нет.
1.7. Некая кампания проводит опрос, чтобы определить, насколько популярна ее продукция - записи эстрадных песен, а самые популярные песни должны быть объявлены в хит-параде. Опрашиваемую выборку покупателей нужно разделить на 4 группы в соответствии с полом и возрастом (не старше 20 / старше 20). Каждого покупателя просят назвать пять любимых песен. Песни нумеруются числами от 1 до N (=30). Результаты опроса нужно подходящим образом закодировать в виде последовательности литер.
Подсказка: Использовать процедуры Read и ReadInt для чтения данных опроса.
	TYPE hit = INTEGER;
		response = RECORD name, firstname: Name;
		male: boolean;
		age: integer;
		choice: ARRAY 5 OF hit
	END;

	VAR poll: Files.File

Этот файл содержит входные данные для программы, вычисляющей следующие результаты:
 - 1) Список A песен в порядке популярности. Каждая запись списка состоит из номера песни и количества ее упоминаний в опросе. Ни разу не названные песни в список не включаются.
 - 2) Четыре разных списка с фамилиями и именами всех респондентов, которые поставили на первое место один из трех самых популярных хитов в своей группе.
Перед каждым из пяти списков должен идти подходящий заголовок.