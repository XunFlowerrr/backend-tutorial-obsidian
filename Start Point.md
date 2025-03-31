# **สิ่งที่ควรทราบก่อนเริ่ม**

## **Client คืออะไร**

![[Client]]

## **Server คืออะไร**

![[Server]]

## **HTTP**

![[1_hUWVb9Ecll30810Ni1Oq8Q.webp]]

- HTTP Request คือ การส่งคำขอจากฝั่ง _[[Client]]_ ไปยังฝั่ง _[[Server]]_ เพื่อต้องการข้อมูลบางอย่าง ^2d82a9
- HTTP Response คือ การที่ _Server_ ส่งข้อมูลที่ _Client ร้องขอกลับมา_ ^7b3493
- HTTP คือ Protocol ที่ใช้ในการเชื่อมต่อระหว่าง Client และ Server

🔶 **💡เปรียบเทียบให้เห็นภาพ**
ลองจินตนาการว่า **บ้านของ Frontend** (ฝั่ง Client) คือผู้ส่งจดหมาย และ **บ้านของ Backend** (ฝั่ง Server) คือบ้านของเพื่อนที่เราอยากขอข้อมูลบางอย่าง เช่น รายชื่อสินค้า หรือข้อมูลผู้ใช้งาน

- **HTTP Request** ก็เหมือนกับ **จดหมายที่ส่งจากบ้าน Frontend ไปบ้าน Backend** เพื่อขอข้อมูล
- **HTTP Response** ก็เหมือนกับ **จดหมายตอบกลับจากบ้าน Backend มายังบ้าน Frontend** พร้อมกับข้อมูลที่เราขอไว้ เช่น รายการสินค้า, ผลลัพธ์ของการสมัครสมาชิก, หรือผลการเข้าสู่ระบบ
- ส่วน **HTTP Protocol** ก็คือ **ระบบไปรษณีย์มาตรฐาน** ที่ใช้ในการส่งจดหมายระหว่างบ้านทั้งสองหลังให้สื่อสารกันได้ถูกต้องและมีรูปแบบที่แน่นอน

### **Component of HTTP Request Message**

การที่ [[Client]] ส่งคำร้องไปหา Server นั้นจะมีรูปแบบของการส่ง เรียกว่า [[Start Point#^2d82a9|_HTTP Request Message_]] คือส่วนที่บอกข้อมูลรายละเอียดให้กับอีกฝั่งทราบ (ในที่นี้คือ [[Server]]) ซึ่ง [[Start Point#^7b3493|HTTP Response]] ก็มีลักษณะเช่นเดียวกัน

🔶 **💌 เปรียบเทียบกับจดหมาย**
ลองนึกภาพว่า HTTP Request คือจดหมายที่เราส่งออกไป มันจะต้องมีส่วนประกอบครบถ้วนเหมือนจดหมายจริงๆ เพื่อให้ปลายทางเข้าใจว่าเราต้องการอะไร เช่น

### **HTTP Request Message ประกอบด้วย 3 ส่วน**

![[1_FOH7gWJH5CA20pCaKoABvg.gif]]

#### **1. Request Line**
คือส่วนที่ระบุ HTTP Method, URI และ Version ของ Protocol ที่ใช้ (HTTP/1.0, HTTP/1.1, HTTP/2.0)
- HTTP Method คือ วิธีการที่ Client ใช้ในการร้องขอข้อมูลจาก Server เช่น GET, POST, PUT, DELETE
- URI (Uniform Resource Identifier) คือ ที่อยู่ของ Resource ที่ Client ต้องการร้องขอ เช่น /api/user, /api/product
- Version คือ เวอร์ชันของ Protocol ที่ใช้ในการเชื่อมต่อ เช่น HTTP/1.1, HTTP/2.0

🔶 **✉️ เปรียบเทียบกับหน้าซองจดหมาย**
- HTTP Method เหมือนการระบุว่าเราส่งจดหมายเพื่อ **ขอของ (GET)**, **ส่งข้อมูลใหม่ (POST)**, หรือ **อัปเดตของเดิม (PUT)**
- URI คือ **ชื่อและที่อยู่ของเพื่อนที่เราจะส่งจดหมายถึง**
- Version ก็เหมือนกับ **มาตรฐานการเขียนจดหมาย** ที่ทั้งสองฝ่ายเข้าใจร่วมกัน เช่น จะเขียนด้วยภาษาทางการหรือไม่

#### **2. Header**
คือส่วนที่ระบุข้อมูล และกฏต่างๆ ในการเชื่อมต่อ เช่น
- **Content-type** คือระบุประเภทของข้อมูลใน Body ที่จะส่งไปพร้อมกับ Request เช่น application/json, text/html
- **accept-language** คือระบุภาษาที่ Client รองรับ เช่น en-US, th-TH
- **user-agent** คือระบุประเภทของ Client เช่น Mozilla/5.0 (หรือก็คือ Request นี้ถูกส่งมาจาก Browser Mozilla Firefox นั่นเอง)

🔶 **📦 เปรียบเทียบกับบันทึกแนบในจดหมาย**
Header ก็เหมือนกับ **กระดาษโน้ตหรือสัญลักษณ์แนบในจดหมาย** ที่บอกว่า
- "สิ่งที่แนบมานี้เป็นเอกสาร PDF นะ" (`Content-Type`)
- "กรุณาตอบกลับเป็นภาษาไทยหรืออังกฤษ" (`accept-language`)
- "จดหมายนี้ส่งมาจากมือถือหรือคอมพิวเตอร์" (`user-agent`)

#### **3. Body**
คือส่วนที่เก็บข้อมูลที่ต้องการส่งไปยัง Server เช่น ข้อมูลการ Login, ข้อมูลการ Register, ข้อมูลการ Update Profile เป็นต้น
- Body จะมีเฉพาะในบาง HTTP Method เท่านั้น เช่น POST, PUT, PATCH

🔶 **📄 เปรียบเทียบกับเนื้อหาของจดหมาย**
Body ก็คือ **สิ่งที่เราอยากพูดหรือร้องขอในจดหมายนั้นจริงๆ** เช่น
- "สวัสดีครับ ผมชื่อ... ผมต้องการลงทะเบียน"
- "นี่คือรายละเอียดการสั่งซื้อของผม กรุณายืนยันกลับด้วย"

### **HTTP Method**
HTTP Request Method คือส่วนที่ใช้กำหนดประเภทของคำร้องขอ โดยจะมีอยู่ 4 Methods ที่ใช้งานบ่อย มีดังนี้
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

🎯 สรุป: HTTP Method คือ **เป้าหมายหลักของการสื่อสารในแต่ละจดหมาย** ว่าเราจะ "ขอข้อมูล", "เพิ่ม", "อัปเดต" หรือ "ลบ" สิ่งใดจากบ้าน Backend

### **HTTP Status Code**

^16cb86

เมื่อ _[[Server]]_ ได้รับ _[[Start Point#^2d82a9|HTTP Request]]_ แล้ว จะทำการประมวลผลคำร้องขอ และส่งกลับไปยัง _[[Client]]_ โดยจะมีการส่ง _[[Start Point#^7b3493|HTTP Response]]_ กลับไปด้วย ซึ่งใน _[[Start Point#^7b3493|HTTP Response]]_ จะมีส่วนที่เรียกว่า _[[Start Point#^16cb86|Status Code]]_ เพื่อบอกสถานะของคำร้องขอที่ส่งไปว่าเป็นอย่างไร เช่น
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
เมื่อเราส่งจดหมาย (HTTP Request) ไปที่บ้าน Backend ฝั่งตรงข้าม ก็เหมือนเรารอรับจดหมายตอบกลับกลับมา ซึ่งในจดหมายนั้นจะมี **"สถานะการตอบกลับ"** ว่าเกิดอะไรขึ้น เช่น:

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

🎯 สรุป: HTTP Status Code คือ **ข้อความสั้นๆ ในจดหมายตอบกลับ** จากบ้าน Backend เพื่อบอกเราว่าผลของคำขอเป็นอย่างไร — สำเร็จ, ล้มเหลว, หรือระบบมีปัญหา

# ขั้นตอนทั้งหมดของการทำ Backend
## **1. สร้างโฟลเดอร์**
### **1.1 สร้างโฟลเดอร์ในตำแหน่งที่ต้องการ**
![[Pasted image 20250401034412.png]]
### **1.2 เปิดโฟลเดอร์ สร้างโฟลเดอร์ย่อยข้างใน**
สร้างโฟลเดอร์ backend และ frontend
![[Pasted image 20250401034424.png]]
## **2. Setup Database**
### **2.1 สร้างไฟล์ Docker Compose**

สร้างไฟล์ docker-compose.yml ในโฟลเดอร์ใหญ่

![[Pasted image 20250401034840.png]]

docker-compose.yml

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

### **2.2 สร้างไฟล์ init.sql**
สร้างโฟลเดอร์ database และสร้างไฟล์ init.sql ในโฟลเดอร์นั้น
![[Pasted image 20250401035227.png]]

ในไฟล์ init.sql ให้ใส่คำสั่ง SQL (DDL) ที่ต้องการให้สร้างตารางใน Database

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

### **2.3 วิธี run database**
#### 2.3.1 เปิด Docker Desktop ขึ้นมา
![[20250331-2102-30.8108024.mp4]]

#### 2.3.2 ถ้ามี container ให้ลบ container ที่มีอยู่แล้ว
![[20250331-2109-07.5062965.mp4]]

#### 2.3.3 เปิด terminal ขึ้นมาในโฟลเดอร์ใหญ่ที่มีไฟล์ docker-compose.yml
สามารถเปิด powershell ก็ได้ หรือจะใช้ terminal ใน VS Code ก็ได้ ในตัวอย่างนี้จะใช้ terminal ใน VS Code
และพิมพ์คำสั่ง

```bash
docker-compose up
```


![[20250331-2133-18.5619454.mp4]]

ถ้าเราเห็นข้อความว่า "database system is ready to accept connections" แสดงว่า database ของเราพร้อมใช้งานแล้ว


#### 2.3.4 !!!ถ้ามีการเปลี่ยนแปลงไฟล์ init.sql!!!
ถ้ามีการเปลี่ยนแปลงไฟล์ init.sql แล้วต้องรีสตาร์ท database มี 2 วิธี

- **วิธีที่ 1**: ลบ container ที่มีอยู่แล้วใน Docker Desktop แล้วรัน docker-compose up ขึ้นมาใหม่
![[20250331-2144-03.6506825.mp4]]

- **วิธีที่ 2**: ใช้คำสั่งใน terminal

```bash
docker-compose down
docker-compose up
```

![[20250331-2145-23.2271100.mp4]]

## **3. สร้าง npm project**
### **3.1 เปิด terminal ขึ้นมาในโฟลเดอร์ backend**
และพิมพ์คำสั่ง

```bash
npm init -y
```

![[20250331-2152-06.9653725.mp4]]

### **3.2 ติดตั้ง express, nodemon**
พิมพ์คำสั่ง

```bash
npm install express     หรือ npm i express
```

```bash
npm install nodemon --save-dev     หรือ npm i nodemon --save-dev
```

![[20250331-2159-48.3310727.mp4]]

### 3.3 เลือกใช้ nodemon ในการรันโปรเจค
![[20250331-2203-00.4222062.mp4]]

### 3.4 เลือกใช้วิธีในการ import
เนื่องจาก Javascript มี 2 วิธีในการ import คือ

- **CommonJS**: ใช้ `require`
``` javascript
const express = require('express');
```

- **ES Module**: ใช้ `import`
``` javascript
import express from 'express';
```

ในตัวอย่างนี้จะใช้ `Es Module` ดังนั้นให้ไปที่ไฟล์ package.json แล้วเพิ่ม `"type": "module"` เข้าไปในไฟล์ package.json

![[20250331-2208-29.1184242.mp4]]

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
## **4. สร้างไฟล์ index.js และ Express เบื้องต้น**
### **4.1 สร้างไฟล์ index.js**
สร้างไฟล์ index.js ในโฟลเดอร์ backend

```javascript
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

คือการบอกให้ _[[Server]]_ รอรับคำร้องขอจาก _[[Client]]_ ที่พอร์ตเลขที่เก็บไว้ในตัวแปร PORT (ในที่นี้คือ 3000) และเมื่อ _[[Server]]_ เริ่มทำงาน จะมีการแสดงข้อความใน console ว่า "Server is running on http://localhost:3000"

🔶 **🏠 เปรียบเทียบแบบบ้านและจดหมาย**
- `const app = express();` 👉 เหมือนกับเรากำลังสร้าง "บ้านเปล่าๆ" ยังไม่มีห้อง ไม่มีที่อยู่ชัดเจน
- `app.listen(PORT)` 👉 คือการ **บอกที่อยู่บ้าน (บ้านเลขที่)** ให้คนอื่นรู้ว่าจะมาหาเราที่พอร์ตไหน เช่น `localhost:3000`
- เมื่อบ้านพร้อมและมีเลขที่แล้ว ก็สามารถ **เปิดรับจดหมายจากเพื่อนบ้าน (Client)** ได้แล้ว

---

### **4.2 รับ HTTP Request**
ในส่วนนี้เราจะเรียนรู้วิธีการรับ HTTP Request โดยใช้ Express

```javascript
app.[ชื่อ HTTP Method] ([path], [handler function])
```

ซึ่ง handler function อาจจะมี 2 รูปแบบคือ

- **Normal Function**
```javascript
function handlerFunction(req, res) {
  res.send('Hello World');
}

app.get('/api/user', handlerFunction);
```

- **Arrow Function**
```javascript
app.get('/api/user', (req, res) => {
  res.send('Hello World');
});
```

โดย Function ที่เราสร้างขึ้นจะมี 2 parameter คือ
- **req**: คือ Request Object ที่เก็บข้อมูลของคำร้องขอที่ส่งมาจาก _[[Client]]_
- **res**: คือ Response Object ที่ใช้ในการส่งข้อมูลกลับไปยัง _[[Client]]_

🔶 **🏠✉️ เปรียบเทียบแบบบ้าน-ห้อง-จดหมาย**
- `app.get("/")` 👉 คือการสร้าง "ห้องรับแขก" ในบ้านของเรา ที่อยู่ตำแหน่ง `/`
- `"GET"` 👉 คือวิธีที่ใช้ส่งจดหมายมาห้องนี้ เช่น “เขียนจดหมายมาขอข้อมูลที่ห้องรับแขก”
- `res.send(...)` 👉 คือการตอบกลับจากห้องนั้น ว่าจะส่งอะไรกลับไปให้ผู้ที่ส่งจดหมายเข้ามา

📌 ดังนั้นถ้าเรามีโค้ดแบบนี้:

```javascript
app.get("/", (req, res) => {
  res.send("Hello World from GET request!");
});
```

จะหมายความว่า
> "ถ้ามีคนส่งจดหมายแบบ **GET** มาที่บ้านของเรา (ที่ `localhost:3000`) และเจาะจงมาที่ **ห้องรับแขก `/`**,
> เราจะตอบกลับไปว่า **'Hello World from GET request!'**"

🎯 สรุป:
- บ้าน = `app`
- ห้อง = endpoint เช่น `/`, `/api/user`
- จดหมาย = HTTP Request
- วิธีส่งจดหมาย = Method (GET, POST, PUT, DELETE)
- การเปิดบ้านให้คนมาหาได้ = `app.listen(...)`

![[20250331-2234-58.4582297.mp4]]
## **5. ใช้ Environment Variables**

เนื่องจากบางครั้งเราต้องการเก็บข้อมูลที่เป็นความลับ เช่น รหัสผ่าน, Token, หรือ URL ของ Database ซึ่งไม่ควรเก็บไว้ในโค้ดโดยตรง หรือ บางตัวแปรที่เราต้องการให้เปลี่ยนแปลงได้ตามสภาพแวดล้อมเช่น เมื่อเรา deploy ขึ้น server จริงๆ เราอาจจะต้องการให้ URL ของ Database เปลี่ยนไปจาก localhost เป็น IP Address ของ Server จริงๆ หรือเมื่อเปลี่ยนจาก Development เป็น Production เราอาจจะต้องการให้ PORT เปลี่ยนไปจาก 3000 เป็น 80 หรือ 443 เป็นต้น
ดังนั้นเราจึงต้องใช้ Environment Variables เพื่อเก็บข้อมูลเหล่านี้ โดยเราจะใช้ package ที่ชื่อว่า `dotenv` ในการโหลด Environment Variables จากไฟล์ `.env` เข้ามาใน process.env
### **5.1 ติดตั้ง dotenv**
พิมพ์คำสั่ง

```bash
npm install dotenv
```

### **5.2 สร้างไฟล์ .env**
สร้างไฟล์ .env ในโฟลเดอร์ backend

.env
```env
PORT=3000
```

### **5.3 ใช้งาน Environment Variables**
ในไฟล์ index.js ให้ import package dotenv ขึ้นมา และเรียกใช้ฟังก์ชัน config() เพื่อโหลด Environment Variables จากไฟล์ .env เข้ามาใน process.env

```javascript
import express from "express";
import dotenv from "dotenv";
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


## **6. เขียนโค้ดเชื่อมต่อกับ Database**
## **7. สร้าง Router ต่างๆ**
## **8. สร้าง Controller ต่างๆ**
## **9. สร้าง User Authentication**

