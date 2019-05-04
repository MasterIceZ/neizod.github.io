---
title: Code Jam 2019 รอบคัดเลือกและรอบ 1C
tags:
  - Competitive Programming
  - Google Code Jam
  - Python
  - Haskell
  - C
date: 2019-05-04 20:12:13 +0700
---

ปีนี้เป็นปีที่ยุ่งและเหนื่อยมากๆ เพราะมีงานพิเศษวันเสาร์เพิ่มเติมเข้ามาในชีวิต เลยแทบไม่มีเวลาได้เล่น (และเขียนบล็อก) เลย ตอนรอบคัดเลือกเมื่อเดือนที่ผ่านมานี่แทบจะเททิ้งแล้ว ถ้าไม่เห็นว่า [@lewcpe][] กับ [@jittat][] กำลังสนุกสนานกับมันอยู่ เลยเจียดเวลาเท่าที่มีมาเขียนเล่นโดยไม่ได้หวังเข้ารอบแต่อย่างใด

---

## Foregone Solution

โจทย์ง่ายๆ สุดคลาสสิกที่มองข้อมูลตัวเลขเป็นสายอักขระก็จะได้อัลกอริทึมง่ายๆ แล้ว ... พอเจอโจทย์ง่ายประมาณนึงก็จะพยายามใช้ภาษาอื่นที่ไม่ค่อยมีโอกาสได้ใช้บ่อยๆ ในชีวิตประจำวันมาเขียนกันลืม เช่นข้อนี้เขียนด้วย Haskell

``` haskell
import Text.Printf

getInt :: IO Int
getInt = do
    it <- getLine
    return $ read it

less :: Char -> Char
less c = if c == '4' then pred c else c

more :: Char -> Char
more c = if c == '4' then succ '0' else '0'

splitValue :: String -> (String,String)
splitValue = aux "" "" . reverse
    where aux a b (h:t) = aux ((less h):a) ((more h):b) t
          aux a b ""    = (a,b)

test :: Int -> IO ()
test t = do
    check <- getLine
    let (a,b) = splitValue check
    printf "Case #%i: %s %s\n" t a b

main :: IO ()
main = do
    loop <- getInt
    sequence_ [test t | t <- [1..loop]]
```

---

## You Can Go Your Own Way

ส่วนข้อนี้ก็ยังง่าย แค่สลับไปเดินทิศตรงข้ามกับอีกฝั่งให้หมดก็พอ ... เสียดายที่ใช้ภาษา C แล้วปล่อยเบลอ จองขนาดอาเรย์ขาดไปครึ่งนึง ถถถ

``` c
#include <stdio.h>
int main(void) {
    int testcase;
    scanf("%d", &testcase);
    for (int t=0; t<testcase; t++) {
        int dimension;
        char paths[50020];
        scanf("%d", &dimension);
        scanf("%s", paths);
        printf("Case #%i: ", t+1);
        for (int i=0; i<2*(dimension-1); i++) {
            printf("%c", paths[i] ^ 0x16);
        }
        printf("\n");
    }
    return 0;
}
```

เรื่องตลกก็คือเพื่อนที่จองขนาดอาเรย์ประมาณนี้เหมือนกัน แต่เปลี่ยนไปคอมไพล์ด้วย C++ กลับรันผ่านแฮะ งงใจเวอร์ ถถถถถถถถ

---

## Cryptopangrams

ข้อนี้ทำเอาชะงักไปหลายที เริ่มเลยก็ตรงที่ดันไปคิดว่าต้องแยกตัวประกอบของผลคูณจำนวนเฉพาะขนาดใหญ่สองตัว กว่าจะคิดออกว่าเราสามารถหา $\gcd$ ของเลขที่อยู่ติดกันเพื่อแยกตัวประกอบได้ก็กินเวลาไปเป็นชั่วโมง พอเขียนโค้ดส่งก็เจอ run time error รัวๆ เข้าให้อีก เพราะลืมคิดไปว่าเลขที่อยู่ติดกันอาจมีค่าเท่าก็ได้ (และทำให้ผลลัพธ์ $\gcd$ ไม่ใช่การแยกตัวประกอบ) กว่าจะเจอบั๊กและแก้ให้หา $\gcd$ แค่ครั้งเดียวพอ แล้วค่อยๆ รูดซิปจากจุดนั้นออกแก้หาตัวอักษรทั้งหมดก็เสียเวลาเพิ่มอีกชั่วโมง (ถ้าเป็นรอบอื่นก็เรียกว่าถอดใจข้อนี้ได้เลย)

``` python
from fractions import gcd
from itertools import count

def find_entry(ciphertext, words):
    for index, a, b in zip(count(1), ciphertext, ciphertext[1:]):
        if a != b:
            words[index] = gcd(a, b)
            return index

def recover_words(ciphertext):
    words = [None for _ in range(len(ciphertext)+1)]
    entrance_index = find_entry(ciphertext, words)
    for index in range(entrance_index+1, len(ciphertext)+1):
        words[index] = ciphertext[index-1] // words[index-1]
    for index in reversed(range(entrance_index)):
        words[index] = ciphertext[index] // words[index+1]
    return words

def decipher(ciphertext):
    words = recover_words(ciphertext)
    mapping = dict(zip(sorted(set(words)), 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'))
    return ''.join(mapping[w] for w in words)

for testcase in range(int(input())):
    input()
    ciphertext = [int(n) for n in input().split()]
    print('Case #{}: {}'.format(testcase+1, decipher(ciphertext)))
```

---

## Robot Programming Strategy

ตอนแรกอ่านโจทย์นึกว่าขอให้เจอแค่ 1 วิธีที่จะจับคู่การแข่งขันเพื่อชนะทั้งทัวร์นาเมนต์ก็พอ แต่โจทย์กลับใจดีกว่านั้นคือต้องชนะโดยไม่สนว่าการจับคู่จะเป็นยังไง เลยคิดได้ง่ายๆ โดยไล่ดูว่าที่การเป่ายิงฉุบแต่ละครั้งคู่แข่งทั้งหมดออกครบทั้งกรรไกรค้อนกระดาษหรือไม่ ถ้าออกครบก็แปลว่าเราไม่มีทางชนะทุกคู่แข่งได้แน่ แต่ถ้าออกน้อยกว่านั้นเราสามารถเลือกวิธีเล่นที่จะทำให้ไม่แพ้คู่แข่งทั้งหมดได้

``` python
from operator import and_ as intersect
from functools import reduce

HANDS = {'R': 'RP', 'P': 'PS', 'S': 'SR'}

def eliminated(robots, rnd, hand):
    return [robot for robot in robots if robot[rnd%len(robot)] == hand]

def response(robots, rnd):
    opponents = {robot[rnd%len(robot)] for robot in robots}
    hands = reduce(intersect, (set(HANDS[h]) for h in opponents))
    if not hands:
        return False
    if len(hands) == 2:
        hands -= opponents
    return hands.pop()

def strategy(robots):
    moves = []
    for rnd in range(500):
        hand = response(robots, rnd)
        if not hand:
            break
        moves += [hand]
        robots = eliminated(robots, rnd, hand)
        if not robots:
            return ''.join(moves)
    return 'IMPOSSIBLE'

for testcase in range(int(input())):
    robots = [input().strip() for _ in range(int(input()))]
    print('Case #{}: {}'.format(testcase+1, strategy(robots)))
```

---

สรุปว่าปีนี้จบแค่นี้ แต่ก็ไม่เป็นไรได้พักงานเขียนโค้ดซีเรียสในโลกความจริง มาเขียนโค้ดแก้ปัญหาสนุกๆ หลุดโลกแบบนี้ มันก็เติมพลังชีวิตได้ดีเหมือนกัน 😉


[@lewcpe]: //twitter.com/lewcpe
[@jittat]: //twitter.com/jittat
