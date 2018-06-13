FROM php
COPY game /tmp/
CMD ["php", "-S", "0.0.0.0:80", "-t", "/tmp"]
#to build
#build -t game1 .
#to run
#docker run -d --name gamme -p 8080:80 game1
#check on "ip of char":8080