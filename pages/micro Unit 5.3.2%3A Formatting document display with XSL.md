- **Basic XSL**
	- **XSL Transformation Language (XSLT):**
		- **คำอธิบาย:** XSLT (Extensible Stylesheet Language Transformations) เป็นภาษาที่ใช้ในการแปลงเอกสาร XML จากรูปแบบหนึ่งไปยังรูปแบบอื่น ๆ โดยใช้ XSLT Stylesheet หรือ XSLT Transformation ซึ่งกำหนดโครงสร้างและรูปแบบของเอกสารผลลัพธ์ โดยใช้รูปแบบและกฎของ XSLT ในกระบวนการแปลง. XSLT มีฟังก์ชันที่สามารถนำมาใช้ในการค้นหาข้อมูล, กระทำกับข้อมูล, และสร้างเอกสารใหม่.
		- **Namespace:** XSLT มี namespace เป็นส่วนหนึ่งของ XML ซึ่งจะปรากฏในเอกสาร XSLT Stylesheet ด้วย xmlns:xsl เพื่อระบุว่าภายในส่วนของ Stylesheet จะมีคำสั่งและความหมายที่เป็นของ XSLT.
		  ```xml
		  <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
		  <!-- XSLT Stylesheet content here -->
		  </xsl:stylesheet>
		  ```
	- **Formatting Object Specification (XSL-FO):**
		- **คำอธิบาย:** XSL-FO (Extensible Stylesheet Language Formatting Objects) เป็นส่วนหนึ่งของ XSL (Extensible Stylesheet Language) ที่ใช้ในการกำหนดรูปแบบและการจัดหน้าสำหรับเอกสาร XML เพื่อพิมพ์หรือนำเสนอ. XSL-FO ใช้เอกสาร XSL-FO Stylesheet ที่กำหนดรูปแบบเอกสาร และปรับเปลี่ยนโครงสร้างของเอกสาร XML เป็นรูปแบบที่เหมาะสมสำหรับการพิมพ์หรือนำเสนอ.
		- **Namespace:** XSL-FO ก็มี namespace เป็นส่วนหนึ่งของ XML ที่ใช้ในเอกสาร XSL-FO Stylesheet โดยใช้ xmlns:fo เพื่อระบุคำสั่งและความหมายที่เป็นของ XSL-FO.
		  ```xml
		  <fo:root xmlns:fo="http://www.w3.org/1999/XSL/Format">
		  <!-- XSL-FO Stylesheet content here -->
		  </fo:root>
		  ```
- **XSL Template** คือส่วนหนึ่งของ XSLT (Extensible Stylesheet Language Transformations) ที่ใช้ในการระบุวิธีการแปลงและจัดรูปแบบข้อมูล XML ในเอกสารต้นฉบับเป็นเอกสารผลลัพธ์ตามรูปแบบที่กำหนด การใช้ XSL Template เป็นวิธีการระบุเงื่อนไขเมื่อต้องการที่จะประมวลผลส่วนข้อมูลที่มีโครงสร้างหรือลักษณะที่แตกต่างกันในเอกสาร XML ต้นฉบับ สามารถจัดรูปแบบหรือแปลงส่วนข้อมูลต่าง ๆ ของเอกสารในรูปแบบที่ต้องการโดยใช้ XSL Template.
	- มีโครงสร้าง XSL Template ที่ต่างกันอยู่สองประเภทหลัก:
		- **Single Template Structure (โครงสร้างเทมเพลตเดียว):**
			- ในโครงสร้างนี้มีเทมเพลตเดียวที่ใช้ในการแปลงข้อมูล XML ทั้งหมดในเอกสารต้นฉบับ โครงสร้างของ XSLT Stylesheet มีลักษณะดังนี้:
			  ```xml
			  <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
			  <xsl:template match="/">
			  <!-- XSLT Template content here -->
			  </xsl:template>
			  </xsl:stylesheet>
			  ```
		- **Multiple Template Structure (โครงสร้างเทมเพลตหลายรูปแบบ):**
			- ในโครงสร้างนี้มีเทมเพลตหลายรูปแบบที่ใช้ในการแปลงข้อมูล XML ในเอกสารต้นฉบับตามเงื่อนไขที่กำหนด โครงสร้างของ XSLT Stylesheet มีลักษณะดังนี้:
			  ```xml
			  <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
			  <xsl:template match="/">
			  <!-- XSLT Template for the root element -->
			  </xsl:template>
			  
			  <xsl:template match="element1">
			  <!-- XSLT Template for elements matching 'element1' -->
			  </xsl:template>
			  
			  <xsl:template match="element2">
			  <!-- XSLT Template for elements matching 'element2' -->
			  </xsl:template>
			  
			  <!-- Additional templates for other elements -->
			  </xsl:stylesheet>
			  ```
	- ในโครงสร้างเทมเพลตหลายรูปแบบ, การใช้ `match` อย่างสม่ำเสมอเพื่อระบุว่าเทมเพลตนี้จะถูกเรียกใช้เมื่อข้อมูล XML ตรงกับเงื่อนไขที่ระบุ ในขณะที่ในโครงสร้างเทมเพลตเดียว มีเทมเพลตเดียวที่ถูกเรียกใช้สำหรับเอกสารทั้งหมด.
	- การเลือกใช้โครงสร้างเทมเพลตที่เหมาะสมขึ้นอยู่กับความต้องการและโครงสร้างของเอกสาร XML ต้นฉบับของคุณ โครงสร้างเทมเพลตหลายรูปแบบมีความยืดหยุ่นมากขึ้นและช่วยให้คุณสามารถปรับแต่งการแปลงข้อมูลในรายละเอียดแต่ละส่วนของเอกสาร XML ได้.