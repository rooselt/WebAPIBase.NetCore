# WebAPIBase
WebAPI (.NET Core 3.1) Base Project with JWT Auth, Dapper (ORM), MySQL, Password Hash, Swagger

[![Build status](https://ci.appveyor.com/api/projects/status/2g98rixcdtqq89br?svg=true)](https://ci.appveyor.com/project/thiagoloureiro/webapibase-netcore)

[![Build history](https://buildstats.info/appveyor/chart/thiagoloureiro/webapibase-netcore)](https://ci.appveyor.com/project/thiagoloureiro/webapibase-netcore/history)

## Instalation / Configuration Steps:

1) Clone the repository
git clone https://github.com/thiagoloureiro/WebAPIBase.NetCore.git

2) Open the Solution file (Visual Studio 2019)

3) Create a Database (any desired name) in MySQL, you can use an existing one.

4) Modify **appsettings.json** file in **TORO.WebApi**, connectionstring:
   ```
     "ConnectionStrings": {
    "localhost": "Server=server;Port=123456;Database=DB;Uid=USRID;Pwd=PASSWD;"
   ```
Modify using your values.

5) Run the Project.

6) After run the project, in the address bar you will have something like: http://localhost:5001/ (the port may change) add swagger to address, for ex: http://localhost:5001/swagger, a Swagger page should be displayed.

7) You will notice 2 endpoints, **api/user** and **/api/users/create**, the first one is to login and the second one to create a new user to generate the token for the JWT Authentication.

8) Access the **/api/user/register** endpoind and create a new user, you should receive a result "User Created Successfully! :)"

9) Test Login with the Created User in the **/api/users/authenticate** endpoint, with the following request
```
{
  "username": "UserNameHere",
  "password": "PasswordHere"
}
```
10) You Should receive a ReponseBody like this:
```
{
  "id": 1,
  "firstName": "Administrador",
  "lastName": "",
  "username": "admin",
  "cpf": "",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1bmlxdWVfbmFtZSI6IjEiLCJyb2xlIjoidXNlciIsIm5iZiI6MTYyNjQ1NTM1OSwiZXhwIjoxNjI2NDU3MTU5LCJpYXQiOjE2MjY0NTUzNTl9.D0ZQYKCsuLlBt8W1wACIzVVJML-KcLDz-6m_-gPm_EE"
}
```

11) Now you are all set, just create the other Controllers following the patterns and rock on :)
Remember to dot use the **[AllowAnonymous]**  from the other Controllers you are going to create, because with this property will ignore and you can access the API Without Authentication.

12) To use Authentication for example using Postman, in the HEADER add a Key called "Authorization" **(without quotes)** and Value add: Bearer "the received token from the login" **(without quotes)**

13) Any Questions please feel free to ask ! :)

Enjoy!

