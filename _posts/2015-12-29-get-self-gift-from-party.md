---
title: เจองานจับฉลากแลกของขวัญที่มีคนได้ของตัวเอง ไม่ต้องตกใจไปโอกาสมีสูงเกินครึ่ง
tags:
  - Mathematics
  - Mathematical Proof
  - Python
  - Algorithm
  - Thought
date: 2015-12-29 06:38:00 +0700
---

วันก่อนเห็นเพื่อนแลกของขวัญปีใหม่แล้วดันจับได้ของตัวเองก็ฮาดี มองเผินๆ เหมือนว่าเรื่องแบบนี้จะเกิดขึ้นได้ยาก แต่เท่าที่เคยเล่นแลกของขวัญมา เรื่องประมาณนี้เกิดขึ้นบ่อยกว่าที่คิดนะ เลยลองมานั่งโซ้วสมการความน่าจะเป็นดู ว่าโอกาสที่ในงานเลี้ยงหนึ่งๆ จะมีคนจับของขวัญได้ของตัวเองเป็นเท่าไหร่

แต่ก่อนอื่นต้องเข้าใจกฎการแลกของขวัญ ซึ่งมีขั้นตอนประมาณนี้

- ทุกคนซื้อของขวัญมาร่วมสนุกในงานคนละอย่าง โดยเอาของขวัญใส่กล่องไว้ไม่ให้ใครรู้ว่าด้านในเป็นอะไร
- พอแต่ละคนไปถึงงาน คนจัดงานจะแปะป้ายชื่อเจ้าของของขวัญไว้กับกล่อง พร้อมหย่อนฉลากรายชื่อของคนนั้นลงไห
- เมื่อถึงเวลาแลกของขวัญ ให้ประธานในพิธีหรือใครซักคนที่ใหญ่ที่สุดในงาน เป็นคนเริ่มจับฉลากรายชื่อจากไหเป็นคนแรก
- ประธานจับได้ชื่อใครก็เอากล่องของขวัญของคนนั้นไป แล้วก็ให้คนที่โดนจับชื่อเมื่อกี้ เป็นคนเริ่มจับฉลากในไหวนต่อไปเรื่อยๆ
- ถ้าเกิดมีคนจับได้ชื่อประธาน จะถือว่าเป็นการแลกของขวัญที่ครบรอบวง ก็ให้คนนั้นเอาของขวัญของประธานไป แล้วผู้จัดงานเลือกใครซักคนจากคนที่ยังไม่ได้จับของขวัญ มาเป็นหัวจับของขวัญรอบต่อไป
- การแลกของขวัญจะสิ้นสุดลงเมื่อไม่มีฉลากรายชื่อเหลือในไห

จากกฎนี้เห็นได้ชัดว่า เมื่อถึงตอนใกล้จบการแลกของขวัญที่มีฉลากรายชื่อในไหเหลือแค่ 2 ใบ ใบนึงจะเป็นของคนแรกและอีกใบเป็นของคนที่ยังไม่ได้จับฉลาก ดังนั้นโอกาสที่คนจับก่อนจะจับฉลากได้ชื่อคนแรกและบังคับให้คนสุดท้ายจับชื่อตัวเอง โอกาสนี้จะสูงถึง 50% เลย

ยกตัวอย่างให้ชัดขึ้นไปอีก สมมตินายประธานเป็นคนจับฉลากคนแรก แล้วก็มีคนจับตามๆ กันมาอีกหลายคน จนตอนสุดท้ายเหลือคนที่ยังไม่ได้จับฉลาก 2 คนคือสมศักดิ์กับมานี ถ้าคนก่อนหน้าจับฉลากได้ชื่อสมศักดิ์ แปลว่าสมศักดิ์จะเป็นคนจับฉลากคนต่อไป แต่รายชื่อในไหตอนนี้จะเหลือแค่มานีกับประธานเท่านั้น ที่โอกาสครึ่งๆ ถ้าสมศักดิ์จับได้ชื่อประธาน ก็จะเหลือคนไม่ได้จับฉลากคือมานี และฉลากที่เหลือในไหก็เป็นชื่อมานี นั่นก็คือมานีจะถูกบังคับให้จับฉลากได้ของขวัญของตัวเองแน่นอน

โอกาสที่ในงานแลกของขวัญงานหนึ่งมีคนได้ของขวัญเป็นของตัวเองจะสูงถึง 50% ซึ่งจริงๆ แล้วโอกาสน่าจะมากกว่านี้อีกนิดหน่อยด้วยซ้ำ เพราะยังไม่ได้คิดโอกาสที่คนกลางๆ จะจับได้ของตัวเองทันทีหลังจากเกิดการจับฉลากครบรอบวงเลย

---

คิดได้แค่นี้ก็พอใจแล้ว แต่ก็โดน [@NungNing][] ถามต่อว่า ถ้าไม่จับฉลากกันต่อไปเรื่อยๆ แบบนี้หละ แต่เปลี่ยนเป็นให้ทุกคนหยิบฉลากจากไหพร้อมกันเลย แล้วค่อยเปิดดูทีเดียวว่าใครได้ของขวัญจากใคร ยังจะมีโอกาสสูงอยู่มั้ยที่จะมีคนจับฉลากได้ของขวัญของตัวเอง?

ตอนนั้นหมดพลังแล้ว ให้คิดต่ออย่างเดียวคงไม่ออกแน่ๆ เลยเขียนโปรแกรมง่ายๆ มาดูค่าเอาเลยนั่นแหละ

``` python
#!/usr/bin/env python3
from random import shuffle
from collections import Counter

shuffled = lambda ls: shuffle(ls) or ls
own_gift = lambda n: [i for i, j in enumerate(shuffled(list(range(n)))) if i == j]
```

สมมติให้มีคนแลกของขวัญกัน 10 คน ทดลองไปล้านครั้ง พบว่ามีประมาณสามแสนหกหมื่นครั้งเท่านั้น (36%) ที่การแลกของขวัญนั้นจะไม่มีคนได้ของตัวเอง

ตอนนั้นก็ตกใจว่าเลข 36% มาจากไหน นึกว่าโอกาสไม่ได้ของตัวเองมันจะมีค่าแถวๆ 50% ที่คิดได้จากการแลกของขวัญวนไปเรื่อยๆ ซะอีก นี่กลายเป็นว่าโอกาสไม่ได้ของตัวเองมันยิ่งเหลือน้อย เลยทดลองเพิ่มโดยแยกนับเป็นกรณีเลยว่า ในแต่ละการแลกของขวัญนั้น มีคนกี่คนที่ได้ของขวัญของตัวเอง

ทดลองแลกของขวัญด้วยกลุ่มขนาด 10 คนเป็นจำนวนหนึ่งล้านครั้งเหมือนเดิม แล้วก็ตกใจเพิ่มกับหน้าตาผลลัพธ์ที่ไม่โกหกดังนี้

| จำนวนคนได้ของขวัญของตัวเอง |   ความถี่  |      ข้อคาดการณ์โอกาสการเกิด      |
|:----------------------- | --------:| ------------------------------:|
| 0                       |  368,243 | $ \frac{1}{0!} \times e^{-1} $ |
| 1                       |  367,640 | $ \frac{1}{1!} \times e^{-1} $ |
| 2                       |  183,800 | $ \frac{1}{2!} \times e^{-1} $ |
| 3                       |   61,406 | $ \frac{1}{3!} \times e^{-1} $ |
| 4                       |   15,269 | $ \frac{1}{4!} \times e^{-1} $ |
| 5                       |    3,014 | $ \frac{1}{5!} \times e^{-1} $ |
| 6                       |      545 | $ \frac{1}{6!} \times e^{-1} $ |
| 7                       |       67 | $ \frac{1}{7!} \times e^{-1} $ |
| 8                       |       16 | $ \frac{1}{8!} \times e^{-1} $ |

ถึงตอนนี้ก็พอจะเข้าใจแล้วว่ามันเกิดอะไรขึ้น

---

แม้แค่เห็นข้อมูลข้างบนแล้วจะสรุปได้ว่าเกิดอะไรขึ้น แต่เรื่องที่ยากกว่าก็คือการพิสูจน์หาคำอธิบายเป๊ะๆ ว่าทำไมถึงเป็นอย่างนั้น

เริ่มจากกรณีที่ไม่มีใครจับของขวัญได้ของตัวเองก่อน จะได้ว่า

- คนแรกมีโอกาสจะจับไม่ได้ของตัวเองที่ $\frac{n-1}{n}$
- คนที่สองมีโอกาสที่จะจับไม่ได้ของตัวเอง แบ่งได้ 2 แบบ คือ
  - คนแรกจับได้ของคนที่สองไปแล้วด้วยโอกาส $\frac{1}{n}$ ดังนั้นคนที่สองจับไม่ได้ของตัวเองแน่ๆ ด้วยโอกาส $1$ รวมโอกาสจับไม่ได้ของตัวเองสำหรับกรณีนี้เป็น $\frac{1}{n}$
  - คนแรกจับไม่ได้ของคนที่สองด้วยโอกาส $\frac{n-1}{n}$ คนที่สองต้องจับหลบให้ไม่ได้ของตัวเองซึ่งมีโอกาส $\frac{n-2}{n-1}$ รวมโอกาสของกรณีนี้เป็น $\frac{n-1}{n}\frac{n-2}{n-1}$
  - สรุปว่าโอกาสทั้งหมดที่คนที่สองจะจับไม่ได้ของตัวเองคือ $\frac{1}{n}+\frac{n-1}{n}\frac{n-2}{n-1}$
- โอกาสคนที่สามจะคล้ายๆ กับของคนที่สอง คือ $\frac{2}{n}+\frac{n-2}{n}\frac{n-3}{n-2}$
- คนที่ $i$ มีโอกาส $\frac{i-1}{n}+\frac{n-i-1}{n}\frac{n-i}{n-i-1}$ ที่จะจับไม่ได้ของตัวเอง

เนื่องจากเหตุการณ์ทั้งหมด ต้องเกิดขึ้นพร้อมกัน ดังนั้นสรุปได้ว่า

$$ \begin{align}
    P(\text{n คนไม่มีใครได้ของตัวเอง})
        &= \frac{n-1}{n} \times
           \left( \frac{1}{n}+\frac{n-1}{n}\frac{n-2}{n-1} \right) \times
           \cdots \times
           \left( \frac{i-1}{n}+\frac{n-i-1}{n}\frac{n-i}{n-i-1} \right) \times
           \cdots \times
           \left( \frac{n-1}{n}+\frac{n-n-1}{n}\frac{n-n}{n-n-1} \right) \\
         &= \prod_{i=1}^{n-1} \frac{n-1}{n} \\
         &= \prod_{i=1}^{n-1} 1 - \frac{1}{n} \\
         &= \left( 1 - \frac{1}{n} \right)^{n-1}
\end{align} $$

จากสมการข้างต้น ถ้าลองแทนตัวเลขน้อยๆ เช่น $n=1,2,3,4$ เข้าไป จะได้คำตอบเป็น $1, 0.5, 0.445, 0.422$ ตามลำดับ แต่เมื่อลองแทนเลขมากๆ แล้ว ผลลัพธ์จะลู่เข้าหาค่าเดียวกันคือ $0.367879...$ นั่นก็เพราะ

$$ \begin{align}
    \lim_{n \to \infty} \left( 1 - \frac{1}{n} \right)^{n-1}
        &= \lim_{n \to \infty} \left( 1 - \frac{1}{n} \right)^n \\
        &= \lim_{n \to \infty} \left( \frac{n-1}{n} \right)^n \\
        &= \lim_{n \to \infty} \left( \frac{n}{n+1} \right)^n \\
        &= \lim_{n \to \infty} \frac{1}{ \left( \frac{n+1}{n} \right)^n} \\
        &= \frac{1}{ \lim\limits_{n \to \infty} \left( \frac{n+1}{n} \right)^n } \\
        &= \frac{1}{ \lim\limits_{n \to \infty} \left( 1 + \frac{1}{n} \right)^n } \\
        &= \frac{1}{e}
\end{align} $$

สวยมั้ย อยู่ดีๆ ก็ได้ค่า $e$ ออกมาเฉยเลย

ส่วนการพิสูจน์กรณีมีคนได้ของขวัญของตัวเองแค่คนเดียว จะมีฟอร์มที่ต่างไปเล็กน้อยเนื่องจากเหตุการณ์จะไม่เกิดขึ้นต่อเนื่องกันแล้ว เขียนสมการออกมาได้เป็น

$$ \begin{align}
    P(\text{n คนมี 1 คนได้ของตัวเอง}) &= \frac{1}{n} P(\text{n-1 คนไม่มีใครได้ของตัวเอง}) \\
            &\quad\quad + \frac{n-1}{n}\frac{1}{n-1} P(\text{n-2 คนไม่มีใครได้ของตัวเอง}) \\
            &\quad\quad + \cdots \\
            &\quad\quad + \frac{n-(n-1)}{n}\frac{1}{n-(n-1)} P(\text{n-n คนไม่มีใครได้ของตัวเอง}) \\
        &= \frac{1}{n} P(\text{n-1 คนไม่มีใครได้ของตัวเอง}) \\
            &\quad\quad + \frac{1}{n} P(\text{n-2 คนไม่มีใครได้ของตัวเอง}) \\
            &\quad\quad + \cdots \\
            &\quad\quad + \frac{1}{n} P(\text{n-n คนไม่มีใครได้ของตัวเอง}) \\
        &= \frac{1}{n} \left( \sum_{i=1}^{n}  P(\text{n-i คนไม่มีใครได้ของตัวเอง}) \right)
\end{align} $$

สมมติว่ามีคนมาร่วมงานแลกของขวัญเยอะ อาจจะมองว่า $P(\text{n-i คนที่ไม่มีใครได้ของตัวเอง})$ มีค่าไม่แตกต่างกันสำหรับแต่ละค่า $i$ เลยก็ได้ ทำให้เราสามารถยุบผลรวมยุ่งๆ ด้านหลัง ให้เหลือแค่เอาความน่าจะเป็นไปคูณด้วย $n$ ก็พอ ซึ่งมันก็จะโดนหักล้างทิ้งไปกับ $\frac{1}{n}$ ด้านหน้าทันที

ดังนั้นจะได้ว่า ค่าความน่าจะเป็นของงานเลี้ยงแลกของขวัญที่จะมีคนหนึ่งคนได้จับได้ของตัวเอง เป็น $\frac{1}{e}$ เท่ากันกับกรณีไม่มีใครจับได้ของตัวเองเลย

สำหรับกรณีที่มีคนสองคนจับได้ของตัวเอง จะเริ่มพิสูจน์ยุ่งยากมากขึ้นไปอีก แต่ใจความจะคล้ายๆ กับการพิสูจน์คนเดียวได้ของตัวเอง ซึ่งได้แก่การมองแยกกรณี โดยแบบที่หนึ่งจะให้คนแรกจับได้ของตัวเองไปแล้ว หลังจากนั้นจึงหาโอกาสของคนที่เหลือที่จะมีหนึ่งคนจับได้ของตัวเองเป็นเท่าไหร่ กับแบบที่สองที่ให้คนแรกจับไม่ได้ของตัวเอง แล้วหาโอกาสของคนที่เหลือที่จะมีสองคนจับได้ของตัวเองเป็นเท่าไหร่ (ถ้าคิดด้วยวิธีนี้ไม่ผิด จะได้หน้าตาสมการเป็นการหาผลรวมของเทอม $\frac{n-k}{n}\frac{n-k+1}{n-1}\frac{n-k+2}{n-2}\cdots\frac{1}{n-k+1}P(\text{n-k คนมี 1 คนได้ของตัวเอง})$)

กรณีอื่นๆ ที่เหลือเนื่องด้วยพื้นที่กระดาษไม่พอเขี.... เฮ้ย ไม่ใช่แฟร์มาต์! จริงๆ แล้วต้องบอกว่าการพิสูจน์ด้วยท่านี้มันเริ่มยุ่งยากซับซ้อนจนไปต่อไม่ไหวแล้ว แต่ถ้ายังจำกันได้ นี่มัน[การแจกแจงปัวซอง][poisson distribution]ที่มีค่า $\lambda=1$ ชัดๆ ก็เอาเป็นว่าใครอยากพิสูจน์ต่อก็ลองใช้ท่านี้ดูนะ อาจจะได้บทพิสูจน์ที่สั้นและสวยงามกว่าด้วย

---

เห็นแล้วว่าการสุ่มจับฉลากทั้งหมดทีเดียวพร้อมกันมันไม่เวิร์ค กลับไปดูวิธีดั้งเดิมที่ค่อยๆ ให้จับฉลากทีละคน จับได้ชื่อใครก็ให้คนนั้นไปจับฉลากต่อ วิธีนี้เขียนเป็นโค้ดออกมาได้ว่า

``` python
from random import randint

def exchange(ls):
    owned = [None for _ in ls]
    current = 0
    while ls:
        if owned[current] is not None:
            current = owned.index(None)
        gone = randint(0, len(ls)-1)
        owned[current] = ls[gone]
        current = ls[gone]
        del ls[gone]
    return owned
```

เอาฟังก์ชัน `exchange` ไปแทนที่ฟังก์ชัน `shuffled` ข้างบนแล้วทดลองใหม่ ก็ได้ผลลัพธ์ที่ไม่ต่างไปจากตารางแรกซักเท่าไหร่เลย

---

ดังนั้นไม่ว่าจะให้จับฉลากพร้อมกันหมดในทีเดียว หรือจะค่อยๆ จับทีละคน พอจับได้ชื่อใครก็ให้คนนั้นจับต่อ ทั้งสองวิธีนี้ยังไงก็จะมีคน~~ซวย~~โชคดีอย่างน้อยหนึ่งคน ที่จับได้ของขวัญของตัวเองด้วยโอกาสสูงเท่ากันที่ $1-\frac{1}{e}$ หรือประมาณ 63.21% ครับ โดยที่(แทบ)ไม่ต้องสนใจด้วยว่ามีคนมาแลกของขวัญกันกี่คน

แต่วิธีแก้ก็ไม่ได้ยากเกินไป ใช้วิธีค่อยๆ ไล่จับฉลากไปทีละคนนั่นแหละ (จะได้เล่นมุกคั่นเวลา ดูรีแอคชันของคนได้ของขวัญด้วย) แล้วเพิ่มกฎเข้าไปสองข้อดังนี้

1. ถ้าจับได้ชื่อตัวเอง ให้จับฉลากเพิ่มอีกใบเพื่อจะได้เอาของขวัญจากคนนั้น แต่อย่าลืมหย่อนฉลากชื่อตัวเองที่จับขึ้นมาเมื่อกี้ใส่กลับลงไหก่อนเอาไปให้จับฉลากต่อ
2. ตอนเหลือคนยังไม่ได้จับฉลาก 2 คน ไม่ต้องให้จับฉลากแล้ว ให้คนที่กำลังจะจับฉลากไปเอาของขวัญจากคนสุดท้ายได้เลย ส่วนคนสุดท้ายก็ไปเอาของขวัญจากคนแรก

อย่างไรก็ตาม หากรู้สึกว่ากฎพวกนี้มันวุ่นวายจนทำให้งานกร่อยก็ไม่ต้องไปทำตามหรอก เพราะการมีคนจับได้ของขวัญของตัวเองก็ไม่ใช่เรื่องเลวร้ายแต่อย่างใด หนำซ้ำมันยังเป็นประสบการณ์สุดประหลาดที่หาได้ยาก และเป็นเรื่องขำขันชั้นดีที่สามารถเก็บเอาไว้เล่นได้เรื่อยๆ ยันลูกบวชเลยหละ

สวัสดีปีใหม่ 2016 ล่วงหน้าครับ


[@NungNing]: //twitter.com/NungNing

[poisson distribution]: //en.wikipedia.org/wiki/Poisson_distribution
