
# 1 总览

ADs are structured around Root, domains, trees, and forests.

- At the lowest level, domains contain sets of objects. Domains are defined as a logical group of network objects, such as computers, devices, or users, that share the same AD database.
- At the middle level, trees are hierarchical collections of one or more domains.
- And at the highest level, forests are hierarchical groupings of trees that share the same global catalog and directory schema.

This hierarchical structure often mirrors the structure of the company or organization the AD serves.

![](image/Pasted%20image%2020240221124143.png)


One Person can belong to different groups : 
![](image/Pasted%20image%2020240221124206.png)

如何 call a persion， 使用 groups of UniqueName：
![](image/Pasted%20image%2020240221124215.png)

![](image/Pasted%20image%2020240221124221.png)


![](image/Pasted%20image%2020240221124228.png)



# 2 例子

![](image/Pasted%20image%2020240221140322.png)


![](image/Pasted%20image%2020240221140925.png)



# 3 Understanding Inter-site & inra-site replication in AS Site & Services 
NTDS: Windows NT Directory Services

![](image/Pasted%20image%2020240221144953.png)

Site： 
![](image/Pasted%20image%2020240221144746.png)


Site 中的 Servers 
![](image/Pasted%20image%2020240221145013.png)


## 3.1 create a new site

![](image/Pasted%20image%2020240221145253.png)





