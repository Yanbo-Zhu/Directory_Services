
# 1 bindDN

[https://serverfault.com/questions/616698/in-ldap-what-exactly-is-a-bind-dn](https://serverfault.com/questions/616698/in-ldap-what-exactly-is-a-bind-dn)

A bind DN is an object that you bind to inside LDAP to give you permissions to do whatever you're trying to do. Some (many?) LDAP instances don't allow anonymous binds, or don't allow certain operations to be conducted with anonymous binds, so you must specify a bindDN to obtain an identity to perform that operation.

In a similar non-technical way - and yes this is a stretch - a bank will allow you to walk in and look at their interest rates without giving them any sort of ID, but in order to open an account or withdraw money, you have to have an identity they know about - that identity is the bindDN.

the bindDN always correspond to a node in the directory:

It must correspond to a node that has the capability of carrying a password attribute or otherwise being authenticated against


## 1.1 例子

[https://serverfault.com/questions/616698/in-ldap-what-exactly-is-a-bind-dn](https://serverfault.com/questions/616698/in-ldap-what-exactly-is-a-bind-dn)

Now, the string dc=example,dc=com is not the best example for a bindDN as it is a "domain" for an LDAP tree.

dc stands for domain component and every LDAP tree defines its root with a string in the form of dc=string,dc=string,... But these strings are NOT a "path" like the rest of the tree.

Valid examples are:
dc=example,dc=com
dc=mydomain
dc=avery,dc=long,dc=list,dc=of,dc=domains

But, these root elements are indivisible. Although they look like they might be several elements representing a path like the rest of the tree, but they are not. (So for these elements the comma "," is NOT an element separator.)

So for the `dc=avery,dc=long,dc=list,dc=of,dc=domains `example this means that this is the entire element name.

It it is NOT a path of elements. It can NOT be broken down into sub elements: There IS NO object dc=of,dc=domains.


# 2 To make an analogy to file system paths: 
和 file 类比

Imagine naming your C: drive like `D:\my\folder\.`

Every path in there will look something like `D:\my\folder\my\real\path` which would be confusing as the real file path would be `\my\real\path` right?

就是说 我们用 c: 代表 `D:\my\folder\`
则 D:\my\folder\my\real\path 他的 dn 为 ： `dc=D:\my\folder\, dc =my\real\path`

Well, that is the way the base (root) of an LDAP looks like, with a set of dc= elements.
Relevant link: Oracle documentation: "The ldapsearch Tool" [http://docs.oracle.com/cd/E19199-01/816-6400-10/lsearch.html](http://docs.oracle.com/cd/E19199-01/816-6400-10/lsearch.html)

# 3 between the baseDN and the bindDN.

[https://serverfault.com/questions/616698/in-ldap-what-exactly-is-a-bind-dn](https://serverfault.com/questions/616698/in-ldap-what-exactly-is-a-bind-dn)

The baseDN of a search is the starting point. Where it will start searching. Pretty self-explanatory.
The bindDN is basically the credential you are using to authenticate against an LDAP.

When using a bindDN it usually comes with a password associated with it.

In other words when you specify a bindDN you are using that object security access to go through the LDAP tree.


