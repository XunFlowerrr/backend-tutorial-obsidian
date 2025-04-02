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

SQL Database นั้นจริงๆ แล้วมีหลายตัวมาก เช่น MySQL, PostgreSQL, SQLite แต่ในที่นี้จะใช้ PostgreSQL เนื่องจากเป็น Database ที่นิยมใช้กันมากในปัจจุบัน และมีความสามารถในการจัดการข้อมูลที่ซับซ้อนได้ดี
และ สาเหตุที่ต้องเปิดใน Docker เพราะว่า Docker ช่วยให้การติดตั้งและจัดการ Database เป็นไปอย่างง่ายดายและรวดเร็ว โดยไม่ต้องกังวลเกี่ยวกับการตั้งค่าและการจัดการไฟล์ต่างๆ ที่เกี่ยวข้องกับ Database

ตัว Docker จะช่วยให้เราสามารถสร้าง Container ที่มี PostgreSQL ติดตั้งอยู่ภายในได้อย่างรวดเร็ว และสามารถลบหรือรีสตาร์ท Container ได้ง่ายๆ โดยไม่กระทบกับระบบปฏิบัติการหลักของเรา

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

^4e71ae

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
//index.js
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
### **6.1 ติดตั้ง pg**
พิมพ์คำสั่ง
pg คือ package ที่ใช้ในการเชื่อมต่อกับ PostgreSQL Database

```bash
npm install pg
```
### **6.2 สร้าง Folder ชื่อ config และข้างในสร้างไฟล์ database.js**

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

![[20250331-2317-13.2749414.mp4]]

### **6.3 ทดสอบว่าต่อ Database สำเร็จหรือไม่**

สร้างไฟล์ test.js ในโฟลเดอร์ backend

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

ถ้าขึ้นว่า "Connected to the database" แสดงว่าเชื่อมต่อกับ Database สำเร็จแล้ว
ถ้าขึ้นว่า Error ให้ตรวจสอบว่า Docker รันอยู่หรือเปล่า ถ้าไม่ได้ให้รันให้ไปทำ [[Start Point#^4e71ae| เปิด Docker]]

## 7. สร้าง Router และ Controller

Router คือการจัดการเส้นทางของ URL ที่เราต้องการให้ _[[Server]]_ ตอบสนองต่อ _[[Client]]_ โดยเราจะสร้าง Router แยกตามฟังก์ชันการทำงาน เช่น User, Project, Task, Attachment, Project Member, Task Assignee
เหตุที่ต้องแยก Router ออกไปเป็นไฟล์ต่างๆ เพราะว่าเมื่อแอปพลิเคชันมีขนาดใหญ่ขึ้น URL จะมีความซับซ้อนมากขึ้นและการจัดการ Router ในไฟล์เดียวอาจทำให้โค้ดยุ่งเหยิงได้
ดังนั้นเราจึงควรแยก Router ออกไปเป็นไฟล์ต่างๆ เพื่อให้โค้ดอ่านง่ายและดูแลรักษาง่ายขึ้น

🔶 **🏠 เปรียบเทียบแบบบ้าน – Router คือโถงทางเดิน**
- ลองนึกว่า `app` คือบ้านหลังหนึ่ง
- ในบ้านมีหลาย "ห้อง" (endpoint) เช่น ห้อง user, ห้อง project, ห้อง task
- การเขียน Route แบบตรงๆ ใน `index.js` คือการ “เอาประตูแต่ละห้องไปวางไว้กลางบ้าน” ซึ่งพอห้องเยอะขึ้น บ้านก็จะรกรุงรัง
- แต่ถ้าเราใช้ `Router` ก็เหมือนกับการสร้าง "โถงทางเดิน" ที่แยกแต่ละห้องไว้เป็นสัดส่วน เช่น `userRouter`, `taskRouter`
- จากนั้นโถงทางเดินแต่ละสายก็เชื่อมกับห้องนั้นๆ ไปอีกที

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

เห็นได้ว่าเรานั้นไม่ต้อง มาเขียน "/api/v1/user" ซ้ำๆ หลายๆ ครั้ง
และยังสามารถจัดการ Route ได้ง่ายขึ้น

---

ต่อไปคือ **Controller**

Controller คือการจัดการ Logic ของ API ที่เราต้องการให้ _[[Server]]_ ทำงาน เช่น การดึงข้อมูลจาก Database, การประมวลผลข้อมูล, การส่งข้อมูลกลับไปยัง _[[Client]]_

🔶 **🧑‍🍳 เปรียบเทียบกับคนในห้องที่ทำหน้าที่เฉพาะทาง**
- Router เหมือนโถงทางเดินที่พาเราไปถึง “ห้องต่างๆ”
- Controller คือ “คนที่อยู่ในห้องนั้นๆ” ที่รับคำสั่งและทำงานจริง เช่น จัดการข้อมูลผู้ใช้
- ถ้าเรายัด logic ไว้ใน Router โดยตรง ก็เหมือนเรามี “คนทำงานเต็มทางเดิน” ทำให้บ้านรกและดูแลยาก
- ถ้าแยกเป็น Controller ก็เหมือนให้ "พนักงานแต่ละคนอยู่ในห้องของตัวเอง" และโถงทางเดินก็แค่พาเราไปหาเขา

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

เราจะเห็นว่า Logic ของ API นั้นอยู่ใน Router ซึ่งทำให้โค้ดดูยุ่งเหยิงและอ่านยาก
เราสามารถแยก Logic (arrow function) ออกไปเป็น Controller ได้ โดยการสร้างไฟล์แยกออกไป เช่น userController.js

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

### **7.1 สร้าง Folder ชื่อ routes**
สร้าง Folder ชื่อ routes และ Folder ชื่อ controllers ใน backend

![[Pasted image 20250401114259.png]]

### **7.2 เดี๋ยวพาทำของ User**
โอเค! ตอนนี้เราจะทำส่วนของ User ก่อนนะ

โดย User ควรจะมีการลงทะเบียน (Register) และเข้าสู่ระบบ (Login)
- ลงทะเบียน (Register) คือการสร้างบัญชีผู้ใช้ใหม่
- เข้าสู่ระบบ (Login) คือการตรวจสอบว่าผู้ใช้มีบัญชีอยู่ในระบบหรือไม่
(- ออกจากระบบ (Logout) คือการทำให้ผู้ใช้ไม่สามารถเข้าถึงข้อมูลส่วนตัวได้อีกต่อไป แต่การออกจากระบบจะเป็นส่วนของ Frontend)

ดังนั้นเราจะสร้าง Router และ Controller สำหรับ User ขึ้นมา
โดยเราจะสร้าง Router โดยคิดก่อนว่าเราจะต้องการทำอะไรที่เกี่ยวกับ User บ้าง
ในที่นี้เราจะมีการลงทะเบียน (Register) และเข้าสู่ระบบ (Login)

🔶 **🧑‍🍳 เปรียบเทียบกับคนในห้องที่ทำหน้าที่เฉพาะทาง**
- Router เหมือนโถงทางเดินที่พาเราไปถึง “ห้องต่างๆ”
- Controller คือ “คนที่อยู่ในห้องนั้นๆ” ที่รับคำสั่งและทำงานจริง เช่น จัดการข้อมูลผู้ใช้

**โดยบ้านหลักเราอยู่ที่ตำแหน่ง  (starting point of server):**
```
http://localhost:3000/
```


**เรามีโถงทางเดินที่พาเรามาห้องที่เกี่ยวกับ User (authRouter):**
```
/api/v1/auth/
```


**ในโถงทางเดินนี้ (/api/v1/auth/) มีห้องย่อยๆ ที่ทำหน้าที่ต่างกันคือ (authRouter)**

- ห้องลงทะเบียน (Register): ที่มีวิธีการเข้าห้องคือ POST
```
/register
```

- ห้องเข้าสู่ระบบ (Login): ที่มีวิธีการเข้าห้องคือ POST
```
/login
```


ดังนั้นเส้นทางที่อยู่ในปลายทางของ Http Request หรือซองจดหมายที่เราจะส่งไปยังห้องต่างๆ จะมีลักษณะดังนี้
```
POST http://localhost:3000/api/v1/auth/register
POST http://localhost:3000/api/v1/auth/login
```

POST http://localhost:3000/api/v1/auth/register
POST http://localhost:3000/api/v1/auth/login

เกร็ดความรู้ ทำไมต้องเป็น /api/v1/auth/

📌 ทำไมต้องมี API Versioning เช่น /api/v1/ ?

เมื่อเราเริ่มต้นพัฒนา API สำหรับแอปหรือเว็บไซต์ เราอาจคิดว่าเส้นทางแบบง่าย ๆ เช่น /register หรือ /login ก็เพียงพอแล้ว
แต่นั่นเป็นเพียงจุดเริ่มต้นเท่านั้น เพราะเมื่อระบบเติบโต ฟีเจอร์มากขึ้น และมีผู้ใช้งานหลากหลายประเภท
เราจะต้องมีการ **เปลี่ยนแปลง** API อยู่เรื่อย ๆ เช่น เปลี่ยนรูปแบบข้อมูล เพิ่มฟิลด์บังคับ หรือปรับปรุงกระบวนการยืนยันตัวตน
หากเราเปลี่ยนแปลงโดยไม่แยกเวอร์ชัน จะเกิดปัญหากับผู้ใช้งานเดิมทันที

✅ API Versioning คือแนวทางแก้ไขปัญหานี้ โดยการกำหนดเวอร์ชันไว้ใน URL เช่น /api/v1/
เพื่อแยกความสามารถและข้อกำหนดของ API แต่ละรุ่นออกจากกัน ทำให้ระบบมีความยืดหยุ่นและเสถียร

✅ ผู้ใช้เก่าสามารถใช้ API เวอร์ชันเดิมต่อไปได้โดยไม่พัง
✅ ผู้ใช้ใหม่สามารถใช้ฟีเจอร์ล่าสุดใน API เวอร์ชันใหม่ได้ทันที

ตัวอย่าง:
- /api/v1/auth/register => API รุ่นแรก
- /api/v2/auth/register => API รุ่นใหม่ที่อาจรองรับ OAuth, ส่งรหัส OTP หรือโครงสร้างข้อมูลใหม่

❌ ถ้าไม่มี API Versioning:
- ผู้ใช้เก่าจะได้รับ Error เมื่อ API เปลี่ยนไป
- แอปเก่าจะไม่สามารถสื่อสารกับ Backend ได้
- นักพัฒนาอาจต้องเขียนโค้ดซับซ้อนเพื่อรองรับหลายเวอร์ชันใน endpoint เดียว

🎯 สรุป: การมี /api/v1/ คือการ "จัดระเบียบ" และ "วางแผนอนาคต" ของระบบให้เติบโตได้อย่างมั่นคง


#### 7.2.1 สร้างไฟล์ authRouter.js ใน Folder routes

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

#### 7.2.2 สร้างไฟล์ authController.js ใน Folder controllers
ในตอนนี้ยังไม่ต้องเขียน Logic อะไรใน Controller เดี๋ยวเราจะลองดูก่อนว่าสร้าง Router และ Controller ถูกต้องหรือไม่ โดยให้ส่ง Response กลับไปว่า "User registered successfully" และ "User logged in successfully" ก่อน
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

#### 7.2.3 เพิ่ม authRouter ใน index.js
ใน index.js ให้ import authRouter เข้ามาและใช้ Router ที่เราสร้างขึ้น
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


เค้าจะใช้ Postman ในการทดสอบ API ของเรา
Postman เป็นเครื่องมือที่ใช้ในการทดสอบ API โดยเราสามารถส่ง Request ไปยัง API ของเราได้
Postman จะช่วยให้เราสามารถทดสอบ API ได้ง่ายขึ้น โดยไม่ต้องเขียน Code ขึ้นมาเอง
เดี๋ยวเราจะลองใช้ Post man เพื่อทดสอบดูว่าเราสร้าง Router และ Controller ถูกต้องหรือไม่


#### 7.2.4 ทดสอบ API ด้วย Postman
- 1. มั่นใจว่า Run Docker อยู่
- 2. เปิด run backend ด้วย คำสั่ง
```bash
npm run dev
```
- 3. เปิด Postman ขึ้นมา
- 4. สร้าง Request ใหม่ โดยเลือก Method เป็น POST
- 5. ใส่ URL เป็น
```
http://localhost:3000/api/v1/auth/register
```
- 6. กด Send
- 7. ถ้าสำเร็จจะได้ Response กลับมาว่า
```json
{
    "message": "User registered successfully"
}
```

![[Untitled video - Made with Clipchamp.mp4]]

ถ้าทำสำเร็จจะได้แสดงว่า เราได้สร้าง Router และ Controller สำหรับ User ได้ถูกต้องแล้ว
แต่ตอนนี้เรายังไม่ได้ส่งข้อมูลอะไรไปยัง Backend เลย เราส่ง Request เปล่าๆ ไป
ดังนั้นขั้นตอนต่อไปเราจะต้องส่งข้อมูลไปยัง Backend ด้วย


#### 7.2.5 ส่งข้อมูลไปยัง Backend
ในตอนนี้เราจะส่งข้อมูลไปยัง Backend โดยการใช้ Body ของ Request
Body คือข้อมูลที่เราต้องการส่งไปยัง Backend โดยเราสามารถส่งข้อมูลได้หลายรูปแบบ เช่น JSON, Form Data, x-www-form-urlencoded
ในที่นี้เราจะใช้ JSON เป็นรูปแบบในการส่งข้อมูลไปยัง Backend
แต่ก่อนที่ Backend ของเราจะรับ Body ที่เป็น JSON ได้ เราต้องบอก Express ว่าให้ใช้ Body Parser ในการแปลง Body ที่ส่งมาจาก Client(Frontend) เป็น JSON ก่อน

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

และใน authController.js ให้เพิ่มการรับข้อมูลจาก Body ของ Request
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

แล้วใน Postman ให้เลือก Body และเลือก raw และเลือก JSON แล้วใส่ข้อมูลตามนี้
```
{
    "username": "testuser",
    "password": "testpassword"
}
```
แล้วกด Send

![[20250402-1242-22.4709951.mp4]]

ถ้าเราทำถูกต้องจะได้ Response กลับมาว่า
```json
{
  "message":"User registered successfully",
  "username":"testuser",
  "password":"testpassword"
}
```

#### 7.2.6 ทำ Logic การลงทะเบียน (Register)

ใน authController.js ให้ทำ Logic การลงทะเบียน (Register) และเข้าสู่ระบบ (Login) แต่การเก็บข้อมูล User นั้นจะมีประเด็นนิดหน่อยนั่นคือ
- เราไม่ควรเก็บ Password ของ User ไว้ใน Database แบบโดยไม่เข้ารหัส

ดังนั้นเราจะทำยังไงดี
คำตอบก็คือ มี Package(Library) ที่ชื่อว่า bcrypt เป็น Package ที่ใช้ในการเข้ารหัสต่างๆ (Encrypt) ข้อมูลให้ใช้ได้ง่ายๆผ่าน Fucntion ที่ Package นี้ให้มา

เกร็ดความรู้
hash function นั้นมีขั้นตอนการเข้ารหัสที่แน่นอน ซึ่งหมายความว่า
- ถ้า Input เหมือนเดิม Hash output ก็จะเหมือนเดิม

สมมุติว่ามี User 2 คนที่ตั้ง Password เหมือนกันในระบบของเราก็จะมี Password ที่เหมือนกันใน Database ซึ่งเป็นเรื่องที่ไม่ดี เพราะถ้าหากมีคนแฮกข้อมูลใน Database ของเราได้ เขาก็จะรู้ Password ของ User ทุกคนที่ใช้ Password เดียวกัน

ดังนั้นจึงมีสิ่งที่เรียกว่า Salt
Salt คือการเพิ่มข้อมูลที่ไม่ซ้ำกันเข้าไปใน Passwordเดิม ก่อนที่จะทำการ Hash
มันเหมือนกับการส่ม string ขึ้นมาตัวนึง ต่อท้ายกับ Password แล้วค่อยเอาอันที่ต่อแล้วไป Hash
เนื่องจาก Salt นั้นจะถูกสร้างขึ้นมาแบบสุ่มในแต่ละครั้งที่มีการลงทะเบียน User ใหม่
ดังนั้นถ้าสมมุติว่า User 2 คนใช้ Password เดียวกัน แต่ Salt ที่ใช้ในการ Hash แตกต่างกัน
Password ที่ได้จากการ Hash ก็จะไม่เหมือนกัน

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

จะเห็นว่า Hashed Password 1 และ Hashed Password 2 นั้นไม่เหมือนกัน
แม้ว่าจะใช้ Password เดียวกันก็ตาม
ดังนั้นการใช้ Salt จะทำให้ Password ที่เก็บใน Database นั้นไม่เหมือนกัน แม้ว่าจะมี User 2 คนที่ใช้ Password เดียวกันก็ตาม



ดังนั้นเราจะใช้ Package นี้ในการเข้ารหัส Password ของ User ก่อนที่จะเก็บลง Database
เราจะใช้ bcrypt ในการเข้ารหัส Password ของ User โดยการติดตั้ง Package นี้ก่อน

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
#### 7.2.7 ทำ Logic การเข้าสู่ระบบ (Login)

โอเค! ตอนนี้เราจะทำ Logic การเข้าสู่ระบบ (Login) โดยการตรวจสอบว่า User มีอยู่ในระบบหรือไม่
แต่การ Login ก็มีประเด็นเหมือนกัน
นั่นคือ เราเป็น Backend เราไม่รู้ว่า frontend ของเรานั้นเข้าสู่ระบบหรือยัง

📌 สมมุติว่า User คนหนึ่ง Login เข้ามาในระบบผ่านหน้าเว็บสำเร็จ แล้วหลังจากนั้นเขาก็เข้าไปยังหน้า Dashboard
**คำถามคือ** เราจะรู้ได้ยังไงว่า User คนนี้ Login แล้วจริง ๆ?

✅ วิธีที่นิยมใช้ในการแก้ปัญหานี้ในระบบ Web ทั่วไปก็คือ **การส่ง Token (โทเคน)** กลับไปให้ฝั่ง Frontend หลังจากที่ Login สำเร็จ

---

##### 🔑 Token คืออะไร?

- Token คือ “หลักฐานยืนยันตัวตน” ที่เราจะสร้างขึ้นมา และส่งกลับไปให้ Client (Frontend)
- โดยทั่วไป Token จะเก็บข้อมูลของ User ที่ Login เข้ามา
- แล้ว Frontend ก็จะต้องแนบ Token นี้มาด้วยทุกครั้งที่เรียกใช้งาน API ที่ต้องมีการยืนยันตัวตน

---

#### 🔐 แล้วเราจะสร้าง Token อย่างไร?

💡 คำตอบคือ เราจะใช้ **JWT (JSON Web Token)**

---

#### JWT คืออะไร?

JWT (JSON Web Token) คือ มาตรฐานการเข้ารหัสข้อมูลให้อยู่ในรูปแบบของ Token ที่สามารถใช้ส่งข้อมูลระหว่างระบบแบบปลอดภัย
ซึ่งใน JWT จะมีทั้งหมด 3 ส่วนหลัก ๆ คือ:

1. **Header** – บอกว่าใช้วิธีเข้ารหัสแบบไหน เช่น HS256
2. **Payload** – ข้อมูลที่เราอยากฝังไว้ใน Token เช่น user_id, email, role เป็นต้น
3. **Signature** – ลายเซ็นที่ใช้ยืนยันว่า Token นี้ถูกสร้างโดยเรา (Server)

🧠 เมื่อ User Login สำเร็จ เราจะสร้าง JWT Token ให้ และแนบข้อมูลที่จำเป็นลงไปใน Payload
จากนั้นส่ง Token กลับไปให้ฝั่ง Frontend เก็บไว้ เช่นใน LocalStorage หรือ Cookie

และในการเรียก API ถัด ๆ ไป ฝั่ง Frontend ก็จะแนบ JWT Token นี้มาใน Header ของ HTTP Request
เช่น:
```
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

ดังนั้นต่อกันเลยยย
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

^84a15c

ก่อนใช้งาน JWT Token เราต้องสร้าง Secret Key ขึ้นมาก่อน
ซึ่ง Secret Key นี้จะถูกใช้ในการเข้ารหัส Token และตรวจสอบความถูกต้องของ Token
โดย Secret Key นี้จะต้องเก็บเป็นความลับ ไม่ควรเปิดเผยให้ใครรู้
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

ใน Token ที่เราสร้างขึ้นมานั้นจะมีข้อมูลที่ Backend ตอบกลับไปให้ Frontend ฝั่งเก็บไว้ สิ่งที่ฝังไว้จะเป็นตาม Function [[Start Point#^84a15c | generateToken ของเรา]]
ซึ่งเราสามารถลองนำ Token มาถอดรหัสได้ที่ https://jwt.is/



จากในรูปจะเห็นว่า Token ที่เราสร้างขึ้นมา เมื่อถอดรหัสนั้นจะมีข้อมูลที่เราฝังไว้

### **7.3 เดี๋ยวจะพาทำส่วนของ Project ก่อน**
โอเค! ตอนนี้เราจะทำส่วนของ Project ก่อนนะ
โดย Project เนี่ยเราควรจะขอได้ว่ามีโปรเจคอะไรบ้างในระบบของเรา ควรจะสร้างโปรเจคใหม่ได้ ควรจะแก้ไขข้อมูลโปรเจคที่มีอยู่ในได้ และควรจะลบโปรเจคที่ไม่ต้องการออกไป
4 ฟังก์ชันการทำงานนี้มักถูกเรียกว่า CRUD Operations
หรือก็คือ Create, Read, Update, Delete

CRUD Operations เป็นพื้นฐานของการพัฒนาแอปพลิเคชันที่ทำงานกับข้อมูล
ในเมื่อเรารู้แล้วว่าเราต้องการทำอะไรบ้าง เราก็จะไปออกแบบว่า Router ของเราควรจะมีอะไรบ้าง และ Controller ของเราควรจะทำอะไรบ้าง

การ Create Project
ในการสร้างโปรเจคใหม่ เราจะใช้ HTTP Method POST (ตามค่านิยมที่ Method POST นั้นสื่อถึงการสร้างข้อมูลใหม่)
แล้วเส้นทางล่ะ?
จากบ้านหลักของเราอยู่ที่ http://localhost:3000
เราจะสร้างโถงทางเดินใหม่ที่ชื่อว่า /api/v1/projects

ดังนั้นมาดูกันว่าต้องทำอะไรบ้าง
#### **7.3.1 สร้างไฟล์ projectRouter.js ใน Folder routes**
![[Pasted image 20250401120514.png]]
```javascript
// projectRouter.js
import express from "express";
import { createProject, getAllProjects, getProjectById, updateProject, deleteProject } from "../controllers/projectController.js";
const projectRouter = express.Router();
projectRouter.post("/", createProject);
projectRouter.get("/", getAllProjects);
projectRouter.get("/:id", getProjectById);
projectRouter.put("/:id", updateProject);
projectRouter.delete("/:id", deleteProject);

export default projectRouter;
```
#### **7.3.2 สร้างไฟล์ projectController.js ใน Folder controllers**
![[Pasted image 20250401120546.png]]
```javascript
// projectController.js
import { query } from "../config/database.js";

const createProject = async (req, res) => {
}

const getAllProjects = async (req, res) => {
}

const getProjectById = async (req, res) => {
}

const updateProject = async (req, res) => {
}

const deleteProject = async (req, res) => {
}
export { createProject, getAllProjects, getProjectById, updateProject, deleteProject };
```
#### **7.3.3 แก้ไขไฟล์ index.js**
``` javascript
import express from "express";

import dotenv from "dotenv";

import { testConnection } from "./test.js";

import projectRouter from "./routes/projectRouter.js";



dotenv.config();

const app = express();

const PORT = process.env.PORT || 3000;



app.use("/api/v1/projects", projectRouter);



app.listen(PORT, () => {

  console.log(`Server is running on http://localhost:${PORT}`);

  testConnection();

});
```

### 7.3.4 เขียน Logic ใน Controller
ขั้นตอนนี้เราจะเขียน Logic ใน Controller กันซึ่งจะใช้ ทั้ง javascript และ SQL (DML) ในการเข้าไปจัดการกับ Database

เดี๋ยวเราจะทำ Create Project กันก่อน
```javascript
// projectController.js
// query คือฟังก์ชันที่เรา import มาจาก database.js สิ่งที่มันทำคือมันจะรับ SQL Query และส่งไปยัง Database ของเรา และตอบกลับมาเป็นผลลัพธ์
import { query } from "../config/database.js";

// createProject คือฟังก์ชันที่เราจะใช้ในการสร้างโปรเจคใหม่
// req คือ Request Object ที่เก็บข้อมูลที่ส่งมาจาก Client(Frontend)
// ซึ่งก็ใน Object ของ Request ก็ Attribute ต่างๆให้เราใช้แต่ที่เราใช้กันหลักๆ ก็จะมี
// req.body คือข้อมูลที่ส่งมาจาก Client(Frontend) เช่น ชื่อโปรเจค, รายละเอียดโปรเจค
// req.params คือข้อมูลที่ส่งมาจาก URL เช่น id ของโปรเจคที่เราต้องการจะอัพเดท
// req.query คือข้อมูลที่ส่งมาจาก URL เช่น ?id=1&name=project1
// res คือ Response Object ที่เราจะใช้ในการส่งข้อมูลกลับไปยัง Client(Frontend)
// ซึ่งก็ใน Object ของ Response ก็ Attribute ต่างๆให้เราใช้แต่ที่เราใช้กันหลักๆ ก็จะมี
// res.send คือการส่งข้อมูลกลับไปยัง Client(Frontend)
// res.status คือการตั้งค่า Status Code ของ Response เช่น 200, 201, 400, 404, 500
// res.json คือการส่งข้อมูลกลับไปยัง Client(Frontend) ในรูปแบบ JSON

// ซึ่งการสร้างโปรเจคใหม่เราจะใช้ นั้นเราจะต้องใช้ข้อมูลของโปรเจคใหม่ที่เราต้องการจะสร้าง
// ดังนั้นเราจะต้องดึงข้อมูลจาก req.body เพื่อใช้ในการสร้างโปรเจคใหม่
// เราจะออกแบบให้ Backend ของเรารับข้อมูลในรูปแบบ JSON
// และซิ่งที่ส่งมาต้องตรงกับตารางที่ออกแบบไว้ใน Database
const createProject = async (req, res) => {
  try {
    const { projectName, projectDescription, category ,ownerId } = req.body; // ดึงข้อมูลจาก req.body

    // และในกรณีที่นี้เราต้อง generate projectId ขึ้นมาใหม่จาก ฟังก์ชันที่เขียนไว้ใน database.js
    const idRes = await query("SELECT generate_project_id() as id");
    const projectId = idRes[0].id; // ดึง projectId ที่ generate ขึ้นมาใหม่

    const result = await query(
      `INSERT INTO project (project_id, project_name, project_description, owner_id, category)
       VALUES ($1, $2, $3, $4, $5)`,
      [projectId, projectName, projectDescription, ownerId, category]
    );
    res.status(201).json({
      message: "Project created successfully",
      projectId: projectId,
    });
  } catch (error) {
    // ถ้ามีข้อผิดพลาดเกิดขึ้น
    console.error(error); // แสดงข้อผิดพลาดใน Console
    res.status(500).json({ message: "Internal server error" });
    // ส่งข้อความกลับไปยัง Client(Frontend) ว่ามีข้อผิดพลาดเกิดขึ้น
  }
};
```

โอเค! ตอนนี้เราก็สามารถสร้างโปรเจคใหม่ได้แล้ว ต่อไปคือการขอข้อมูลโปรเจคทั้งหมด
```javascript
// projectController.js
const getAllProjects = async (req, res) => {
  try {
    const { userId } = req.query; // ดึง userId จาก req.query
    // ตัวอย่าง URL ที่มี req.query http://localhost:3000/projects?userId=1

    const result = await query(
      `SELECT p.* FROM project p
       LEFT JOIN project_member pm ON p.project_id = pm.project_id
       WHERE p.owner_id = $1 OR pm.user_id = $1`,
      [userId]
    );
    res.status(200).json(result.rows); // ส่งข้อมูลกลับไปยัง Client(Frontend) ในรูปแบบ JSON
  } catch (error) {
    console.error(error); // แสดงข้อผิดพลาดใน Console
    res.status(500).json({ message: "Internal server error" });
    // ส่งข้อความกลับไปยัง Client(Frontend) ว่ามีข้อผิดพลาดเกิดขึ้น
  }
};
```



โอเค! ตอนนี้เราสร้างได้ ดูได้ ดังนั้นเราจะลองทดสอบดู ด้วยการลองใช้  Backend ของเรากันน





