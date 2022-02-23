# CodeWarsKatasSQL
My solutions to the SQL katas from <a href="https://www.codewars.com">CodeWars</a>. 
Started in February 17th, 2022 to practice SQL Server.

<img src="https://www.codewars.com/users/matheusguifer/badges/large" alt="Profile badge" data-canonical-src="https://www.codewars.com/users/matheusguifer/badges/large" style="max-width: 100%;">

# About CodeWars

Codewars is a platform that helps you learn, train, and improve your coding skills by solving programming tasks of many types and difficulty levels. You choose how you would like to learn. Do you want to take on increasingly difficult challenges? Maybe you prefer training through repetition and by improving your solutions. After solving a task, compare your answer with other users and learn from them or help less experienced users by answering their questions.

# Leveling system

Ranks are used to indicate the proficiency of users and the difficulty of Kata. There are two classes of ranks, Kyu and Dan, which are divided in 8 levels each. By increasing order of proficiency/difficulty:

    8 Kyu to 1 Kyu
    1 Dan to 8 Dan

Why the names Kyu and Dan? The terms are borrowed from a system in Japanese martial arts, which is in turn borrowed from the game of Go. Kyu (or Kyū) indicates the number of degrees away from master level (Dan). This is why they count downward. Once you reach master level, we count upward. Black belts in martial arts are Dan level.

<img src="https://camo.githubusercontent.com/5f28e2e61b2abbc1144a892d684a6b87e58f5b10526170cf7496012a3dbe08bb/68747470733a2f2f692e696d6775722e636f6d2f566d3737584d762e706e67" alt="CodeWars Leveling System">

# My Solutions

## 6 Kyu

##### [SQL Basics: Top 10 customers by total payments amount](https://www.codewars.com/kata/580d08b5c049aef8f900007c/train/sql)

```
SELECT 
  customer.customer_id, 
  customer.email, 
  COUNT(payment.payment_id) AS payments_count,
  CAST(SUM(payment.amount) AS float) AS total_amount
FROM customer
LEFT JOIN payment
  ON customer.customer_id = payment.customer_id
GROUP BY customer.customer_id
ORDER BY total_amount DESC
LIMIT 10;
```
## 7 Kyu

##### [SQL Basics: Simple JOIN with COUNT](https://www.codewars.com/kata/580918e24a85b05ad000010c/train/sql)

```
SELECT 
  p.id,
  p.name,
  COUNT(t.name) AS toy_count
FROM people AS p
LEFT JOIN toys AS t
  ON p.id = t.people_id
GROUP BY p.id;
```

##### [Easy SQL: Cube Root and Natural Log](https://www.codewars.com/kata/594a6ad320ac16a54400007f)

```
SELECT 
  cbrt(number1)  AS cuberoot, 
  ln(number2) AS logarithm
FROM decimals;
```
##### [Collect Tuition (SQL for Beginners #4)](https://www.codewars.com/kata/5910b0d378cc2ba91400000b)

```
SELECT * FROM students
where tuition_received = false;
```

##### [SQL Basics: Maths with String Manipulations](https://www.codewars.com/kata/594901ba44645fd7bd00005f)

```
SELECT 
  BIT_LENGTH (name) + CHAR_LENGTH(race) 
AS calculation
FROM demographics;
```

##### [SQL Basics - Position](https://www.codewars.com/kata/59401e0e54a655a298000040)

```
SELECT id, name, 
      POSITION(',' IN characteristics) AS comma
FROM monsters  
ORDER BY comma;
```

##### [Best-Selling Books (SQL for Beginners #5)](https://www.codewars.com/kata/591127cbe8b9fb05bd00004b)

```
SELECT * FROM books
ORDER BY copies_sold DESC
LIMIT 5;
```

##### [SQL with Harry Potter: Sorting Hat Comparators](https://www.codewars.com/kata/5abcf0f930488ff1a6000b66)

```
SELECT * FROM students
  WHERE 
    (quality1 = 'evil' AND quality2 = 'cunning')
    OR
    (quality1 = 'brave' AND quality2 != 'evil')
    OR
    (quality1 = 'studious' OR quality2 = 'intelligent')
    OR
    (quality1 = 'hufflepuff' OR quality2 = 'hufflepuff')
ORDER BY id ASC;
```

##### [Hello SQL World!](https://www.codewars.com/kata/581283eb0a5fb13e06000020)

```
CREATE TABLE tabela ("Greeting" VARCHAR PRIMARY KEY);
INSERT INTO tabela VALUES ('hello world!');
SELECT * FROM tabela;
```

## 8 kyu

##### [SQL Basics: Simple DISTINCT](https://www.codewars.com/kata/58111670e10b53be31000108)

```
SELECT DISTINCT age FROM people;
```



