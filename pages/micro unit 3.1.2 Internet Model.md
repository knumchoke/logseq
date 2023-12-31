- Hierarchy of the TCP/I model
  ![The-logical-mapping-between-OSI-basic-reference-model-and-the-TCP-IP-stack.png](../assets/The-logical-mapping-between-OSI-basic-reference-model-and-the-TCP-IP-stack_1704575594208_0.png)
	- การผ่านข้อมูล จะต้องทำกับชั้นที่ติดกันเหมือน OSI Model
	- มีรายละเอียดดังนี้
		- 1) Network Interface Layer (ชั้นการเชื่อมต่อเครือข่าย): ชั้นนี้เกี่ยวข้องกับการสื่อสารในระดับฮาร์ดแวร์ เช่น การส่งข้อมูลผ่านอุปกรณ์เครือข่ายที่ใช้ฟิสิกัล เช่น เคเบิล, การ์ดเครือข่าย และสวิตช์ ระบบหลายชนิดเช่น Ethernet, Wi-Fi, และ Bluetooth อยู่ในชั้นนี้
		- 2) Internet Layer (ชั้นอินเทอร์เน็ต): ชั้นนี้เกี่ยวข้องกับการส่งข้อมูลจากต้นทางไปยังปลายทางผ่านเครือข่าย โดยใช้ IP (Internet Protocol) เพื่อกำหนดเส้นทางและเชื่อมต่อระหว่างเครือข่าย ชั้นนี้จัดการกับการเปรียบเทียบที่อยู่ IP และการเลือกเส้นทางที่เหมาะสมในการส่งข้อมูล
		- 3) Transport Layer (ชั้นขนส่ง): ชั้นนี้จัดการกับการส่งข้อมูลจากจุดเริ่มต้นไปยังปลายทาง โดยใช้โปรโตคอลเช่น TCP (Transmission Control Protocol) และ UDP (User Datagram Protocol) เพื่อควบคุมการสื่อสาร, การจัดเรียงข้อมูล, และการตรวจสอบความถูกต้องของข้อมูล
		- 4) Application Layer (ชั้นแอปพลิเคชัน): ชั้นนี้เป็นชั้นบนสุดใน TCP/IP Model และรับผิดชั้นของแอปพลิเคชันและการสื่อสารในระดับสูง โดยรวมถึงการจัดการกับแอปพลิเคชันแต่ละอัน เช่น การส่งอีเมล, การเรียกเว็บไซต์, การใช้งานแอปพลิเคชันต่าง ๆ เช่น ไฟล์โอนถ่าย, การแชท, และการวิดีโอคอล
- TCP/IP Model และ OSI Model เป็นโมเดลที่ใช้ในการอธิบายและแบ่งแยกการสื่อสารในระบบเครือข่ายคอมพิวเตอร์ แม้ว่าทั้งสองโมเดลจะมีหลักการหลักที่คล้ายกันในการแบ่งแยกการสื่อสารเป็นชั้น ๆ แต่มีความแตกต่างบางอย่างดังนี้:
	- 1. จำนวนชั้น:
		- TCP/IP Model มี 4 ชั้นหลัก: Network Interface, Internet, Transport, และ Application Layers.
		- OSI Model มี 7 ชั้นหลัก: Physical, Data Link, Network, Transport, Session, Presentation, และ Application Layers.
	- 2. ชื่อชั้นและหน้าที่:
		- ชื่อชั้นในทั้งสองโมเดลอาจมีการตั้งชื่อและหน้าที่ที่คล้ายกัน แต่ก็อาจมีความแตกต่างบางอย่างในการอธิบายรายละเอียดของหน้าที่ในชั้นที่แตกต่างกัน.
	- 3. ความสัมพันธ์กับอินเทอร์เน็ต:
		- TCP/IP Model ถูกสร้างขึ้นโดยเฉพาะสำหรับใช้ในอินเทอร์เน็ต และเป็นโมเดลที่ใช้ในการสื่อสารในโลกของอินเทอร์เน็ตอย่างเดียว.
		- OSI Model ถูกสร้างขึ้นในสมัยที่ไม่มีอินเทอร์เน็ตเป็นที่รู้จักอย่างกว้างขวาง และถูกออกแบบให้เป็นโมเดลทั่วไปสำหรับการสื่อสารในเครือข่ายคอมพิวเตอร์ทั้งหมด ไม่จำกัดเฉพาะอินเทอร์เน็ต.
	- 4. การนำไปใช้:
		- TCP/IP Model นั้นถูกนำมาใช้จริงในโลกของอินเทอร์เน็ตและใช้กับโปรโตคอลอินเทอร์เน็ตทั้งหมด เช่น TCP, IP, UDP, HTTP, SMTP, และอื่น ๆ.
		- OSI Model ถูกนำมาใช้ในบางครั้งเป็นเครื่องมือในการออกแบบและอธิบายเครือข่าย แต่ไม่ได้นำไปใช้ในระบบเครือข่ายจริง ๆ อย่างแพร่หลาย.
	- 5. ความซับซ้อน:
		- OSI Model มีชั้นทั้งหมด 7 ชั้นและมีรายละเอียดมากขึ้นในการอธิบายหน้าที่ของแต่ละชั้น ทำให้มีความซับซ้อนมากขึ้นเมื่อเทียบกับ TCP/IP Model ที่มีเพียง 4 ชั้น.
	- 6. การนำเสนอ:
		- OSI Model ถูกนำเสนอในรูปแบบที่มีการแบ่งแยกชั้นอย่างชัดเจน และมักถูกใช้ในการศึกษาและการสอน.
		- TCP/IP Model มักถูกนำเสนอในรูปแบบที่สั้นกะทันหันและมีการใช้ในอินเทอร์เน็ตเพื่ออธิบายการสื่อสารในโลกของวันนี้.
- ในทางปฏิบัติ ในโลกของอินเทอร์เน็ตและเครือข่ายคอมพิวเตอร์ ส่วนใหญ่จะใช้ TCP/IP Model เป็นหลักในการอธิบายและแบ่งแยกระบบเครือข่าย แต่ OSI Model ยังคงมีความเป็นประโยชน์ในการศึกษาและการอธิบายหลักการของระบบเครือข่ายในรูปแบบที่มีความละเอียดมากขึ้น