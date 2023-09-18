# Work flow
## การสร้าง project ใหม่จาก ESP WiFi provision Manager และแก้ไขที่ผิดในขั้นตอนการ build

1. Copy project จาก ESP WiFi provision Manager เป็น project  ใหม่ ชื่อ wifi_prov_mgr_LED_server
2. Build project
3. แก้ไข  sdkconfig เปลี่ยน flash size เป็น 4 MB


![image](https://github.com/Special-Topics-Computer-2023/wifi_prov_mgr_LED_server/assets/567256/82b76451-bba7-46b2-abb7-5c79ca3f9ef6)

4. Build project

5. เลือก Websocket Server Support ใน sdkconfig -> Http Server
 
   ![image](https://github.com/Special-Topics-Computer-2023/wifi_prov_mgr_LED_server/assets/567256/fd3b7577-65f9-4eb9-a882-5d82624c580c)

6. Build Project

7. ถ้าเรียกเว็บแล้วปรากฏแบบนี้
![image](https://github.com/Special-Topics-Computer-2023/wifi_prov_mgr_LED_server/assets/567256/ca2d6a3c-4817-41f7-be9a-f52a145ac873)
หรือใน smartphone มีข้อความ `Header field are too long for server to interpret`

มีสาเหตุมาจากการตั้งค่าความยาว buffer สำหรับ http request น้อยเกินไป (512) ให้เปลี่ยนเป็น 1024

![image](https://github.com/Special-Topics-Computer-2023/wifi_prov_mgr_LED_server/assets/567256/213c08f1-f549-41b2-84a9-cbf22fb95a38)

8. Build Project
