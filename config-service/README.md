# config-service

默认用户名： user

生成jks:

keytool -genkeypair -alias config-service -keyalg RSA -dname "CN=Config Service,OU=Unit,O=Abba" -keypass abba.123 -keystore config-service.jks -storepass abba.123

加密：

curl -X POST -u user:abba.123 http://localhost:11110/encrypt -d root

postman: 

curl --location --request POST 'http://localhost:11110/encrypt' \
         --header 'Authorization: Basic dXNlcjphYmJhLjEyMw==' \
         --header 'Content-Type: text/plain' \
         --data-raw 'root'                                                   