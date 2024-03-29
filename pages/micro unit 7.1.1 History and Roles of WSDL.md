- WSDL History
	- WSDL (Web Services Description Language) เป็นภาษามาตรฐานที่ใช้สำหรับการอธิบายบริการเว็บ (Web Services) แบบ XML-based ประวัติของ WSDL สามารถสรุปได้ดังนี้:
		- **กำเนิดและการพัฒนา**: WSDL ถูกพัฒนาขึ้นเป็นครั้งแรกโดย Microsoft และ IBM ในช่วงต้นปี 2000 มันถูกสร้างขึ้นเพื่อเป็นมาตรฐานในการอธิบายบริการเว็บที่เข้ากันได้กับหลากหลายแพลตฟอร์มและภาษาโปรแกรมมิ่ง
		- **WSDL 1.1**: เวอร์ชันนี้ได้รับการเผยแพร่ในปี 2001 และถือเป็นเวอร์ชันที่ใช้กันอย่างแพร่หลายในอุตสาหกรรม แม้จะไม่เคยได้รับการรับรองเป็นมาตรฐานอย่างเป็นทางการจาก W3C (World Wide Web Consortium)
		- **การรับรองจาก W3C**: ในปี 2003, W3C ได้รับรอง WSDL 2.0 เป็นมาตรฐานอย่างเป็นทางการ โดยมีการปรับปรุงและเพิ่มคุณสมบัติหลายอย่างเพื่อทำให้มันเข้ากันได้ดีกว่ากับเทคโนโลยีเว็บอื่นๆ
		- **WSDL 2.0**: ซึ่งเป็นการอัพเกรดจากเวอร์ชัน 1.1, ได้นำเสนอการเปลี่ยนแปลงที่สำคัญ เช่น การเพิ่มการรองรับเว็บเซอร์วิส RESTful และการปรับปรุงในแง่ของสมรรถนะและการใช้งาน
		- **ความเป็นมาตรฐาน**: แม้ว่า WSDL 2.0 จะเป็นมาตรฐานที่รับรองโดย W3C, หลายองค์กรและบริการเว็บยังคงใช้ WSDL 1.1 เนื่องจากมีการใช้งานอย่างกว้างขวางและมีเครื่องมือหลายอย่างที่รองรับ
		- **บทบาทในการพัฒนาเว็บ**: WSDL มีบทบาทสำคัญในการพัฒนาเว็บเซอร์วิสโดยใช้ SOAP (Simple Object Access Protocol) และมีอิทธิพลอย่างมากต่อการพัฒนาและการดำเนินงานของบริการเว็บในปัจจุบัน
	- WSDL ยังคงเป็นส่วนสำคัญของสถาปัตยกรรมเว็บเซอร์วิสและช่วยให้การพัฒนาและการบูรณาการบริการเว็บเป็นไปได้อย่างราบรื่นและมีประสิทธิภาพ.
- Roles of WSDL
	- เมื่อเปรียบเทียบ SOAP เป็นซองจดหมายแล้ว WSDL จะเป็นเหมือนแบบฟอร์มที่แสดงตัวอย่างการขอใช้บริการ ซึ่งสามารถแยกรายละเอียดได้ดังนี้
	  |<div style="width:100px">W4H1</div>|WSDL|
	  |Where|บริการที่มีสามารถเรียกใช้ได้จากที่ใด|
	  |What|ผู้ให้บริการมีบริการอะไรบ้าง|
	  |How|บริการที่มีจะสามารถเรียกใช้ได้อย่างไร|
	  |Why|บริการที่มีแตกต่างจากบริการที่เหมือนกันของผู้ให้บริการอื่นอย่างไรเหตุใดผู้ร้องขอบริการจึงต้องเรียกใช้จากบริการนี้|
	  |Who|รายละเอียดของผู้ให้บริการ|
	- WSDL 1.1 -> SOAP 1.1
	- WSDL 2.0 -> SOAP 1.2