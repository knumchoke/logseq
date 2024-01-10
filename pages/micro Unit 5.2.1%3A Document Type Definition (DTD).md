- External DTD ตัวอย่าง
  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <!DOCTYPE library SYSTEM "dtdfile.dtd">
  <library>
    <book>
      <title>Introduction to XML</title>
      <author>John Doe</author>
      <genre>Programming</genre>
      <price>29.99</price>
    </book>
  </library>
  ```
	- ประกาศ Reference ได้ที่ใต้ Prolog ก่อนเริ่ม element ตามตัวอย่างบรรทัดที่ 2
	- ตามตัวอย่าง
		- `library` คือ root element ที่ต้องการ Declaration
		- `SYSTEM|PUBLIC` คือการบอกตำแหน่งของ identifier ว่า จะไปเอา DTD จากที่ไหน
			- `SYSTEM` เป็นการบอกว่า DTD ที่ใช้จะอยู่ในรูปของไฟล์
			- `PUBLIC` เป็นการบอกว่า DTD ที่ใช้จะ Resolve จาก Public Id Catalog ซึ่งต้องใช้ `EntityResolver` หรือ `XmlResolver` ในการเข้าถึง
				- เมื่อกำหนดเป็น `PUBLIC` จะสามารถใช้ URL หรือชื่อไฟล์เป็น Optional ได้
				- ตัวอย่าง Public DTD เช่น
					- `"-//Hibernate/Hibernate Configuration DTD 3.0//EN"`
					- `"-//W3C//DTD HTML 4.0 Transitional//EN"`
		- `"dtdfile.dtd"` คือไฟล์ที่เก็บข้อมูล DTD ไว้ อาจจะเป็น URL ที่ชี้ไปหา DTD บน Internet ก็ได้
- Internal DTD
	- สามารถประกาศไว้ก่อน root element ได้ ตามตัวอย่าง
	  ```xml
	  <?xml version="1.0" encoding="UTF-8"?>
	  <!DOCTYPE bookstore [
	    <!ELEMENT bookstore (book+)>
	    <!ELEMENT book (title, author, price)>
	    <!ELEMENT title (#PCDATA)>
	    <!ELEMENT author (#PCDATA)>
	    <!ELEMENT price (#PCDATA)>
	  ]>
	  <bookstore>
	    <book>
	      <title>Introduction to XML</title>
	      <author>John Doe</author>
	      <price>29.99</price>
	    </book>
	    <book>
	      <title>Data Structures and Algorithms</title>
	      <author>Jane Smith</author>
	      <price>39.95</price>
	    </book>
	  </bookstore>
	  ``` 
	  สามารถอธิบายได้ดังนี้
		- `<bookstore>` ต้องมีสิ่งถูกให้ค่าเป็นอิลิเมนต์ `<book>` อย่างน้อย 1 รายการ `(book+)`.
		- `<book>` ต้องมีอิลิเมนต์ `<title>`, `<author>`, และ `<price>` ที่มีค่าเป็นข้อมูลข้อความ (#PCDATA).
		- `<title>`, `<author>`, และ `<price>` ต้องมีค่าเป็นข้อมูลข้อความ (#PCDATA).
- DTD Validation
	- DTD (Document Type Definition) รองรับหลาย Data Type สำหรับกำหนดความละเอียดในอิลิเมนต์และคุณลักษณะ (attributes) ในเอกสาร XML ซึ่งสามารถนำมาใช้ในรายละเอียดของ DTD ได้ตามความเหมาะสมของแต่ละบริการ XML. นี่คือ Data Type ที่ DTD รองรับ:
		- 1. `CDATA` (Character Data): หรือ `PCDATA` ใช้สำหรับข้อมูลข้อความที่ไม่ได้มีโครงสร้างเฉพาะ และอนุญาตให้ใส่อักขระพิเศษโดยไม่ต้องใช้ character references.
		- 2. `ID` (Identifier): ใช้สำหรับระบุค่าที่เป็นไปตามข้อกำหนดตามชื่อที่ไม่ซ้ำกันภายในเอกสาร XML.
		- 3. `IDREF` (ID Reference): ใช้สำหรับระบุค่าที่เป็นอ้างอิงถึงค่า `ID` ในเอกสาร XML.
		- 4. `IDREFS` (ID References): ใช้สำหรับระบุค่าที่เป็นรายการของอ้างอิงไปยังค่า `ID` ในเอกสาร XML.
		- 5. `NMTOKEN` (Name Token): ใช้สำหรับระบุค่าที่เป็นชื่อที่ไม่มีช่องว่างหรืออักขระพิเศษ.
		- 6. `NMTOKENS` (Name Tokens): ใช้สำหรับระบุค่าที่เป็นรายการของชื่อที่ไม่มีช่องว่างหรืออักขระพิเศษ.
		- 7. `ENTITY` (Entity Name): ใช้สำหรับระบุค่าที่เป็นชื่อของ entity ภายใน DTD.
		- 8. `ENTITIES` (Entity Names): ใช้สำหรับระบุค่าที่เป็นรายการของชื่อ entity ภายใน DTD.
		- 9. `NOTATION` (Notation Name): ใช้สำหรับระบุค่าที่เป็นชื่อของ notation ภายใน DTD.
		- 10. `ENUMERATION` (Enumeration): ใช้สำหรับระบุค่าที่จะต้องอยู่ในรายการค่าที่ถูกกำหนดล่วงหน้า.
	- DTD ไม่อยู่ใน Syntax ของ XML ทำให้ XML Parser วิเคราะห์ได้