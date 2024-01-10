- Element Declaration จากตัวอย่าง
  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <!DOCTYPE bookstore [
    <!ELEMENT bookstore (book+)>
    <!ELEMENT book (title, author, price, test, test2, (mix|max))>
    <!ELEMENT title (#PCDATA)>
    <!ELEMENT author (#PCDATA)>
    <!ELEMENT price (#PCDATA)>
    <!ELEMENT test EMPTY>
    <!ELEMENT test2 ANY>
    <!ELEMENT mix (#PCDATA)>
    <!ELEMENT max (#PCDATA)>
  ]>
  <bookstore>
    <book>
      <title>Introduction to XML</title>
      <author>John Doe</author>
      <price>29.99</price>
  	<test></test>
      <test2>[any data type can be here]</test2>
      <mix>z123@</mix>
    </book>
    <book>
      <title>Introduction to XML</title>
      <author>John Doe</author>
      <price>29.99</price>
  	<test></test>
      <test2>[any data type can be here]</test2>
      <max>5555</max>
    </book>
  </bookstore>
  ```
	- empty element
		- บรรทัดที่ 8 เป็น Declaration
		- บรรทัดที่ 18 เป็น วิธีใช้งาน
	- any element
		- บรรทัดที่ 9 เป็น Declaration
		- บรรทัดที่ 19 เป็น วิธีใช้งาน
	- content model เพื่อบอกว่า Element ย่อยของ `book` จะต้องมีอะไรบ้าง
		- บรรทัดที่ 4 เป็น Declaration
		- บรรทัดที่ 5 - 11 เป็น วิธีใช้งาน
	- mixed content
		- มี 2 แบบ
			- แบบแทรก element เข้าไปใน element ย่อย
				- เป็นลักษณะของอิลิเมนต์ใน XML ที่อนุญาตให้มีเนื้อหาที่ผสานระหว่างข้อมูลข้อความและอิลิเมนต์ย่อย (sub-elements) อยู่ภายในอิลิเมนต์เดียว
				- ลักษณะ mixed content สามารถกำหนดใน DTD โดยใช้ `#PCDATA` เพื่อระบุข้อมูลข้อความและใช้แท็ก `*` หรือ `+` เพื่อระบุการปรากฎของอิลิเมนต์ย่อยภายในอิลิเมนต์ที่เป็น mixed content
				- ตัวอย่างเช่น
				  ```xml
				  ....
				  <!ELEMENT paragraph (#PCDATA | em | strong)*>
				  ....
				  <paragraph>This is a <em>mixed content</em> example.</paragraph>
				  ....
				  ```
				  ในตัวอย่างนี้, DTD ระบุว่า `<paragraph>` มีลักษณะ mixed content ซึ่งอนุญาตให้มีข้อมูลข้อความ (`#PCDATA`) และอิลิเมนต์ `<em>` หรือ `<strong>` ปรากฎอยู่ภายใน `<paragraph>` โดยใช้ `|` เพื่อแยกระหว่างตัวเลือก. คุณสามารถใช้ `*` เพื่อระบุว่าอิลิเมนต์ย่อยเหล่านี้สามารถปรากฎภายใน `<paragraph>` ในจำนวนไม่จำกัดหรือ `+` เพื่อระบุว่าอิลิเมนต์ย่อยเหล่านี้ต้องปรากฎอย่างน้อยครั้งหนึ่ง.
				  ในตัวอย่างนี้, `<paragraph>` มีเนื้อหา mixed content ที่ประกอบด้วยข้อความ "This is a " และอิลิเมนต์ `<em>` ก่อนที่จะมีข้อความ "mixed content" และ " example." ปรากฎอยู่ภายใน `<paragraph>` ในลำดับที่ต่างกัน. นี่คือตัวอย่างของวิธีที่ mixed content อนุญาตให้ผสานข้อมูลข้อความและอิลิเมนต์ย่อยในเอกสาร XML ได้.
			- แบบ Optional ใน root element
				- บรรทัดที่ 4 `(mix|max)` เป็น Declaration
				- บรรทัดที่ 20, 28 เป็น วิธีใช้งาน จะเห็นว่าสามารถมี element `mix` หรือ `max` เพียงตัวใดตัวนึงก็ได้
- Attribute Declaration
	- ใน DTD (Document Type Definition) เป็นวิธีที่เราสามารถระบุและกำหนดคุณลักษณะของอิลิเมนต์ในเอกสาร XML โดยใช้แท็ก `<!ATTLIST>` ใน DTD. แต่ละ attribute จะถูกระบุในแท็ก `<!ATTLIST>` โดยระบุชื่อ attribute, ประเภทของข้อมูล, และค่าเริ่มต้น (หากมี) ซึ่งเป็นอ็อกชันที่ใช้เฉพาะใน DTD เพื่อกำหนดข้อมูลของ attribute. นี่คือรูปแบบของแท็ก `<!ATTLIST>` ใน DTD:
	  ```xml
	  <!ATTLIST elementName
	    attributeName attributeDataType attributeDefaultValue>
	  ```
	  โดยที่:
		- `elementName`: ชื่อของอิลิเมนต์ที่เราต้องการกำหนด attribute.
		- `attributeName`: ชื่อของ attribute ที่เราต้องการกำหนด.
		- `attributeDataType`: ประเภทของข้อมูล (Data Type) ที่ attribute รองรับ เช่น CDATA, ID, IDREF, NMTOKEN, ENTITY, และอื่น ๆ.
		- `attributeDefaultValue`: ค่าเริ่มต้นของ attribute (หากมี) ซึ่งอาจเป็นค่าที่ต้องระบุหรือไม่ต้องระบุ และสามารถเป็นค่าว่างหรืออื่น ๆ ตามที่ DTD กำหนด.
	- ตัวอย่างการกำหนด attribute ใน DTD:
	  
	  ```xml
	  <!DOCTYPE library [
	    <!ELEMENT library (book+)>
	    <!ELEMENT book (title, author, publicationYear)>
	    <!ATTLIST book
	      isbn CDATA #REQUIRED
	      genre (Fiction|Non-Fiction) "Fiction"
	    >
	    <!ELEMENT title (#PCDATA)>
	    <!ELEMENT author (#PCDATA)>
	    <!ELEMENT publicationYear (#PCDATA)>
	  ]>
	  <library>
	    <book isbn="978-1234567890" genre="Non-Fiction">
	      <title>Introduction to XML</title>
	      <author>John Doe</author>
	      <publicationYear>2022</publicationYear>
	    </book>
	    <!-- รายการหนังสืออื่น ๆ -->
	  </library>
	  
	  ```
	  
	  ในตัวอย่างนี้, DTD กำหนดว่า `<book>` ต้องมี attribute `isbn` และ `genre` ซึ่งกำหนดให้ `isbn` เป็นชนิดข้อมูล CDATA และเป็น attribute ที่บังคับ (REQUIRED) ในขณะที่ `genre` มีค่าเริ่มต้นเป็น "Fiction" และใช้ชนิดข้อมูล (data type) เป็น enumeration โดยระบุให้เลือกได้เฉพาะ "Fiction" หรือ "Non-Fiction". นอกเสียจากนี้, DTD กำหนด element `<book>` ต้องมี element `<title>`, `<author>`, และ `<publicationYear>` ในภายใน.
	- ตาราง Data Type
	  | <div style="width:250px">Attribute Type</div> | Explanation |
	  |1. `CDATA` (Character Data)| หรือ `PCDATA` ใช้สำหรับข้อมูลข้อความที่ไม่ได้มีโครงสร้างเฉพาะ และอนุญาตให้ใส่อักขระพิเศษโดยไม่ต้องใช้ character references.|
	  |2. `ID` (Identifier)| ใช้สำหรับระบุค่าที่เป็นไปตามข้อกำหนดตามชื่อที่ไม่ซ้ำกันภายในเอกสาร XML.|
	  |3. `IDREF` (ID Reference)| ใช้สำหรับระบุค่าที่เป็นอ้างอิงถึงค่า `ID` ในเอกสาร XML.|
	  |4. `IDREFS` (ID References)| ใช้สำหรับระบุค่าที่เป็นรายการของอ้างอิงไปยังค่า `ID` ในเอกสาร XML.|
	  |5. `NMTOKEN` (Name Token)| ใช้สำหรับระบุค่าที่เป็นชื่อที่ไม่มีช่องว่างหรืออักขระพิเศษ.|
	  |6. `NMTOKENS` (Name Tokens)| ใช้สำหรับระบุค่าที่เป็นรายการของชื่อที่ไม่มีช่องว่างหรืออักขระพิเศษ.|
	  |7. `ENTITY` (Entity Name)| ใช้สำหรับระบุค่าที่เป็นชื่อของ entity ภายใน DTD.|
	  |8. `ENTITIES` (Entity Names)| ใช้สำหรับระบุค่าที่เป็นรายการของชื่อ entity ภายใน DTD.|
	  |9. `NOTATION` (Notation Name)| ใช้สำหรับระบุค่าที่เป็นชื่อของ notation ภายใน DTD.|
	  |10. `ENUMERATION` (Enumeration)| ใช้สำหรับระบุค่าที่จะต้องอยู่ในรายการค่าที่ถูกกำหนดล่วงหน้า.|
	- ตารางค่าเริ่มต้นของ Attribute
	  | <div style="width:150px">Value  </div>   | Explanation |
	  |`#REQUIRED`| ระบุว่า attribute นี้เป็นบังคับและต้องระบุค่าเมื่อใช้งานอิลิเมนต์นี้ หากไม่ได้ระบุค่า attribute จะไม่ถูกตรวจสอบความถูกต้องของเอกสาร XML และเอกสารอาจถูกพิจารณาเป็นไม่ถูกต้อง|
	  |`#IMPLIED` | ระบุว่า attribute นี้เป็นทางเลือก หากไม่ได้ระบุค่า attribute ในอิลิเมนต์ จะถือว่า attribute นี้ไม่มีค่าและเอกสาร XML ถือว่าถูกต้อง|
	  |`#FIXED`   | ระบุค่าที่ถูกกำหนดให้ attribute มีค่าคงที่และไม่สามารถเปลี่ยนแปลงได้. ถ้า attribute ถูกระบุในอิลิเมนต์ ค่าที่ระบุในอิลิเมนต์จะถูกเปลี่ยนแปลงให้เท่ากับค่าที่ระบุใน `#FIXED`|
	  |default    | ค่า default อาจเป็นข้อความที่เป็นค่าเริ่มต้นของ attribute และถ้าไม่มีค่า attribute ถูกระบุในอิลิเมนต์ ค่านี้จะถูกใช้เป็นค่าของ attribute|