<h2>CURD OPERATIONS IN SHELL</h2>

- Open Terminal, and Type `python manage.py shell`.
- Then Type in Terminal `from base.models import student_info` ( base : App Name and student_info: Table Name). --- Same line we have Already Added in a models.py


<h3>1) To Insert Record</h3>
   - Here we have to do all Task in a Shell.

`>>> a = student_info.objects.create(s_name='Rohit',s_add='Wai')`</br>
`>>>`

</br></br>

<h3>2) To Read Records</h3>
</br> - To Read one Record </br>

`>>> a = student_info.objects.get(id=6)` </br>
`>>> a.s_name`

Then it will display the name which has id = 6.

</br>  - To Read Multiple Records

`>>> a = student_info.objects.all()`</br>
`>>> for i in a:`</br>
`...     print(i.s_name)`</br>
`... `</br></br>

Unik</br>      -- All Names are Displayed.
Mady Gaikwad</br>
Rohan</br>
Pranav</br>
Rohit</br></br>


<h3>2) To Update Records</h3>

`>>> u = student_info.objects.get(id=3)`
`>>> u.s_add = 'Dubai'`
`>>> u.save()`
`>>> ` </br></br>

Here we change the address which has id=3. </br></br>

<h3>2) To Delete Records</h3>

`>>> d = student_info.objects.get(id=4)`
`>>> d.delete()`
`(1, {'base.student_info': 1})`     -- It will automatically Generated After Delete then Record, No need to write.
`>>> `

</br></br>
- To Delete Mutltiple Records.

`>>> d = student_info.objects.all()`
`>>> d.delete()`
`(4, {'base.student_info': 4})`
`>>>`  </br></br>
