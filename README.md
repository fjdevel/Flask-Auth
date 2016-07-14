For requests using httpie: http://radek.io/2015/10/20/httpie/
pip install httpie

Register:
http POST :5000/v1/auth/register username=test_name password=test_password email=example@example.com

Login:
http POST :5000/v1/auth/login email=example@example.com password=test_password
Got access token and refresh token!

Test requiring authentication handler
http POST :5000/data Authorization:"bearer ACCESS_TOKEN"

------------------------------------------------------------------------------------------------------------------------

For requests using curl: https://curl.haxx.se/download.html

Register:
curl -H "Content-Type: application/json" --data '{"username":"test_name","password":"test_password", "email":"example@example.com"}' http://localhost:5000/v1/auth/register

Login:
curl -H "Content-Type: application/json" --data '{"email":"example@example.com", "password":"test_password"}' http://localhost:5000/v1/auth/login
Got access token and refresh token!

Test requiring authentication handler
curl -H "Content-Type: application/json" -H "Authorization: Bearer ACCESS_TOKEN" http://localhost:5000/data
