---
description: Yong & mungkorn
---

# Farm

```text
{
    pid: 251,
    lpSymbol: 'A-B LP',
    lpAddresses: {
      97: '',
      56: '',
      25925 : '0x2D105fF34641dc54cf7D17df7161C6867DA3f68B'
    },
    token: tokens.a,
    quoteToken: tokens.b,
  }
```

ในการแก้ไขฟาร์มนั้นเราจะต้องดำเนินการแก้ไขในไฟล์ที่ชื่อว่า farm.ts ซึ่งอยู่ภายในส่วนของ frontend อยู่ภายใต้ path src/config/constants/farm.ts

![Path farm.ts](https://github.com/thanakiat-gusgus/bbt-swap-doc/tree/55174b0fd21820ebd2585515d6f9c181514817f2/codebase-structure/configuration/.gitbook/assets/path-farm.jpg)

เมื่อเข้ามาตาม path แล้วจะพบไฟล์ดังกล่าว ซึ่งในการที่เราจะดำเนินการแก้ไฟล์ดังกล่าวนั้น จะต้องมี IpAddresses ของคู่ฟาร์มนั้นๆ โดยเมื่อเราแก้ภายในไฟล์ดังกล่าว จะสังเกตได้ว่า ต้องมีการแก้ไฟล์ tokens.ts ด้วย สังเกตได้จากในรูปข้างต้นนั้น จากมีในส่วนของ token อยู่ ซึ่ง token เหล่านี้นั้นก็คือ token ที่จะต้องใช้ในการ Add Liquidity โดยเราจะไปแก้ไข ในไฟล์ tokens.ts กันซึ่งไฟล์ token นั้นอยู่ในส่วนของ frontend และอยู่ภายใน path เดียวกัน src/config/constants/tokens.ts

![Path tokens.ts](https://github.com/thanakiat-gusgus/bbt-swap-doc/tree/55174b0fd21820ebd2585515d6f9c181514817f2/codebase-structure/configuration/.gitbook/assets/path-token.jpg)

เมื่อเราเข้ามาในไฟล์ดังกล่าวแล้ว คุณเจอโค้ดที่มีจำนวนมากมายมหาศาล ซึ่งภายใต้ code เรานั้นเราจะมาสังเกตในส่วนของโค้ดในส่วนถัดไปกัน

```text
"wbnb":{"symbol":"wBNB","address":{"56":"0xbb4CdB9CBd36B01bD1cBaEBF2De08d9173bc095c","97":"0xae13d989dac2f0debff460ac112a837c89baa7cd","25925":"0xbb4CdB9CBd36B01bD1cBaEBF2De08d9173bc095c"},"decimals":18,"projectLink":"https://pancakeswap.finance/"}
```

ในส่วนของโค้ดข้างต้นนั้นคือการ config token ซึ่งจะประกอบไปด้วย สัญลักษณ์ \(symbol\), ที่อยู่ \(address\) โดยภายใน address นั้นเราจำเป็นต้องมี address token ใน TESTNET หรือ MAINNET ด้วยนั่นเองต่อมา คือ ทศนิยม \(decimal\) ใน ณ ที่นี้นั้นเป็น 18 ซึ่งเป็นมาตรฐานในสุดท้าย คือ ลิงค์โปรเจค \(projectLink\) ซึ่งเป็นลิงค์ของโปรเจค เหรียญนั้นๆ

