- Important
	- API (Application Programming Language: ส่วนต่อประสานโปรแกรมประยุกต์) คือวิธีการที่โปรแกรม ไลบรารี ระบบปฏิบัติการ หรือบริการ เปิดให้โปรแกรมคอนพิวเตอร์สามารถติดต่อเรียกใช้งานได้ แบ่งเป็น 2 ประเภท
		- Language-Dependent API: UDDI จัดเป็นประเภทนี้
		- Language-Independent API
			- UDDI API เรียกใช้โดย SOAP Binding จาก HTTP Post ซึ่ง OASIS แบ่ง UDDI API ออกเป็น 2 กลุ่มคือ
				- Service Publication (The UDDI Publishing APIs)
				  |<div style="width: 210px">API Name</div>|Description|<div style="width: 20px">V1</div>|<div style="width: 20px">V2</div>|
				  |get_authToken|ดึงข้อมูล Token การอนุญาต การดำเนินการในอินเตอร์เฟซของ publisher ทั้งหมดจำเป็นต้องใช้การอนุญาตที่ถูกต้องและส่งมอบอนุญาตที่ถูกต้องพร้อมกับคำขอ|Y|Y|
				  |discard_authToken|บอกที่ทะเบียน UDDI ให้ไม่อนุญาต  Token  ที่กำหนดอีกต่อไป ขั้นตอนนี้เทียบเท่ากับการออกจากระบบ|Y|Y|
				  |save_business|สร้างหรือปรับปรุงข้อมูลของธุรกิจในทะเบียน UDDI|Y|Y|
				  |save_service|สร้างหรือปรับปรุงข้อมูลเกี่ยวกับเว็บเซอร์วิสที่ธุรกิจให้บริการ|Y|Y|
				  |save_binding|สร้างหรือปรับปรุงข้อมูลทางเทคนิคเกี่ยวกับการดำเนินการเว็บเซอร์วิส|Y|Y|
				  |save_tModel|สร้างหรือปรับปรุงการลงทะเบียนของแนวคิดนามธรรมที่ระบบ UDDI จัดการ|Y|Y|
				  |delete_business|นำธุรกิจที่ระบุไว้ออกจากทะเบียน UDDI โดยสมบูรณ์|Y|Y|
				  |delete_service|นำเว็บเซอร์วิสที่ระบุไว้ออกจากทะเบียน UDDI โดยสมบูรณ์|Y|Y|
				  |delete_binding|นำรายละเอียดทางเทคนิคของเว็บเซอร์วิสที่ระบุไว้ออกจากทะเบียน UDDI|Y|Y|
				  |delete_tModel|นำ tModels ที่ระบุไว้ออกจากทะเบียน UDDI|Y|Y|
				  |get_registeredInfo|ส่งข้อมูลสรุปของทุกอย่างที่ทะเบียน UDDI กำลังเก็บข้อมูลให้กับผู้ใช้ในปัจจุบัน รวมถึงธุรกิจทั้งหมด เซอร์วิสทั้งหมด และ tModels ทั้งหมด|Y|Y|
				  |set_publisherAssertions|จัดการกับคำประกาศเรื่องความสัมพันธ์ที่ติดตามที่เกี่ยวข้องกับบัญชี publisher 1 account||Y|
				  |add_publisherAssertions|ทำให้เกิดคำประกาศเรื่องความสัมพันธ์หนึ่งรายการหรือมากกว่าในคอลเลกชันคำประกาศของ publisher 1 account||Y|
				  |delete_publisherAssertions|นำคำประกาศเรื่องความสัมพันธ์หนึ่งรายการหรือมากกว่าออกจากคอลเลกชันคำประกาศของ publisher ||Y|
				  |get_assertionStatusReport|ให้ Administrative Support หาสถานะคำประกาศของ publisher ที่ใช้อยู่ในปัจจุบันและคำประกาศที่รอดำเนินการที่เกี่ยวข้องกับการลงทะเบียนธุรกิจของ account publisher||Y|
				  |get_publisherAssertions|รับข้อมูลคำประกาศของ publisher ทั้งหมดที่เกี่ยวข้องกับบัญชี publisher 1 account||Y|
				- Service Discovery
				  |<div style="width: 210px">API Name</div>|Description|<div style="width: 20px">V1</div>|<div style="width: 20px">V2</div>|
				  |find_binding|ค้นหาการผูกพันตามแบบแผนที่เชื่อมโยงกับบริการที่ระบุ.|Y|Y|
				  |find_business|ค้นหาธุรกิจที่ตรงกับเกณฑ์ที่ระบุ.|Y|Y|
				  |find_relatedBusinesses|ค้นพบธุรกิจที่ได้เชื่อมโยงผ่านรูปแบบ uddi-org:relationships.||Y|
				  |find_service|ค้นหาบริการที่เชื่อมโยงกับธุรกิจที่ระบุ.|Y|Y|
				  |find_tModel|ค้นหาบันทึก tModel ที่ตรงกับเกณฑ์ที่ระบุ.|Y|Y|
				  |get_bindingDetail|ดึงข้อมูลการผูกพันตามแบบแผน (bindingTemplate) อย่างครบถ้วนสำหรับแต่ละ bindingKey ที่ระบุ.|Y|Y|
				  |get_businessDetail|ดึงข้อมูลเอนทิตี้ธุรกิจ (businessEntity) อย่างครบถ้วนสำหรับแต่ละ businessKey ที่ระบุ.|Y|Y|
				  |get_businessDetailExt|ดึงข้อมูลเอนทิตี้ธุรกิจขยาย (extended businessEntity) สำหรับแต่ละ businessKey ที่ระบุ.|Y|Y|
				  |get_serviceDetail|ดึงบันทึกบริการธุรกิจ (businessService record) สำหรับแต่ละ serviceKey ที่ระบุ.|Y|Y|
				  |get_tModelDetail|ดึงบันทึก tModel สำหรับแต่ละ tModelKey ที่ระบุ.|Y|Y|
-