- XML
  ```xml
  <?xml version="1.0" encoding="UTF-8" ?>
  <definitions name="StockQuote"
    targetNamespace="http://example.com/stockquote.wsdl"
    xmlns:tns="http://example.com/stockquote.wsdl" 
    xmins:xsd1="http://example.com/stockquote.xsd" 
    xmlns:soap="http://schemas.xmlsoap.org/wsdl/soap/"
    xmlns="http://schemas.xmlsoap.org/wsdl/">
    <types>
      <schema targetNamespace="http://example.com/stockquote.xsd"
        xmlns="http://www.w3.org/2000/10/XMLSchema">
        <element name="TradePriceRequest">
          <complexType>
            <all>
              <element name="tickerSymbol" type="string"/>
            </all>
          </complexType>
        </element>
        <element name="TradePrice">
          <complexType>
            <all>
              <element name="price" type="float"/>
            </all>
          </complexType>
        </element>
      </schema>
    </types>
    ...
  </definitions>
  ```
	- Tag: สำหรับ WSDL จากตัวอย่าง Tag คือส่วนที่เริ่มต้นด้วย `<` และปิดด้วย `>` สามารถแยกได้ 3 อย่างคือ
		- start tag: เช่น `<types>`
		- end tag: `</types>`
		- empty tag: `<element name="price" type="float"/>`
	- Element: สำหรับ WSDL คือส่วนที่เริ่มตั้งแต่ Start-Tag ถึง End-Tag เช่น `<types> ... </types>` ที่เป็น element ครอบคลุมตั้งแต่บรรทัดที่ 8 - 26
	- Attribute: สำหรับ WSDL คือส่วนที่เป็นค่าใน Tag เช่น `name="TradePriceRequest"` ของ `<element> ... </element>` จากบรรทัดที่ 11
	- Unicode: WSDL รองรับทุกภาษาที่เป็น Unicode และเป็น Case Sensitive เช่น `<complexType>` จะถือว่าเป็นคนละตัวกับ `<complextype>`
	- XML Declaration WSDL ต้องมีการประกาศ XML ที่บรรทัดแรกทุกครั้ง `<?xml version="1.0" encoding="UTF-8" ?>`
- Schema XML (XSD)
	- Roles of XSD
		- กำหนด element หรือ attribute ที่สามารถมีได้ในเอกสาร
		- ระบุ Child Element
		- ลำดับ Element ในเอกสาร
		- จำนวน Child Element ที่ Element หนึ่งสามารถมีได้
		- Element ใดเป็น Empty Element ได้
		- Data type ของ Element และ Attribute
		- ระบุค่า Default หรือ Constant ของ Element และ Attribute
	- จากตัวอย่างดังนี้
	  file xml ทั่วไป
	  ```xml
	  <?xml version="1.0"?>
	  <note>
	    <to>Tove</to>
	    <from>Jani</from>
	    <heading>Reminder</heading>
	    <body>Don't forget me this weekend</body>
	  </note>
	  ```
	  file xml schema `note.xsd`
	  ```xml
	  <?xml version="1.0"?>
	  <xs:schema  xmlns:xs="http://www.w3.org/2001/XMLSchema"
	              targetNamespace="http://www.w3schools.com"
	              xmlns="http://www.w3schools.com"
	              elementFormDefault="gualified">
	    <xs:element name="note">
	      <xs:complexType> 
	        <xs:sequence>
	          <xs:element name="to" type="xs:string" />
	          <xs:element name="from" type="xs:string" />
	          <xs:element name="heading" type="xs:string" /> 
	          <xs:element name="body" type="xs:string" />
	        </xs:sequence> 
	      </xs:complexType>
	    </xs:element> 
	  </xs:schema>
	  ```
		- ใน root element `note`
			- child element จะถูก XSD กำหนด data type ตามชื่อและลำดับที่สัมพันธ์กัน เมื่อนำมาเขียนเป็น XML ใหม่ที่อ้างอิง XSD จะได้
			  ```xml
			  <?xml version="1.0"?>
			  <note xmlns="http://www.w3schools.com" 
			        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
			        xsi:schemaLocation="http://www.w3schools.com/note.xsd">
			    <to>Tove</to>
			    <from>Jani</from>
			    <heading>Reminder</heading>
			    <body>Don't forget me this weekend</body>
			  </note>
			  ```
- XML Name Space
	- การใช้ Name Space (ns) มีไว้เพื่อ
		- ป้องกันการตั้งชื่อ element ไม่ให้เกิดความซ้ำซ้อน
		- ลดความกำกวมในการตั้งชื่อ
	- จากตัวอย่างนี้
	  ```xml
	  <root xmlns:ns1="http://www.example.com/ns1" 
	        xmlns:ns2="http://www.example.com/ns2">
	    <ns1:element1>ข้อมูลในชื่อนามสเปซ ns1</ns1:element1>
	    <ns2:element1>ข้อมูลในชื่อนามสเปซ ns2</ns2:element1>
	  </root>
	  ```
		- จะเห็นได้ว่ามี element `<element1>` อยู่ 2 อัน โดยที่ ns จะเติม prefix ลงไปกลายเป็น `<ns1:element1>` และ `<ns2:element1>` ตามลำดับ
		- `ns1` และ `ns2` ได้จากการ reference ใน root element
	- xmlns:wsdl ในเอกสาร WSDL ต้องมีการประกาศ wsdl name space สามารถดูรายละเอียด WSDL ได้จาก https://schemas.xmlsoap.org/wsdl/
	- xmlns:soap ในเอกสาร SOAP ต้องมีการประกาศ soap name space ใช้ในการทำ <ins>SOAP binding</ins> สำหรับ WSDL1.1 สามารถดูรายละเอียด SOAP ได้จาก https://schemas.xmlsoap.org/wsdl/soap
	- xmlns:http ใช้ในการทำ <ins>HTTP binding</ins> สำหรับ WSDL1.1 สามารถดูรายละเอียด SOAP ได้จาก https://schemas.xmlsoap.org/wsdl/http
	- xmlns:mime ใช้ในการทำ <ins>MIME binding</ins> สำหรับ WSDL1.1 สามารถดูรายละเอียด SOAP ได้จาก https://schemas.xmlsoap.org/wsdl/mime