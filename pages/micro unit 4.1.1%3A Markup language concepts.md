- แนวคิด
	- Web Site แบ่งเป็น 2 ประเภท
		- Static Web Page
			- นำเสนอเนื้อหาที่ไม่ต้องมีการเปลี่ยนแปลงบ่อย
			- สร้างได้โดยใช้ HTML พื้นฐาน หรือ Application
			- ไม่ต้องใช้ความชำนาญในการดูแล
		- Dynamic Web Page
			- สามารถนำเสนอที่มีการเปลี่ยนแปล และตอบสนองการใช้งานได้ดีกว่า Static
			- สร้างโดยใช้ Markup Language + Script Language
			- ผู้ดูแลต้องมีความรู้ในการเขียน Script Language
- เครื่องมือที่ใช้พัฒนาแบ่งเป็น 2 กลุ่มหลักๆ
	- เครื่องมือที่นักพัฒนาเว็บไม่จําเป็นต้องมีความรู้ในการเขียนโปรแกรมากนัก เช่น
		- CMS (Content Management System)
			- ระบบที่เขียนจาก Programing Language
			- เป็น Web Appplication
			- ในระบบจะมีเครื่องมือสร้าง Web Page ด้วย Script และ Database เพื่อจัดเก็บข้อมูล
		- Package Program for create websites
			- เป็นเครื่องมือ support การสร้าง/แก้ไข Web site โดยผู้ใช้ไม่จำเป็นต้องมีความรู้มาก
			- เป็น Application
			- ในหนังสือยกตัวอย่าง DreamWeaver และ WebMatrix แต่ปัจจุบันไม่มีใครใช้แล้ว
	- เครื่องมือที่นักพัฒนาเว็บจําเป็นต้องมีความรู้ในการเขียนโปรแกรม
		- Markup Language
			- เป็นพื้นฐานในการสร้าง Web เช่น HTML XHTML XML
		- Script Language
			- เป็นพื้นฐานในการส่งข้อมูลเพื่อติดต่อกับ Web Services
- **Meaning, importance**, **evolution** of markup language. Benefits and **steps for using markup language to create web pages** Principles and working structure of each type of markup language.
	- Meaning, importance of markup language
		- เป็นพื้นฐานในการสร้าง Web Page
		- มีโครงสร้างชัดเจน ใช้จัดรูปแบบเนื้อหา ข้อความ รูปภาพ เสียง วิดีโอ เป็นต้น
		- นำเสนอข้อมูลเป็น Web ด้วยข้อมูลที่เป็น Text file ทำให้ง่ายต่อการเรียนรู้
	- evolution of markup language
		- มีหลายภาษาดังนี้
		  | <div style="width:200px">Language </div>| <div style="width:120px"> ORG </div>| Detail |
		  | GML (Generalized Markup Language) | IBM | เป็นไฟล์เท็กซ์ที่ใช้ในการกําหนดรูปแบบของเอกสาร สามารถแลกเปลี่ยนข้อมูลได้ในหลากหลายระบปฏิบัติการ |
		  | SGML (Standard Generalized Markup Language) | IBM | พัฒนามาจาก GML แต่ไม่ได้รับความนิยมเพราะความซับซ้อน |
		  | HTML (Hyper Text Markup Language) | W3C | ได้รับความนิยม ในปัจจุบันเป็น Version 5 |
		  | XML (eXtensible Markup Language) | W3C | พัฒนาขึ้นให้เป็นมาตฐานในการส่งข้อมูลระหว่าง Platform รวมเอาข้อดีของ SGML มาใช้ แต่ทำให้ง่ายขึ้น ในปัจจุบันเป็น Version 1.1 2nd ed. |
		  | XHTML (eXtensible Hyper Text Markup Language) | WHATWG + W3C | รวมความสามารถและการใช้งานของทั้ง HTML และ XML เข้าด้วยกัน แม้ไม่ได้รับความนิยมในปัจจุบันเพราะการผลักดัน HTML5 แต่ก็ยังมีการใช้งานอยู่ เพราะมีประโยชน์ในเรื่องโครงสร้างที่ strict กว่า|
	- steps for using markup language to create web pages
		- create  `Markup Language` file
		- save file in `.html` `.xml` `.xhtml` extension
		- open file using web browser
	-