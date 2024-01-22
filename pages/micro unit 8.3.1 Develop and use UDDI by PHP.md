- จากตัวอย่างนี้
  ```xml
  <find_business [maxRows="nn"] generic="2.0" xmlns="urn:uddi-org:api_v2">
    [<findQualifiers/>]
    [<name/><name/> ...]
    [<discoveryURLs/>]
    [<identifierBag/>]
    [<categoryBag/>]
    [<tModelBag/>]
  </find_business>
  ```
  
  ```php
  <?php  
    require_once 'UDDI_Inquiry.class.inc';
    $my_uddi = new UDDI_Inquiry('IBM');
    $my_uddi->version = 2;
    $input = array(
      'findQualifiers' => 'sortByNameAsc',
      'maxRows'        => 25,
      'name'           => '%Acme%'
    );
    $result = $my_uddi->find_busness($input);
  ?>
  ```
	- script php เรียกใช้ class `phpUDDI` จาก `UDDI_Inquiry.class.inc` ที่มี service ชื่อ `find_bussiness` อยู่
	- `$my_uddi = new UDDI_Inquiry('IBM');` เรียกดูข้อมูลจาก IBM
	- `$my_uddi->version = 2;` ระบุว่าเรียกด้วย version 2
	- `$input = array(...);` กำหนดค่า input เป็น array แบบ key:value
	- `%Acme` = `*` (wildcard)
	- `$result = $my_uddi->find_busness($input);` เรียกใช้ `find_busness`
- จากตัวอย่างนี้
  ```php
  <?php
    require_once 'UDDI.php';
    $uddi = new UDDI('IBM', 2);
    $options = array(
      'findQualifiers' => 'sortByNameAsc',
      'maxRows'        => 25,
      'name'           => '%Acme%'
    );
    $result = $uddi->query('find_busness', $options);
  ?>
  ```
	- script php เรียกใช้ class `pear` จาก `UDDI.php` ที่มี service ชื่อ `find_bussiness` อยู่
	- `$uddi = new UDDI('IBM', 2);` เรียกดูข้อมูลจาก IBM ที่เป็น version 2
	- `$$options = array(...);` กำหนดค่า input เป็น array แบบ key:value
	- `$result = $uddi->query('find_busness', $options);` เรียกใช้ `find_busness` ผ่าน pear
-