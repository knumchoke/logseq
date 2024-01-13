- Attribute of Entity
	- General and Parameter Entity เป็นสองประเภทของ entities ที่สามารถใช้เพื่อการใส่ข้อมูลและการจัดรูปแบบ DTD ได้:
		- General Entity
			- General Entity เป็น entities ที่ใช้ใน DTD และสามารถใช้ในเอกสาร XML เอง.
			- อ้างอิง General Entity ด้วย entity reference โดยใช้ `&` และ `;` (ตัวอย่าง: `&entityName;`).
			- สามารถใช้ General Entity เพื่อจัดการข้อมูลที่ใช้ซ้ำ หรือสร้าง entity references ที่ช่วยให้ DTD มีโครงสร้างที่ถูกต้องและง่ายต่อการดูแลรักษา.
			- ตัวอย่างการใช้ General Entity ใน DTD:
			  ```xml
			  <!ENTITY authorName "John Doe">
			  <!ENTITY companyName "Example Corp">
			  <!ELEMENT book (title, author)>
			  <!ATTLIST book
			    publisher CDATA #IMPLIED
			  >
			  ```
		- Parameter Entity
			- Parameter Entity เป็น entities ที่ใช้ใน DTD เพื่อจัดรูปแบบ DTD และช่วยให้ DTD มีโครงสร้างที่สะดวกต่อการบริหารจัดการ โดยมักถูกใช้ในการแยกส่วนของ DTD เพื่อเป็นความสะดวกในการอ่านและแก้ไข.
			- Parameter Entity ถูกอ้างอิงใน DTD โดยใช้ `%` และ `;` (ตัวอย่าง: `%entityName;`).
			- Parameter Entity มักใช้ในการกำหนดชุดของอิลิเมนต์, คุณลักษณะ (attributes), หรือ entities ใน DTD.
			- ตัวอย่างการใช้ Parameter Entity ใน DTD:
			  ```xml
			  <!ENTITY % content "(title, author, publicationYear)">
			  <!ELEMENT book %content;>
			  <!ATTLIST book
			    isbn CDATA #REQUIRED
			  >
			  ```
	- Internal and External Entity ntity สามารถถูกนิยามในรูปแบบ Internal Entity หรือ External Entity ตามความต้องการของเอกสาร XML และการอ้างอิง entity แตกต่างกันดังนี้:
		- Internal Entity
			- Internal Entity คือ entities ที่ถูกนิยามภายใน DTD หรือภายในเอกสาร XML โดยใช้ entity declaration.
			- การนิยาม Internal Entity จะถูกแทรกไว้ใน DTD หรือภายในเอกสาร XML โดยใช้ `<!ENTITY>` declaration.
			- Internal Entity สามารถใช้ภายในเอกสาร XML โดยการอ้างอิง entity ด้วย entity reference (`&` และ `;`).
			- ตัวอย่าง Internal Entity ใน DTD:
			  ```xml
			  <!ENTITY companyName "Example Corp">
			  <!ELEMENT book (title, author)>
			  <!ATTLIST book
			    publisher CDATA #IMPLIED
			  >
			  ```
		- External Entity
			- External Entity คือ entities ที่ถูกนิยามภายนอกเอกสาร XML และถูกอ้างอิงใน DTD หรือเอกสาร XML เพื่อนำเข้าข้อมูลจากเอกสารอื่น.
			- External Entity สามารถถูกนิยามในไฟล์ที่แยกออกไป (external entity declaration) และเอกสาร XML สามารถอ้างอิง External Entity และนำข้อมูลจากไฟล์ภายนอกมาใช้.
			- ตัวอย่าง External Entity ใน DTD:
			  ```xml
			  <!ENTITY % externalEntity SYSTEM "external.xml">
			  ```
	- Parsed and Unparsed Entity สามารถถูกนิยามในรูปแบบ Parsed Entity หรือ Unparsed Entity ตามลักษณะของข้อมูลของ entity และวิธีการประมวลผลข้อมูลดังนี้:
		- Parsed Entity
			- Parsed Entity คือ entities ที่มีข้อมูลที่สามารถถูกประมวลผลและตีความได้ใน DTD หรือเอกสาร XML.
			- ข้อมูลใน Parsed Entity มักเป็นข้อความ XML ที่ถูกตีความและจัดการโดย XML โปรแกรมตามกฎระเบียบ XML.
			- Parsed Entity สามารถใช้ในรูปแบบของ Internal Entity หรือ External Entity.
			- ตัวอย่าง Parsed Entity ใน DTD:
			  ```xml
			  <!ENTITY companyName "Example Corp">
			  <!ELEMENT book (title, author)>
			  <!ATTLIST book
			    publisher CDATA #IMPLIED
			  >
			  ```
		- Unparsed Entity
			- Unparsed Entity คือ entities ที่มีข้อมูลที่ไม่ได้ถูกตีความและจัดการโดย XML โปรแกรม แต่มีลักษณะข้อมูลที่ไม่สามารถตีความได้โดยตรง และส่วนใหญ่เป็นไฟล์ที่ไม่ใช่ข้อความ XML.
			- Unparsed Entity มักถูกใช้ในการอ้างอิงไฟล์ที่ไม่ใช่ XML ซึ่งอาจเป็นไฟล์เอกสารอื่น ๆ เช่น รูปภาพ, ไฟล์เสียง, ไฟล์วิดีโอ หรือไฟล์อื่น ๆ.
			- ใน DTD, Unparsed Entity จะถูกนิยามในรูปแบบของ External Entity โดยระบุความเกี่ยวข้องกับไฟล์ภายนอก (external file) และมักใช้สำหรับการนำเข้าไฟล์เหล่านี้ลงในเอกสาร XML.
			- ตัวอย่าง Unparsed Entity ใน DTD:
			  ```xml
			  <!ENTITY logo SYSTEM "logo.png" NDATA PNG>
			  ```
- General Entity Declaration
	- Parsed Internal General Entity Declaration ใน DTD (Document Type Definition) ของ XML มีลักษณะดังนี้:
		- การประกาศ:
			- Parsed Internal General Entity ประกาศภายใน DTD โดยใช้ของคำสั่ง `<!ENTITY>` ภายในส่วนของ DTD.
			- ประกาศของ Parsed Internal General Entity ประกอบด้วยชื่อของ Entity, ค่าของ Entity ที่ตีความและใช้ในเอกสาร XML, และรายละเอียดอื่น ๆ เกี่ยวกับ Entity (หากมี).
			- ตัวอย่างการประกาศ Parsed Internal General Entity ใน DTD:
			  ```xml
			  <!ENTITY companyName "Example Corp">
			  ```
		- การอ้างอิง Entity:
			- Parsed Internal General Entity สามารถอ้างอิงในเอกสาร XML โดยใช้ entity reference ที่เป็นชื่อของ Entity ระบุระหว่าง `&` และ `;` เช่น `&companyName;`.
			- เมื่อเอกสาร XML ถูกประมวลผล  Entity reference จะถูกแทนที่ด้วยค่าของ Entity ที่ถูกประกาศ.
			- ตัวอย่างการอ้างอิง Parsed Internal General Entity ในเอกสาร XML:
			  ```xml
			  <company>
			   <name>&companyName;</name>
			  </company>
			  ```
	- Parsed external General Entity Declaration ใน DTD (Document Type Definition) ของ XML มีลักษณะดังนี้:
		- การประกาศ:
			- Parsed External General Entity ประกาศภายใน DTD โดยใช้ของคำสั่ง `<!ENTITY>` แต่ระบุ URL หรือ URI ของไฟล์ภายนอกที่มีข้อมูลของ Entity ภายใน.
			- ตัวอย่างการประกาศ Parsed External General Entity ใน DTD:
			  ```xml
			  <!ENTITY companyName SYSTEM "companyName.txt">
			  ```
		- การอ้างอิง Entity:
			- Parsed External General Entity สามารถอ้างอิงในเอกสาร XML โดยใช้ entity reference ที่เป็นชื่อของ Entity ระบุระหว่าง `&` และ `;` เช่น `&companyName;`.
			- เมื่อเอกสาร XML ถูกประมวลผล  Entity reference จะถูกแทนที่ด้วยข้อมูลที่อ่านจากไฟล์ภายนอกที่ระบุใน Parsed External General Entity.
			- ตัวอย่างการอ้างอิง Parsed External General Entity ในเอกสาร XML:
			  ```xml
			  <company>
			  <name>&companyName;</name>
			  </company>
			  ```
		- ในตัวอย่างนี้, Entity reference `&companyName;` ถูกอ้างอิงใน `<name>` element ในเอกสาร XML และข้อมูลที่อ่านจากไฟล์ "companyName.txt" ที่ระบุใน Parsed External General Entity จะถูกแทนที่ในเอกสาร XML.
	- Unparsed external General Entity Declaration ใน DTD (Document Type Definition) ของ XML มีลักษณะดังนี้:
		- การประกาศ:
			- Unparsed External General Entity ประกาศภายใน DTD โดยใช้ของคำสั่ง `<!ENTITY>` และระบุ URL หรือ URI ของไฟล์ภายนอกที่ไม่ตีความได้ และระบุประเภทข้อมูลของ Entity ด้วยคำสั่ง `NDATA`.
			- ตัวอย่างการประกาศ Unparsed External General Entity ใน DTD:
			  ```xml
			  <!ENTITY logo SYSTEM "logo.png" NDATA PNG>
			  ```
		- การอ้างอิง Entity:
			- Unparsed External General Entity สามารถอ้างอิงในเอกสาร XML โดยใช้ entity reference ที่เป็นชื่อของ Entity ระบุระหว่าง `&` และ `;` เช่น `&logo;`.
			- เมื่อเอกสาร XML ถูกประมวลผล  Entity reference จะไม่ถูกตีความ แต่มีหน้าที่ใช้ในการอ้างอิงไฟล์ภายนอกที่ระบุใน Unparsed External General Entity.
			- ตัวอย่างการอ้างอิง Unparsed External General Entity ในเอกสาร XML:
			  ```xml
			  <company>
			  <logo>&logo;</logo>
			  </company>
			  ```
		- ในตัวอย่างนี้, Entity reference `&logo;` ถูกอ้างอิงใน `<logo>` element ในเอกสาร XML และมีหน้าที่ใช้ในการอ้างอิงไฟล์ "logo.png" ที่ระบุใน Unparsed External General Entity แต่ Entity reference ไม่ได้ตีความ และเป็นข้อมูลของไฟล์ "logo.png" โดยตรง.
- Parameter Entity Declaration
	- Parsed Internal Parameter Entity Declaration ใน DTD (Document Type Definition) ของ XML มีลักษณะดังนี้:
		- การประกาศ:
			- Parsed Internal Parameter Entity ประกาศภายใน DTD โดยใช้ของคำสั่ง `<!ENTITY>` และระบุ entity name ด้วย `%` หน้าชื่อ Entity.
			- ประกาศของ Parsed Internal Parameter Entity ประกอบด้วยชื่อของ Entity, ค่าของ Entity ที่ตีความและใช้ใน DTD, และรายละเอียดอื่น ๆ เกี่ยวกับ Entity (หากมี).
			- ตัวอย่างการประกาศ Parsed Internal Parameter Entity ใน DTD:
			  ```xml
			  <!ENTITY % companyName "Example Corp">
			  ```
		- การอ้างอิง Entity:
			- Parsed Internal Parameter Entity สามารถอ้างอิงใน DTD โดยใช้ entity reference ที่เป็นชื่อของ Entity ระบุระหว่าง `%` และ `;` เช่น `%companyName;`.
			- ตัวอย่างการอ้างอิง Parsed Internal Parameter Entity ใน DTD:
			  ```xml
			  <!ELEMENT book (title, author)>
			  <!ATTLIST book
			  publisher CDATA #IMPLIED
			  company (%companyName;) #IMPLIED
			  >
			  ```
		- ในตัวอย่างนี้, Parameter Entity `%companyName;` ถูกอ้างอิงใน `<!ATTLIST>` ของ `<book>` element ใน DTD เพื่อกำหนดค่าของ attribute `company` และค่า `%companyName;` จะถูกใช้ในการกำหนดค่า default ของ attribute `company`.
	- Parsed External Parameter Entity Declaration ใน DTD (Document Type Definition) ของ XML มีลักษณะดังนี้:
		- การประกาศ:
			- Parsed External Parameter Entity ประกาศภายใน DTD โดยใช้ของคำสั่ง `<!ENTITY>` และระบุ entity name ด้วย `%` หน้าชื่อ Entity และระบุ URL หรือ URI ของไฟล์ภายนอกที่มีข้อมูลของ Entity ภายใน.
			- ประกาศของ Parsed External Parameter Entity ประกอบด้วยชื่อของ Entity, ที่อยู่ของไฟล์ภายนอกที่มีข้อมูลของ Entity, และรายละเอียดอื่น ๆ เกี่ยวกับ Entity (หากมี).
			- ตัวอย่างการประกาศ Parsed External Parameter Entity ใน DTD:
			  ```xml
			  <!ENTITY % companyName SYSTEM "companyName.txt">
			  ```
		- การอ้างอิง Entity:
			- Parsed External Parameter Entity สามารถอ้างอิงใน DTD โดยใช้ entity reference ที่เป็นชื่อของ Entity ระบุระหว่าง `%` และ `;` เช่น `%companyName;`.
			- ตัวอย่างการอ้างอิง Parsed External Parameter Entity ใน DTD:
			  ```xml
			  <!ELEMENT book (title, author)>
			  <!ATTLIST book
			  publisher CDATA #IMPLIED
			  company (%companyName;) #IMPLIED
			  >
			  ```
		- ในตัวอย่างนี้, Parameter Entity `%companyName;` ถูกอ้างอิงใน `<!ATTLIST>` ของ `<book>` element ใน DTD เพื่อกำหนดค่าของ attribute `company` และค่า `%companyName;` จะถูกใช้ในการกำหนดค่า default ของ attribute `company`.