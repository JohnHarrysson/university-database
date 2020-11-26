# Everything taken from domain description

Domain ( R ) = {dName, dAbbreviation, pName, pAbbreviation, bName, IDnr, sName, login, grade, credit, code, coName, capacity, position, clName}

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

coCode


## Questions:
- I

<!--stackedit_data:
eyJoaXN0b3J5IjpbODA1NDQ0OTA4LDEwNjg0NDA1XX0=
-->