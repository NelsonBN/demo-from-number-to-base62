# Demo - From Number to Base62

Base 62 is a base-62 numeral system. It uses 62 characters. The characters include 0-9, a-z, and A-Z. This system is used to encode URLs, shorten URLs, and more.

* 10 digits: 0-9
* 26 lowercase letters: abcdefghijklmnopqrstuvwxyz
* 26 uppercase letters: ABCDEFGHIJKLMNOPQRSTUVWXYZ

The following is a Python program that converts a number to a base 62 number.

```python
chars = "0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ"

def int_to_base62(num):
    if num == 0:
        return chars[0]

    base62_encoded = ""
    while num > 0:
        remainder = num % 62
        base62_encoded = chars[remainder] + base62_encoded
        num = num // 62

    return base62_encoded

result1 = int_to_base62(0)
result2 = int_to_base62(10)
result3 = int_to_base62(4541240)
result4 = int_to_base62(123456789)

print(result1)
print(result2)
print(result3)
print(result4)
```

Output:
```
0
a
j3nO
8m0Kx
```

The following is a Python program that converts a base 62 number to a number.

```python
def base62_to_int(base62_str):

    num = 0

    for char in base62_str:
        ascii_val = ord(char)
        if 48 <= ascii_val <= 57:
            num = num * 62 + ascii_val - 48
        elif 97 <= ascii_val <= 122:
            num = num * 62 + ascii_val - 87
        else:
            num = num * 62 + ascii_val - 29

    return num

print(base62_to_int(result1))
print(base62_to_int(result2))
print(base62_to_int(result3))
print(base62_to_int(result4))
```

Output:
```
0
10
4541240
123456789
```
