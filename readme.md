Задание 1
3.99

Задание 2
26.8

Задание 3
63;97

Задание 4
```
def is_isomorphic(s, t):
    if len(s) != len(t):
        return False

    s_to_t = {}
    t_to_s = {}

    for a, b in zip(s, t):
        if a in s_to_t and s_to_t[a] != b:
            return False

        if b in t_to_s and t_to_s[b] != a:
            return False

        s_to_t[a] = b
        t_to_s[b] = a

    return True
```

Время: O(n), n - длина строки
Память: O(k), где k — количество разных символов в строках

Задание 5
```
def missing_number(nums):
    n = len(nums) + 1

    expected_sum = n * (n + 1) // 2
    real_sum = sum(nums)

    return expected_sum - real_sum
```
Время: O(n)
Память: O(1)

Задание 6
```
def prime_factors(n):
    factors = []

    d = 2
    while d * d <= n:
        while n % d == 0:
            factors.append(d)
            n //= d
        d += 1

    if n > 1:
        factors.append(n)

    return factors
```
Время: O(sqrt(n))
Память: O(k), где k — количество простых множителей в ответе

Задание 7
```
SELECT
    id,
    scores,
    RANK() OVER (ORDER BY scores DESC) AS rating_position
FROM examination;
```

Задание 8
минимально 30 и максимально 600 строк

Задание 9
```
SELECT
    a.client_id
FROM account a
JOIN "transaction" t
    ON t.account_id = a.id
WHERE t.transaction_date >= CURRENT_DATE - INTERVAL '1 month'
  AND t.type = 'BUY'
GROUP BY a.client_id
HAVING SUM(t.amount) < 5000;
```

Задание 10
234

Задание 11
2 Вероятность наблюдения такого или более экстремального результата при
условии, что нулевая гипотеза верна.

Задание 12
да

Задание 13
Я бы взял вторую модель с ROC-AUC = 0.1, потому что для бинарной классификации это почти идеальная модель, которая просто перепутала классы местами. Если она уверенно отличает лошадок от пони, но ставит высокие вероятности неправильному классу, то достаточно инвертировать её предсказания.

Задание 14
Положительных объектов: 7
Отрицательных объектов: 8
Всего пар positive-negative: 7 * 8 = 56
0.95: выше всех 8 отрицательных → 8
0.85: выше 7 отрицательных → 7
0.75: выше 6 отрицательных → 6
0.70: выше 6 отрицательных → 6
0.65: выше 6 отрицательных → 6
0.60: выше 6 отрицательных → 6
0.40: выше 3 отрицательных → 3
Правильных пар: 42
ROC/AUC=42/56 = 0.75
Ответ: 0.75

Задание 15
-0.85
Это сильная отрицательная линейная связь: в этих данных чем больше чашек кофе выпито, тем ниже итоговый балл за экзамен.
