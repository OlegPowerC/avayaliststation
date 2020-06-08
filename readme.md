avayaliststation

New ver.

Avaya Unicode phone names

Please modify docker-compose.yaml as:

services: nginx: image: nginx:1.13.7
  container_name: nginx
    volumes:
      - ./nginx:/etc/nginx/conf.d <------- Path to folder with nginx config folder
      - ./html:/usr/share/nginx/html <---- Path to folder with html from this repository
       ports: - 80:80

flask-app: image: ciscoliveru/avayaliststation environment:
  - AVAYACM=10.10.10.5 <-------------- Your Avaya CM IP address
  - AVAYAUSER=list1 <----------------- Avaya CM user with SAT access but restricted to read stations only
  - AVAYAPASSWD=listpass123 <--------- Password for this user