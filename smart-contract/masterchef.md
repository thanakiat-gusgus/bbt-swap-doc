# MasterChef

### MasterChef คืออะไร? <a id="3fd3"></a>

`MasterChef` คือ contract สำหรับ stake ตัว liquidity provider token \(LP Token\) ซึ่งแสดงความเป็นเจ้าของ liquidity ที่เรา provide ให้กับ BBTSwap โดยการ stake จะทำให้เราได้ CAKE เป็น reward เพิ่มเติมจาก platform โดย BBTSwap จะมี pool หรือคู่เหรียญต่างๆให้เราได้ stake เช่น CAKE-BNB, PBTC-BNB เป็นต้น

ในการที่เราจะดำเนินการแก้ไขเพื่อปรับเปลี่ยนเป็นของตัวเองได้นั้น เราจำเป็นต้องมี Masterchef deployed แล้วจึงจะสามารถดำเนินการได้ โดยเราจะต้องดำเนินการเปลี่ยน address ของ Masterchef ได้ในไฟล์ contracts.ts ซึ่งอยู่ในส่วนของ frontend โดยไฟล์นี่จะอยู่ใน Path ดังนี้ src/config/constants/contracts.ts

โดยเมื่อเราทำการเข้ามาแล้วให้เราสังเกตที่ ในส่วนต่อไปนี้

```text
masterChef: {
    97: '0x1d32c2945C8FDCBc7156c553B7cEa4325a17f4f9',
    56: '0x73feaa1eE314F8c655E354234017bE2193C9E24E',
  }
```

จะสังเกตได้ว่าในตัวของ Masterchef นั้นประกอบไปด้วยเลข chain id และ address ของ chain id นั้นๆ นั่นหมายถึงสิ่งที่เราจะต้องมีเพื่อมาดำเนินการแก้ไขนั้นก็คือ chain id และ address นั่นเอง 

โดยเมื่อเรามีทั้งสองสิ่งแล้วให้เราทำการเพิ่มต่อด้านล่างต่อจากบรรทัดที่มีเลข chain id : 56 อยู่ ให้เราทำการใส่เลข chain id และ address เข้าไปเลย เท่านี้ก็เสร็จเรียบร้อย โดยตัวอย่างที่เราจะใส่เข้าไปนั้นเป็นดังนี้

```text
chain id : 'address',
```

เท่านั้นก็เสร็จสิ้นแล้วในการแก้ไข Masterchef ของเรา