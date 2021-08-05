---
description: Yong & mungkorn
---

# Tokens

ในตอนนี้เราจะมาเริ่มทำการ config token กันนะครับ โดยในส่วนแรกที่เริ่มต้นนั้น เราจะมาเริ่มจัดการที่ไฟล์ tokens.ts กัน โดยไฟล์ดังกล่าวนี้เราสามารถไปค้นเจอได้ใน Path ต่อไปนี้ src/config/constants/tokens.ts ซึ่งจะอยู่ในส่วนของ frontend

![Tokens Path](https://github.com/thanakiat-gusgus/bbt-swap-doc/tree/34af74db1a254f99785656261652d3c16620694f/codebase-structure/configuration/.gitbook/assets/path-token%20%281%29.jpg)

โดยสิ่งที่เราจะทำการแก้ไขนั้นจะอยู่ภายใต้การประกาศตัวแปร const tokens อีกทีหนึ่ง

```text
a: {
    symbol: 'A',
    address: { '56': '', '97': '', '25925': '0x7d7e6a44118e9baef79e74c25054101f32cdf983' },
    decimals: 18,
    projectLink: '',
  }
```

จากในโค้ดข้างต้นนั้นจะเห็นได้ว่า token ที่เรานำมาเป็นตัวอย่างนั้นคือ token a ซึ่งภายในนั้นจะประกอบไปด้วยเครื่องหมาย \(symbol\) ซึ่งในตัวอย่างนั้นคือ A ถัดไปคือ ที่อยู่ \(address\) โดยภายใน address ดังกล่าวนั้นต้องประกอบไปด้วย chainID และที่อยู่ของ chainID นั้นๆ ต่อมาก็คือ ทศนิยม \(decimals\) ในตัวอย่างนั้นเรากำหนดให้เป็น 18 ซึ่งเป็นจำนวนมาตรฐาน สุดท้าย คือ ลิงค์โปรเจค \(projectLink\) จะเห็นได้ว่าในตัวอย่างนั้นของเราปล่อยให้ว่างไว้เนื่องจาก token ที่เราทำการเพิ่มเข้าไปนั้นเป็น token ที่เป็นการจำลองขึ้นมา ต่อไปเราจะทำการแก้ไขไฟล์ถัดไปซึ่งก็ คือ ไฟล์ bbt-default-tokenlist.json ซึ่งจะอยู่ใน Path ต่อไปนี้ src/config/constants/tokenLists/bbt-default.tokenlist.json โดยในไฟล์นี้นั้นอยู่ใน frontend ด้วยเช่นกัน

![tokenlist Path](https://github.com/thanakiat-gusgus/bbt-swap-doc/tree/34af74db1a254f99785656261652d3c16620694f/codebase-structure/configuration/.gitbook/assets/json-path.jpg)

ในไฟล์นี้นั้นจะสิ่งที่เราจะต้องดำเนินการแก้ไขจะมีลักษณะคล้ายกับไฟล์ที่ผ่านมา

```text
{
      "name": "Token A",
      "symbol": "A",
      "address": "0x7d7e6a44118E9BaeF79e74C25054101F32cDF983",
      "chainId": 25925,
      "decimals": 18,
      "logoURI": "https://www.svgrepo.com/show/275501/coin.svg"
    }
```

โดยเราจะยกตัวอย่างซึ่งเป็น token เดิมเพื่อให้สามารถมองภายได้ชัดมากขึ้น หากเราทำการสังเกตจะพบว่าจะมีทั้งสิ่งที่เหมือนและแตกต่างออกไป โดยสิ่งที่เหมือนเดิมและไม่มีการเปลี่ยนแปลง ซึ่งสิ่งที่เราจะพูดถึงเป็นอันดับแรกนั้นก็ คือ ชื่อ\(name\), เครื่องหมาย\(symbol\) และ ทศนิยม\(decimals\) ทั้งสามที่กล่าวมานั้นเราไม่ได้มีการเปลี่ยนแปลงสิ่งใดเพื่อให้ข้อมูลนั้นตรงกัน ต่อมาเราจะพูดถึงสิ่งที่เปลี่ยนไปเล็กน้อย ก็คือ ที่อยู่\(address\) และ chainID โดยใน code ข้างต้นที่เราได้กล่าวไปก่อนนั้น chainID และ address จะถูกประกาศอยู่ในจุดเดียวกัน ซึ่งในไฟล์นั้นเราจะแยกทั้งสองออกจากกันเป็นคนละตัวแปร สุดท้าย คือ สิ่งที่เราได้ทำการเพิ่มเข้ามาใหม่ logoURL ซึ่งจะเป็นตัวกำหนดรูปภาพให้ token ที่เราได้ทำการเพิ่มไป และในตอนนี้เราได้เดินทางมาถึงไฟล์สุดท้ายแล้วที่เราจะดำเนินการแก้ไข โดยไฟล์นี้จะมี ชื่อว่า lists.ts โดยไฟล์ดังกล่าวจะอยู่ใน Path เดียวกันกับ token.ts ซึ่งก็คือ src/config/constants/lists.ts

![list Path](https://github.com/thanakiat-gusgus/bbt-swap-doc/tree/34af74db1a254f99785656261652d3c16620694f/codebase-structure/configuration/.gitbook/assets/path-list.jpg)

เมื่อเราเขามาตาม path ดังกล่าวแล้วจะเห็นการประกาศตัวแปร

```text
const BBT_OFFICIAL = 'https://thanakiat-gusgus.github.io/bbt-api/bbt-official.json'
const BBT_SAMPLE = 'https://thanakiat-gusgus.github.io/bbt-api/bbt-sample.json'
```

