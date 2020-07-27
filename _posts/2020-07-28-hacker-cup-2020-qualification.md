---
title: Hacker Cup 2020 รอบคัดเลือก
tags:
  - Competitive Programming
  - Facebook Hacker Cup
  - Python
date: 2020-07-28 01:37:47 +0700
---

ปีนี้วุ่นจัดๆ งานเข้าแทบวันเว้นวันแถมมีปัญหาสุขภาพจนไม่มีเวลาเล่น Code Jam ที่เล่นประจำ เอาจริงๆ ตอนนี้ก็ไม่ได้คิดว่าจะเปลี่ยนมาเล่น Hacker Cup แทนหรอก แต่อยู่ๆ [@ipats][] ก็เดินมาบอกว่าเล่นมั้ยเหลือเวลาอีกแค่ 2 ชั่วโมง ... ก็เลยเอาซักหน่อยดีกว่า

สรุปว่าทำทันแค่ 2 ข้อแรก ส่วนข้อที่ 3 นี่ถ้าโค้ดเร็วกว่านี้อีกนิดเดียวก็จะได้คะแนนเพิ่ม (และตอนนี้ง่วงนอนแล้วคิดว่าคงไม่อยู่ลองทำอีกข้อ) โดยรวมก็สนุกดีนะ เหมือนได้กลับมารู้สึกมีชีวิตชีวาหน่อยนึง 🙂

---

## Travel Restrictions

ตอนแรกอ่านโจทย์ผิด เข้าใจว่าเป็นกราฟที่แต่ละเมืองสามารถบินไปยังเมืองใดๆ ก็ได้ เสียเวลาเขียนโค้ดเวอร์ชันกราฟไปมากโข เพื่อที่จะเห็นว่าแค่เขียนเป็น $O(n^2)$ ก็ออกแล้วนี่หน่า 😓

``` python
def flight_table(n, incoming, outgoing):
    table = [[i == j for i in range(n)] for j in range(n)]
    for i in range(n):
        for j in range(i+1, n):
            if outgoing[j-1] == 'N' or incoming[j] == 'N':
                break
            table[i][j] = True
        for j in reversed(range(i)):
            if outgoing[j+1] == 'N' or incoming[j] == 'N':
                break
            table[i][j] = True
    return table

for c in range(int(input())):
    print(f'Case #{c+1}:')
    for line in flight_table(int(input()), input().strip(), input().strip()):
        print(''.join('NY'[x] for x in line))
```

---

## Alchemy

อ่านโจทย์เสร็จคิดว่าน่าจะยากมากๆ ก็เลยลองคิดย้อนหลังดูโดยเริ่มจากผลลัพธ์ที่เหลือหินชิ้นเดียวแล้วพยายามสร้างข้อมูลเริ่มต้นใดๆ ซึ่งจะสังเกตได้ว่าตอนควบรวมเศษหินเข้าด้วยกันนั้น เศษหินชิ้นที่หายกลายเป็นพลังงาน จะเป็นหินสีดำกับสีน้ำตาลอย่างละหนึ่งก้อนเสมอไม่ว่าผลลัพธ์คือหินสีใด ถึงตอนนี้เริ่มอ๋อแล้วก็พยายามจะ[พิสูจน์นิรนัย][math induction]กับทุกเคส แต่ก็ทำไม่ออกเลยใช้ความเชื่อมั่นว่ามันน่าจะถูกแล้วเขียนโค้ดตอบไปเลย

``` python
from collections import Counter

def fusable(shards):
    c = Counter(shards)
    return abs(c['A'] - c['B']) == 1

for c in range(int(input())):
    input()
    shards = input().strip()
    print(f'Case #{c+1}: {"NY"[fusable(shards)]}')
```

---

## Timber

เคยเจอโจทย์แบบนี้มาประมาณนึงแล้ว รู้ตัวทันที่ว่าต้องใช้[กำหนดการพลวัต][dynamic programming]แน่ๆ แต่เสียเวลาหาวิธีตบให้มันลงล็อกโจทย์นานไปหน่อย แถมพอค่อนข้างมั่นใจว่าคำตอบถูกแล้วก็เหลือเวลาอีกแค่ 5 นาทีเท่านั้น ลงมือเขียนโค้ดเสร็จก็หมดเวลาแข่งขันไปแล้ว 10 นาที แอบเสียดายมากๆ 😭

``` python
def longest_interval(logs):
    logs.sort()
    seq = {}
    for pos, height in logs:
        for start, stop in [(pos, pos+height), (pos-height, pos)]:
            if start not in seq:
                seq[start] = 0
            if stop not in seq:
                seq[stop] = seq[start] + height
            else:
                seq[stop] = max(seq[stop], seq[start] + height)
    return max(seq.values())

for c in range(int(input())):
    logs = [[int(n) for n in input().split()] for _ in range(int(input()))]
    print(f'Case #{c+1}: {longest_interval(logs)}')
```

---

ไว้เคลียร์งานเคลียร์ปัญหาชีวิตเสร็จเมื่อไหร่ หวังว่าจะมีโอกาสได้กลับมาแข่งเขียนโปรแกรมแบบมีคุณภาพมากกว่านี้



[@ipats]: //twitter.com/ipats



[math induction]: //en.wikipedia.org/wiki/Mathematical_induction
[dynamic programming]: //en.wikipedia.org/wiki/Dynamic_programming
