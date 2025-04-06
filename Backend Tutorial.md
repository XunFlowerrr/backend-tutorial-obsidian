
## **Client คืออะไร** 🧑‍💻

![[Client]]

---

## **Server คืออะไร** 🖥️

![[Server]]

---

## **HTTP** 🌐

![[1_hUWVb9Ecll30810Ni1Oq8Q.webp]]

- HTTP Request คือ การส่งคำขอจากฝั่ง _[[Client]]_ ไปยังฝั่ง _[[Server]]_ เพื่อต้องการข้อมูลบางอย่าง ^2d82a9
- HTTP Response คือ การที่ _Server_ ส่งข้อมูลที่ _Client ร้องขอกลับมา_ ^7b3493
- HTTP คือ Protocol ที่ใช้ในการเชื่อมต่อระหว่าง Client และ Server

🔶 **💡เปรียบเทียบให้เห็นภาพ**
ลองจินตนาการว่า **บ้านของ Frontend** (ฝั่ง Client) คือผู้ส่งจดหมาย
และ **บ้านของ Backend** (ฝั่ง Server) คือบ้านของเพื่อนที่เราอยากขอข้อมูลบางอย่าง เช่น รายชื่อสินค้า หรือข้อมูลผู้ใช้งาน

- **HTTP Request** ก็เหมือนกับ **จดหมายที่ส่งจากบ้าน Frontend ไปบ้าน Backend** เพื่อขอข้อมูล
- **HTTP Response** ก็เหมือนกับ **จดหมายตอบกลับจากบ้าน Backend มายังบ้าน Frontend** พร้อมกับข้อมูลที่เราขอไว้ เช่น รายการสินค้า, ผลลัพธ์ของการสมัครสมาชิก, หรือผลการเข้าสู่ระบบ
- ส่วน **HTTP Protocol** ก็คือ **ระบบไปรษณีย์มาตรฐาน** ที่ใช้ในการส่งจดหมายระหว่างบ้านทั้งสองหลังให้สื่อสารกันได้ถูกต้องและมีรูปแบบที่แน่นอน

---

### **Component of HTTP Request Message** ✉️

การที่ [[Client]] ส่งคำร้องไปหา Server นั้นจะมีรูปแบบของการส่ง เรียกว่า [[Backend Tutorial#^2d82a9| HTTP Request Message]]
คือส่วนที่บอกข้อมูลรายละเอียดให้กับอีกฝั่งทราบ (ในที่นี้คือ [[Server]])
ซึ่ง [[Backend Tutorial#^7b3493|HTTP Response]] ก็มีลักษณะเช่นเดียวกัน

🔶 **💌 เปรียบเทียบกับจดหมาย**
ลองนึกภาพว่า HTTP Request คือจดหมายที่เราส่งออกไป
มันจะต้องมีส่วนประกอบครบถ้วนเหมือนจดหมายจริงๆ เพื่อให้ปลายทางเข้าใจว่าเราต้องการอะไร เช่น

---

### **HTTP Request Message ประกอบด้วย 3 ส่วน** 📦

![[1_FOH7gWJH5CA20pCaKoABvg.gif]]

#### **1. Request Line** 🧾
คือส่วนที่ระบุ HTTP Method, URI และ Version ของ Protocol ที่ใช้ (HTTP/1.0, HTTP/1.1, HTTP/2.0)

- HTTP Method คือ วิธีการที่ Client ใช้ในการร้องขอข้อมูลจาก Server เช่น GET, POST, PUT, DELETE
- URI (Uniform Resource Identifier) คือ ที่อยู่ของ Resource ที่ Client ต้องการร้องขอ เช่น /api/user, /api/product
- Version คือ เวอร์ชันของ Protocol ที่ใช้ในการเชื่อมต่อ เช่น HTTP/1.1, HTTP/2.0

🔶 **✉️ เปรียบเทียบกับหน้าซองจดหมาย**
- HTTP Method เหมือนการระบุว่าเราส่งจดหมายเพื่อ **ขอของ (GET)**, **ส่งข้อมูลใหม่ (POST)**, หรือ **อัปเดตของเดิม (PUT)**
- URI คือ **ชื่อและที่อยู่ของเพื่อนที่เราจะส่งจดหมายถึง**
- Version ก็เหมือนกับ **มาตรฐานการเขียนจดหมาย** ที่ทั้งสองฝ่ายเข้าใจร่วมกัน เช่น จะเขียนด้วยภาษาทางการหรือไม่

---

#### **2. Header** 📎
คือส่วนที่ระบุข้อมูล และกฏต่างๆ ในการเชื่อมต่อ เช่น

- **Content-type** คือระบุประเภทของข้อมูลใน Body ที่จะส่งไปพร้อมกับ Request เช่น application/json, text/html
- **accept-language** คือระบุภาษาที่ Client รองรับ เช่น en-US, th-TH
- **user-agent** คือระบุประเภทของ Client เช่น Mozilla/5.0 (หรือก็คือ Request นี้ถูกส่งมาจาก Browser Mozilla Firefox นั่นเอง)

🔶 **📦 เปรียบเทียบกับบันทึกแนบในจดหมาย**
Header ก็เหมือนกับ **กระดาษโน้ตหรือสัญลักษณ์แนบในจดหมาย** ที่บอกว่า

- "สิ่งที่แนบมานี้เป็นเอกสาร PDF นะ" (`Content-Type`)
- "กรุณาตอบกลับเป็นภาษาไทยหรืออังกฤษ" (`accept-language`)
- "จดหมายนี้ส่งมาจากมือถือหรือคอมพิวเตอร์" (`user-agent`)

---

#### **3. Body** 📄
คือส่วนที่เก็บข้อมูลที่ต้องการส่งไปยัง Server เช่น ข้อมูลการ Login, ข้อมูลการ Register, ข้อมูลการ Update Profile เป็นต้น
- Body จะมีเฉพาะในบาง HTTP Method เท่านั้น เช่น POST, PUT, PATCH

🔶 **📄 เปรียบเทียบกับเนื้อหาของจดหมาย**
Body ก็คือ **สิ่งที่เราอยากพูดหรือร้องขอในจดหมายนั้นจริงๆ** เช่น

- "สวัสดีครับ ผมชื่อ... ผมต้องการลงทะเบียน"
- "นี่คือรายละเอียดการสั่งซื้อของผม กรุณายืนยันกลับด้วย"

---

### **HTTP Method** 🛠️
HTTP Request Method คือส่วนที่ใช้กำหนดประเภทของคำร้องขอ
โดยจะมีอยู่ 4 Methods ที่ใช้งานบ่อย มีดังนี้

- `GET` : สำหรับขอ request จาก server เช่น รายชื่อทั้งหมด หรือรายชื่อเดี่ยว
- `PUT` : สำหรับ update ค่าที่มีอยู่แล้ว และค่าที่ต้องการจะอัปเดตจะอยู่ใน Body
- `POST` : สำหรับ create หรือเพิ่มค่าใหม่ และค่าที่ต้องการจะเพิ่มจะอยู่ใน Body
- `DELETE` : สำหรับลบค่า

🔶 **💌 เปรียบเทียบกับจดหมายที่ส่งถึงบ้าน Backend**
ลองจินตนาการว่า HTTP Method คือ **เจตนาหลักของจดหมายที่เราส่งไป** ว่าเราต้องการให้บ้าน Backend ทำอะไรให้บ้าง:

- ✉️ `GET` 👉 เหมือนการส่งจดหมายไปถามว่า
  > "ขอรายชื่อสินค้าทั้งหมดหน่อยครับ" หรือ
  > "ขอรายละเอียดของสินค้าชิ้นนี้หน่อยครับ"
  ✅ ไม่แนบอะไรไปเลย แค่ขอข้อมูลกลับมา

- ✉️ `POST` 👉 เหมือนการส่งจดหมายพร้อมแนบแบบฟอร์มลงทะเบียน
  > "นี่คือข้อมูลของสมาชิกใหม่ กรุณาสร้างให้ด้วยครับ"
  ✅ แนบข้อมูลใหม่ไปใน Body เพื่อให้ Backend สร้างสิ่งใหม่

- ✉️ `PUT` 👉 เหมือนการส่งจดหมายพร้อมไฟล์ข้อมูลอัปเดต
  > "นี่คือรายละเอียดที่อัปเดตของสมาชิกคนนี้ รบกวนแก้ไขให้ด้วยครับ"
  ✅ แนบข้อมูลเดิมที่ต้องการแก้ พร้อมข้อมูลใหม่ไปใน Body

- ✉️ `DELETE` 👉 เหมือนการส่งจดหมายไปแจ้งยกเลิก
  > "รบกวนลบสมาชิกหมายเลขนี้ออกจากระบบด้วยครับ"
  ✅ ไม่จำเป็นต้องแนบข้อมูลมาก แค่ระบุว่า “จะลบอะไร”

🎯 **สรุป:** HTTP Method คือ **เป้าหมายหลักของการสื่อสารในแต่ละจดหมาย**
ว่าเราจะ "ขอข้อมูล", "เพิ่ม", "อัปเดต" หรือ "ลบ" สิ่งใดจากบ้าน Backend

---

### **HTTP Status Code** 📬

^16cb86

เมื่อ _[[Server]]_ ได้รับ _[[Backend Tutorial#^2d82a9| HTTP Request]]_ แล้ว
จะทำการประมวลผลคำร้องขอ และส่งกลับไปยัง _[[Client]]_
โดยจะมีการส่ง _[[Backend Tutorial#^7b3493|HTTP Response]]_ กลับไปด้วย
ซึ่งใน _[[Backend Tutorial#^7b3493|HTTP Response]]_ จะมีส่วนที่เรียกว่า _[[Backend Tutorial#^16cb86|Status Code]]_
เพื่อบอกสถานะของคำร้องขอที่ส่งไปว่าเป็นอย่างไร เช่น

- 200 OK : คำร้องขอสำเร็จ
- 201 Created : คำร้องขอสำเร็จ และมีการสร้าง Resource ใหม่
- 204 No Content : คำร้องขอสำเร็จ แต่ไม่มีข้อมูลส่งกลับ
- 400 Bad Request : คำร้องขอไม่ถูกต้อง
- 401 Unauthorized : คำร้องขอไม่ถูกต้อง ต้องมีการยืนยันตัวตน
- 403 Forbidden : คำร้องขอไม่ถูกต้อง ไม่มีสิทธิ์เข้าถึง Resource
- 404 Not Found : ไม่พบ Resource ที่ร้องขอ
- 500 Internal Server Error : เกิดข้อผิดพลาดภายใน Server
- 502 Bad Gateway : Server ไม่สามารถติดต่อกับ Server อื่นได้

🔶 **📬 เปรียบเทียบกับการได้รับจดหมายตอบกลับจากบ้าน Backend**
เมื่อเราส่งจดหมาย (HTTP Request) ไปที่บ้าน Backend ฝั่งตรงข้าม
ก็เหมือนเรารอรับจดหมายตอบกลับกลับมา ซึ่งในจดหมายนั้นจะมี **"สถานะการตอบกลับ"** ว่าเกิดอะไรขึ้น เช่น:

- ✅ `200 OK` 👉 "ขอที่คุณร้องขอได้เรียบร้อยแล้ว!"
  > เหมือนบ้าน Backend ตอบกลับมาว่า "ได้รับคำขอและจัดการให้เสร็จแล้วครับ"

- ✅ `201 Created` 👉 "เราได้สร้างสิ่งใหม่ให้เรียบร้อยแล้ว!"
  > เหมือนบอกว่า "สมัครสมาชิกให้เรียบร้อยแล้วนะครับ"

- ✅ `204 No Content` 👉 "จัดการเรียบร้อย แต่ไม่มีอะไรจะตอบกลับ"
  > เหมือนบ้าน Backend บอกว่า "จัดการให้แล้ว แต่ไม่มีข้อมูลต้องส่งกลับ"

- ❌ `400 Bad Request` 👉 "จดหมายคุณส่งมาผิดฟอร์ม อ่านไม่เข้าใจเลย!"
  > เช่น ข้อมูลที่ส่งมาขาดบางช่อง หรือใช้ฟอร์มผิด

- ❌ `401 Unauthorized` 👉 "คุณยังไม่ยืนยันตัวตน ห้ามเข้า!"
  > เหมือนจดหมายที่ส่งมาไม่แนบหลักฐานยืนยันตัวตน เช่น token

- ❌ `403 Forbidden` 👉 "ถึงคุณจะล็อกอินแล้ว แต่ก็ยังไม่มีสิทธิ์ดูข้อมูลนี้"
  > เช่น พนักงานทั่วไปจะดูข้อมูลลับของผู้บริหารไม่ได้

- ❌ `404 Not Found` 👉 "บ้านเลขที่หรือทรัพยากรที่คุณขอมา... ไม่มีอยู่จริง!"
  > เหมือนพยายามเข้าหน้า `/product/999` ที่ไม่มีในระบบ

- ❌ `500 Internal Server Error` 👉 "ระบบภายในบ้าน Backend ล่ม!"
  > เหมือนเจ้าของบ้านทำงานผิดพลาดเองในระบบหลังบ้าน

- ❌ `502 Bad Gateway` 👉 "บ้าน Backend ติดต่อบ้านหลังอื่นที่เกี่ยวข้องไม่ได้เลย"
  > เช่น ระบบพยายามไปดึงข้อมูลจาก API อื่นแล้วเจอปัญหา

🎯 **สรุป:** HTTP Status Code คือ **ข้อความสั้นๆ ในจดหมายตอบกลับ**
จากบ้าน Backend เพื่อบอกเราว่าผลของคำขอเป็นอย่างไร — สำเร็จ, ล้มเหลว, หรือระบบมีปัญหา

---


# ขั้นตอนทั้งหมดของการทำ Backend 🛠️💻

## **1. สร้างโฟลเดอร์** 📁

---

### **1.1 สร้างโฟลเดอร์ในตำแหน่งที่ต้องการ** 🗂️

![[Pasted image 20250401034412.png]]

---

### **1.2 เปิดโฟลเดอร์ สร้างโฟลเดอร์ย่อยข้างใน** 🧱

สร้างโฟลเดอร์ย่อยชื่อ `backend` และ `frontend` เพื่อแยกงานฝั่งเซิร์ฟเวอร์และหน้าบ้านออกจากกันอย่างชัดเจน

![[Pasted image 20250401034424.png]]

---

## **2. Setup Database** 🗄️🐘

**SQL Database** นั้นจริงๆ แล้วมีหลายตัวมาก เช่น:

- MySQL
- PostgreSQL
- SQLite

แต่ในที่นี้จะเลือกใช้ **PostgreSQL** เนื่องจากเป็นหนึ่งใน Database ที่นิยมมากในปัจจุบัน และมีความสามารถในการจัดการข้อมูลที่ซับซ้อนได้ดี

🔹 **ทำไมต้องใช้ Docker ในการเปิด Database?**
Docker ช่วยให้การติดตั้งและจัดการ PostgreSQL ง่ายขึ้นโดย:

- ไม่ต้องติดตั้งตัวโปรแกรมลงเครื่องโดยตรง
- จัดการผ่าน Container ได้สะดวก เช่น สร้าง, ลบ, รีสตาร์ท
- ไม่กระทบกับระบบปฏิบัติการหลักของเราเลย 🎯
- ทำให้การ Setup สำหรับทีม หรือย้ายเครื่อง ทำได้ง่ายและรวดเร็ว

💡 **สรุป:**
> Docker ช่วยให้เราสร้าง “กล่อง” (Container) ที่มี PostgreSQL พร้อมใช้งานอยู่ข้างใน
> เราแค่รันคำสั่ง เปิดกล่องนั้นขึ้นมา แล้วก็เชื่อมต่อได้ทันที

---

### **2.1 สร้างไฟล์ Docker Compose** ⚙️
https://github.com/XunFlowerrr/backend-tutorial/tree/c6c66d31af1afe23424d8341393eaf538e1d9f3a
สร้างไฟล์ชื่อ `docker-compose.yml` ในโฟลเดอร์ใหญ่สุด (Root Project Folder) เพื่อกำหนดว่าอยากให้ Docker สร้างบริการอะไรให้เราบ้าง

![[Pasted image 20250401034840.png]]

🔹 ชื่อไฟล์: **docker-compose.yml**
```yml
version: '3.4'

services:

  postgres-db:

    image: postgres:17.4

    restart: always

    environment:

      POSTGRES_USER: admin

      POSTGRES_PASSWORD: password

      POSTGRES_DB: taskmanagement

    ports:

      - 5432:5432



    volumes:

      - type: bind

        source: ./database/init.sql

        target: /docker-entrypoint-initdb.d/init.sql
```
---
### **2.2 สร้างไฟล์ init.sql** 📝📁🧱
https://github.com/XunFlowerrr/backend-tutorial/tree/51cfc4f610d844dfb67f11c0667aa4ac683d42dc

สร้างโฟลเดอร์ชื่อ `database` 📂
และสร้างไฟล์ `init.sql` 📄 ภายในโฟลเดอร์นั้น

![[Pasted image 20250401035227.png]]

📌 **ในไฟล์ `init.sql`**
ให้ใส่คำสั่ง SQL (DDL) ที่ต้องการให้ **สร้างตาราง (Table)** ภายใน Database 🧩

🧠 โดยทั่วไปจะใช้คำสั่งประเภท:
- `CREATE TABLE` ➕ สำหรับสร้างตารางใหม่
- `ALTER TABLE` 🔧 สำหรับปรับเปลี่ยนโครงสร้าง
- `DROP TABLE` ❌ สำหรับลบตาราง

⚙️ เมื่อนำไปใช้กับ Docker PostgreSQL Container
ระบบจะสามารถ **รันไฟล์ `init.sql` อัตโนมัติ** ในขณะสร้าง Container ได้ทันที 🚀

🟡 เหมาะสำหรับ:
- การเตรียม Database ตั้งแต่ต้นโปรเจกต์
- การแชร์โครงสร้างตารางให้ทีม Dev ทุกคน
- การ reset ฐานข้อมูลให้พร้อมใช้งานเสมอ


init.sql
```sql
CREATE TABLE users(
    user_id CHAR(5) PRIMARY KEY,
    username VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    password VARCHAR(255) NOT NULL,
    role VARCHAR(100) NOT NULL,
    CONSTRAINT uk_user_email UNIQUE (email)
);

CREATE TABLE project (
  project_id CHAR(5) PRIMARY KEY NOT NULL,
  project_name VARCHAR(100) NOT NULL,
  project_description TEXT,
  owner_id CHAR(5) NOT NULL,
  created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  progress INT DEFAULT 0,
  category VARCHAR(100) NOT NULL,
  CONSTRAINT fk_owner FOREIGN KEY (owner_id) REFERENCES users(user_id) ON DELETE CASCADE ON UPDATE CASCADE
);

CREATE TABLE task(
  task_id CHAR(5) PRIMARY KEY NOT NULL,
  project_id CHAR(5) NOT NULL,
  task_name VARCHAR(100),
  task_description VARCHAR(280),
  start_date TIMESTAMP,
  due_date TIMESTAMP,
  status VARCHAR(20) DEFAULT 'pending',
  priority INT DEFAULT 0,
  created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  CONSTRAINT fk_project FOREIGN KEY (project_id) REFERENCES project(project_id) ON DELETE CASCADE ON UPDATE CASCADE
);

CREATE TABLE attachment(
  attachment_id CHAR(5) PRIMARY KEY,
  attachment_name VARCHAR(100) NOT NULL,
  task_id CHAR(5) NOT NULL,
  file_url VARCHAR(1000),
  file_type VARCHAR(20) NOT NULL,
  created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  CONSTRAINT fk_task FOREIGN KEY (task_id) REFERENCES task(task_id) ON DELETE CASCADE ON UPDATE CASCADE
);

CREATE TABLE project_member(
  project_id CHAR(5) NOT NULL,
  user_id CHAR(5) NOT NULL,
  CONSTRAINT fk_project FOREIGN KEY (project_id) REFERENCES project(project_id) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT fk_user FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE ON UPDATE CASCADE,
  PRIMARY KEY (project_id, user_id)
);

CREATE TABLE task_assignee(
  task_id CHAR(5) NOT NULL,
  user_id CHAR(5) NOT NULL,
  PRIMARY KEY (task_id, user_id),
  CONSTRAINT fk_task FOREIGN KEY (task_id) REFERENCES task(task_id) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT fk_user FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE ON UPDATE CASCADE
);

-- Add generate id function

CREATE OR REPLACE FUNCTION generate_user_id() RETURNS CHAR(5) AS $$
DECLARE
    max_id INT;
BEGIN
    SELECT COALESCE(MAX(user_id::int), 0) INTO max_id FROM users;
    RETURN LPAD((max_id + 1)::text, 5, '0');
END;
$$ LANGUAGE plpgsql;

CREATE OR REPLACE FUNCTION generate_project_id() RETURNS CHAR(5) AS $$
DECLARE
    max_id INT;
BEGIN
    SELECT COALESCE(MAX(project_id::int), 0) INTO max_id FROM project;
    RETURN LPAD((max_id + 1)::text, 5, '0');
END;
$$ LANGUAGE plpgsql;

CREATE OR REPLACE FUNCTION generate_task_id() RETURNS CHAR(5) AS $$
DECLARE
    max_id INT;
BEGIN
    SELECT COALESCE(MAX(task_id::int), 0) INTO max_id FROM task;
    RETURN LPAD((max_id + 1)::text, 5, '0');
END;
$$ LANGUAGE plpgsql;

CREATE OR REPLACE FUNCTION generate_attachment_id() RETURNS CHAR(5) AS $$
DECLARE
    max_id INT;
BEGIN
    SELECT COALESCE(MAX(attachment_id::int), 0) INTO max_id FROM attachment;
    RETURN LPAD((max_id + 1)::text, 5, '0');
END;
$$ LANGUAGE plpgsql;

```
---

### **2.3 วิธี run database** 🚀🗄️

^4e71ae

---

#### **2.3.1 เปิด Docker Desktop ขึ้นมา** 🐳💻

เปิดแอป **Docker Desktop** ขึ้นมาให้พร้อมทำงาน
หากยังไม่ได้เปิด Docker ไว้ก่อนหน้านี้ ต้องเปิดก่อนจึงจะสามารถรันคำสั่งต่าง ๆ ได้

![[20250331-2102-30.8108024.mp4]]

---

#### **2.3.2 ถ้ามี container ให้ลบ container ที่มีอยู่แล้ว** 🧹🧱

เพื่อลดความสับสนหรือปัญหาที่อาจเกิดจาก container เก่า แนะนำให้ลบ container เดิมที่มีอยู่ก่อนจะรันใหม่

![[20250331-2109-07.5062965.mp4]]

🛑 วิธีลบ:
- คลิกขวาที่ container แล้วเลือก **Remove**
- หรือจะใช้คำสั่ง `docker rm` ผ่าน terminal ก็ได้

---

#### **2.3.3 เปิด terminal ขึ้นมาในโฟลเดอร์ใหญ่ที่มีไฟล์ docker-compose.yml** 💼📂

สามารถเลือกเปิดได้หลายแบบ:
- เปิด **PowerShell** 💻
- หรือเปิด **Terminal ใน VS Code** 🧑‍💻 (ในตัวอย่างใช้แบบนี้)

จากนั้นให้พิมพ์คำสั่งเพื่อรัน Docker Compose
🧩 *คำสั่งจะสั่งให้ Docker สร้าง Container สำหรับ PostgreSQL ตามที่ระบุไว้ใน `docker-compose.yml`*

```bash
docker-compose up
```

![[20250331-2133-18.5619454.mp4]]

✅ ถ้าคุณเห็นข้อความว่า
**"database system is ready to accept connections"**
นั่นหมายความว่า **Database พร้อมใช้งานแล้ว!** 🎉🎯

---

#### **2.3.4 ⚠️ !!!ถ้ามีการเปลี่ยนแปลงไฟล์ init.sql!!!** 📝🔁

ถ้าคุณมีการแก้ไขหรือเปลี่ยนแปลงคำสั่งในไฟล์ `init.sql` และต้องการให้ Database ใช้ไฟล์ใหม่นี้
จำเป็นต้อง **รีสตาร์ท Database Container** เพื่อให้ PostgreSQL โหลดไฟล์ `init.sql` ใหม่ ✨

มี 2 วิธีให้เลือกใช้ 👇

---

🔹 **วิธีที่ 1**: ❌ ลบ container ที่มีอยู่แล้วใน Docker Desktop แล้วรัน `docker-compose up` ใหม่ 🐳

1. เปิด Docker Desktop
2. คลิกขวาที่ container แล้วเลือก **Remove**
3. เปิด terminal แล้วพิมพ์คำสั่ง:

```bash
docker-compose up
```


![[20250331-2144-03.6506825.mp4]]

✅ วิธีนี้จะ **สร้าง Container ใหม่ตั้งแต่ต้น** และรัน `init.sql` อัตโนมัติ

---

🔹 **วิธีที่ 2**: 🔄 ใช้คำสั่งใน Terminal เพื่อรันใหม่อย่างรวดเร็ว 💻⚙️

สามารถใช้คำสั่งเพื่อหยุด และลบ container แล้วรันใหม่ได้ผ่าน terminal ในขั้นตอนเดียว เช่น:

```bash
docker-compose down
docker-compose up
```

![[20250331-2145-23.2271100.mp4]]

✅ เหมาะกับคนที่ทำงานผ่าน CLI เป็นหลัก และต้องการควบคุมขั้นตอนเอง

---

💡 **สรุปสั้น ๆ:**
ทุกครั้งที่คุณเปลี่ยนคำสั่งใน `init.sql` และอยากให้ PostgreSQL โหลดคำสั่งใหม่
> ต้องลบ Container เดิม แล้วรันใหม่เท่านั้น ⚠️
> PostgreSQL จะไม่โหลดไฟล์ `init.sql` ซ้ำอัตโนมัติหาก Container ยังอยู่

---

## **3. สร้าง npm project** 📦💻

---

### **3.1 เปิด terminal ขึ้นมาในโฟลเดอร์ backend** 🖥️📂
https://github.com/XunFlowerrr/backend-tutorial/tree/9e5ee970cbd1e4d615ccc5992fc5570aceecaa68

เปิด Terminal ที่ตำแหน่งโฟลเดอร์ `backend`
ซึ่งเป็นโฟลเดอร์หลักสำหรับงานฝั่ง Server ของเรา

จากนั้นพิมพ์คำสั่ง ✍️

```bash
npm init -y
```
![[20250331-2152-06.9653725.mp4]]

---
### **3.2 ติดตั้ง express, nodemon** 🚀📦
https://github.com/XunFlowerrr/backend-tutorial/tree/f5e104fff9c66ebf654774fdf8a4442ce89ce48d

หลังจากที่สร้าง npm project แล้ว ต่อไปให้ติดตั้ง dependencies ที่จำเป็น

🔹 พิมพ์คำสั่งใน Terminal ✍️
เพื่อทำการติดตั้ง **Express** (Web Framework) และ **Nodemon** (ใช้สำหรับรัน server แล้ว auto-reload เมื่อมีการเปลี่ยนแปลง)


```bash
npm install express     หรือ npm i express
```

```bash
npm install nodemon --save-dev     หรือ npm i nodemon --save-dev

![[20250331-2159-48.3310727.mp4]]
```

### **3.3 เลือกใช้ nodemon ในการรันโปรเจค** 🔄⚙️
https://github.com/XunFlowerrr/backend-tutorial/tree/85f09d16c404969a3efcca20a580f7dc90541d68

ใช้ **nodemon** เพื่อช่วยให้โปรเจคสามารถรันอัตโนมัติเมื่อมีการแก้ไขไฟล์
ทำให้ไม่ต้องพิมพ์ `node index.js` ใหม่ทุกครั้งที่แก้ไขโค้ด

![[20250331-2203-00.4222062.mp4]]

📌 ส่วนใหญ่จะกำหนดใน `scripts` ของ `package.json` แบบนี้:
```json
"scripts": {
  "dev": "nodemon index.js"
}
```

จากนั้นสามารถใช้คำสั่ง:
```bash
npm run dev
```
![[20250331-2203-00.4222062.mp4]]

---
### **3.4 เลือกใช้วิธีในการ import 📥📦**
https://github.com/XunFlowerrr/backend-tutorial/tree/ade449c495b82b13f06480540a060e79c8d09c3b
เนื่องจาก JavaScript มี 2 วิธีหลักในการ import modules ได้แก่:

- 🔸 **CommonJS** 👉 ใช้ require
``` javascript
const express = require('express');
```

- 🔸 **ES Module** 👉 ใช้ import
``` javascript
import express from 'express';
```

ในตัวอย่างนี้จะใช้ `ES Module` 📦
ดังนั้นให้ไปที่ไฟล์ **`package.json`** แล้วเพิ่มบรรทัด:

```json
"type": "module"
```
![[20250331-2208-29.1184242.mp4]]

---
### ไฟล์ package.json
```json
{
  "name": "backend",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev" : "nodemon index.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^5.1.0"
  },
  "devDependencies": {
    "nodemon": "^3.1.9"
  }
}

```
---

## **4. สร้างไฟล์ index.js และ Express เบื้องต้น** 🛠️📄🚀

---

### **4.1 สร้างไฟล์ index.js** 📂📝

สร้างไฟล์ชื่อ `index.js` ภายในโฟลเดอร์ `backend`
ไฟล์นี้จะเป็นจุดเริ่มต้น (Entry Point) ของโปรเจคฝั่ง Backend ที่ใช้ Express ในการจัดการ Web Server 🌐

📌 จากจุดนี้ เราจะเริ่มเขียนโค้ด Express เพื่อรับส่งข้อมูลระหว่าง Client และ Server ได้แล้ว!

```javascript
//index.js
import express from "express";

const app = express();
const PORT = 3000;

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
});
```

**app.listen**
```javascript
app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
});
```

คือการบอกให้ _[[Server]]_ รอรับคำร้องขอจาก _[[Client]]_ ที่พอร์ตเลขที่เก็บไว้ในตัวแปร `PORT`
(ในที่นี้คือ `3000`) และเมื่อ _[[Server]]_ เริ่มทำงาน จะมีการแสดงข้อความใน console ว่า:

```
Server is running on http://localhost:3000
```

🔶 **🏠 เปรียบเทียบแบบบ้านและจดหมาย**

- 🧱 `const app = express();` 👉 เหมือนกับเรากำลังสร้าง **"บ้านเปล่าๆ"**
  ⤷ ยังไม่มีห้อง ไม่มีที่อยู่ ไม่มีแขกมาหา

- 🏠 `app.listen(PORT)` 👉 คือการ **บอกที่อยู่บ้าน (บ้านเลขที่)**
  ⤷ ให้คนอื่นรู้ว่าจะมาหาเราได้ที่ไหน เช่น `localhost:3000`

- 📬 เมื่อบ้านพร้อมและมีเลขที่แล้ว
  ก็สามารถ **เปิดรับจดหมาย (HTTP Request) จากเพื่อนบ้าน (Client)** ได้ทันที

---

### **4.2 รับ HTTP Request** 📥🌐
https://github.com/XunFlowerrr/backend-tutorial/tree/53c1aa1417605dbf73ca124c340d7b3cf96528c6

ในส่วนนี้เราจะเรียนรู้ **วิธีการรับ HTTP Request** โดยใช้ Express
เพื่อให้ Server สามารถตอบสนองคำขอจากฝั่ง _[[Client]]_ ได้อย่างถูกต้อง

📌 Express ช่วยให้การสร้าง Web API เป็นเรื่องง่ายมาก โดยสามารถกำหนดว่า
- เมื่อมีคน **ส่งคำขอ (Request)** มายัง URL ไหน
- จะให้ Server ตอบกลับอะไรกลับไป

🧠 ตัวอย่างที่พบบ่อย:
- รับคำขอแบบ `GET` เพื่อดึงข้อมูล
- รับคำขอแบบ `POST` เพื่อเพิ่มข้อมูล
- รับ `Query Params`, `URL Params`, หรือ `Body` จาก Request

✨ เมื่อเข้าใจการรับ Request แล้ว
คุณจะสามารถสร้าง API ที่ตอบสนองคำสั่งจาก Frontend ได้อย่างมีประสิทธิภาพ

```javascript
app.[ชื่อ HTTP Method] ([path], [handler function])
```

ซึ่ง **handler function** ที่ใช้รับ HTTP Request ใน Express
สามารถเขียนได้ **2 รูปแบบหลัก** ดังนี้ 👇

🔹 **แบบที่ 1: Normal Function** 🧑‍💻
เป็นรูปแบบฟังก์ชันปกติที่ประกาศแยกก่อน แล้วนำไปใช้ใน `app.get()`

```javascript
function handlerFunction(req, res) {
  res.send('Hello World');
}

app.get('/api/user', handlerFunction);
```

🔹 **แบบที่ 2: Arrow Function** 🪄
เป็นรูปแบบฟังก์ชันลูกศรที่เขียนในบรรทัดเดียว
```javascript
app.get('/api/user', (req, res) => {
  res.send('Hello World');
});
```

โดย Function ที่เราสร้างขึ้นจะมี **2 parameter** ที่สำคัญ คือ 👇

- **`req`** 📨: คือ **Request Object**
  ใช้สำหรับเก็บข้อมูลของคำร้องขอที่ส่งมาจาก _[[Client]]_ เช่น พารามิเตอร์, query, body ฯลฯ

- **`res`** 📦: คือ **Response Object**
  ใช้สำหรับส่งข้อมูลกลับไปยัง _[[Client]]_ ไม่ว่าจะเป็นข้อความธรรมดา, JSON, status code หรืออื่น ๆ

---

🔶 **🏠✉️ เปรียบเทียบแบบบ้าน-ห้อง-จดหมาย**

- 🏠 `app.get("/")` 👉 เหมือนกับการสร้าง **"ห้องรับแขก"** ในบ้านของเรา
  ⤷ ตำแหน่ง `/` คือเส้นทางหรือจุดที่แขก (Client) จะเข้ามาติดต่อเรา

- ✉️ `"GET"` 👉 เปรียบเสมือนการเขียนจดหมายส่งมาห้องรับแขก
  ⤷ คือวิธีการที่ Client ใช้ส่งคำขอ เช่น "ขอดูข้อมูลหน่อยครับ"

- 📤 `res.send(...)` 👉 คือการ **ตอบกลับจดหมาย** จากห้องนั้น
  ⤷ บอกว่าจะส่งข้อมูลอะไรกลับไปให้ผู้ที่ส่งจดหมายเข้ามา

---

🎯 สรุป: Handler Function จะใช้ `req` รับข้อมูล และใช้ `res` ส่งข้อมูลกลับไป
พร้อมระบุว่า "จะให้ใครเข้าบ้าน", "เข้ามายังห้องไหน", และ "จะตอบกลับยังไง" 💬

จะหมายความว่า
> ✉️ "ถ้ามีคนส่งจดหมายแบบ **GET** มาที่บ้านของเรา (ที่ `localhost:3000`)
> และเจาะจงมาที่ **ห้องรับแขก `/`**,
> เราจะตอบกลับไปว่า **'Hello World from GET request!'**" 📬🎉


📌 ดังนั้นถ้าเรามีโค้ดแบบนี้:

```javascript
app.get("/", (req, res) => {
  res.send("Hello World from GET request!");
});
```

🎯 **สรุปเปรียบเทียบแบบบ้าน-จดหมาย** 🏡📩

| สิ่งที่ใช้ใน Express         | เปรียบเทียบแบบบ้านและจดหมาย         |
|------------------------------|----------------------------------------|
| 🏠 บ้าน                      | `app` (คือ server ของเรา)             |
| 🚪 ห้อง                      | endpoint เช่น `/`, `/api/user`        |
| ✉️ จดหมาย                   | HTTP Request                          |
| 🖊️ วิธีส่งจดหมาย             | Method (GET, POST, PUT, DELETE)       |
| 🔔 การเปิดบ้านให้คนมาหาได้   | `app.listen(...)`                     |

![[20250331-2234-58.4582297.mp4]]

🧠 สรุปสั้น ๆ:
เมื่อมีคน "เคาะประตูบ้านเรา" ด้วย `GET /`
เราจะ "เปิดประตู" แล้วพูดว่า **"Hello World from GET request!"**

---

## **5. ใช้ Environment Variables** 🔐🌍

---

ในบางครั้ง เราจำเป็นต้องเก็บข้อมูลที่เป็น **ความลับ** หรือ **ขึ้นอยู่กับสภาพแวดล้อมของระบบ** เช่น:

- 🔑 รหัสผ่าน (Password)
- 🪪 Token สำหรับยืนยันตัวตน
- 🌐 URL ของ Database

ซึ่ง **ไม่ควรเก็บไว้ในโค้ดโดยตรง** ❌
เพราะหากเผลอแชร์โค้ดขึ้น GitHub หรือส่งให้คนอื่น ข้อมูลเหล่านี้อาจหลุดได้ง่าย

---

📦 **ตัวอย่างตัวแปรที่ควรใช้ Environment Variables เช่น:**

- `PORT` 👉 เพื่อให้เปลี่ยนพอร์ตได้ เช่น `3000` → `80` หรือ `443` เมื่อไป Production
- `DATABASE_URL` 👉 เปลี่ยนจาก `localhost` → IP Address ของ Server จริง
- `JWT_SECRET`, `API_KEY` และค่า Config ต่าง ๆ

---

🧰 **วิธีการจัดการ Environment Variables**

เราจะใช้ **package ที่ชื่อว่า `dotenv`**
เพื่อช่วยโหลดค่าจากไฟล์ `.env` เข้ามาเก็บใน `process.env` แบบอัตโนมัติ

📌 ไฟล์ `.env` จะเป็นไฟล์ที่แยกเก็บตัวแปรต่าง ๆ เช่น

```env
PORT=3000
DATABASE_URL=postgres://user:password@localhost:5432/mydb
```

จากนั้นในไฟล์ `index.js` หรือ `server.js` เราสามารถเขียนแบบนี้ได้:

``` javascript
import dotenv from 'dotenv';
dotenv.config();

const PORT = process.env.PORT || 3000;
```

✅ เมื่อเขียนแบบนี้ เราสามารถเปลี่ยนค่าโดยไม่ต้องแก้โค้ดเลย
เพียงแค่เปลี่ยนใน `.env` ก็เพียงพอ

🛡️ **ข้อดีของการใช้ Environment Variables**

- ปลอดภัย ✅

- ยืดหยุ่นต่อการ Deploy ✅

- ไม่ต้อง hard-code ค่าลงในโค้ด ✅

- ใช้ร่วมกับ CI/CD และระบบ Production ได้ง่าย ✅

---

### **5.1 ติดตั้ง dotenv** 📦🌱

เพื่อให้สามารถใช้ Environment Variables จากไฟล์ `.env` ได้
เราต้องติดตั้ง package ที่ชื่อว่า `dotenv` ก่อน

📌 พิมพ์คำสั่งใน Terminal เพื่อทำการติดตั้ง:

```bash
npm install dotenv
```

---
### **5.2 สร้างไฟล์ .env** 🗂️🌱

สร้างไฟล์ชื่อ `.env` ภายในโฟลเดอร์ `backend`
เพื่อเก็บค่าตัวแปรสภาพแวดล้อม (Environment Variables) ที่จำเป็นต่อโปรเจค

📌 ตัวแปรที่นิยมเก็บไว้ใน `.env` เช่น:
- `PORT=3000`
- `DATABASE_URL=...`
- `JWT_SECRET=...`

🛑 **ข้อควรระวัง**
- ห้าม push ไฟล์ `.env` ขึ้น GitHub หรือแชร์ให้ผู้อื่น ❗
- อย่าลืมเพิ่ม `.env` เข้าไฟล์ `.gitignore` ด้วยเพื่อความปลอดภัย 🔒

✅ เมื่อตั้งค่าใน `.env` แล้วสามารถเรียกใช้ได้ในโค้ดด้วย:
```javascript
process.env.PORT
```
---

### **5.3 ใช้งาน Environment Variables** 🛠️🌍
https://github.com/XunFlowerrr/backend-tutorial/tree/5bd678d99642c3ca359c4c4a83ab22345e8d426f

ในไฟล์ `index.js` ให้ทำการ `import` package `dotenv` ขึ้นมา
แล้วเรียกใช้ฟังก์ชัน `config()` เพื่อโหลด Environment Variables จากไฟล์ `.env`
เข้ามาไว้ใน `process.env` ของ Node.js


```javascript
//index.js
import express from "express";
import dotenv from "dotenv"; // Load environment variables
dotenv.config();
const app = express();
const PORT = process.env.PORT || 3000;

app.get("/", (req, res) => {
  res.send("Hello World from GET request!");
});
app.get("/api/user", (req, res) => {
  res.send("Hello World from GET request!");
});

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
});
```

![[20250331-2253-26.3410778.mp4]]

---
## **6. เขียนโค้ดเชื่อมต่อกับ Database** 🛠️🗄️🐘

---

### **6.1 ติดตั้ง pg** 📦🔌

ก่อนจะเชื่อมต่อกับ PostgreSQL Database
เราต้องติดตั้ง package ที่ชื่อว่า `pg` ซึ่งเป็นไลบรารีมาตรฐานในการใช้งาน PostgreSQL ร่วมกับ Node.js

📌 พิมพ์คำสั่งใน Terminal:

```bash
npm install pg
```

📚 **pg คืออะไร?**

- `pg` (ย่อมาจาก _node-postgres_) คือ package ที่ช่วยให้ Node.js สามารถเชื่อมต่อกับ **PostgreSQL** ได้อย่างสะดวก

- เราสามารถใช้ `pg` เพื่อ:

    - connect ไปยัง database

    - ส่ง query (SELECT, INSERT, UPDATE, DELETE)

    - จัดการผลลัพธ์ที่ได้กลับมา


✨ เมื่อติดตั้งเสร็จแล้วก็พร้อมเริ่มเขียนโค้ดเชื่อมต่อกับฐานข้อมูลได้ทันที!

---
### **6.2 สร้าง Folder ชื่อ config และข้างในสร้างไฟล์ database.js** 📁🗄️
https://github.com/XunFlowerrr/backend-tutorial/tree/7432c5a8d66eb8ac625130a8ddf7c078c436ddd0

สร้างโฟลเดอร์ชื่อ `config` ภายในโฟลเดอร์ `backend`
และภายใน `config` ให้สร้างไฟล์ชื่อ `database.js`


![[Pasted image 20250401061446.png]]


database.js
```javascript
//database.js
import pg from "pg";
import dotenv from "dotenv";

dotenv.config();


export const pool = new pg.Pool({ connectionString: process.env.DATABASE_URL });

export const query = async (text, params) => {

  const start = Date.now();

  const res = await pool.query(text, params);

  const duration = Date.now() - start;

  console.log("executed query", { text, duration, rows: res.rowCount });

  return res;

};
```

ใน .env ให้เพิ่ม DATABASE_URL ด้วยค่านี้

```env

PORT=3000

DATABASE_URL=postgres://admin:password@localhost:5432/taskmanagement

```

🧠 **ไฟล์ `database.js` จะเป็นที่เก็บโค้ดสำหรับเชื่อมต่อกับ PostgreSQL**
โดยจะเรียกใช้ `pg` ที่เราติดตั้งไว้ และใช้ค่าจาก `.env` ผ่าน `process.env`

![[20250331-2317-13.2749414.mp4]]


---


### **6.3 ทดสอบว่าต่อ Database สำเร็จหรือไม่** 🧪📡✅
https://github.com/XunFlowerrr/backend-tutorial/tree/3a4cd73444e9a296205756d4ae472b4c5e02ae8a

สร้างไฟล์ `test.js` ภายในโฟลเดอร์ `backend`
เพื่อใช้ทดสอบว่าโค้ดของเราสามารถเชื่อมต่อกับ **PostgreSQL Database** ได้สำเร็จหรือไม่

![[Pasted image 20250401110304.png]]

test.js
```javascript
//test.js
import { pool } from "./config/database.js";
import dotenv from "dotenv";

dotenv.config();
export const testConnection = async () => {
    try {
        const client = await pool.connect();
        console.log("Connected to the database");
        client.release();
      } catch (err) {
       console.error("Error connecting to the database", err);
      }
};

```

แล้วใน index.js ให้เรียกใช้ฟังก์ชัน testConnection() ใน app.listen()
```javascript
//index.js
import express from "express";
import dotenv from "dotenv";
import { testConnection } from "./test.js";

dotenv.config();
const app = express();
const PORT = process.env.PORT || 3000;

app.get("/", (req, res) => {
  res.send("Hello World from GET request!");
});

app.get("/api", (req, res) => {
  res.send("Hello World from API GET request!");
});

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
  testConnection();
});


```

![[Screen Recording 2025-04-01 111039.mp4]]

ถ้าขึ้นว่า
```bash
Connected to the database
```

✅ แสดงว่าเชื่อมต่อกับ Database สำเร็จแล้ว 🎉🎯


❌ แต่ถ้าขึ้นว่า `Error` หรือเชื่อมต่อไม่ได้
ให้ตรวจสอบตามนี้:

🔍 **ตรวจเช็กเบื้องต้น**:

- 🐳 Docker เปิดอยู่หรือไม่?

- 📦 Container PostgreSQL กำลังรันอยู่หรือเปล่า?

- 🔑 ค่าใน `.env` ถูกต้องไหม? เช่น `DATABASE_URL`


หาก Docker ยังไม่ได้เปิด ให้ย้อนกลับไปทำตามขั้นตอนนี้ก่อน:
👉 [[Backend Tutorial#^4e71ae|เปิด Docker]]

---

## **7. สร้าง Router และ Controller** 🧭🧩

---

**Router** คือการจัดการเส้นทาง (URL Paths) ที่เราต้องการให้ _[[Server]]_ ตอบสนองต่อ _[[Client]]_
โดยทั่วไปเราจะสร้าง Router แยกตามฟังก์ชันการทำงาน เช่น:

- 👤 `User`
- 📁 `Project`
- ✅ `Task`
- 📎 `Attachment`
- 👥 `Project Member`
- 👤 `Task Assignee`

📌 **เหตุผลที่ควรแยก Router ออกเป็นไฟล์ย่อย**:
- เมื่อแอปพลิเคชันเติบโตขึ้น 🔺 URL จะมีความซับซ้อนมากขึ้น
- หากเราเขียน Route ทุกอย่างไว้ใน `index.js` ไฟล์เดียว โค้ดจะดู **รก** และ **เข้าใจยาก**
- การแยกไฟล์จะช่วยให้โค้ด **อ่านง่าย**, **ดูแลรักษาง่าย** และ **จัดการเป็นระบบ** มากขึ้น ✅

---

🔶 **🏠 เปรียบเทียบแบบบ้าน – Router คือโถงทางเดิน** 🚪📌

- ลองนึกว่า `app` คือ **บ้านหลังหนึ่ง** 🏡
- ในบ้านมีหลาย "ห้อง" ที่แทนแต่ละ endpoint เช่น:
  - ห้อง `user`
  - ห้อง `project`
  - ห้อง `task`

---

- 👎 **ถ้าเขียน Route ทุกอย่างไว้ใน `index.js`**
  👉 ก็เหมือนการเอาประตูของทุกห้องไปวางไว้ "กลางบ้าน"
  📉 บ้านจะดู **รกรุงรัง** และจัดการยากมากเมื่อมีห้องเพิ่ม

- 👍 **ถ้าใช้ `Router` แยกเป็นไฟล์**
  👉 ก็เหมือนกับเรามี “โถงทางเดิน” ที่พาไปยังห้องต่าง ๆ อย่างเป็นสัดส่วน เช่น:
  - `userRouter` 👉 ทางเดินไปห้อง user
  - `taskRouter` 👉 ทางเดินไปห้อง task

🔗 จากนั้นเราค่อย **เชื่อมแต่ละโถงทางเดินเข้ากับบ้านหลัก (app)** ผ่าน `app.use(...)`

---

ตัวอย่างที่ไม่มีการใช้ Router
สมมติว่าเรามี API ที่มีหลาย Endpoint และ Endpoint นั้นยาวมากๆ เช่น

```javascript
//index.js
import express from "express";
import dotenv from "dotenv";
import { testConnection } from "./test.js";

dotenv.config();
const app = express();
const PORT = process.env.PORT || 3000;

app.get("/", (req, res) => {
  res.send("Hello World from GET request!");
});

app.get("/api/v1/user", (req, res) => {
  res.send("Hello World from API GET request!");
});

app.post("/api/v1/user", (req, res) => {
  res.send("Hello World from API POST request!");
});

app.put("/api/v1/user", (req, res) => {
  res.send("Hello World from API PUT request!");
});

app.delete("/api/v1/user", (req, res) => {
  res.send("Hello World from API DELETE request!");
});

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
  testConnection();
});
```

ซึ่งเทียบกับการใช้ Router
```javascript
//index.js
import express from "express";
import dotenv from "dotenv";
import { testConnection } from "./test.js";
import userRouter from "./userRouter.js";

dotenv.config();
const app = express();
const PORT = process.env.PORT || 3000;

app.get("/", (req, res) => {
  res.send("Hello World from GET request!");
});

app.use("/api/v1/user", userRouter); // โถงทางเดินที่พาไปยัง "ห้อง user"

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
  testConnection();
});
```

```javascript
// userRouter.js ตัวอย่างที่ 1
import express from "express";
const userRouter = express.Router();

userRouter.get("/", (req, res) => {
  res.send("Hello World from API GET request!");
});
userRouter.post("/", (req, res) => {
  res.send("Hello World from API POST request!");
});
userRouter.put("/", (req, res) => {
  res.send("Hello World from API PUT request!");
});
userRouter.delete("/", (req, res) => {
  res.send("Hello World from API DELETE request!");
});

export default userRouter;
```

หรือจะเป็นแบบนี้ก็ได้
```javascript
// userRouter.js ตัวอย่างที่ 2
import express from "express";
const userRouter = express.Router();

userRouter.route("/")
  .get((req, res) => {
    res.send("Hello World from API GET request!");
  })
  .post((req, res) => {
    res.send("Hello World from API POST request!");
  })
  .put((req, res) => {
    res.send("Hello World from API PUT request!");
  })
  .delete((req, res) => {
    res.send("Hello World from API DELETE request!");
  });

export default userRouter;
```
เห็นได้ว่าเรานั้น **ไม่ต้องมาเขียน `/api/v1/user` ซ้ำๆ หลายๆ ครั้ง**
และยังสามารถจัดการ Route ได้ **ง่ายขึ้น** และ **มีระบบมากขึ้น** ✅

---

 **ต่อไปคือ Controller** 🧑‍💼🧠

**Controller** คือส่วนที่จัดการ **Logic ของ API** ที่เราต้องการให้ _[[Server]]_ ทำงาน
เช่น:

- ดึงข้อมูลจาก Database 📥
- ประมวลผลข้อมูล 💡
- ส่งข้อมูลกลับไปยัง _[[Client]]_ 📤

---

🔶 **🧑‍🍳 เปรียบเทียบกับ “คนในห้อง” ที่มีหน้าที่เฉพาะทาง**

- 🧭 **Router** 👉 คือ **โถงทางเดิน** ที่พาเราไปยัง “ห้องต่างๆ”
  ⤷ เช่น `/api/v1/user`, `/api/v1/task`

- 🧑‍💼 **Controller** 👉 คือ **“คนที่อยู่ในห้องนั้นๆ”**
  ⤷ ที่ทำหน้าที่เฉพาะ เช่น จัดการข้อมูลผู้ใช้, ตรวจสอบสิทธิ์, ติดต่อกับฐานข้อมูล ฯลฯ

---

❌ ถ้าเรายัด logic ทั้งหมดไว้ใน Router โดยตรง
👉 ก็เหมือนกับเราให้ "พนักงานทุกคนมาทำงานอยู่กลางทางเดิน"
⤷ บ้านจะ **รก**, **ดูแลยาก**, และ **แก้โค้ดยาก** เมื่อระบบใหญ่ขึ้น

✅ ถ้าเราแยกเป็น Controller
👉 ก็เหมือนกับให้ **พนักงานแต่ละคนแยกอยู่ในห้องของตัวเอง**
⤷ ทำให้โค้ดสะอาด เป็นระบบ และขยายง่ายในอนาคต

---

📌 **สรุปแนวคิด Router & Controller:**

| ส่วนที่ทำหน้าที่ | เปรียบเทียบกับบ้าน | หน้าที่หลัก |
|------------------|----------------------|--------------|
| `Router`         | โถงทางเดิน 🏠        | จัดเส้นทาง รับคำขอ |
| `Controller`     | คนในห้อง 👨‍🔧         | ทำงานตามคำขอ |

---

💡 การแยก Controller ออกจาก Router เป็นแนวทางมาตรฐานในการเขียน Express App ที่ดี
ทั้ง **ช่วยให้โค้ดอ่านง่าย**, **ปรับปรุงง่าย**, และ **เหมาะสำหรับทีมพัฒนาหลายคน** 💪

---


จากตัวอย่างข้างบน

```javascript

// userRouter.js ตัวอย่างที่ 1

import express from "express";

const userRouter = express.Router();



userRouter.get("/", (req, res) => {

  res.send("Hello World from API GET request!");

});

userRouter.post("/", (req, res) => {

  res.send("Hello World from API POST request!");

});

userRouter.put("/", (req, res) => {

  res.send("Hello World from API PUT request!");

});

userRouter.delete("/", (req, res) => {

  res.send("Hello World from API DELETE request!");

});



export default userRouter;

```

เราจะเห็นว่า **Logic ของ API นั้นอยู่ใน Router** โดยตรง
ซึ่งทำให้โค้ดดู **ยุ่งเหยิง 🌀** และ **อ่านยาก 👀** โดยเฉพาะเมื่อโครงการใหญ่ขึ้น

---

💡 วิธีแก้คือ 👉 **แยก Logic (arrow function)** ออกไปเป็น **Controller**
โดยการสร้างไฟล์แยกออกจาก Router เช่น:

📁 สร้างไฟล์ชื่อ `userController.js` ภายในโฟลเดอร์ `controllers`

```javascript
// userController.js
export const getUser = (req, res) => {
  res.send("Hello World from API GET request!");
};

export const createUser = (req, res) => {
  res.send("Hello World from API POST request!");
};

export const updateUser = (req, res) => {
  res.send("Hello World from API PUT request!");
};

export const deleteUser = (req, res) => {
  res.send("Hello World from API DELETE request!");
};
```

แล้วใน userRouter.js ให้ import ฟังก์ชันจาก userController.js มาใช้
```javascript
// userRouter.js
import express from "express";
import { getUser, createUser, updateUser, deleteUser } from "./userController.js";

const userRouter = express.Router();

userRouter.get("/", getUser);
userRouter.post("/", createUser);
userRouter.put("/", updateUser);
userRouter.delete("/", deleteUser);

export default userRouter;
```

🎯 สรุป:
- `Router` = โถงทางเดินในบ้าน
- `Endpoint` = ห้องแต่ละห้อง
- `Method` = วิธีการส่งจดหมายไปยังห้อง (GET, POST, PUT, DELETE)
- `Controller` = คนในห้องที่รับคำสั่งและตอบกลับ

---
### **7.1 สร้าง Folder ชื่อ routes** 📁🧭

ให้สร้าง **โฟลเดอร์ชื่อ `routes`** และ **โฟลเดอร์ชื่อ `controllers`**

![[Pasted image 20250401114259.png]]

---

### **7.2 เดี๋ยวพาทำเกี่ยวกับ User และ Authentication ก่อน** 👤🔐

โอเค! ตอนนี้เราจะเริ่มทำ **ส่วนของ User** ก่อนนะ

โดย User ควรจะมีความสามารถพื้นฐาน ได้แก่:
- 📝 **ลงทะเบียน (Register)** = การสร้างบัญชีผู้ใช้ใหม่
- 🔐 **เข้าสู่ระบบ (Login)** = การตรวจสอบว่า user มีบัญชีในระบบหรือไม่
- 🚪 **ออกจากระบบ (Logout)** = ทำให้ผู้ใช้ไม่สามารถเข้าถึงข้อมูลส่วนตัวได้อีก (❗ ส่วนนี้จะอยู่ฝั่ง Frontend)

---

ดังนั้นเราจะเริ่มจากการสร้าง **Router และ Controller** สำหรับ User
โดยตั้งต้นจากสิ่งที่เกี่ยวข้อง ได้แก่:

- ✅ ลงทะเบียน (Register)
- ✅ เข้าสู่ระบบ (Login)

---

🔶 **🧑‍🍳 เปรียบเทียบกับคนในห้องที่ทำหน้าที่เฉพาะทาง**

- 🧭 **Router** 👉 คือ **โถงทางเดิน** ที่พาเราไปยัง “ห้องต่าง ๆ”
- 👨‍💻 **Controller** 👉 คือ **“คนในห้อง”** ที่ทำหน้าที่จริง เช่น จัดการข้อมูลผู้ใช้

---

📌 **โดยบ้านหลักเราอยู่ที่ (Starting Point):**
```
http://localhost:3000/
```


📌 **เรามีโถงทางเดินที่พาไปยังห้องที่เกี่ยวกับ User (authRouter):**

```
api/v1/auth
```


📌 **ในโถงทางเดินนี้ (`/api/v1/auth/`) มีห้องย่อย ๆ ดังนี้:**

- 📥 ห้องลงทะเบียน (Register): ใช้ **POST**

```
/register
```


- 🔑 ห้องเข้าสู่ระบบ (Login): ใช้ **POST**
```
/login
```

---

🧾 **ดังนั้น ปลายทางของ HTTP Request จะเป็น:**

```
POST http://localhost:3000/api/v1/auth/register
POST http://localhost:3000/api/v1/auth/login
```


---

📚 **เกร็ดความรู้: ทำไมต้องเป็น `/api/v1/auth/` ?**

📌 **API Versioning คืออะไร?**

เมื่อระบบของเราขยายตัว 📈
- ข้อมูลเปลี่ยนรูปแบบ
- เพิ่มเงื่อนไข เช่น OTP, OAuth
- เปลี่ยนโครงสร้าง JSON

หากเรา **เปลี่ยน API โดยไม่แยกเวอร์ชัน** 👉 ผู้ใช้เดิมจะเจอปัญหาทันที ❌

---

✅ **API Versioning** = การวางแผนระบบให้มั่นคงและยืดหยุ่น
โดยเพิ่มเวอร์ชันไว้ใน URL เช่น `/api/v1/`

🔹 ผู้ใช้เก่าใช้ `/api/v1/` ได้ต่อ โดยไม่เจอ error
🔹 ผู้ใช้ใหม่ใช้ `/api/v2/` ได้ทันที พร้อมฟีเจอร์ใหม่
🔹 นักพัฒนาแยกจัดการแต่ละรุ่นได้สะดวก

---

📌 **ตัวอย่าง Versioning**
- `/api/v1/auth/register` 👉 API รุ่นแรก
- `/api/v2/auth/register` 👉 รุ่นใหม่ที่อาจรองรับ OTP หรือ OAuth

---

❌ ถ้าไม่มี API Versioning:
- แอปเก่าอาจพังทันที
- ต้องเขียนโค้ดซับซ้อนเพื่อรองรับหลายรูปแบบใน endpoint เดียว
- การทดสอบและดูแลจะยุ่งยากมาก

---

🎯 **สรุป:**
> การใช้ `/api/v1/` คือการ **จัดระเบียบ**, **แยกเวอร์ชัน**, และ **วางแผนอนาคตของระบบ**
> เพื่อให้ระบบเติบโตได้อย่างมั่นคง แข็งแรง และไม่พังง่าย 💪🌱

---

#### 7.2.1 สร้างไฟล์ authRouter.js ใน Folder routes
https://github.com/XunFlowerrr/backend-tutorial/tree/acb2a4ebb6cd82f36877d3931523f38378ec48dd

![[Pasted image 20250402184715.png]]

authRouter.js
```javascript
// authRouter.js
import express from "express";
import { registerUser, loginUser } from "../controllers/authController.js";

const router = express.Router();

router.post("/register", registerUser);
router.post("/login", loginUser);

export default router;
```

---

#### **7.2.2 สร้างไฟล์ authController.js ใน Folder controllers** 🧠📄
https://github.com/XunFlowerrr/backend-tutorial/tree/85e75bae8712e70092e5bd4111338ce07c90020a

ให้สร้างไฟล์ชื่อ `authController.js` ภายในโฟลเดอร์ `controllers`

![[Pasted image 20250402190106.png]]

```javascript
// authController.js
export const registerUser = async (req, res) => {
  res.status(200).send({ message: "User registered successfully" });
};
export const loginUser = async (req, res) => {
  res.status(200).send({ message: "User logged in successfully" });
};
```

📌 ในขั้นตอนนี้ **ยังไม่ต้องเขียน Logic อะไรจริงจัง**
เพียงแค่เขียนฟังก์ชันเพื่อ **ทดสอบว่า Router เชื่อมกับ Controller ถูกต้องหรือไม่** ✅


---


#### **7.2.3 เพิ่ม authRouter ใน index.js** 🧩🔗
https://github.com/XunFlowerrr/backend-tutorial/tree/a00824662dbaf33f1513ef8e8f0000314cd6d482

ในไฟล์ `index.js` ให้ทำการ **import `authRouter` เข้ามา**
แล้วใช้ Router ที่เราสร้างขึ้น โดยเชื่อมกับ prefix `/api/v1/auth` เพื่อให้ URL มีความเป็นระบบ


📌 ตัวอย่างสิ่งที่ต้องทำใน index.js:

1. 📥 import `authRouter` จากโฟลเดอร์ `routes`
2. 🔗 ใช้ `app.use()` เพื่อเชื่อม prefix กับ `authRouter`

```javascript
// index.js
import express from "express";
import dotenv from "dotenv";
import { testConnection } from "./test.js";
import authRouter from "./routes/authRouter.js";

dotenv.config();
const app = express();
const PORT = process.env.PORT || 3000;

app.use("/api/v1/auth/", authRouter); // เพิ่ม Router ที่เราสร้างขึ้น

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
  testConnection();
});
```

เค้าจะใช้ **Postman** 🧪📬 ในการทดสอบ API ของเรา

---

🔧 **Postman คืออะไร?**

**Postman** เป็นเครื่องมือสำหรับ **ทดสอบ API** โดยเฉพาะ
เราสามารถใช้ Postman เพื่อ:

- 📨 ส่ง Request ไปยัง API ของเรา (GET, POST, PUT, DELETE ฯลฯ)
- 🔎 ดู Response ที่ได้จาก Server
- 📋 ตั้งค่าพารามิเตอร์, headers, body, token ฯลฯ ได้ตามต้องการ
- 🧪 ทดสอบ API แบบไม่ต้องเขียน frontend หรือสร้างหน้าฟอร์มเอง

---

💡 Postman ช่วยให้การทดสอบ API ง่ายขึ้นมาก
โดยเฉพาะในขั้นตอนที่เราต้องการดูว่า:

- ✅ Route ที่เราสร้างไว้ทำงานหรือยัง
- ✅ Controller ส่ง response กลับมาหรือเปล่า
- ✅ ค่า body/query/header ถูกต้องไหม

---

📌 เดี๋ยวเราจะลองใช้ **Postman** เพื่อทดสอบว่า
เราได้สร้าง **Router** และ **Controller** สำหรับ Auth (`register` และ `login`) ถูกต้องหรือไม่

---

#### **7.2.4 ทดสอบ API ด้วย Postman** 🧪📬

เพื่อทดสอบว่าเราสร้าง **Router และ Controller** สำหรับ `User` ได้ถูกต้อง
ให้ทำตามขั้นตอนนี้:

---

##### ✅ ขั้นตอนการทดสอบ API ด้วย Postman

1. 🐳 **ตรวจสอบว่า Docker กำลังรันอยู่**
   ⤷ PostgreSQL ต้องรันใน Container เพื่อรองรับการเชื่อมต่อ

2. ▶️ **เปิดรัน backend** ด้วยคำสั่ง:
```bash
npm run dev
```

3. 📬 **เปิด Postman** ขึ้นมา
4. ➕ **สร้าง Request ใหม่** โดยเลือก Method เป็น `POST`
5. 🌐 **ใส่ URL เป็น**:
```
http://localhost:3000/api/v1/auth/register
```

6. 🚀 กดปุ่ม Send
7. ✅ **หากสำเร็จ จะได้ Response กลับมาว่า:**
```json
{
    "message": "User registered successfully"
}
```

![[Untitled video - Made with Clipchamp.mp4]]

ถ้าทำสำเร็จ ✅
จะแสดงว่าเราได้สร้าง **Router และ Controller สำหรับ User** ได้ **ถูกต้องแล้ว** 🎉

---

❗แต่ตอนนี้เรายังไม่ได้ส่ง **ข้อมูลใด ๆ** ไปยัง Backend เลย
เราส่งเพียงแค่ **Request เปล่า ๆ** แบบไม่มีเนื้อหาไปเท่านั้น

---

📦 ดังนั้นในขั้นตอนถัดไป
เราจะต้องเรียนรู้การ **ส่งข้อมูลไปยัง Backend** ด้วย — เช่น
ชื่อผู้ใช้ (username), รหัสผ่าน (password) หรือข้อมูลลงทะเบียนต่าง ๆ

🔜 เพื่อให้ Server สามารถรับและจัดการข้อมูลที่ส่งมาจาก _[[Client]]_ ได้อย่างถูกต้อง

---

#### **7.2.5 ส่งข้อมูลไปยัง Backend** 📦➡️🖥️
https://github.com/XunFlowerrr/backend-tutorial/tree/a176b3385ec420b326f7f1565acb91c81e89303d

ในตอนนี้ เราจะลอง **ส่งข้อมูลจาก Postman ไปยัง Backend**
โดยใช้ **Body ของ Request** ✨

---

📌 **Body คืออะไร?**
Body คือ **ข้อมูลที่ฝั่ง Client (เช่น Frontend หรือ Postman)** ต้องการส่งไปยัง Backend
โดยข้อมูลที่ส่งมาใน Body อาจมีได้หลายรูปแบบ เช่น:

- 🧾 **JSON** (นิยมที่สุดสำหรับ REST API)
- 📝 Form Data
- 🔤 x-www-form-urlencoded

---

📍 ในที่นี้เราจะใช้ **JSON** เป็นรูปแบบในการส่งข้อมูลไปยัง Backend
เพราะอ่านง่าย, ใช้งานสะดวก และเป็นมาตรฐานในการพัฒนา API

---

⚠️ แต่ก่อนที่ Backend ของเราจะสามารถรับ Body ที่เป็น JSON ได้
เราจำเป็นต้อง **บอก Express ให้แปลง JSON ให้เราก่อน**
โดยใช้สิ่งที่เรียกว่า **Body Parser **

ใน index.js ให้เพิ่ม
```javascript
// index.js
import express from "express";
import dotenv from "dotenv";
import { testConnection } from "./test.js";
import authRouter from "./routes/authRouter.js";

dotenv.config();
const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.json()); // เพิ่มการใช้ Body Parser
app.use("/api/v1/auth", authRouter);

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
  testConnection();
});

```

และในไฟล์ `authController.js` 📄
ให้เพิ่มการ **รับข้อมูลจาก Body ของ Request** เพื่อให้ Backend สามารถอ่านข้อความที่ Client ส่งมาได้

---

##### ✅ วิธีรับข้อมูลจาก `req.body`

ในฟังก์ชันของ Controller เช่น `register` หรือ `login`
เราสามารถดึงค่าจาก `req.body` ได้โดยตรง (หลังจากตั้งค่า `express.json()` ใน `index.js` แล้ว)

---


```javascript
// authController.js
export const registerUser = async (req, res) => {
  const { username, password } = req.body; // รับข้อมูลจาก Body
  res
    .status(200)
    .send({ message: "User registered successfully", username, password });
};
export const loginUser = async (req, res) => {
  const { username, password } = req.body; // รับข้อมูลจาก Body
  res
    .status(200)
    .send({ message: "User logged in successfully", username, password });
};

```

และใน **Postman** 🧪 ให้ทำตามขั้นตอนต่อไปนี้เพื่อส่งข้อมูลแบบ JSON ไปยัง Backend:

---

##### 🧾 วิธีส่งข้อมูล JSON จาก Postman

1. ✅ ไปที่ **แท็บ "Body"**

2. 🔘 เลือกตัวเลือก **raw**

3. 📄 ทางขวา ให้เลือกประเภทเป็น **JSON** (ไม่ใช่ Text)

4. 🧑‍💻 จากนั้นให้ใส่ข้อมูลลงไปในช่อง Body ตามตัวอย่างนี้:

```json
{
  "username": "johndoe",
  "password": "123456"
}
```
5. 🚀 กดปุ่ม **Send** เพื่อส่งข้อมูลไปยัง Backend
6. ✅ **หากสำเร็จ จะได้ Response กลับมาว่า:**
```json
{
    "message": "User registered successfully",
    "username": "johndoe",
    "password": "123456"
}
```

![[20250402-1242-22.4709951.mp4]]

---

#### **7.2.6 ทำ Logic การลงทะเบียน (Register)** 📝🔐
https://github.com/XunFlowerrr/backend-tutorial/tree/a1973f675acafb96a2c0c5975e4f1d003b393c6c

ในไฟล์ `authController.js` เราจะเริ่มทำ **Logic สำหรับการลงทะเบียน (Register)** และ **เข้าสู่ระบบ (Login)**

---

❗ แต่มีประเด็นสำคัญเกี่ยวกับการเก็บข้อมูล User คือ...

> เราไม่ควรเก็บ **Password** ของ User ไว้ใน Database แบบไม่เข้ารหัส ❌

เพราะถ้ามีผู้ไม่หวังดีเข้าถึงฐานข้อมูลได้ ก็จะสามารถเห็น Password ของผู้ใช้ทุกคนทันที ซึ่งเป็นอันตรายอย่างมากต่อระบบและผู้ใช้

---

🔐 แล้วควรทำยังไงดี?

เราจะใช้ **Library ที่ชื่อว่า `bcrypt`**
ซึ่งเป็นเครื่องมือยอดนิยมที่ช่วยให้เรา **เข้ารหัส (Encrypt)** ข้อมูลได้อย่างปลอดภัย โดยเฉพาะ Password

`bcrypt` มีฟังก์ชันให้ใช้ทั้ง:
- การเข้ารหัสข้อมูล (Hash)
- การเปรียบเทียบข้อมูลกับรหัสที่ถูกเข้ารหัสไว้ (Compare)

---

🧠 เกร็ดความรู้: Hash Function คืออะไร?

- `Hash` คือการแปลงข้อมูล เช่น Password ให้กลายเป็นข้อความที่อ่านไม่ออก
- จุดสำคัญคือ⚠️:
  - hash function นั้นมีขั้นตอนการเข้ารหัสที่แน่นอน ซึ่งหมายความว่า
  - ถ้า Input เหมือนกัน → ผลลัพธ์ที่ได้จาก Hash ก็จะเหมือนกันทุกครั้ง
  - ซึ่งหมายความว่า hash function จะให้ผลลัพธ์ที่เหมือนกันสำหรับข้อมูลที่เหมือนกันเสมอ

ซึ่งนำไปสู่ **ปัญหา** หากมีผู้ใช้ 2 คนใช้ Password เดียวกัน
ระบบก็จะเก็บค่า Hash ที่เหมือนกันไว้ใน Database
และถ้าแฮกเกอร์รู้ Hash ของ Password หนึ่งคน ก็จะรู้ทันทีว่าอีกคนใช้ Password เดียวกันด้วย

---

🧂 แล้ว Salt ช่วยอะไร?

เพื่อแก้ปัญหานี้ จึงมีสิ่งที่เรียกว่า **Salt**
ซึ่งก็คือการ “สุ่มข้อความพิเศษ” มาต่อท้าย Password ก่อนจะทำการ Hash

ข้อดีของ Salt:
- เพิ่มความแตกต่างให้กับ Password ที่เหมือนกัน
- ป้องกันการเปรียบเทียบ Hash แบบตรง ๆ
- เพิ่มความปลอดภัยให้ระบบอีกระดับ

Salt จะถูกสร้างขึ้นใหม่ทุกครั้งที่มีผู้ใช้ทำการลงทะเบียน
แม้ว่าผู้ใช้สองคนจะใช้ Password เดียวกัน แต่เนื่องจาก Salt ไม่เหมือนกัน
จึงทำให้ Hash ที่ได้ก็ **ไม่เหมือนกัน** ด้วย

ตัวอย่าง

```javascript

const bcrypt = require("bcrypt");



const password1 = "test";

const password2 = "test";



// bcrypt.hashSync คือการ Hash Password

const hashedPassword1 = bcrypt.hashSync(password1, 10); // 10 คือการใส่ Salt

const hashedPassword2 = bcrypt.hashSync(password2, 10); // 10 คือการใส่ Salt



console.log("Hashed Password 1:", hashedPassword1);

console.log("Hashed Password 2:", hashedPassword2);

```



Output

```

Hashed Password 1: $2b$10$F4ZNSJRu7HWsqc7GenrerOx1NbsMTzh36l6nhZUDjBOyJpoVfu/im

Hashed Password 2: $2b$10$a2nwTbO1is7pg5ZOOoZplu7dRbBn43ArHwIg1F.s4Wf9L4zhL1606

```

จะเห็นว่า **Hashed Password 1** และ **Hashed Password 2** นั้น **ไม่เหมือนกัน**
แม้ว่าจะใช้ **Password เดียวกัน** ก็ตาม 🧂🔐

✨ ดังนั้น...
> การใช้ **Salt** จะทำให้ Password ที่เก็บใน Database นั้นไม่ซ้ำกัน
> แม้ว่า User หลายคนจะใช้ Password เดียวกันก็ตาม

---

📌 ดังนั้น เราจะใช้ **Package นี้ (`bcrypt`)** ในการ **เข้ารหัส Password ของ User**
ก่อนที่จะบันทึกลงใน Database ✅

##### 🛠️ เริ่มทำกันเลย

> **ติดตั้ง `bcrypt`** เพื่อใช้งานในโปรเจค

```bash

npm install bcrypt

```

แล้วใน authController.js ให้ทำการ import bcrypt เข้ามา
```javascript
// authController.js
import bcrypt from "bcrypt";
import { query } from "../config/database.js";

export async function registerUser(req, res) {
  try {
    const { username, email, password } = req.body; // รับข้อมูลจาก Body

    // เช็คว่ามีข้อมูลครบถ้วนหรือไม่
    if (!username || !email || !password) {
      return res.status(400).json({
        error: "Please provide username, email, and password.",
      });
    }

    // ใส่ role ไว้ก่อน
    const role = "user";

    // เช็คว่ามี email นี้อยู่ในระบบหรือไม่ ถ้ามีให้ return error
    const existing = await query("SELECT * FROM users WHERE email = $1", [
      email,
    ]);
    if (existing.rowCount > 0) {
      return res.status(400).json({
        error: "User with this email already exists.",
      });
    }

    // สร้าง user_id ใหม่
    const idRes = await query("SELECT generate_user_id() as id");
    const user_id = idRes.rows[0].id;

    // ใช้ bcrypt ในการเข้ารหัส Password พร้อมกับ Salt
    const hashedPassword = await bcrypt.hash(password, 10);

    // สร้าง User ใหม่ใน ตาราง users
    await query(
      `INSERT INTO users (user_id, username, email, password, role)
       VALUES ($1, $2, $3, $4, $5)`,
      [user_id, username, email, hashedPassword, role]
    );

    // ส่ง Response กลับไปว่า User ลงทะเบียนสำเร็จ
    res.status(201).json({
      success: true,
      message: "Registration successful",
      userId: user_id,
    });
  } catch (error) {
    // ถ้ามี Error ให้ส่ง Response กลับไปว่า Internal server error
    res.status(500).json({ error: "Internal server error" });
  }
} catch (error) {
  // Handle any unexpected errors
  console.error(error);
  res.status(500).json({ error: "Internal server error" });
}

export const loginUser = async (req, res) => {
  const { username, password } = req.body; // รับข้อมูลจาก Body
  res
    .status(200)
    .send({ message: "User logged in successfully", username, password });
};

```
---

#### **7.2.7 ทำ Logic การเข้าสู่ระบบ (Login)** 🔐👤
https://github.com/XunFlowerrr/backend-tutorial/tree/48a3b944bd471bd1cd00ad15a203c7a6269055c2

โอเค! ตอนนี้เราจะเริ่มเขียน **Logic สำหรับการเข้าสู่ระบบ (Login)**
โดยมีเป้าหมายคือ 👉 ตรวจสอบว่า User ที่ส่งข้อมูลเข้ามา **มีอยู่ในระบบหรือไม่**

---

❗ แต่การ Login ก็มีประเด็นสำคัญเหมือนกัน

เราทำงานฝั่ง Backend — แล้วจะรู้ได้ยังไงว่า Frontend “Login แล้ว” จริงไหม?

---

📌 สมมุติว่า User คนหนึ่ง Login สำเร็จผ่านหน้าเว็บไซต์
แล้วเข้าไปยังหน้า **Dashboard**
**คำถามคือ:**
> เรา (ฝั่ง Backend) จะรู้ได้ยังไงว่า User คนนี้ Login แล้วจริง ๆ?

---

✅ วิธีที่นิยมใช้ในการแก้ปัญหานี้ก็คือ...

> ส่ง **Token (โทเคน)** กลับไปให้ฝั่ง Frontend
> ทันทีหลังจากที่ Login สำเร็จ

---

🔑 **Token คืออะไร?**

- Token คือ “หลักฐานยืนยันตัวตน” 🪪
- เป็นค่าที่ Backend สร้างขึ้น หลังจากตรวจสอบว่า Login สำเร็จ
- ฝั่ง Frontend จะเก็บ Token ไว้ (เช่นใน LocalStorage หรือ Cookie)
- และ **ต้องแนบ Token นี้มาด้วยทุกครั้ง** ที่เรียก API ที่ต้องมีการยืนยันตัวตน

---

🔐 แล้วเราจะสร้าง Token อย่างไร?

💡 คำตอบคือ...
> เราจะใช้เครื่องมือที่ชื่อว่า **JWT (JSON Web Token)**

---

📦 **JWT คืออะไร?**

**JWT (JSON Web Token)** คือมาตรฐานในการเข้ารหัสข้อมูลให้อยู่ในรูปแบบของ Token
ที่สามารถใช้ส่งข้อมูลระหว่างระบบได้ **อย่างปลอดภัย** 🔒

📌 โครงสร้างของ JWT แบ่งเป็น 3 ส่วนหลัก:

1. **Header** – ระบุชนิดของ Token และวิธีเข้ารหัส (เช่น `HS256`)
2. **Payload** – ส่วนที่เก็บข้อมูลของผู้ใช้ เช่น `user_id`, `email`, `role`
3. **Signature** – ลายเซ็นที่ใช้ตรวจสอบความถูกต้องของ Token (ถูกสร้างโดย Server เท่านั้น)

---

🧠 สรุปกระบวนการ:

1. เมื่อ User Login สำเร็จ ✅
2. Backend จะสร้าง **JWT Token**
3. ข้อมูลของ User บางส่วนจะถูกฝังไว้ใน **Payload**
4. จากนั้น Backend จะ **ส่ง Token กลับให้ Frontend**
5. Frontend จะเก็บ Token นั้นไว้ (ใน LocalStorage หรือ Cookie)
6. ทุกครั้งที่เรียก API ถัด ๆ ไป → Frontend ต้องแนบ Token มาใน **HTTP Header**

---

##### ดังนั้นต่อกันเลยยย

เราจะใช้ Package ที่ชื่อว่า jsonwebtoken ในการสร้าง Token เพื่อใช้ในการยืนยันตัวตนของผู้ใช้
โดยการติดตั้ง Package นี้ก่อน
```bash
npm install jsonwebtoken
```

แล้วใน authController.js ให้ทำการ import jsonwebtoken เข้ามา
```javascript
// authController.js
import bcrypt from "bcrypt";
import { query } from "../config/database.js";
import jwt from "jsonwebtoken";

export async function registerUser(req, res) {
  try {
    const { username, email, password } = req.body; // รับข้อมูลจาก Body

    // เช็คว่ามีข้อมูลครบถ้วนหรือไม่
    if (!username || !email || !password) {
      return res.status(400).json({
        error: "Please provide username, email, and password.",
      });
    }

    // ใส่ role ไว้ก่อน
    const role = "user";

    // เช็คว่ามี email นี้อยู่ในระบบหรือไม่ ถ้ามีให้ return error
    const existing = await query("SELECT * FROM users WHERE email = $1", [
      email,
    ]);
    if (existing.rowCount > 0) {
      return res.status(400).json({
        error: "User with this email already exists.",
      });
    }

    // สร้าง user_id ใหม่
    const idRes = await query("SELECT generate_user_id() as id");
    const user_id = idRes.rows[0].id;

    // ใช้ bcrypt ในการเข้ารหัส Password พร้อมกับ Salt
    const hashedPassword = await bcrypt.hash(password, 10);

    // สร้าง User ใหม่ใน ตาราง users
    await query(
      `INSERT INTO users (user_id, username, email, password, role)
       VALUES ($1, $2, $3, $4, $5)`,
      [user_id, username, email, hashedPassword, role]
    );

    // ส่ง Response กลับไปว่า User ลงทะเบียนสำเร็จ
    res.status(201).json({
      success: true,
      message: "Registration successful",
      userId: user_id,
    });
  } catch (error) {
    // Handle any unexpected errors
    console.error(error);
    res.status(500).json({ error: "Internal server error" });
  }
}

export async function loginUser(req, res) {
  try {
    const { email, password } = req.body; // รับข้อมูลจาก Body

    // เช็คว่ามีข้อมูลครบถ้วนหรือไม่
    if (!email || !password) {
      return res.status(400).json({
        error: "Please provide email and password.",
      });
    }

    // หา User ใน Database
    const userRes = await query("SELECT * FROM users WHERE email = $1", [
      email,
    ]);
    if (userRes.rowCount === 0) {
      return res.status(401).json({ error: "Invalid credentials" });
    }

    const user = userRes.rows[0];

    // ตรวจสอบ Password กับ Hashed Password ที่เก็บใน Database
    const passwordMatch = await bcrypt.compare(password, user.password);
    if (!passwordMatch) {
      return res.status(401).json({ error: "Invalid credentials" });
    }

    // สร้าง JWT Token โดยใช้ fucntion generateToken ที่เราสร้างขึ้น
    const token = generateToken(user);

    console.info(`User ${user.user_id} logged in successfully`);

    // ส่ง Response กลับไปว่า User Login สำเร็จ
    res.status(200).json({
      success: true,
      token,
      userId: user.user_id,
      name: user.username || user.email.split("@")[0],
      email: user.email,
    });
  } catch (error) {
    // ถ้ามี Error ให้ส่ง Response กลับไปว่า Internal server error
    console.error("Login error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

function generateToken(user) {
  // สร้าง JWT Token โดยใช้ jsonwebtoken jwt.sign คือ ฟังก์ชันที่ใช้ในการสร้าง Token โดยที่เราจะส่งข้อมูลที่เราต้องการเก็บใน Token ไป
  return jwt.sign(
    {
      userId: user.user_id,
      email: user.email,
      role: user.role,
    },
    process.env.JWT_SECRET, // Secret Key ที่ใช้ในการเข้ารหัส Token
    { expiresIn: "15d" }
  );
}

```

^055acc

ก่อนใช้งาน **JWT Token** 🪪 เราจำเป็นต้องมีการ **สร้าง Secret Key** ขึ้นมาก่อน

---

 🔐 Secret Key คืออะไร?

- Secret Key คือ “กุญแจลับ” ที่ใช้สำหรับ:
  - 🔏 **เข้ารหัส Token**
  - ✅ **ตรวจสอบความถูกต้องของ Token**

📌 **สำคัญมาก:**
> Secret Key นี้ต้องเป็น **ความลับ** ห้ามเปิดเผยหรือแชร์ให้คนอื่นเด็ดขาด
> เพราะถ้ามีใครรู้ Secret นี้ ก็สามารถปลอมแปลง Token ได้ทันที ❗

ในที่นี้เราจะใส่ String อะไรก็ได้ลงไปก่อน
ไปที่ไฟล์ .env แล้วเพิ่มบรรทัดนี้เข้าไป

ในไฟล์ .env
```bash
PORT=3000
DATABASE_URL=postgres://admin:password@localhost:5432/taskmanagement
JWT_SECRET=your_jwt_secret
```

แล้วลองทดสอบ Login ใหม่ใน Postman โดยการส่ง POST Request ไปที่
```
http://localhost:3000/api/v1/auth/login
```
และ Body
```
{
    "email" : "test@gmail.com",
    "password" : "testpassword"
}
```

แล้วกด Send

![[20250402-1930-54.5167538.mp4]]

ถ้าทำได้สำเร็จจะได้รับการตอบกลับเป็นแบบด้านล่าง และเราจะได้ Token มาด้วย
``` json
{
    "success": true,
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9....",
    "userId": "00001",
    "name": "testuser",
    "email": "test@gmail.com"
}
```
ใน **Token** ที่เราสร้างขึ้นมานั้น 🪪
จะมี **ข้อมูลของผู้ใช้** ที่ Backend **ฝังไว้** ก่อนส่งกลับไปให้ Frontend เก็บไว้

📌 ข้อมูลที่ฝังอยู่ใน Token จะขึ้นอยู่กับ Function
👉 `generateToken` ที่เราเขียนไว้ในโปรเจกต์
[[Backend Tutorial#^055acc| Function Generate Token]]

---

🧪 เราสามารถ **ลองนำ Token ที่ได้มาถอดรหัสดู** ได้ที่เว็บไซต์:

🔗 https://jwt.is/

---

![[20250403-0534-27.1798150.mp4]]

![[Pasted image 20250403123553.png]]

---

จากในภาพจะเห็นว่า…

📌 เมื่อเรานำ Token ที่สร้างไว้ไปถอดรหัส
จะพบว่า **Payload ของ Token** มีข้อมูลที่เราฝังไว้ เช่น `userId`, `email`, `role` ฯลฯ

✅ สิ่งเหล่านี้คือ "ตัวตน" ของผู้ใช้ที่ถูกยืนยันแล้ว

---

 🚀 แล้ว Token นี้เอาไปทำอะไร?

หลังจากที่ Login สำเร็จ
> ฝั่ง **Frontend** จะต้องเก็บ Token นี้ไว้ (ใน LocalStorage หรือ Cookie)
> และ **แนบ Token นี้มากับทุก Request** ที่ต้องการยืนยันตัวตน

เช่น:
- การเรียกดูข้อมูลโปรไฟล์
- การแก้ไขข้อมูลผู้ใช้
- การเข้าถึง resource ส่วนตัว ฯลฯ

---

 🔍 ฝั่ง Backend จะทำอย่างไร?

เมื่อ Backend ได้รับ Request ที่มี Token แนบมา
> Backend จะ **ถอดรหัส Token** เพื่อตรวจสอบว่า Token นี้เป็นของใคร
> และใช้ข้อมูลจากใน Token เพื่อตัดสินใจว่าจะอนุญาตให้ทำ Operation นั้น ๆ หรือไม่

---

🎉 **โอเค!** ตอนนี้เราสามารถ **ยืนยันตัวตนของผู้ใช้ผ่าน JWT Token ได้แล้ว!**

---

### **7.3 สร้าง Middleware** 🧩🔐

---

**Middleware** คือ ฟังก์ชันพิเศษที่ทำงาน **อยู่ระหว่าง** `Request` และ `Response`
มันจะถูกเรียกใช้ก่อนที่คำขอ (Request) จะไปถึง **Route Handler** จริง ๆ

---

 🧠 Middleware มีประโยชน์อย่างไร?

- ✅ ใช้ในการตรวจสอบว่า **Token** ที่ส่งมาจาก Client (Frontend) ถูกต้องหรือไม่
- ✅ ถ้าถูกต้อง ก็จะ **ถอดรหัส Token**
- ✅ จากนั้นจะ **แนบข้อมูลของผู้ใช้** กลับเข้าไปใน `Request`
- ✅ แล้วส่งต่อไปยัง Route Handler ให้ดำเนินการต่อได้ทันที

---

🖼️ มาดูภาพรวมการทำงานของ Middleware

---

📩 **1. เริ่มต้นที่มี HTTP Request เข้ามายัง Backend**

![[Pasted image 20250403141514.png]]

- เมื่อมีคำขอเข้ามาที่ API
- **Router** จะตรวจสอบว่า เส้นทางนั้นมีการกำหนด Middleware ไว้หรือไม่
- ถ้ามี จะ **ส่งต่อ Request ไปให้ Middleware ทำงานก่อน**

---

🔍 **2. Middleware ตรวจสอบ Token + ถอดรหัส**

![[Pasted image 20250403142108.png]]

- Middleware จะดูว่าใน Request มี Token มาหรือไม่ (ส่วนมากอยู่ใน Header)
- จากนั้นจะ **ตรวจสอบว่า Token ถูกต้องหรือไม่**
- ถ้า Token ถูกต้อง → จะ **ถอดรหัส Token** และดึงข้อมูล User ออกมา

---

📥 **3. แนบข้อมูล User กลับเข้าไปใน Request**

![[Pasted image 20250403142504.png]]

- Middleware จะทำการ **แนบข้อมูลของผู้ใช้ (เช่น userId, email)** เข้าไปใน `req.user`
- แล้วส่ง `req` นี้ไปยัง Route Handler ต่อไป

---

🛠️ **4. Route Handler ใช้งานข้อมูลที่ Middleware ส่งต่อมา**

![[Pasted image 20250403142926.png]]

- Route Handler สามารถ **อ่านข้อมูล User** จาก `req.user`
- และใช้ข้อมูลนี้เพื่อระบุว่า **ใครคือคนที่เรียก API นี้**
- หรือจะใช้สำหรับตรวจสอบสิทธิ์ (Authorization) ก็ได้

---

🎉 เท่านี้เราก็สามารถรู้ได้แล้วว่า
> ✅ ผู้ใช้ที่เรียก API นี้คือใคร
> ✅ Token ถูกต้องหรือไม่
> ✅ มีสิทธิ์เรียก API นี้หรือเปล่า

---

#### **7.3.1 สร้างไฟล์ Middleware** 🛠️📁
https://github.com/XunFlowerrr/backend-tutorial/tree/79cbf1fdd6f20e7f779d7a38910bb435438b4a6a

เริ่มต้นด้วยการสร้างโฟลเดอร์ใหม่ชื่อว่า `middleware` ภายในโฟลเดอร์ `backend` และสร้างไฟล์ authMiddleware.js ขึ้นมา

![[Pasted image 20250403144939.png]]


```javascript
import jwt from "jsonwebtoken";

export function authMiddleware(req, res, next) {
  try {
    // เช็คว่า request มี header Authorization หรือไม่
    const authHeader = req.headers.authorization;
    let token = null;

    // ดึง token จาก header Authorization ถ้ามี
    if (authHeader && authHeader.startsWith("Bearer ")) {
      token = authHeader.split(" ")[1];
    }
    // ถ้าไม่มี token ใน header Authorization ให้ลองดึงจาก cookie
    else if (req.cookies && req.cookies.token) {
      token = req.cookies.token;
    }

    // ถ้าไม่มี token ให้ส่ง response กลับไปว่าไม่อนุญาตให้เข้าถึง
    if (!token) {
      return res.status(401).json({ error: "Authentication required" });
    }

    // ถ้ามี token ให้ทำการ verify token ด้วย secret key
    try {
      // อันนี้คือการถอดรหัส token ออกมาโดยใช้ secret key ไว้ตรวจสอบว่า Token ที่ส่งมานั้นถูกต้องหรือไม่
      const decoded = jwt.verify(token, process.env.JWT_SECRET);
      req.user = decoded; // เก็บข้อมูลผู้ใช้ใน request object ก่อนส่งต่อไปยัง route handler function
      next(); // ถ้า token ถูกต้อง ให้เรียกใช้ next() เพื่อไปยัง route handler ถัดไป
    } catch (jwtError) {
      console.error("JWT verification failed", jwtError);
      return res.status(401).json({ error: "Invalid or expired token" });
    }
  } catch (err) {
    console.error("Auth middleware error", err);
    return res.status(500).json({ error: "Authentication error" });
  }
}
```
---

#### 7.3.2 ลองสร้าง Endpoint ใหม่เพื่อลองดึงข้อมูล User ดู
https://github.com/XunFlowerrr/backend-tutorial/tree/5eb1998b8a2266bf29b34ec529da315461044080
ในไฟล์ authRouter.js ให้ลองสร้าง Endpoint ใหม่ขึ้นมา
```javascript
// authRouter.js
import express from "express";
import { registerUser, loginUser,  getMe } from "../controllers/authController.js";
import { authMiddleware } from "../middleware/authMiddleware.js";

const router = express.Router();

router.post("/register", registerUser); // POST /api/v1/auth/register
router.post("/login", loginUser); // POST /api/v1/auth/login

// เป็นการบอกว่าให้ใช้ middleware ก่อนจะส่งไปยัง controller getMe น้ะะ
router.get("/me", authMiddleware, getMe); // GET /api/v1/auth/me

export default router;

```
แล้วใน authController.js ให้ลองสร้างฟังก์ชัน getMe ขึ้นมา
```javascript
// authController.js
import bcrypt from "bcrypt";
import { query } from "../config/database.js";
import jwt from "jsonwebtoken";

export async function registerUser(req, res) {
  try {
    const { username, email, password } = req.body; // รับข้อมูลจาก Body

    // เช็คว่ามีข้อมูลครบถ้วนหรือไม่
    if (!username || !email || !password) {
      return res.status(400).json({
        error: "Please provide username, email, and password.",
      });
    }

    // ใส่ role ไว้ก่อน
    const role = "user";

    // เช็คว่ามี email นี้อยู่ในระบบหรือไม่ ถ้ามีให้ return error
    const existing = await query("SELECT * FROM users WHERE email = $1", [
      email,
    ]);
    if (existing.rowCount > 0) {
      return res.status(400).json({
        error: "User with this email already exists.",
      });
    }

    // สร้าง user_id ใหม่
    const idRes = await query("SELECT generate_user_id() as id");
    const user_id = idRes.rows[0].id;

    // ใช้ bcrypt ในการเข้ารหัส Password พร้อมกับ Salt
    const hashedPassword = await bcrypt.hash(password, 10);

    // สร้าง User ใหม่ใน ตาราง users
    await query(
      `INSERT INTO users (user_id, username, email, password, role)
       VALUES ($1, $2, $3, $4, $5)`,
      [user_id, username, email, hashedPassword, role]
    );

    // ส่ง Response กลับไปว่า User ลงทะเบียนสำเร็จ
    res.status(201).json({
      success: true,
      message: "Registration successful",
      userId: user_id,
    });
  } catch (error) {
    // Handle any unexpected errors
    console.error(error);
    res.status(500).json({ error: "Internal server error" });
  }
}
export async function loginUser(req, res) {
  try {
    const { email, password } = req.body; // รับข้อมูลจาก Body

    // เช็คว่ามีข้อมูลครบถ้วนหรือไม่
    if (!email || !password) {
      return res.status(400).json({
        error: "Please provide email and password.",
      });
    }

    // หา User ใน Database
    const userRes = await query("SELECT * FROM users WHERE email = $1", [
      email,
    ]);
    if (userRes.rowCount === 0) {
      return res.status(401).json({ error: "Invalid credentials" });
    }

    const user = userRes.rows[0];

    // ตรวจสอบ Password กับ Hashed Password ที่เก็บใน Database
    const passwordMatch = await bcrypt.compare(password, user.password);
    if (!passwordMatch) {
      return res.status(401).json({ error: "Invalid credentials" });
    }

    // สร้าง JWT Token โดยใช้ fucntion generateToken ที่เราสร้างขึ้น
    const token = generateToken(user);

    console.info(`User ${user.user_id} logged in successfully`);

    // ส่ง Response กลับไปว่า User Login สำเร็จ
    res.status(200).json({
      success: true,
      token,
      userId: user.user_id,
      name: user.username || user.email.split("@")[0],
      email: user.email,
    });
  } catch (error) {
    // ถ้ามี Error ให้ส่ง Response กลับไปว่า Internal server error
    console.error("Login error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

export async function getMe(req, res) {
  try {
    const { userId } = req.user;
    const userRes = await query(
      "SELECT user_id, username, email, role FROM users WHERE user_id = $1",
      [userId]
    );
    if (userRes.rowCount === 0) {
      return res.status(404).json({ error: "User not found" });
    }

    const user = userRes.rows[0];

    res.status(200).json({
      userId: user.user_id,
      name: user.username,
      email: user.email,
      role: user.role,
    });
  } catch (error) {
    log.error("Get current user error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

function generateToken(user) {
  // สร้าง JWT Token โดยใช้ jsonwebtoken jwt.sign คือ ฟังก์ชันที่ใช้ในการสร้าง Token โดยที่เราจะส่งข้อมูลที่เราต้องการเก็บใน Token ไป
  return jwt.sign(
    {
      userId: user.user_id,
      email: user.email,
      role: user.role,
    },
    process.env.JWT_SECRET, // Secret Key ที่ใช้ในการเข้ารหัส Token
    { expiresIn: "15d" }
  );
}
```
---

#### 7.3.3 ทดสอบโดย Postman
ลองทดสอบโดยการส่ง GET Request ไปที่
```
http://localhost:3000/api/v1/auth/me
```

แล้วแนบ Token ที่ได้จากการ Login ไปใน Header
```
Authorization: Bearer <your_token_here>
```

![[20250403-1010-16.8296460.mp4]]
เมื่อทำสำเร็จ Backend จะตอบกลับ
``` json
{
  "userId":"00001",
  "name":"testuser",
  "email":"test@gmail.com",
  "role":"user"
}
```

---

🎉 **เท่านี้เราก็สำเร็จในการสร้างระบบ Authentication พร้อม Middleware เรียบร้อยแล้ว!** 🎯

พร้อมที่จะไปลุยทำส่วนที่เหลือของโปรเจคกันต่อได้เลยครับ 🚀✨

---

### **7.4 Implement CRUD operations สำหรับตารางอื่นๆ** 📂🛠️

เมื่อ Backend ของเราสามารถยืนยันตัวตนของ User ได้อย่างถูกต้องแล้ว ✅
ขั้นตอนต่อไปก็คือการพัฒนาระบบในส่วนอื่นๆ ที่ยังเหลืออยู่ เช่น

- 📁 ระบบจัดการ Project
- ✅ ระบบจัดการ Task
- 📝 ระบบ Assignment
- 📎 ระบบ Attachment
- 🔧 ระบบอื่นๆ ที่ต้องใช้งานเพิ่มเติม

---

📌 โดยที่ตารางหรือโมเดลเหล่านี้จะมี Operation พื้นฐานสำคัญๆ ที่ควรจะมีอยู่ก็คือ:

| Operation              | ความหมาย                                    |
|------------------------|-------------------------------------------|
| ➕ **Create**          | การสร้างข้อมูลใหม่ (Insert ข้อมูลลงใน Database)   |
| 📖 **Read**            | การอ่านข้อมูลจาก Database                  |
| ✏️ **Update**          | การแก้ไขหรือปรับปรุงข้อมูลที่มีอยู่แล้ว           |
| 🗑️ **Delete**          | การลบข้อมูลที่ไม่ต้องการออกจาก Database        |

✨ ทั้งหมดนี้เราเรียกรวมกันสั้นๆ ว่า "**CRUD Operation**"

---

🔹 **CRUD Operation** เหล่านี้คือการจัดการข้อมูลพื้นฐานที่ทุกตารางส่วนใหญ่ควรจะมี
แต่ถ้าหากบางตารางมีการจัดการเฉพาะหรือเป็นกรณีพิเศษ อาจจะมีหรือไม่มีก็ได้ ขึ้นอยู่กับความต้องการของระบบเรา

แต่สำหรับโปรเจคนี้
เราจะถือว่าทุกๆ ตารางนั้นมีการจัดการแบบ CRUD Operation ครบทุกขั้นตอน 🧩

---

🎯 **ดังนั้น**
ต่อไปเราจะมาทดลองทำ CRUD Operation สำหรับตาราง **Project**
เพื่อเป็นตัวอย่างให้เข้าใจชัดเจน ก่อนนำไปประยุกต์กับตารางอื่นๆ ที่เหลือในภายหลังครับ 🚀

---

#### 7.4.1 สร้างไฟล์ projectRouter.js และ projectController.js
https://github.com/XunFlowerrr/backend-tutorial/tree/b701d0b8114c83aa18deb0944ed027db810c9479

ใน Folder routes ให้สร้างไฟล์ projectRouter.js ขึ้นมา
![[Pasted image 20250403172307.png]]

```javascript
// routes/projectRouter.js
import express from "express";
import {
  createProject,
  getProjectFromID,
  getProject,
  updateProject,
  deleteProject,
} from "../controllers/projectController.js";
import { authMiddleware } from "../middleware/authMiddleware.js";

const router = express.Router();

router.post("/", authMiddleware, createProject);
router.get("/", authMiddleware, getProjectFromID);

// /:id เรียกว่า reqest parameter ตัวอย่างเช่น http://localhost:3000/projects/1
// เป็นตัวแปรที่ใช้ในการระบุ project_id ที่เราต้องการดึงข้อมูลที่สามารถใส่มาใน URL ได้เลยโดยไม่ต้องส่งใน body
// ซึ่ง Method GET ปกติจะไม่ส่งข้อมูลใน body แต่จะส่งใน URL แทน
// ดังนั้นเราจึงใช้ request parameter ในการดึงข้อมูล project_id ที่เราต้องการ
router.get("/:id", authMiddleware, getProject);
router.put("/:id", authMiddleware, updateProject);
router.delete("/:id", authMiddleware, deleteProject);

export default router;

```

ใน Folder controllers ให้สร้างไฟล์ projectController.js ขึ้นมา
![[Pasted image 20250403172611.png]]

```javascript
// controllers/projectController.js
import { query } from "../config/database.js";

export async function createProject(req, res) {}

export async function getAllProjects(req, res) {}

export async function getProjectFromID(req, res) {}

export async function updateProject(req, res) {}

export async function deleteProject(req, res) {}
```

เดี๋ยวจะพาทำไปทีละฟังก์ชันนะ
เริ่มจากการสร้าง Project ก่อน

#### 7.4.2 Create Project
https://github.com/XunFlowerrr/backend-tutorial/tree/c77ae0cafc72a6463edafd18b198d6dc1e6721c2

```javascript
export async function createProject(req, res) {
  try {
    // เริ่มจากการดึงข้อมูลที่จำเป็นจาก request body
    const { projectName, projectDescription, category } = req.body;

    // ตรวจสอบว่าข้อมูลที่จำเป็นถูกส่งมาหรือไม่
    if (!projectName || !category) {
      return res.status(400).json({ error: "Missing required fields." });
    }

    // สร้าง project_id ใหม่
    // โดยใช้ฟังก์ชัน generate_project_id() ที่เราสร้างไว้ใน init.sql
    const idRes = await query("SELECT generate_project_id() as id");
    const projectId = idRes.rows[0].id; // ดึง project_id ที่สร้างขึ้นมา

    // สร้าง Project ใหม่ใน ตาราง project
    await query(
      `INSERT INTO project (project_id, project_name, project_description, owner_id, category)
         VALUES ($1, $2, $3, $4, $5)`,
      [projectId, projectName, projectDescription, req.user.userId, category] // ณ ต่ำแหน่ง $n จะถูกแทนที่ด้วยค่าที่เราส่งไปตามลำดับ
    );

    res.status(201).json({ message: "Project created", projectId });
  } catch (error) {
    console.error("Create project error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}
```

#### 7.4.3 Get All Projects
https://github.com/XunFlowerrr/backend-tutorial/tree/9e5d0c8720266369a795785a24703f0a6872e8cf
```javascript
export async function getAllProjects(req, res) {
  try {
    // ดึงข้อมูลโปรเจคทั้งหมดที่ผู้ใช้เป็นเจ้าของหรือเป็นสมาชิก
    const result = await query(
      `SELECT p.* FROM project p
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE p.owner_id = $1 OR pm.user_id = $1`,
      [req.user.userId]
    );
    res.status(200).json(result.rows);
  } catch (error) {
    console.error("getAllProjects error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}
```

#### 7.4.4 Get Project From ID
https://github.com/XunFlowerrr/backend-tutorial/tree/fcde03ae25462d29df537c4bacdc34302e8c69d5
```javascript
export async function getProjectFromID(req, res) {
  try {
    // ดึงข้อมูลโปรเจคจาก project_id ที่ส่งมาใน request parameters
    // ตัวอย่าง URL: http://localhost:3000/projects/1
    const { id } = req.params;

    // หาข้อมูลโปรเจคที่มี project_id ตรงกับที่ส่งมาใน request parameters
    const result = await query(
      `SELECT p.* FROM project p
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE p.project_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [id, req.user.userId]
    );

    // ถ้าไม่พบข้อมูลโปรเจคที่ตรงกับ project_id ที่ส่งมาใน request parameters
    // จะส่ง status 404 Not Found กลับไป
    if (result.rowCount === 0)
      return res.status(404).json({ error: "Not found" });

    // ถ้าพบข้อมูลโปรเจคที่ตรงกับ project_id ที่ส่งมาใน request parameters
    res.status(200).json(result.rows[0]);
  } catch (error) {
    console.error("getProject error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}
```

#### 7.4.5 Update Project
https://github.com/XunFlowerrr/backend-tutorial/tree/265f2132741fa9e5cc4183a72ef3d1def07f68c2
```javascript
export async function updateProject(req, res) {
  try {
    const { id } = req.params; // ดึง project_id จาก request parameters
    const { projectName, projectDescription, category } = req.body; // ดึงข้อมูลที่ส่งมาใน request body

    // ตรวจสอบว่าข้อมูลที่จำเป็นถูกส่งมาหรือไม่
    if (!projectName || !category) {
      return res.status(400).json({ error: "Missing required fields." });
    }

    // ทำการตรวจสอบว่าคนที่ส่งคำขออัปเดตโปรเจคนี้เป็นเจ้าของโปรเจคหรือไม่
    const ownerCheck = await query(
      "SELECT owner_id FROM project WHERE project_id = $1",
      [id]
    );
    if (
      !ownerCheck.rows[0] ||
      ownerCheck.rows[0].owner_id !== req.user.userId
    ) {
      // ถ้าคนที่ส่งคำขอไม่ใช่เจ้าของโปรเจค หรือไม่พบโปรเจคในฐานข้อมูล จะตอบกลับด้วย status 403 และไม่ให้ทำการอัปเดต
      return res.status(403).json({ error: "Not authorized" });
    }

    // ถ้าผ่านการตรวจสอบแล้ว ทำการอัปเดตโปรเจค
    await query(
      `UPDATE project SET project_name=$1, project_description=$2, category=$3
       WHERE project_id=$4`,
      [projectName, projectDescription, category, id]
    );
    // ถ้าอัปเดตสำเร็จ จะตอบกลับด้วย status 200 และข้อความว่า "Project updated"
    res.status(200).json({ message: "Project updated" });
  } catch (error) {
    // ถ้ามีข้อผิดพลาดเกิดขึ้น จะตอบกลับด้วย status 500 และข้อความว่า "Internal server error"
    console.error("updateProject error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}
```

#### 7.4.6 Delete Project
https://github.com/XunFlowerrr/backend-tutorial/tree/c18f22aee8c740e2f4f369ef4d178e2855256ca7
```javascript
export async function deleteProject(req, res) {
  try {
    const { id } = req.params; // ดึง project_id จาก request parameters

    // ทำการตรวจสอบว่าคนที่ส่งคำขอจะลบโปรเจคนี้เป็นเจ้าของโปรเจคหรือไม่
    const ownerCheck = await query(
      "SELECT owner_id FROM project WHERE project_id = $1",
      [id]
    );
    if (
      !ownerCheck.rows[0] ||
      ownerCheck.rows[0].owner_id !== req.user.userId
    ) {
      // ถ้าคนที่ส่งคำขอไม่ใช่เจ้าของโปรเจค หรือไม่พบโปรเจคในฐานข้อมูล จะตอบกลับด้วย status 403 และไม่ให้ทำการลบ
      return res.status(403).json({ error: "Not authorized" });
    }

    // ถ้าผ่านการตรวจสอบแล้ว ทำการลบโปรเจค
    await query("DELETE FROM project WHERE project_id = $1", [id]);

    // ถ้าลบสำเร็จ จะตอบกลับด้วย status 200 และข้อความว่า "Project deleted"
    res.status(200).json({ message: "Project deleted" });
  } catch (error) {
    // ถ้ามีข้อผิดพลาดเกิดขึ้น จะตอบกลับด้วย status 500 และข้อความว่า "Internal server error"
    console.error("deleteProject error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}
```

#### 7.4.7 สร้าง Route ใหม่ใน index.js
https://github.com/XunFlowerrr/backend-tutorial/tree/045a14b998d71aaa4a2a5315e6a3b50270848f0f
ในไฟล์ index.js ให้ import projectRouter เข้ามา
```javascript
import express from "express";
import dotenv from "dotenv";
import { testConnection } from "./test.js";
import authRouter from "./routes/authRouter.js";
import projectRouter from "./routes/projectRouter.js";

dotenv.config();
const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.json());
app.use("/api/v1/auth", authRouter);
app.use("/api/v1/projects", projectRouter);

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
  testConnection();
});
```

#### 7.4.8 ทดสอบ CRUD Project
ลองทดสอบ CRUD Project โดยใช้ Postman
![[postman_test.mp4]]

1. **Create Project**
    - Method: POST
    - URL: http://localhost:3000/api/v1/projects
    - Body:
  ```json
  {
    "projectName": "Test Project",
    "projectDescription": "This is a test project",
    "category": "Development"
  }
  ```
    - Header:
  ```
  Authorization: Bearer <your_token_here>
  ```

  2. **Get All Projects**
    - Method: GET
    - URL: http://localhost:3000/api/v1/projects
    - Header:
  ```
  Authorization: Bearer <your_token_here>
  ```

  3. **Get Project From ID**
    - Method: GET
    - URL: http://localhost:3000/api/v1/projects/<project_id>
    - Header:
  ```
  Authorization: Bearer <your_token_here>
  ```

  4. **Update Project**
    - Method: PUT
    - URL: http://localhost:3000/api/v1/projects/<project_id>
    - Body:
  ```json
  {
    "projectName": "Updated Project",
    "projectDescription": "This is an updated project",
    "category": "Development"
  }
  ```
    - Header:
  ```
  Authorization: Bearer <your_token_here>
  ```

  5. **Delete Project**
    - Method: DELETE
    - URL: http://localhost:3000/api/v1/projects/<project_id>
    - Header:
  ```
  Authorization: Bearer <your_token_here>
  ```

#### 7.4.9 สำหรับตารางอื่นๆ
https://github.com/XunFlowerrr/backend-tutorial/tree/fac62147560ca7ccda7d2943f3d1a68244aaf1c5
สำหรับตารางอื่นๆก็จะมี CRUD Operation ที่คล้ายกัน
- taskRouter.js
``` javascript
// routes/taskRouter.js
import express from "express";
import {
  createTask,
  getAllTasks,
  getTask,
  updateTask,
  deleteTask,
  assignUser,
  unassignUser,
  getTaskAssignees,
  getUserTasks,
} from "../controllers/taskController.js";
import { authMiddleware } from "../middleware/authMiddleware.js";

const router = express.Router();

router.use(authMiddleware);

router.get("/", getAllTasks);
router.get("/me", getUserTasks);
router.get("/:id", getTask);
router.post("/", createTask);
router.put("/:id", updateTask);
router.delete("/:id", deleteTask);

// Task assignee routes
router.get("/:taskId/assignees", getTaskAssignees);
router.post("/:taskId/assignees", assignUser);
router.delete("/:taskId/assignees/:userId", unassignUser);

export default router;

```

- taskController.js
```javascript
// controllers/taskController.js
import { query } from "../config/database.js";

export async function createTask(req, res) {
  console.info(
    "createTask: Request received, body=" + JSON.stringify(req.body)
  );
  try {
    const {
      projectId,
      taskName,
      taskDescription,
      startDate,
      dueDate,
      status,
      priority,
      assignees,
    } = req.body;
    if (!projectId || !taskName) {
      return res.status(400).json({ error: "Missing required fields." });
    }
    const sanitizedProjectId = projectId.trim();
    const sanitizedTaskName = taskName.trim();
    const sanitizedTaskDescription = taskDescription
      ? taskDescription.trim()
      : "";
    const sanitizedStatus = status ? status.trim() : "pending";
    const membershipCheck = await query(
      `SELECT p.project_id
       FROM project p
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE p.project_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [sanitizedProjectId, req.user.userId]
    );
    if (membershipCheck.rowCount === 0)
      return res.status(403).json({ error: "Not authorized" });

    const newId = await query("SELECT generate_task_id() as id");
    const taskId = newId.rows[0].id;
    await query(
      `INSERT INTO task (task_id, project_id, task_name, task_description, start_date, due_date, status, priority)
       VALUES ($1, $2, $3, $4, $5, $6, $7, $8)`,
      [
        taskId,
        sanitizedProjectId,
        sanitizedTaskName,
        sanitizedTaskDescription,
        startDate,
        dueDate,
        sanitizedStatus,
        priority,
      ]
    );

    // Add assignees if provided
    if (assignees && Array.isArray(assignees) && assignees.length > 0) {
      // Validate that all assignees are members of the project
      for (const assigneeId of assignees) {
        const isMember = await query(
          `SELECT user_id FROM project_member
           WHERE project_id = $1 AND user_id = $2
           UNION
           SELECT owner_id FROM project
           WHERE project_id = $1 AND owner_id = $2`,
          [sanitizedProjectId, assigneeId]
        );

        if (isMember.rowCount > 0) {
          await query(
            "INSERT INTO task_assignee (task_id, user_id) VALUES ($1, $2)",
            [taskId, assigneeId]
          );
          console.debug(
            `createTask: User ${assigneeId} assigned to task ${taskId}`
          );
        } else {
          console.warn(
            `createTask: Attempted to assign non-member ${assigneeId} to task ${taskId}`
          );
        }
      }
    }

    console.info(
      `createTask: Task ${taskId} created in project ${sanitizedProjectId}`
    );
    res.status(201).json({ message: "Task created", taskId });
  } catch (error) {
    console.error("createTask error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

export async function getAllTasks(req, res) {
  console.info(
    "getAllTasks: Request received, query=" + JSON.stringify(req.query)
  );
  try {
    const { projectId } = req.query;
    const membershipCheck = await query(
      `SELECT p.project_id
       FROM project p
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE p.project_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [projectId, req.user.userId]
    );
    if (membershipCheck.rowCount === 0)
      return res.status(403).json({ error: "Not authorized" });

    // Get tasks with their assignees
    const result = await query(
      `SELECT t.*,
        (SELECT json_agg(json_build_object('user_id', ta.user_id))
         FROM task_assignee ta
         WHERE ta.task_id = t.task_id) as assignees
       FROM task t WHERE t.project_id = $1`,
      [projectId]
    );
    console.info(
      `getAllTasks: Retrieved ${result.rowCount} tasks for project ${projectId}`
    );
    res.status(200).json(result.rows);
  } catch (error) {
    console.error("getAllTasks error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

export async function getTask(req, res) {
  console.info(
    "getTask: Request received, params=" + JSON.stringify(req.params)
  );
  try {
    const { id } = req.params;

    // Get task with assignee details
    const result = await query(
      `SELECT t.*,
        (SELECT json_agg(json_build_object('user_id', ta.user_id))
         FROM task_assignee ta
         WHERE ta.task_id = t.task_id) as assignees
       FROM task t
       JOIN project p ON t.project_id = p.project_id
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE t.task_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [id, req.user.userId]
    );
    if (result.rowCount === 0)
      return res.status(404).json({ error: "Not found or not authorized" });
    console.info(`getTask: Retrieved task ${id}`);
    res.status(200).json(result.rows[0]);
  } catch (error) {
    console.error("getTask error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

export async function updateTask(req, res) {
  console.info(
    "updateTask: Request received, params=" +
      JSON.stringify(req.params) +
      ", body=" +
      JSON.stringify(req.body)
  );
  try {
    const { id } = req.params;
    const {
      taskName,
      taskDescription,
      startDate,
      dueDate,
      status,
      priority,
      assignees,
    } = req.body;
    if (!taskName) {
      return res.status(400).json({ error: "Missing required fields." });
    }
    const sanitizedTaskName = taskName.trim();
    const sanitizedTaskDescription = taskDescription
      ? taskDescription.trim()
      : "";
    const sanitizedStatus = status ? status.trim() : "pending";

    // Get task and project info to verify membership and project ID
    const membershipCheck = await query(
      `SELECT t.*, p.project_id
       FROM task t
       JOIN project p ON t.project_id = p.project_id
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE t.task_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [id, req.user.userId]
    );
    if (membershipCheck.rowCount === 0)
      return res.status(403).json({ error: "Not authorized" });

    const projectId = membershipCheck.rows[0].project_id;

    // Update task details
    await query(
      `UPDATE task SET task_name=$1, task_description=$2, start_date=$3, due_date=$4, status=$5, priority=$6
       WHERE task_id=$7`,
      [
        sanitizedTaskName,
        sanitizedTaskDescription,
        startDate,
        dueDate,
        sanitizedStatus,
        priority,
        id,
      ]
    );

    // Update assignees if provided
    if (assignees && Array.isArray(assignees)) {
      // Clear existing assignments
      await query("DELETE FROM task_assignee WHERE task_id = $1", [id]);

      // Add new assignments
      if (assignees.length > 0) {
        for (const assigneeId of assignees) {
          const isMember = await query(
            `SELECT user_id FROM project_member
             WHERE project_id = $1 AND user_id = $2
             UNION
             SELECT owner_id FROM project
             WHERE project_id = $1 AND owner_id = $2`,
            [projectId, assigneeId]
          );

          if (isMember.rowCount > 0) {
            await query(
              "INSERT INTO task_assignee (task_id, user_id) VALUES ($1, $2)",
              [id, assigneeId]
            );
            console.debug(
              `updateTask: User ${assigneeId} assigned to task ${id}`
            );
          } else {
            console.warn(
              `updateTask: Attempted to assign non-member ${assigneeId} to task ${id}`
            );
          }
        }
      }
    }

    console.info(`updateTask: Task ${id} updated`);
    res.status(200).json({ message: "Task updated" });
  } catch (error) {
    console.error("updateTask error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

export async function deleteTask(req, res) {
  console.info(
    "deleteTask: Request received, params=" + JSON.stringify(req.params)
  );
  try {
    const { id } = req.params;
    const membershipCheck = await query(
      `SELECT t.*
       FROM task t
       JOIN project p ON t.project_id = p.project_id
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE t.task_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [id, req.user.userId]
    );
    if (membershipCheck.rowCount === 0)
      return res.status(403).json({ error: "Not authorized" });

    // Note: Deletion from task_assignee table will be handled by CASCADE constraint
    await query("DELETE FROM task WHERE task_id = $1", [id]);
    console.info(`deleteTask: Task ${id} deleted`);
    res.status(200).json({ message: "Task deleted" });
  } catch (error) {
    console.error("deleteTask error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

// New functions for managing task assignees
export async function assignUser(req, res) {
  console.info(
    "assignUser: Request received, params=" +
      JSON.stringify(req.params) +
      ", body=" +
      JSON.stringify(req.body)
  );
  try {
    const { taskId } = req.params;
    const { userId } = req.body;

    if (!userId) {
      return res.status(400).json({ error: "Missing required field: userId." });
    }

    // Check if user has permission to modify the task (is member of the project)
    const taskCheck = await query(
      `SELECT t.task_id, p.project_id
       FROM task t
       JOIN project p ON t.project_id = p.project_id
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE t.task_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [taskId, req.user.userId]
    );

    if (taskCheck.rowCount === 0) {
      return res
        .status(403)
        .json({ error: "Not authorized to modify this task" });
    }

    const projectId = taskCheck.rows[0].project_id;

    // Check if the assignee is a member of the project
    const memberCheck = await query(
      `SELECT user_id FROM project_member
       WHERE project_id = $1 AND user_id = $2
       UNION
       SELECT owner_id FROM project
       WHERE project_id = $1 AND owner_id = $2`,
      [projectId, userId]
    );

    if (memberCheck.rowCount === 0) {
      return res
        .status(400)
        .json({ error: "User is not a member of the project" });
    }

    // Check if the assignment already exists
    const assignmentCheck = await query(
      "SELECT * FROM task_assignee WHERE task_id = $1 AND user_id = $2",
      [taskId, userId]
    );

    if (assignmentCheck.rowCount > 0) {
      return res
        .status(400)
        .json({ error: "User is already assigned to this task" });
    }

    // Add assignment
    await query(
      "INSERT INTO task_assignee (task_id, user_id) VALUES ($1, $2)",
      [taskId, userId]
    );

    console.info(`assignUser: User ${userId} assigned to task ${taskId}`);
    res.status(201).json({ message: "User assigned to task" });
  } catch (error) {
    console.error("assignUser error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

export async function unassignUser(req, res) {
  console.info(
    "unassignUser: Request received, params=" + JSON.stringify(req.params)
  );
  try {
    const { taskId, userId } = req.params;

    // Check if user has permission to modify the task
    const taskCheck = await query(
      `SELECT t.task_id
       FROM task t
       JOIN project p ON t.project_id = p.project_id
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE t.task_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [taskId, req.user.userId]
    );

    if (taskCheck.rowCount === 0) {
      return res
        .status(403)
        .json({ error: "Not authorized to modify this task" });
    }

    // Remove assignment
    await query(
      "DELETE FROM task_assignee WHERE task_id = $1 AND user_id = $2",
      [taskId, userId]
    );

    console.info(`unassignUser: User ${userId} unassigned from task ${taskId}`);
    res.status(200).json({ message: "User unassigned from task" });
  } catch (error) {
    console.error("unassignUser error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

export async function getTaskAssignees(req, res) {
  console.info(
    "getTaskAssignees: Request received, params=" + JSON.stringify(req.params)
  );
  try {
    const { taskId } = req.params;

    // Check if user has permission to view the task
    const taskCheck = await query(
      `SELECT t.task_id
       FROM task t
       JOIN project p ON t.project_id = p.project_id
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE t.task_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [taskId, req.user.userId]
    );

    if (taskCheck.rowCount === 0) {
      return res
        .status(403)
        .json({ error: "Not authorized to view this task" });
    }

    // Get assignees with user details
    const assignees = await query(
      `SELECT ta.user_id, u.username, u.email
       FROM task_assignee ta
       JOIN users u ON ta.user_id = u.user_id
       WHERE ta.task_id = $1`,
      [taskId]
    );

    console.info(
      `getTaskAssignees: Retrieved ${assignees.rowCount} assignees for task ${taskId}`
    );
    res.status(200).json(assignees.rows);
  } catch (error) {
    console.error("getTaskAssignees error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

export async function getUserTasks(req, res) {
  console.info("getUserTasks: Request received");
  try {
    const userId = req.user.userId;

    // Get tasks with more details and assignee information
    const tasks = await query(
      `SELECT t.*, p.project_name,
        (SELECT json_agg(json_build_object('user_id', u.user_id, 'username', u.username, 'email', u.email))
         FROM task_assignee ta
         JOIN users u ON ta.user_id = u.user_id
         WHERE ta.task_id = t.task_id) as assignees
       FROM task t
       JOIN task_assignee ta ON t.task_id = ta.task_id
       JOIN project p ON t.project_id = p.project_id
       WHERE ta.user_id = $1
       ORDER BY t.due_date ASC NULLS LAST, t.priority DESC`,
      [userId]
    );

    console.info(
      `getUserTasks: Retrieved ${tasks.rowCount} tasks for user ${userId}`
    );
    res.status(200).json(tasks.rows);
  } catch (error) {
    console.error("getUserTasks error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}
```

projectMemberRouter.js
```javascript
// routes/projectMemberRouter.js
import express from "express";
import {
  addProjectMember,
  removeProjectMember,
} from "../controllers/projectMemberController.js";
import { authMiddleware } from "../middleware/authMiddleware.js";

const router = express.Router();

router.use(authMiddleware);

router.post("/:projectId/members", addProjectMember);
router.delete("/:projectId/members/:userId", removeProjectMember);

export default router;
```

projectMemberController.js
```javascript
// controllers/projectMemberController.js
import { query } from "../config/database.js";

export async function addProjectMember(req, res) {
  console.info(
    "addProjectMember: Request received, params=" +
      JSON.stringify(req.params) +
      ", body=" +
      JSON.stringify(req.body)
  );
  try {
    const { projectId } = req.params;
    let { userId } = req.body;
    if (!userId) {
      return res.status(400).json({ error: "Missing required field: userId." });
    }
    userId = userId.trim();
    // Verify requester is the owner
    const ownerRes = await query(
      "SELECT owner_id FROM project WHERE project_id = $1",
      [projectId]
    );
    console.debug(
      "addProjectMember: Owner response: " + JSON.stringify(ownerRes)
    );
    if (!ownerRes.rows[0] || ownerRes.rows[0].owner_id !== req.user.userId) {
      return res.status(403).json({ error: "Not authorized" });
    }
    // Add user to project_member
    await query(
      "INSERT INTO project_member (project_id, user_id) VALUES ($1, $2)",
      [projectId, userId]
    );
    console.debug(
      `addProjectMember: Project member insertion complete for project ${projectId}`
    );
    console.info(
      `addProjectMember: Member ${userId} added to project ${projectId}`
    );
    res.status(201).json({ message: "User added to project" });
  } catch (error) {
    console.error("addProjectMember error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

export async function removeProjectMember(req, res) {
  console.info(
    "removeProjectMember: Request received, params=" +
      JSON.stringify(req.params)
  );
  try {
    const { projectId, userId } = req.params;
    // Verify requester is the owner
    const ownerRes = await query(
      "SELECT owner_id FROM project WHERE project_id = $1",
      [projectId]
    );
    console.debug(
      "removeProjectMember: Owner response: " + JSON.stringify(ownerRes)
    );
    if (!ownerRes.rows[0] || ownerRes.rows[0].owner_id !== req.user.userId) {
      return res.status(403).json({ error: "Not authorized" });
    }
    // Remove user from project_member
    await query(
      "DELETE FROM project_member WHERE project_id = $1 AND user_id = $2",
      [projectId, userId]
    );
    console.debug(
      `removeProjectMember: Deletion query complete for user ${userId} and project ${projectId}`
    );
    console.info(
      `removeProjectMember: Member ${userId} removed from project ${projectId}`
    );
    res.status(200).json({ message: "User removed from project" });
  } catch (error) {
    console.error("removeProjectMember error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}
```

- attachmentsRouter.js
```javascript
// routes/attachmentsRouter.js
import express from "express";
import {
  createAttachment,
  getAttachment,
  getAllAttachments,
  updateAttachment,
  deleteAttachment,
} from "../controllers/attachmentController.js";
import { authMiddleware } from "../middleware/authMiddleware.js";

const router = express.Router();

router.use(authMiddleware);

router.post("/", createAttachment);
router.get("/", getAllAttachments);
router.get("/:id", getAttachment);
router.put("/:id", updateAttachment);
router.delete("/:id", deleteAttachment);

export default router;
```

- attachmentController.js
```javascript
// controllers/attachmentController.js
import { query } from "../config/database.js";

// Create attachment - checking user membership via task
export async function createAttachment(req, res) {
  console.info(
    "createAttachment: Request received, body=" + JSON.stringify(req.body)
  );
  try {
    // New input validation and sanitization
    const { attachmentName, taskId, file_url, file_type } = req.body;
    if (!attachmentName || !taskId || !file_url || !file_type) {
      return res.status(400).json({ error: "Missing required fields." });
    }
    const sanitizedAttachmentName = attachmentName.trim();
    const sanitizedTaskId = taskId.trim();
    const sanitizedFile_url = file_url.trim();
    const sanitizedFile_type = file_type.trim();
    // Verify user membership in the task's project
    const membershipCheck = await query(
      `SELECT t.task_id
       FROM task t
       JOIN project p ON t.project_id = p.project_id
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE t.task_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [sanitizedTaskId, req.user.userId]
    );
    if (membershipCheck.rowCount === 0) {
      return res
        .status(403)
        .json({ error: "Not authorized to add attachment to this task" });
    }
    const newIdRes = await query("SELECT generate_attachment_id() as id");
    const attachmentId = newIdRes.rows[0].id;
    await query(
      `INSERT INTO attachment (attachment_id, attachment_name, task_id, file_url, file_type)
       VALUES ($1, $2, $3, $4, $5)`,
      [
        attachmentId,
        sanitizedAttachmentName,
        sanitizedTaskId,
        sanitizedFile_url,
        sanitizedFile_type,
      ]
    );
    console.info(
      `createAttachment: Attachment ${attachmentId} created on task ${sanitizedTaskId}`
    );
    res.status(201).json({ message: "Attachment created", attachmentId });
  } catch (error) {
    console.error("createAttachment error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

// Get a single attachment with membership check
export async function getAttachment(req, res) {
  console.info(
    "getAttachment: Request received, params=" + JSON.stringify(req.params)
  );
  try {
    const { id } = req.params;
    const attachmentRes = await query(
      "SELECT * FROM attachment WHERE attachment_id = $1",
      [id]
    );
    if (attachmentRes.rowCount === 0)
      return res.status(404).json({ error: "Attachment not found" });
    const attachment = attachmentRes.rows[0];
    // Verify user membership via the task on which the attachment is attached
    const membershipCheck = await query(
      `SELECT t.task_id
       FROM task t
       JOIN project p ON t.project_id = p.project_id
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE t.task_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [attachment.task_id, req.user.userId]
    );
    if (membershipCheck.rowCount === 0) {
      return res
        .status(403)
        .json({ error: "Not authorized to view this attachment" });
    }
    console.info(`getAttachment: Attachment ${id} retrieved`);
    res.status(200).json(attachment);
  } catch (error) {
    console.error("getAttachment error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

// Get all attachments; if taskId provided, check membership, else retrieve attachments for allowed tasks
export async function getAllAttachments(req, res) {
  console.info(
    "getAllAttachments: Request received, query=" + JSON.stringify(req.query)
  );
  try {
    const { taskId } = req.query;
    if (taskId) {
      const membershipCheck = await query(
        `SELECT t.task_id
         FROM task t
         JOIN project p ON t.project_id = p.project_id
         LEFT JOIN project_member pm ON p.project_id = pm.project_id
         WHERE t.task_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
        [taskId, req.user.userId]
      );
      if (membershipCheck.rowCount === 0) {
        return res
          .status(403)
          .json({ error: "Not authorized to view attachments for this task" });
      }
      const result = await query(
        "SELECT * FROM attachment WHERE task_id = $1",
        [taskId]
      );
      console.info(
        `getAllAttachments: Attachments for task ${taskId} retrieved`
      );
      return res.status(200).json(result.rows);
    } else {
      const result = await query(
        `SELECT a.*
         FROM attachment a
         JOIN task t ON a.task_id = t.task_id
         JOIN project p ON t.project_id = p.project_id
         LEFT JOIN project_member pm ON p.project_id = pm.project_id
         WHERE p.owner_id = $1 OR pm.user_id = $1`,
        [req.user.userId]
      );
      console.info(
        "getAllAttachments: Attachments for allowed tasks retrieved"
      );
      return res.status(200).json(result.rows);
    }
  } catch (error) {
    console.error("getAllAttachments error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

// Update attachment with membership check
export async function updateAttachment(req, res) {
  console.info(
    "updateAttachment: Request received, params=" +
      JSON.stringify(req.params) +
      ", body=" +
      JSON.stringify(req.body)
  );
  try {
    const { id } = req.params;
    // New input validation and sanitization
    const { attachmentName, file_url, file_type } = req.body;
    if (!attachmentName || !file_url || !file_type) {
      return res.status(400).json({ error: "Missing required fields." });
    }
    const sanitizedAttachmentName = attachmentName.trim();
    const sanitizedFile_url = file_url.trim();
    const sanitizedFile_type = file_type.trim();
    const attachmentRes = await query(
      "SELECT * FROM attachment WHERE attachment_id = $1",
      [id]
    );
    if (attachmentRes.rowCount === 0)
      return res.status(404).json({ error: "Attachment not found" });
    const attachment = attachmentRes.rows[0];
    const membershipCheck = await query(
      `SELECT t.task_id
       FROM task t
       JOIN project p ON t.project_id = p.project_id
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE t.task_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [attachment.task_id, req.user.userId]
    );
    if (membershipCheck.rowCount === 0) {
      return res
        .status(403)
        .json({ error: "Not authorized to update this attachment" });
    }
    await query(
      `UPDATE attachment SET attachment_name = $1, file_url = $2, file_type = $3
       WHERE attachment_id = $4`,
      [sanitizedAttachmentName, sanitizedFile_url, sanitizedFile_type, id]
    );
    console.info(`updateAttachment: Attachment ${id} updated`);
    res.status(200).json({ message: "Attachment updated" });
  } catch (error) {
    console.error("updateAttachment error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}

// Delete attachment with membership check
export async function deleteAttachment(req, res) {
  console.info(
    "deleteAttachment: Request received, params=" + JSON.stringify(req.params)
  );
  try {
    const { id } = req.params;
    const attachmentRes = await query(
      "SELECT * FROM attachment WHERE attachment_id = $1",
      [id]
    );
    if (attachmentRes.rowCount === 0)
      return res.status(404).json({ error: "Attachment not found" });
    const attachment = attachmentRes.rows[0];
    const membershipCheck = await query(
      `SELECT t.task_id
       FROM task t
       JOIN project p ON t.project_id = p.project_id
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE t.task_id = $1 AND (p.owner_id = $2 OR pm.user_id = $2)`,
      [attachment.task_id, req.user.userId]
    );
    if (membershipCheck.rowCount === 0) {
      return res
        .status(403)
        .json({ error: "Not authorized to delete this attachment" });
    }
    await query("DELETE FROM attachment WHERE attachment_id = $1", [id]);
    console.info(`deleteAttachment: Attachment ${id} deleted`);
    res.status(200).json({ message: "Attachment deleted" });
  } catch (error) {
    console.error("deleteAttachment error: " + error);
    res.status(500).json({ error: "Internal server error" });
  }
}
```
แล้วอย่าลืม import router เข้ามาใน index.js
```javascript
import express from "express";
import dotenv from "dotenv";
import { testConnection } from "./test.js";
import authRouter from "./routes/authRouter.js";
import projectRouter from "./routes/projectRouter.js";
import taskRouter from "./routes/taskRouter.js";
import attachmentRouter from "./routes/attachmentRouter.js";
import projectMemberRouter from "./routes/projectMemberRouter.js";

dotenv.config();
const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.json());
app.use("/api/v1/auth", authRouter);
app.use("/api/v1/projects", projectRouter);
app.use("/api/v1/tasks", taskRouter);
app.use("/api/v1/project-members", projectMemberRouter);
app.use("/api/v1/attachments", attachmentRouter);

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
  testConnection();
});
```

# 🎉 สรุปการเรียนรู้👏✨

เย้🥳🎉 เบบี๋เรียนเสร็จเรียบร้อยหมดแล้ว เก่งมากก!!❤️

ตลอดเส้นทางที่ผ่านมา เราได้เรียนรู้สิ่งต่างๆ มากมาย ตั้งแต่พื้นฐานสำคัญอย่าง:

- 🌐 **Client-Server และ HTTP Protocol**
- 📨 การส่ง **Request และ Response** ผ่าน HTTP
- 📬 **HTTP Method** (GET, POST, PUT, DELETE) และ **HTTP Status Code**

เราได้ทดลองลงมือทำจริงตั้งแต่:

- 📁 การสร้างโครงสร้างโปรเจกต์และเซ็ตอัพ Database ด้วย Docker และ PostgreSQL
- 🛠️ การสร้าง Backend ด้วย Express และ Node.js
- 🔒 การเก็บข้อมูลที่สำคัญด้วย Environment Variables
- 🗄️ การเชื่อมต่อ Database อย่างปลอดภัยด้วย PostgreSQL
- 🧩 การจัดโครงสร้างโค้ดแบบมืออาชีพ ด้วย Router และ Controller
- 🔐 ระบบ Authentication ที่ปลอดภัยด้วย JWT และ Middleware
- ⚙️ CRUD Operations สำหรับจัดการข้อมูลอย่างครบถ้วน

ขอให้เบบี๋ภูมิใจในตัวเอง แล้วบอกคนอื่นว่าเป็น Backend Developer ได้เลย!😎

# Shortcut ที่ใช้ทั้งหมดในคลิปตัวอย่าง


### 📌 Shortcut ใน VS Code

- **`Ctrl + Shift + P`**: เปิด Command Palette ใน VS Code

- **`Ctrl + J`**: เปิด/ปิด Bottom Panel

- **`Alt + Tab`**: สลับหน้าต่างหรือแท็บของโปรแกรมที่เปิดอยู่


### 📌 Shortcut ขณะใช้งาน Terminal

- **`Ctrl + C`**: หยุดการทำงานของโปรแกรมหรือคำสั่งใน Terminal

- **`Ctrl + L`**: ล้างหน้าจอ Terminal

- **`Ctrl + Shift + 5`**: เปิด Terminal ในมุมมองแบบ Split View (แบ่ง Terminal ออกเป็นหลายหน้าต่าง)


# รวมคำสั่ง Terminal ทั้งหมด

### 📌 Node.js & npm

```
npm init -y
```
  คำสั่งสำหรับเริ่มต้นโปรเจกต์ Node.js ใหม่ โดยสร้างไฟล์ package.json อัตโนมัติ

```
npm install <package-name>
```
  คำสั่งสำหรับติดตั้ง package ที่ต้องการใช้งานในโปรเจกต์

```
npm run dev
```
  คำสั่งสำหรับรันโปรเจกต์ในโหมด Development (Development Mode) โดยใช้ nodemon


### 📌 Docker

```
docker-compose up
```
  คำสั่งสำหรับรัน Docker Compose โดยจะสร้างและเริ่มต้น container ตามที่กำหนดในไฟล์ docker-compose.yml

```
docker-compose down
```
  คำสั่งสำหรับหยุดและลบ container ที่สร้างขึ้นจาก Docker Compose



# Link to github repo

2.1 [สร้างไฟล์ Docker Compose](https://github.com/XunFlowerrr/backend-tutorial/tree/c6c66d31af1afe23424d8341393eaf538e1d9f3a "2.1 สร้างไฟล์ Docker Compose")

2.2  [สร้างไฟล์ init.sql](https://github.com/XunFlowerrr/backend-tutorial/tree/51cfc4f610d844dfb67f11c0667aa4ac683d42dc "2.2 สร้างไฟล์ init.sql")

3.1  [เปิด terminal ขึ้นมาในโฟลเดอร์ backend npm init -y](https://github.com/XunFlowerrr/backend-tutorial/tree/9e5ee970cbd1e4d615ccc5992fc5570aceecaa68 "3.1 เปิด terminal ขึ้นมาในโฟลเดอร์ backend npm init -y")

3.2  [ติดตั้ง express, nodemon](https://github.com/XunFlowerrr/backend-tutorial/tree/f5e104fff9c66ebf654774fdf8a4442ce89ce48d "3.2 ติดตั้ง express, nodemon")

3.3  [เลือกใช้ nodemon ในการรันโปรเจค](https://github.com/XunFlowerrr/backend-tutorial/tree/85f09d16c404969a3efcca20a580f7dc90541d68 "3.3 เลือกใช้ nodemon ในการรันโปรเจค")

3.4  [เลือกใช้วิธีในการ import](https://github.com/XunFlowerrr/backend-tutorial/tree/ade449c495b82b13f06480540a060e79c8d09c3b "3.4 เลือกใช้วิธีในการ import")

4.2  [รับ HTTP Request](https://github.com/XunFlowerrr/backend-tutorial/tree/53c1aa1417605dbf73ca124c340d7b3cf96528c6 "4.2 รับ HTTP Request")

5.3  [ใช้งาน Environment Variables](https://github.com/XunFlowerrr/backend-tutorial/tree/5bd678d99642c3ca359c4c4a83ab22345e8d426f "5.3 ใช้งาน Environment Variables")

6.2  [สร้าง Folder ชื่อ config และข้างในสร้างไฟล์ database.js](https://github.com/XunFlowerrr/backend-tutorial/tree/7432c5a8d66eb8ac625130a8ddf7c078c436ddd0 "6.2 สร้าง Folder ชื่อ config และข้างในสร้างไฟล์ database.js")

6.3  [ทดสอบว่าต่อ Database สำเร็จหรือไม่](https://github.com/XunFlowerrr/backend-tutorial/tree/3a4cd73444e9a296205756d4ae472b4c5e02ae8a "6.3 ทดสอบว่าต่อ Database สำเร็จหรือไม่")

7.2.1  [สร้างไฟล์ authRouter.js ใน Folder routes](https://github.com/XunFlowerrr/backend-tutorial/tree/acb2a4ebb6cd82f36877d3931523f38378ec48dd "7.2.1 สร้างไฟล์ authRouter.js ใน Folder routes")

7.2.2  [สร้างไฟล์ authController.js ใน Folder controllers](https://github.com/XunFlowerrr/backend-tutorial/tree/85e75bae8712e70092e5bd4111338ce07c90020a "7.2.2 สร้างไฟล์ authController.js ใน Folder controllers")

7.2.3  [เพิ่ม authRouter ใน index.js](https://github.com/XunFlowerrr/backend-tutorial/tree/a00824662dbaf33f1513ef8e8f0000314cd6d482 "7.2.3 เพิ่ม authRouter ใน index.js")

7.2.5  [ส่งข้อมูลไปยัง Backend](https://github.com/XunFlowerrr/backend-tutorial/tree/a176b3385ec420b326f7f1565acb91c81e89303d "7.2.5 ส่งข้อมูลไปยัง Backend")

7.2.6  [ทำ Logic การลงทะเบียน (Register)](https://github.com/XunFlowerrr/backend-tutorial/tree/a1973f675acafb96a2c0c5975e4f1d003b393c6c "7.2.6 ทำ Logic การลงทะเบียน (Register)")

7.2.7  [ทำ Logic การเข้าสู่ระบบ (Login)](https://github.com/XunFlowerrr/backend-tutorial/tree/48a3b944bd471bd1cd00ad15a203c7a6269055c2 "7.2.7 ทำ Logic การเข้าสู่ระบบ (Login)")

7.3.1  [สร้างไฟล์ Middleware](https://github.com/XunFlowerrr/backend-tutorial/tree/79cbf1fdd6f20e7f779d7a38910bb435438b4a6a "7.3.1 สร้างไฟล์ Middleware")

7.3.2  [ลองสร้าง Endpoint ใหม่เพื่อลองดึงข้อมูล User ดู](https://github.com/XunFlowerrr/backend-tutorial/tree/5eb1998b8a2266bf29b34ec529da315461044080 "7.3.2 ลองสร้าง Endpoint ใหม่เพื่อลองดึงข้อมูล User ดู")

7.4.1  [สร้างไฟล์ projectRouter.js และ projectController.js](https://github.com/XunFlowerrr/backend-tutorial/tree/b701d0b8114c83aa18deb0944ed027db810c9479 "7.4.1 สร้างไฟล์ projectRouter.js และ projectController.js")

7.4.2  [Create Project](https://github.com/XunFlowerrr/backend-tutorial/tree/c77ae0cafc72a6463edafd18b198d6dc1e6721c2 "7.4.2 Create Project")

7.4.3  [Get All Projects](https://github.com/XunFlowerrr/backend-tutorial/tree/9e5d0c8720266369a795785a24703f0a6872e8cf "7.4.3 Get All Projects")

7.4.4  [Get Project From ID](https://github.com/XunFlowerrr/backend-tutorial/tree/fcde03ae25462d29df537c4bacdc34302e8c69d5 "7.4.4 Get Project From ID")

7.4.5  [Update Project](https://github.com/XunFlowerrr/backend-tutorial/tree/265f2132741fa9e5cc4183a72ef3d1def07f68c2 "7.4.5 Update Project")

7.4.6  [Delete Project](https://github.com/XunFlowerrr/backend-tutorial/tree/c18f22aee8c740e2f4f369ef4d178e2855256ca7 "7.4.6 Delete Project")

7.4.7  [สร้าง Route ใหม่ใน index.js](https://github.com/XunFlowerrr/backend-tutorial/tree/045a14b998d71aaa4a2a5315e6a3b50270848f0f "7.4.7 สร้าง Route ใหม่ใน index.js")

7.4.9  [สำหรับตารางอื่นๆ](https://github.com/XunFlowerrr/backend-tutorial/tree/fac62147560ca7ccda7d2943f3d1a68244aaf1c5 "7.4.9 สำหรับตารางอื่นๆ")

