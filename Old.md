
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

การที่ [[Client]] ส่งคำร้องไปหา Server นั้นจะมีรูปแบบของการส่ง เรียกว่า [[Old#^2d82a9|_HTTP Request Message_]] คือส่วนที่บอกข้อมูลรายละเอียดให้กับอีกฝั่งทราบ (ในที่นี้คือ [[Server]]) ซึ่ง [[Old#^7b3493|HTTP Response]] ก็มีลักษณะเช่นเดียวกัน

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

เมื่อ _[[Server]]_ ได้รับ _[[Old#^2d82a9|HTTP Request]]_ แล้ว จะทำการประมวลผลคำร้องขอ และส่งกลับไปยัง _[[Client]]_ โดยจะมีการส่ง _[[Old#^7b3493|HTTP Response]]_ กลับไปด้วย ซึ่งใน _[[Old#^7b3493|HTTP Response]]_ จะมีส่วนที่เรียกว่า _[[Old#^16cb86|Status Code]]_ เพื่อบอกสถานะของคำร้องขอที่ส่งไปว่าเป็นอย่างไร เช่น
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
ถ้าขึ้นว่า Error ให้ตรวจสอบว่า Docker รันอยู่หรือเปล่า ถ้าไม่ได้ให้รันให้ไปทำ [[Old#^4e71ae| เปิด Docker]]

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

### **7.2 เดี๋ยวพาทำเกี่ยวกับ User และ Authentication ก่อน**
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

##### 🔐 แล้วเราจะสร้าง Token อย่างไร?

💡 คำตอบคือ เราจะใช้ **JWT (JSON Web Token)**

---

##### JWT คืออะไร?

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

ใน Token ที่เราสร้างขึ้นมานั้นจะมีข้อมูลที่ Backend ตอบกลับไปให้ Frontend ฝั่งเก็บไว้ สิ่งที่ฝังไว้จะเป็นตาม Function [[Old#^84a15c| generateToken ของเรา]]
ซึ่งเราสามารถลองนำ Token มาถอดรหัสได้ที่ https://jwt.is/

![[20250403-0534-27.1798150.mp4]]

![[Pasted image 20250403123553.png]]

จากในรูปจะเห็นว่า Token ที่เราสร้างขึ้นมา เมื่อถอดรหัสนั้นจะมีข้อมูลที่เราฝังไว้
และ Token นี้ Frontend จะต้องแนบไปกับทุก Request ที่ต้องการยืนยันตัวตน
แล้ว Backend จะทอดออกมาดูว่า Token นี้เป็นของใครเพื่อที่จะใช้ใน Operation ที่ต้องการการยืนยันตัวตน

โอเค! ตอนนี้เราทำการยืนยันตัวตนของ User ได้แล้ว
ต่อไปเราจะทำให้ Backend ดึงข้อมูล User ที่ Login เข้ามาในระบบจาก Token ที่ส่งมาผ่าน Middleware กัน!

### 7.3 สร้าง Middleware
Middleware คือ ฟังก์ชันที่ทำงานระหว่าง Request และ Response
Middleware จะทำงานก่อนที่ Request จะถูกส่งไปยัง Route Handler
Middleware สามารถใช้ในการตรวจสอบ Token ที่ส่งมาจาก Client (Frontend) ว่าถูกต้องหรือไม่
และสามารถใช้ในการดึงข้อมูล User จาก Token ที่ส่งมาด้วย

เราจะมาลองดูภาพรวมกันว่าเป็นยังไง

![[Pasted image 20250403141514.png]]
เริ่มจากมี HTTP reqeust เข้ามาที่ Backend ของเราโดยต้องการไปยัง API ที่ตัว Router ก็จะมองดูว่า เส้นทางที่ต้องการไปนั้นได้มีการกำหนด Middleware ไว้หรือไม่
ถ้ามีก็จะส่งต่อไปให้ Middleware ทำงานก่อน

![[Pasted image 20250403142108.png]]
เมื่อไปถึง Middleware, Middleware จะทำการตรวจสอบ Token ที่แนบมากับ Request ว่าถูกต้องหรือไม่พร้อมกับถอดรหัสดึงข้อมูล User ออกมาแล้วแนบข้อมูล User กลับเข้าไปใน Request

![[Pasted image 20250403142504.png]]
แล้ว Middleware จะส่งต่อ Request ที่มีข้อมูล User ไปยัง Route Handler


![[Pasted image 20250403142926.png]]
แล้วที่ route handler ก็จะมองหาข้อมูลที่แนบมาด้วยใน Request Header ที่ผ่านจาก Middleware มาแล้ว

เท่านี้เราก็จะสามารถรู้ได้แล้วว่า User ที่ Login เข้ามานั้นคือใคร


#### 7.3.1 สร้างไฟล์ Middleware
ดังนั้นเริ่มเลยโดยเราจะสร้าง Folder ใหม่ชื่อว่า middleware และสร้างไฟล์ authMiddleware.js ขึ้นมา

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

#### 7.3.2 ลองสร้าง Endpoint ใหม่เพื่อลองดึงข้อมูล User ดู
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

เท่านี้เราก็สำเร็จในการสร้างระบบ Authentication พร้อม Middleware เรียบร้อยแล้วพร้อมที่จะไปทำในส่วนที่เหลือของโปรเจคกันต่อ

### **7.4 Implement CRUD operations สำหรับตารางอื่นๆ**
หลังจาก Backend ของเราสามารถยืนยันตัวตนของ User ได้แล้ว
ที่เหลือก็แค่ระบบอื่นๆ เช่น การจัดการ Project, Task, Assignment, Attachment และอื่นๆ

โดยที่ข้อมูลเหล่านี้จะมี Opearation หลักๆคือ
- การสร้าง (Create)
- การอ่าน (Read)
- การแก้ไข (Update)
- การลบ (Delete)
เรียกรวมทั้งหมดนี้เรามักจะเรียกว่า CRUD Operation เหล่านี้เป็น Operation พื้นฐานที่ทุกตารางควรจะมี เว้นแต่มีบางตารางที่ต้องมีการจัดการเป็นพิเศษก็อาจจะไม่มีก็ได้

แต่สำหรับเรา แต่ละตารางจะมี CRUD Operation ดังนั้นเราจะมาทำ CRUD Operation สำหรับตาราง Project เป็นตัวอย่างกัน

#### 7.4.1 สร้างไฟล์ projectRouter.js และ projectController.js

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

##### 7.4.4 Get Project From ID
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





