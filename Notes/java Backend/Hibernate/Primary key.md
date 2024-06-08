## Generatedvalue
- it has attribute strategy , where we specify how the automatic creation of PK will be done , do Generationtype.IDENTITY for serialised increase
## Creating custom primary key
- class that implements Identifier generator , it has one method generate , provide its implementation
- ![](../../statics/Pasted%20image%2020240608115451.png)

## Composite primary key
- the case where more than one column is the primary key 
- we can do it by creating a separate class containing feilds that are primary key  it implements serizable, 
- ![](../../statics/Pasted%20image%2020240608120150.png)
- note the idclass annotation and id annotation on each field
- other approach is to create class having primary keys and annotate it with embeddable , also now in entity , inject instance of the composite key class and annotate it with embeddedid, instead of writing all the fields 