Oauth 2 Demo
==================


Oauth2 get token object
----------------------------
```java
http://localhost:8080/Vince4ServicePartner/oauth/token?grant_type=password&client_id=client_vince_id&client_secret=secret&username=user_vince&password=password
```

```java
{
 access_token:"542aab03-cedf-41cf-9043-79ae83c2cec7" 
 token_type:"bearer"
 refresh_token:"c8a7922e-98fc-420c-a846-706ab91536c2"
 expires_in:99
 scope:"read trust write"
}
```

Protected Resource
------------------
http://localhost:8080/Vince4ServicePartner/test/user_vince?access_token=542aab03-cedf-41cf-9043-79ae83c2cec7