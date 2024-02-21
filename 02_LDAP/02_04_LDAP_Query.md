

An LDAP query is a command that asks a directory service for some information. 

For instance, if you’d like to see which groups a particular user is a part of, you’d submit a query that looks like this:
	(&(objectClass=user)(sAMAccountName=yourUserName)
	(memberof=CN=YourGroup,OU=Users,DC=YourDomain,DC=com))
	
1 现在不用再手写  LDAP queries.
To maintain your sanity, you’ll perform all your directory services tasks through 
1 a point-and-click management interface like Varonis DatAdvantage or 
2 using a command line shell like PowerShell that abstracts away the details of the raw LDAP protocol.


