---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Python】FizzBuzz問題の解答例'
pubDate: 2023-05-20
description: 'FizzBuzz問題の(個人的に好きな)解答例です。'
author: '玖堂いのは'
tags: ["Python"]
---

# 【Python】FizzBuzz問題の解答例
FizzBuzz問題の(個人的に好きな)解答例です。

fizzbuzz.py
```
def fizzbuzz(num: int) -> str:
    result = ''
    if num % 3 == 0:
        result += 'Fizz'
    if num % 5 == 0:
        result += 'Buzz'
    if result == '':
        result += str(num)
    return result


if __name__ == '__main__':
    for i in range(1, 101):
        print(fizzbuzz(i))
```

test_fizzbuzz.py
```
import unittest
from fizzbuzz import fizzbuzz


class FizzBuzzTest(unittest.TestCase):
    def test_number(self):
        self.assertEqual('1', fizzbuzz(1))

    def test_fizz(self):
        self.assertEqual('Fizz', fizzbuzz(3))

    def test_buzz(self):
        self.assertEqual('Buzz', fizzbuzz(5))

    def test_fizzbuzz(self):
        self.assertEqual('FizzBuzz', fizzbuzz(15))


if __name__ == '__main__':
    unittest.main()
```
