

> **API Traffic Control** · กำแพงป้องกันที่ทุก Server ควรมี

---

## 📖 Definition

### English — Cloudflare
> *"Rate limiting is a technique used to control the rate at which requests are made to a network, server, or API. It limits how many requests a user can make within a given time frame, helping protect resources from abuse and ensuring fair usage."*

### English — AWS
> *"Rate limiting is a strategy for limiting network traffic. It puts a cap on how often someone can repeat an action within a certain timeframe — for instance, trying to log in to an account."*

### 🇹🇭 Thai — สรุปในสไตล์ของตัวเอง
Rate Limiting คือ **"ระบบคิว"** ที่กำหนดว่าแต่ละคนใช้งาน Server ได้กี่ครั้งต่อนาที — ป้องกันไม่ให้คนเดียวยิง request มาเยอะเกินจนระบบล่ม และป้องกันการโจมตีแบบ Brute Force ได้ด้วย 🛡️

---

## 🔍 Explanation

### 🔢 ตัวอย่างการกำหนด Rate Limit

| ระดับ | ขีดจำกัด | ใช้กับ |
|---|---|---|
| **Strict** | 10 req / นาที | Login, OTP |
| **Normal** | 100 req / นาที | API ทั่วไป |
| **Loose** | 1,000 req / นาที | Static content |

### 🛠️ Algorithm ที่นิยมใช้

| Algorithm | วิธีการ |
|---|---|
| **Fixed Window** | นับ request ในช่วงเวลาตายตัว |
| **Sliding Window** | หน้าต่างเวลาเลื่อนตาม request ล่าสุด |
| **Token Bucket** | แจก token ต่อเนื่อง ใช้หมดต้องรอเติม |
| **Leaky Bucket** | รับ request ไว้ในคิว แล้วปล่อยออกสม่ำเสมอ |

### 🌍 ตัวอย่างการใช้งานจริง

- **GitHub API** — 5,000 requests / ชั่วโมง สำหรับ authenticated user
- **Twitter API** — จำกัดตาม endpoint และ plan
- **Login Form** — ล็อก 15 นาที หลังพิมพ์รหัสผ่านผิด 5 ครั้ง

---

## 🤖 GenAI Explanation

> *"Rate Limiting เหมือนพนักงานเฝ้าประตูที่ร้านอาหารยอดนิยม — ไม่ใช่ว่าไม่ต้อนรับ แต่ถ้าปล่อยทุกคนเข้าพร้อมกันร้านจะวุ่นวาย การจำกัดจำนวนทำให้ทุกคนได้รับบริการที่ดีอย่างเท่าเทียม"*
>
> — **ChatGPT** (OpenAI)

> *"Rate Limiting เป็นส่วนหนึ่งของ API Security ที่ขาดไม่ได้ นอกจากป้องกัน DDoS และ Brute Force แล้ว ยังช่วยควบคุมค่าใช้จ่ายของ infrastructure และรับประกัน uptime ให้ผู้ใช้ทุกคนด้วย"*
>
> — **Gemini** (Google)

---

## 📚 References

1. Cloudflare. (2024). [*What is Rate Limiting?*](https://www.cloudflare.com/learning/bots/what-is-rate-limiting/)
2. AWS. (2024). [*Rate limiting*](https://aws.amazon.com/builders-library/handling-overload-in-distributed-systems/)
3. OWASP. (2024). [*API Security — Rate Limiting*](https://owasp.org/API-Security/editions/2023/en/0xa4-unrestricted-resource-consumption/)

---

*🔗 กลับไปหน้าหลัก → [sximi.github.io](https://sximi.github.io)*
