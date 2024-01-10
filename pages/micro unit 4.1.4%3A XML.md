- XML language concepts
	- ภาษา XML (Extensible Markup Language) เป็นภาษาที่ใช้ในการเขียนและจัดการข้อมูลแบบลําดับและมีโครงสร้างที่ชัดเจน เนื่องจาก XML เป็นภาษาเพื่อการแลกเปลี่ยนข้อมูล และมีลักษณะที่ยืดหยุ่นและกว้างขวาง
	- มีความเข้มงวดในการใช้งาน `tag` ต่างๆ เช่น `<name>` จะเป็นคนละ `tag` กับ `<NAME>`
- Important characteristics of XML
	- XML (Extensible Markup Language) มีลักษณะสำคัญที่ทำให้มันเป็นภาษาที่มีความหลากหลายและมีความสามารถในการแลกเปลี่ยนข้อมูลอย่างมีประสิทธิภาพ นี่คือลักษณะสำคัญของ XML:
		- **การสนับสนุนการค้นหา (Searchability)**: XML มีโครงสร้างที่ชัดเจนที่ช่วยในการค้นหาข้อมูลได้อย่างง่าย ซึ่งมีประโยชน์ในการสร้างเครื่องมือค้นหาข้อมูล
		- **การสนับสนุนการตรวจสอบความถูกต้อง (Validation)**: XML รองรับการใช้กฎและกฎหมายในการระบุโครงสร้างข้อมูล ซึ่งช่วยในการตรวจสอบความถูกต้องและความสอดคล้องกับมาตรฐานของข้อมูล
		- **ความสามารถในการแลกเปลี่ยนข้อมูล (Data Exchange)**: XML ถูกออกแบบมาเพื่อการแลกเปลี่ยนข้อมูลระหว่างระบบที่แตกต่างกัน ทำให้มันเป็นมาตรฐานสำหรับการสื่อสารและการแลกเปลี่ยนข้อมูลในหลายอุตสาหกรรม
		- **ยืดหยุ่น (Extensible)**: XML อนุญาตให้ผู้ใช้สร้างโครงสร้างข้อมูลที่เฉพาะเจาะจงสำหรับความต้องการของพวกเขา ไม่จำเป็นต้องใช้โครงสร้างที่มีอยู่แล้ว นี่ทำให้ XML เป็นภาษาที่ยืดหยุ่นและสามารถใช้กับหลายแบบหรือวัตถุประสงค์
		- **การระบุโครงสร้างข้อมูล (Data Structure)**: XML ให้ความสามารถในการระบุโครงสร้างข้อมูลของเอกสาร และความสัมพันธ์ระหว่างองค์ประกอบ ทำให้เป็นเครื่องมือที่เหมาะสมในการจัดการข้อมูลที่มีความซับซ้อน โดยมีข้อมูลที่ใช้อธิบายรายละเอียดของข้อมูลนั้นประกอบอยู่ด้วย ซึ่งถือว่าเป็นข้อมูลของข้อมูลได้เช่นกัน
		- **การสนับสนุนการถ่ายโอนข้อมูล (Data Transfer)**: XML มีความสามารถในการถ่ายโอนข้อมูลระหว่างเว็บแอปพลิเคชันและฐานข้อมูล หรือระบบอื่น ๆ โดยใช้ภาษา SOAP (Simple Object Access Protocol) หรือ REST (Representational State Transfer).
	- รูปแบบเอกสารที่ดีของ XML มีลักษณะสำคัญ 2 อย่าง
		- **Well-formed XML Document** (เอกสาร XML ที่ถูกต้องตามข้อกำหนด) คือเอกสาร XML ที่มีโครงสร้างและรูปแบบที่ถูกต้องตามกฎหลักของภาษา XML โดยไม่มีข้อผิดพลาดเบื้องต้น และสามารถถูกประมวลผลและอ่านได้โดยไม่มีปัญหาใด ๆ ต่อตัวประมวลผล XML (XML processor) หรือแอปพลิเคชันที่จะใช้งานเอกสาร XML นั้น ๆ
		- **Valid XML Document** (เอกสาร XML ที่ถูกต้องตามมาตรฐาน) คือเอกสาร XML ที่ไม่เพียงแต่เป็น Well-formed XML Document (เอกสาร XML ที่ถูกต้องตามกฎของ XML) แต่ยังตรงตามข้อกำหนดและโครงสร้างข้อมูลที่ถูกต้องตามมาตรฐานหรือ DTD (Document Type Definition) หรือ Schema ที่ได้รับการระบุไว้. การตรวจสอบความถูกต้องและความสอดคล้องกับมาตรฐานนี้เรียกว่าการตรวจสอบความถูกต้อง (Validation) ของเอกสาร XML.
- Creating an XML file
	- การสร้างไฟล์ XML เป็นกระบวนการที่คุณสามารถทำได้ด้วยการใช้แผนกษาจัดการข้อมูล (XML editor) หรือแม้แต่ใช้เครื่องมือสร้างข้อความปกติ (plain text editor) เช่น Notepad หรือ Visual Studio Code ในกรณีที่คุณต้องการสร้างไฟล์ XML ด้วยตนเอง นี่คือขั้นตอนพื้นฐานในการสร้างไฟล์ XML:
		- 1. **เปิดโปรแกรมหรือเครื่องมือ**: เริ่มต้นโปรแกรมหรือเครื่องมือที่คุณต้องการใช้ในการสร้างไฟล์ XML เช่น Notepad, Visual Studio Code, XML editor หรืออื่น ๆ.
		- 2. **สร้างเอกสาร XML**: ในโปรแกรมหรือเครื่องมือของคุณ สร้างไฟล์ใหม่และเริ่มสร้างเอกสาร XML โดยเริ่มต้นด้วยการประกาศเอกสาร (Document Declaration) ซึ่งระบุเวอร์ชันของ XML และการใช้รหัสความเร็วของอักขระ (character encoding). ตัวอย่าง:
		  ```xml
		  <?xml version="1.0" encoding="UTF-8"?>
		  ```
		- 3. **สร้างโครงสร้างข้อมูล**: ต่อมาคุณสามารถสร้างโครงสร้างข้อมูลของเอกสาร XML โดยใช้แท็ก (tags) และแอตทริบิวต์ (attributes) ตามโครงสร้างที่คุณต้องการ ตัวอย่าง:
		  ```xml
		  <bookstore>
		    <book>
		        <title>สมเด็จพระเจ้าเจ้าฟ้ามหาวชิราลงกรณ ณ วังบางปะอิน</title>
		        <author>พระมหาวชิราลงกรณ ณ วังบางปะอิน</author>
		        <price>200</price>
		    </book>
		  </bookstore>
		  ```
		- 4. **บันทึกไฟล์**: หลังจากสร้างเอกสาร XML เสร็จเรียบร้อยแล้ว คุณควรบันทึกไฟล์โดยใช้นามสกุล `.xml` เพื่อให้โปรแกรมหรือแอปพลิเคชันที่ใช้งานสามารถรู้ว่าเป็นไฟล์ XML ได้ ตัวอย่าง: `mydocument.xml`
		- 5. **ตรวจสอบความถูกต้อง (ตัวเลือก)**: หากคุณกำหนด DTD หรือ Schema สำหรับเอกสาร XML ของคุณ ควรใช้เครื่องมือ Validation หรืออีกครั้งใน XML editor เพื่อตรวจสอบความถูกต้องของเอกสารตามโครงสร้างที่ระบุ.
- XML language structure
	- โครงสร้างภาษา XML ประกอบด้วยส่วนหลักที่สามส่วนคือ Prolog Element, Document Element, และ DTD (Document Type Definition) (หากมี) โดยส่วนทั้งสามส่วนนี้ร่วมกันในการกำหนดโครงสร้างและคุณสมบัติของเอกสาร XML:
		- 1. **Prolog Element (ประกาศเอกสาร)**: Prolog Element เป็นส่วนแรกของเอกสาร XML และใช้ในการประกาศข้อมูลสำหรับเอกสาร เปรียบเสมือนหัวเอกสาร ส่วน Prolog Element ประกาศดังนี้:
		     ```xml
		     <?xml version="1.0" encoding="UTF-8"?>
		     ```
			- `<?xml version="1.0" encoding="UTF-8"?>`: ประกาศเอกสาร XML โดยระบุรุ่นของ XML (version) และการใช้รหัสความเร็วของอักขระ (character encoding) เช่น UTF-8.
		- 2. **Document Element (องค์ประกอบหลัก)**: Document Element เป็นส่วนที่เป็นหัวใจของเอกสาร XML และเป็นส่วนที่บอกว่าเอกสารนี้เกี่ยวกับอะไร ส่วนนี้อยู่ระหว่างแท็กเปิดและปิด ตัวอย่าง:
		  ```xml
		  <bookstore>
		    <!-- เนื้อหาของเอกสารอยู่ในนี้ -->
		  </bookstore>
		  ```
			- `<bookstore>`: Document Element ในตัวอย่างนี้เป็น `<bookstore>` ซึ่งเป็นค่าเริ่มต้นของเอกสาร XML และส่วนนี้คุมโครงสร้างข้อมูลทั้งหมดของเอกสาร.
		- 3. **DTD (Document Type Definition) (ตามความจำเป็น)**: DTD เป็นส่วนที่ไม่บังคับในเอกสาร XML แต่ถ้ามีการใช้ DTD จะช่วยกำหนดโครงสร้างข้อมูลและความสัมพันธ์ระหว่างองค์ประกอบในเอกสาร XML ให้ถูกต้องและมีความสมบูรณ์ ตัวอย่างการใช้ DTD:
		  ```xml
		  <!DOCTYPE bookstore [
		    <!ELEMENT bookstore (book+)>
		    <!ELEMENT book (title, author, price)>
		    <!ELEMENT title (#PCDATA)>
		    <!ELEMENT author (#PCDATA)>
		    <!ELEMENT price (#PCDATA)>
		  ]>
		  ```
			- `<!DOCTYPE bookstore>`: ประกาศ DTD ของเอกสาร XML โดยระบุชื่อ Document Type คือ "bookstore" และกำหนดความสัมพันธ์ขององค์ประกอบในเอกสาร.
			- ตามตัวอย่างนี้ DTD กำหนดว่า Document Element `<bookstore>` จะประกอบด้วยองค์ประกอบ `<book>` ซึ่งมีองค์ประกอบ `<title>`, `<author>`, และ `<price>`.
	- โครงสร้าง XML ประกอบด้วยส่วนหลักที่สามส่วนนี้ทำให้เอกสาร XML มีโครงสร้างที่ถูกต้องและสามารถตรวจสอบความถูกต้องได้ตามมาตรฐานหรือ DTD ที่กำหนดไว้ (ถ้ามี) เพื่อให้เอกสารมีความสมบูรณ์และสามารถใช้งานได้อย่างถูกต้องในแต่ละแอปพลิเคชันหรือระบบที่ใช้งานข้อมูล XML นี้.