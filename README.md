# CodeWarsKatasSQL

Minhas soluções para os Katas (exercícios) de SQL do <a href="https://www.codewars.com">CodeWars</a> desde 17 de Fevereiro de 2022, quando passei a usar a plataforma para praticar SQL Server.

<img src="https://www.codewars.com/users/matheusguifer/badges/large" alt="Profile badge" data-canonical-src="https://www.codewars.com/users/matheusguifer/badges/large" style="max-width: 100%;">

# Sobre o Codewars

Codewars é uma plataforma que te ajuda a aprender, treinar e melhorar suas habilidades de código resolvendo exercícios (chamados de Katas) de programação de vários tipos e níveis de dificuldade. Você escolhe como quer aprender. Quer resolver exercícios cada vez mais desafiadores? Ou prefere treinar através de repetição e melhorando suas soluções? Depois de resolver um Kata, você pode comparar sua solução com a de outros usuários e, com isso, aprender com elas ou ensinar usuários menos experientes respondendo as dúvidas deles.

# Sistema de níveis

Ranks são usados para indicar a proficiência de usuários e dificuldades dos Katas. Existem duas classes de ranks, Kyu e dan, que são divididos em 8 níveis cada. Em ordem de proficiência/dificuldade:

    8 Kyu até 1 Kyu
    1 Dan até 8 Dan

Por que os nomes Kyu and Dan? São termos emprestados do sistema de artes marciais japonesas, que por sua vez são emprestadas do jogo Go. Kyu (or Kyū) indica o número de graus até o nível mestre (Dan). É por isso que são contados de forma descrescente. Ao alcaçar o nível mestre, passamos a contar de forma crescente. Faixas pretas nas artes marciais são nível Dan.

<img src="https://camo.githubusercontent.com/5f28e2e61b2abbc1144a892d684a6b87e58f5b10526170cf7496012a3dbe08bb/68747470733a2f2f692e696d6775722e636f6d2f566d3737584d762e706e67" alt="CodeWars Leveling System">

# Minhas soluções

## 6 Kyu


#### [SQL Basics: Simple UNION ALL](https://www.codewars.com/kata/58112f8004adbbdb500004fe/solutions/sql)

```
SELECT 
  'US' as location,
  *  
FROM ussales
WHERE price > 50.00
UNION ALL
SELECT 
  'EU' as location,
  *  
FROM eusales
WHERE price > 50.00
ORDER BY location DESC, id;
```

##### [SQL Basics: Simple HAVING](https://www.codewars.com/kata/58164ddf890632ce00000220/train/sql)

```
SELECT 
  age,
  COUNT(name) AS total_people
FROM people
GROUP BY age
HAVING COUNT(id) >= 10; /* nao pode usar o alias total_people porque o SELECT é processado depois do HAVING */
```


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

##### [Sum of odd numbers](https://www.codewars.com/kata/55fd2d567d94ac3bc9000064/train/sql)

```
SELECT   
 CAST(n^3 AS int) AS res
FROM nums;
```
##### [SQL Bug Fixing: Fix the QUERY - Totaling](https://www.codewars.com/kata/582cba7d3be8ce3a8300007c/train/sql)

```
SELECT 
  CAST(s.transaction_date as date) as day,
  d.name AS department,
  COUNT(s.id) AS sale_count
FROM department AS d /* esse AS não faz diferença, só torna mais legível */
LEFT JOIN sale AS s 
  ON d.id = s.department_id
GROUP BY 
  day,
  department
ORDER BY day ASC, department ASC, sale_count DESC;
```

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

##### [Easy SQL: ASCII Converter](https://www.codewars.com/kata/594804a218e96caa8d00051b/train/sql)

```
SELECT 
  id,
  ASCII(name) AS name,
  birthday,
  ASCII(race) AS race
FROM demographics;
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



