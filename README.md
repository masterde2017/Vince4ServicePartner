Vince4ServicePartner Demo
==================

The project is based on framework SpringMVC and Jersey, REST API using spring security oauth2

when starting the project, Hibernate will load the data of import_data.sql into the local database
the data is only for the test of retrieving data through controller
As we can see form the RestClient class, we can make several requests for test as below:

1  Direct Request:    http://localhost:8080/Vince4ServicePartner/test/{userName}
----------------------------
 Making request to the controller directly will fail, resulted 401 Unauthorized


2  Get token object by userName and password
----------------------------
Request:
http://localhost:8080/Vince4ServicePartner/oauth/token?grant_type=password&client_id=client_vince_id&client_secret=secret&username=user_vince&password=password

Failed Request would result in: 401 Unauthorized

Successful Result:

{
 access_token:"542aab03-cedf-41cf-9043-79ae83c2cec7" 
 token_type:"bearer"
 refresh_token:"c8a7922e-98fc-420c-a846-706ab91536c2"
 expires_in:99
 scope:"read trust write"
}

3  Getting Protected Resource (using access_token from step 2)
------------------

HTTPHeaders:  "Authorization: Bearer 542aab03-cedf-41cf-9043-79ae83c2cec7"

Request:
   http://localhost:8080/Vince4ServicePartner/test/user_vince?access_token=542aab03-cedf-41cf-9043-79ae83c2cec7

Successful Result (Json Object):

{name=user_vince}



