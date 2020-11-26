# Everything taken from domain description

Domain ( R ) = {dName, dAbbreviation, pName, pAbbreviation, bName, IDnr, sName, login, grade, credit, code, coName (course name), capacity, position, clName (classification name)}

## FD's determined from domain description
dName $\rightarrow$ dAbbreviation
dAbbreviation $\rightarrow$ dName
**Follows from uniqueness of department attributes**

pName $\rightarrow$ pAbbreviation
**Follows from uniqueness of pName. Opposite is not true, as two abbreviations with the same name could point at two different programs.**

IDnr $\rightarrow$ sName, login
login $\rightarrow$ IDnr, sName(by reference)
**Follows from key constraint on IDnr and uniqueness of login**

IDnr $\rightarrow$ pName, pAbbreviation(by reference), *bName*
**Follows from student always part of program and must choose a single branch within that program.**

code $\rightarrow$ coName, credit, capacity, dName, dAbbreviation
**Follows from uniqueness of course code. For dName/dAbbreviation it follows from a course being given by one and only one department.**



## Questions:
- How to treat the mandatory courses? Since mandatory is not an attribute but a relation in our ER I have not added it as an attribute here. But for example: Say we have a course code and a program name. Then we could say whether the course is mandatory for that program or not. So we could model this as the FD: code, pName $\rightarrow$ mandatoryProgram if we would include mandatoryProgram as an attribute.
- How do we define *capacity*? **Option 1**: static definition, the nr of places the course have in total. Example: course CS101 have a capacity of 50 students. **Option 2**: dynamic definition, the nr of places left in the course. Example: course CS101 have 5 places left until it is full.

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ2Njc3NTg5LC0zNTE2NTg1NzMsLTIwMD
A0NjQxNzIsMTA2ODQ0MDVdfQ==
-->