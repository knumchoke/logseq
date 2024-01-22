- DB meaning
	- กลุ่มของข้อมูลมี่รวบรวมไว้โดยมีความสัมพัทธ์กัน
	- อาจจะเก็บรวมใน File เดียวกัน หรือแยกก็ได้
	- DB จะประกอบด้วย 3 ส่วน
		- File
		- Record
		- Field
- DB Model ใช้อธิบาย concept ที่เป็นตัวแทนของ Data Structure และ Relation แบ่งตามลักษระการใช้งานได้ดังนี้
	- Hierarchical Database Model มีโครงสร้างและความสัมพัทธ์แบบต้นไม้ 1 parent record มีได้หลาย child record แต่ chile record มีได้ 1 parent record
	- Network Database Model สามารถกำหนกความสัมพันธ์ได้หลายแบบ เช่น `1:1` `1:N` `N:1` `N:N`
	- Object-oriented Database Model เป็นการมองข้อมูลแบบเดียวกับการเขียนโปรแกรม OOP
	- Relational Database Model (RDB Model) เป็นที่นิยมในปัจจุบัน
- RDB Model
	- Data Structure เป็น Relational โดยใช้ Table มาแสดงให้เห็นเป็นรูปธรรม
	- RDB เป็น set ของ relation table โดยแต่ละ table ประกอบด้วย
		- Schema โดรงสร้างของ Table ที่ระบุ Relation
		- Instance คือข้อมูลที่ถูกบันทึกใน DB ในการสร้าง schema ตอนแรกที่ไม่มีข้อมูลอยู่ จะเรียกว่า Empty Instance
	- คำศัพท์ที่ควรจำ
		- relation หรือ table เป็นโครงสร้าง 2 มิติประกอบด้วย row column
		- tuples คือ rows
		- attribute คือ field หรือ column
		- degree คือจำนวน attribute
		- cardinality คือจำนวน row
- RDB Model attributes
	- SuperKey คือ set ของ attribute ที่สามารถใช้ระบุความ uniq ของ row ได้
	- CandidateKey คือ SuperKey ที่มี Attribute น้อยที่สุดที่สามารถใช้ระบุความ uniq ของ row ได้
	- PrimaryKey คือ CandidateKey เพียง 1 เดียวที่ใช้ระบุความ uniq ของ row ได้มีกฏคือ
		- ห้ามซ้ำกัน
		- อาจจะมีแค่ 1 attribute หรือมากกว่าก็ได้
		- ห้าม null
	- SecondaryKey คือ CandidateKey ที่ไม่ถูกเลือกเป็น PrimaryKey แต่นำมาใช้ปนะโยชนในการช่วยค้นหาข้อมูลได้
- Codd rules for RDB
	- กฎ Codd 12 ข้อ (Codd's 12 Rules) คือเกณฑ์แนวทางสำหรับระบบจัดการฐานข้อมูลแบบสัมพันธ์ (Relational Database Management Systems หรือ RDBMS) ซึ่งถูกนำเสนอโดยดร. เอ็ดการ์ แอฟ. ค็อด (Dr. Edgar F. Codd) นักวิทยาการคอมพิวเตอร์และนักคณิตศาสตร์ในปี ค.ศ. 1970s กฎเหล่านี้กำหนดหลักการพื้นฐานที่ระบบจัดการฐานข้อมูลต้องปฏิบัติตามเพื่อให้ถือว่าเป็นระบบฐานข้อมูลแบบสัมพันธ์แท้จริง และเป็นเกณฑ์ในการประเมินความเหมาะสมของระบบฐานข้อมูลในแง่ของความสัมพันธ์
	- นี่คือการอธิบายกฎ Codd 12 ข้อสำหรับระบบจัดการฐานข้อมูลแบบสัมพันธ์ (RDBMS):
		- 1. กฎข้อมูล (Information Rule):
			- ข้อมูลทั้งหมดในฐานข้อมูลควรถูกเก็บไว้ในตาราง (relation) ที่ประกอบด้วยแถวและคอลัมน์ แต่ละองค์ประกอบในตารางจะต้องสามารถระบุได้โดยไม่ซ้ำซ้อน โดยใช้ชื่อตาราง คีย์หลัก (primary key) และชื่อคอลัมน์
		- 2. กฎการเข้าถึงที่รับประกัน (Guaranteed Access Rule):
			- ข้อมูลใดๆในฐานข้อมูลควรเปิดเข้าถึงได้โดยการระบุชื่อตาราง ค่าคีย์หลัก และชื่อคอลัมน์ โดยไม่มีความกำหนดใดๆที่จะทำให้เกิดความสับสนหรือความสับสน
		- 3. กฎการจัดการค่า Null (Systematic Treatment of Null Values):
			- ระบบจัดการฐานข้อมูล (DBMS) ต้องรองรับการแสดงผลข้อมูลที่ขาดหายหรือไม่ทราบได้โดยใช้ค่า NULL โดยค่า NULL นี้จะต้องถูกจัดการในการดำเนินการและคำสั่งสอบถามอย่างสอดคล้อง
		- 4. กฎแคตตาล็อกออนไลน์แบบเชิงระบบฐานข้อมูล (Dynamic Online Catalog Based on The Relational Model):
			- โครงสร้างและข้อมูลเมตาดาต้าของฐานข้อมูล เช่น ตาราง คอลัมน์ ดัชนี และข้อกำหนดความสอดคล้อง ควรถูกเก็บไว้ในแคตตาล็อกที่สามารถเข้าถึงผ่านคำสั่ง SQL และสามารถสืบค้นเหมือนกับเป็นตาราง
		- 5. กฎภาษาย่อยข้อมูลระดับสูง (Comprehensive Data Sub-Language Rule):
			- ระบบจัดการฐานข้อมูล (DBMS) ต้องรองรับภาษาย่อยข้อมูลระดับสูงที่ให้ผู้ใช้กำหนด จัดการ สอบถาม และควบคุมข้อมูลทั้งหมดในฐานข้อมูลได้อย่างครบถ้วน
		- 6. กฎการอัปเดตมุมมอง (View Updating Rule):
			- มุมมองใดที่สามารถอัปเดตได้ตามทฤษฎี ต้องสามารถถูกอัปเดตโดยระบบจัดการฐานข้อมูล (DBMS) ด้วย หมายความว่าผู้ใช้สามารถดำเนินการอัปเดตผ่านมุมมองเหมือนกับตารางหลัก
		- 7. กฎการอัปเดตระดับสูง (High-Level Insert, Update, and Delete Rule):
			- ระบบจัดการฐานข้อมูล (DBMS) ต้องรองรับการดำเนินการในระดับสูงสำหรับการเพิ่มข้อมูล อัปเดต และลบข้อมูล อนุญาตให้ผู้ใช้ทำงานกับเซ็ตข้อมูลโดยไม่ต้องระบุขั้นตอนการจัดการข้อมูลระดับต่ำ
		- 8. กฎความอิสระทางกายภาพ (Physical Data Independence):
			- การเปลี่ยนแปลงโครงสร้างการจัดเก็บทางกายภาพของฐานข้อมูล (เช่น การจัดระเบียบแฟ้ม การสร้างดัชนี) ไม่ควรมีผลต่อข้อมูลแบบความสัมพันธ์ โครงสร้างควรรักษาความเหมือนกันในการทำงานกับข้อมูล
		- 9. กฎความอิสระทางตรรกศาสตร์ (Logical Data Independence):
			- การเปลี่ยนแปลงโครงสร้างตรรกศาสตร์ (schema) ของฐานข้อมูลไม่ควรต้องการการเปลี่ยนแปลงในโปรแกรมแอปพลิเคชันที่มีอยู่ โปรแกรมแอปพลิเคชันควรยังคงไม่มีผลจากการเปลี่ยนแปลงในโครงสร้างของฐานข้อมูล
		- 10. กฎความอิสระทางความสมบูรณ์ (Integrity Independence):
			- ระบบจัดการฐานข้อมูล (DBMS) ต้องสามารถบังคับความสมบูรณ์ของข้อมูล รวมถึงความสมบูรณ์ขององค์ประกอบข้อมูล เช่น ความสมบูรณ์ของตัวบ่งชี้ และความสมบูรณ์ของข้อมูลในโดเมน โดยเงื่อนไขเหล่านี้ควรเป็นเรื่องแยกต่างหากจากโปรแกรมแอปพลิเคชัน
		- 11. กฎความอิสระทางการกระจาย (Distribution Independence):
			- ระบบจัดการฐานข้อมูล (DBMS) ควรสามารถกระจายข้อมูลไปยังสถานที่ทางกายภาพหลายแห่ง (เช่น บนเซิร์ฟเวอร์หลายตัว) โดยไม่มีผลต่อมุมมองตรรกศาสตร์ของข้อมูล
		- 12. กฎการป้องกันการละเมิด (The Nonsubversion Rule):
			- ระบบจัดการฐานข้อมูล (DBMS) ต้องไม่อนุญาตให้ผู้ใช้หวงห้ามความปลอดภัยและการตรวจสอบความสมบูรณ์ผ่านการดำเนินการระดับต่ำ ระบบจัดการฐานข้อมูลควรให้ความมั่นใจว่าผู้ใช้ที่ได้รับอนุญาตสามารถเข้าถึงและจัดการข้อมูลผ่านกลไกการความปลอดภัยและความสมบูรณ์ที่ถูกกำหนดไว้
	- การปฏิบัติตามกฎ Codd 12 ข้อนี้ช่วยให้ระบบจัดการฐานข้อมูลรักษาความเป็นระบบสัมพันธ์ของโมเดลข้อมูล ส่งผลให้มีความสอดคล้อง ความสมบูรณ์ และความยืดหยุ่นในการจัดการกับความต้องการข้อมูลที่ซับซ้อนได้