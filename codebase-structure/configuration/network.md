---
description: Yong & mungkorn
---

# Network

@sdk : chain id, 

ต่อไปไฟล์ที่เราจะทำการเปลี่ยนนั้นก็คือไฟล์ networks.ts โดยจะอยู่ตาม Path ต่อไปนี้ src/config/constants/networks.ts โดยไฟล์นี้จะอยู่ในส่วน  frontend เมื่อเราได้เข้ามาสู่ไฟล์นี้แล้วนั้น เราจะต้องดำเนินการเปลี่ยนลิงค์ MAINNET และ TESTNET เพื่อให้ลิงค์นั้นตรงกับ chainID ที่เราได้กำหนดไว้ในส่วน SDK ดังโค้ดต่อไปนี้

```text
  [ChainId.MAINNET]: 'https://rpc-testnet.bitkubchain.io',
  [ChainId.TESTNET]: 'https://rpc-testnet.bitkubchain.io',
```

โดยเมื่อเราทำการเปลี่ยนลิงค์ MAINNET และ TESTNET เสร็จสิ้นแล้วเราจะไปดำเนินการกันในส่วนสุดท้ายโดยไฟล์นี้จะชื่อว่า types.ts ซึ่งอยู่ใน Path src/config/constants/types.ts โดยสิ่งที่เราจะต้องดำเนินการเพิ่มนั้นคือ chainID ของเรานั่นเองโดยเราจะต้องกำหนดให้ chainID ด้วย

```text
export interface Address {
  97?: string
  56: string
  25925: string
}
```

จากในโค้ดข้างต้นนั้นเราได้ทำการเพิ่ม chanID ซึ่งก็คือ 25925 โดยกำหนด type เป็น string นั่นเอง

