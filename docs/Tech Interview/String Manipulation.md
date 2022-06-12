---
layout: page
title: String Manipulation
parent: Algorithm
grand_parent: Tech Interview
permalink: /tech-interview/algorithm/string-manipulation
---

## Algorithm

### String Manipulation
문자열 조작
{: .fs-3 .pt-2 .pb-1 }

- `문자열 조작`이란 문자열을 변경하거나 분리하는 등 여러 과정을 의미
- 코딩 테스트에서 매우 빈번하게 출제되는 주제 중 하나이며, 특히 실무에서도 다양한 분야에 쓰이는 실용적인 주제
{: .fs-3 .pt-2 }

---

##### 125. Valid Palindrome [Link](https://leetcode.com/problems/valid-palindrome){:target="_blank"}
유효한 팰린드롬 
{: .fs-2 .pt-2 }

Easy
{: .label .label-green .ml-0 .mt-2}

#### Example

문자열 s가 주어질 때 palindrome이면 true를 반환하고 그렇지 않으면 false를 반환:

```
Input: s = "A man, a plan, a canal: Panama"
Output: true

Input: s = "race a car"
Output: false

```

#### Explanation

- `Palindrome (회문 문자열)`이란 앞뒤가 똑같은 단어나 문장으로, 뒤집어도 같은 말이 되는 단어 or 문장을 의미 ex. 기러기
- 대소문자 여부를 구분하지 않으며 영문자, 숫자만을 대상
- s = " "인 경우 영숫자가 아닌 문자 제거한 후 빈 문자열이 ""가 되므로, 앞뒤가 동일한 회문 문자열이됨


#### Python3

_Solution 1: isalnum() (298 ms)_

- `[isalnum()](https://www.w3schools.com/python/ref_string_isalnum.asp)`은 문자가 알파벳 문자(a-z)와 숫자(0-9)를 의미하는 영숫자이면 True를 반환. 영숫자가 아닌 문자의 예시: (space)!#%&? 등

{% capture code_fence %}
```python
def isPalindrome(self, s: str) -> bool:
    
    letters = []

    for char in s:
        if char.isalnum():
            letters.append(char.lower())
    
    while len(letters) >1:
        if letters.pop(0) != letters.pop()
        return False
    
    return True
```
{% endcapture %}
{% assign code_fence = code_fence | markdownify %}

<Br />

_Solution 2: isalnum() + Slicing (46 ms)_

- `[Slicing](https://www.w3schools.com/python/python_strings_slicing.asp)`을 사용하여 위치를 지정하면 해당 위치의 배열 포인터를 얻게 되며 이를 통해 연결된 객체를 찾아 실제 값을 반환
- 슬라이스 구문을 사용하여 문자를 반환하는 것이 매우 빠르므로 문자열 조작시에는 슬라이싱을 우선으로 사용하는 편이 속도 개선에 유리
- [::-1]을 사용하면 문자를 뒤집을 수 있음

```python
def isPalindrome(self, s: str) -> bool:

     s = [char for char in s.lower() if char.isalnum()]
     return s == s[::-1]
```

---

##### 344. Reverse String [Link](https://leetcode.com/problems/reverse-string){:target="_blank"}
문자열 뒤집기 
{: .fs-2 .pt-2 }

Easy
{: .label .label-green .ml-0 .mt-2}

---