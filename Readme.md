#ใช้ Docker image
docker pull nginx
หรือ 
docker pull nginx:stable
หรือ  
docker pull nginx:1.10

#การสร้าง Container

docker run --name myweb -p 8080:80 -v /myweb:/var/www/html -d nginx

--name demo คือ การตั้งชื่อให้กับ container โดยเมื่อเราใช้คำสั่ง start stop หรือ rm สามารถสั่งงาน container ได้จากชื่อ container ได้เช่นกัน
-d เป็นการสั่ง contianer ให้รันแบบ background
-v /home/me:/home/docker คือการ mount volume หรือเป็นการแชร์ไฟล์ระหว่าง container กับเครื่องเราให้สามารถเรียกใช้ไฟล์ร่วมกันได้
-p 8080:80 เป็นการ map port ระหว่างเครื่อง และ container เช่น อย่าง container ของ nginx จะใช้ port 80 เป็น default หากต้องการให้เครื่องใช้ port 8080 เราก็กำหนดให้เป็น -p 8080:80
image ชื่อของ Docker image ที่เราต้องการเรียกใช้ (จากตัวอย่างจะใช้ nginx เป็น image)

#ตรวจสอบสถานะ Container
docker ps

#ดูรายการ container ทั้งหมด
docker ps -a

#หยุด Container
docker stop <Container ID/Name>

#ลบ Container
docker rm <Container ID/Name>

#ดู Docker Image ทั้งหมด
docker images

#คำสั่งลบ Image
docker rmi <Image ID/Name>

#เปิดผ่าน Browser
http://localhost:8080/ (ถ้าใช้ Docker Toolbox จะเป็น IP : 192.168.99.100 โดย default)


# สร้าง docker image
docker build -t prongbang/image-name