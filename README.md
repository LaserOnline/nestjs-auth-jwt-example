## NestJs Jwt Example

- [Docs](https://docs.nestjs.com/security/authentication)

install package jwt
```bash
  npm install --save @nestjs/jwt
```

GET /profile
```bash
  curl http://localhost:3000/auth/profile
```
{"statusCode":401,"message":"Unauthorized"}

POST /auth/login
```bash
  curl -X POST http://localhost:3000/auth/login -d '{"username": "john", "password": "changeme"}' -H "Content-Type: application/json"
```
{"access_token":"token"}

GET /profile using access_token returned from previous step as bearer code
```bash
  curl http://localhost:3000/auth/profile -H "Authorization: Bearer token"
```
{"sub":1,"username":"john","iat":...,"exp":...}