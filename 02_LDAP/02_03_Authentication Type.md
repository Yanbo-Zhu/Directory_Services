Delegated authentication 验证： to found who it is , check the id
LDAP  authorization 授权 ： what they can do

There are two options for LDAP authentication in LDAP v3
- simple
- SASL (Simple Authentication and Security Layer).

# 1 Simple
Simple authentication allows for three possible authentication mechanisms:

![](image/Pasted%20image%2020240221123854.png)

- Anonymous authentication: Grants client anonymous status to LDAP.
- Unauthenticated authentication: For logging purposes only, should not grant access to a client.
- Name/Password authentication: Grants access to the server based on the credentials supplied – simple user/pass authentication is not secure and is not suitable for authentication without confidentiality protection.

# 2 SASL
SASL authentication allow the client and server to negoitiate a particular authentication mechanism   (不再是 Useraccount 和 password 的方式 )
SASL authentication binds the LDAP server to another authentication mechanism, like Kerberos.
The LDAP server uses the LDAP protocol to send an LDAP message to the other authorization service.
That initiates a series of challenge response messages that result in either a successful authentication or a failure to authenticate.




