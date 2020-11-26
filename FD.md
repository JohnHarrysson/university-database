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

IDnr, code $\rightarrow$ position
**Follows from each course having a waiting list (or none) and knowing the student and course we can see uniquely which position that student have in the waiting list for that course.**

IDnr, code $\rightarrow$ grade
**Follows from knowing the student and course, we can see the grade in that course (if we consider not having done the course $\Rightarrow$ grade U).**

## Questions:
- How to treat the mandatory courses? Since mandatory is not an attribute but a relation in our ER I have not added it as an attribute here. But for example: Say we have a course code and a program name. Then we could say whether the course is mandatory for that program or not. So we could model this as the FD: **code, pName $\rightarrow$ mandatoryProgram** if we would include mandatoryProgram as an attribute.
- How do we handle registered and taken? If we add as attributes, these could create new FD's or make existing ones more sensible. Example: The FD **IDnr, code $\rightarrow$ grade** would work better as not having taken a course should not give a grade U.
- **clName** is still without any FD's. Something I've missed here? This would have much more synergy if we would consider requirements for graduation, but can't see any other use for it.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNzAzMTk3NjEsMTE4Njc4ODk4Myw4ND
M0MTY2NTcsLTM1MTY1ODU3MywtMjAwMDQ2NDE3MiwxMDY4NDQw
NV19
-->