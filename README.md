# Домашнее задание к занятию "`SQL. Часть 1`" - `Попов Александр`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---


### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

#### ОТВЕТ:
```
SELECT DISTINCT district
FROM address
WHERE district LIKE 'K%a' AND district NOT LIKE '% %';

```
![з1](https://github.com/user-attachments/assets/cf838479-a7d7-406a-b6a0-54bf29b9079f)


### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

#### ОТВЕТ:
```
SELECT amount, payment_date
FROM payment
WHERE CAST(payment_date AS DATE) BETWEEN 20050614 AND 20050618 AND amount > 10.00;

```
![з2](https://github.com/user-attachments/assets/0e99a507-41ff-41b6-a3d3-18658c6ee6c0)



### Задание 3

Получите последние пять аренд фильмов.

#### ОТВЕТ:
```
SELECT *
FROM rental
ORDER BY rental_id DESC
LIMIT 5;

```
![з3](https://github.com/user-attachments/assets/160d0c65-bd34-45e3-9e72-ff15f9a6f4c6)


### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

#### ОТВЕТ:
```
SELECT LOWER(REPLACE(first_name, 'LL', 'PP')) AS Имя, LOWER(last_name) AS Фамилия
FROM customer
WHERE active = 1 AND (first_name LIKE 'Kelly' OR first_name LIKE 'Willie');

```
![з4](https://github.com/user-attachments/assets/5ac32297-d8cf-4638-8e68-df36b8d41c2b)


## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.
