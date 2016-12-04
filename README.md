# Third_Question

To solve this question I have used Hive.

In this question we required to get the employees old department, old desgnation, new department, new designation.

To get this I have used below query :
hive> INSERT OVERWRITE LOCAL DIRECTORY '/home/vishal/Downloads/Third_question_csv' SELECT de.emp_no,d.dept_name,t.title,e.first_name,e.last_name,de.from_date,de.to_date FROM dept_emp as de left join departments d on(d.dept_no = de.dept_no) left join employees e on (de.emp_no = e.emp_no ) LEFT JOIN titles t  on (t.emp_no = e.emp_no) WHERE e.emp_no IN (SELECT emp_no FROM dept_emp GROUP BY emp_no HAVING COUNT(*) >1) ORDER BY de.emp_no,de.from_date;

Using Abive query I got the emp id , name of emp name, old designation, old department and new department new designation and I have strored this result in CSV format in mentioned path.

Please find below files with descriptions:
List of files:
Execution Process : This is the file which shows the process followed for the output.
Third_question_csv : This directory is gernated as output of the hive query and the result of hive query stored into Third_question_csv->000000_0 file.




