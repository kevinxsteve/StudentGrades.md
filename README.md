# StudentGrades.md
Database with Entities Student, Enrollment, Class
## Er Diagram on https://mermaid-js.github.io/mermaid-live-editor/#/
```Er
erDiagram
    
    Student ||--o{ Enrollment : has
    Enrollment o{ -- || Class: has
    
    Enrollment{
        int grade
    }

    Student {
        string name
        string email
        string phoneNumber
        boolean isReleased
    }

    Class {
       string name
       string hours 
    }
```
[![](https://mermaid.ink/img/eyJjb2RlIjoiZXJEaWFncmFtXG4gICAgXG4gICAgU3R1ZGVudCB8fC0tb3sgRW5yb2xsbWVudCA6IGhhc1xuICAgIEVucm9sbG1lbnQgb3sgLS0gfHwgQ2xhc3M6IGhhc1xuICAgIFxuICAgIEVucm9sbG1lbnR7XG4gICAgICAgIGludCBncmFkZVxuICAgIH1cblxuICAgIFN0dWRlbnQge1xuICAgICAgICBzdHJpbmcgbmFtZVxuICAgICAgICBzdHJpbmcgZW1haWxcbiAgICAgICAgc3RyaW5nIHBob25lTnVtYmVyXG4gICAgICAgIGJvb2xlYW4gaXNSZWxlYXNlZFxuICAgIH1cblxuICAgIENsYXNzIHtcbiAgICAgICBzdHJpbmcgbmFtZVxuICAgICAgIHN0cmluZyBob3VycyBcbiAgICB9XG5cbiAgIiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)](https://mermaid-js.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoiZXJEaWFncmFtXG4gICAgXG4gICAgU3R1ZGVudCB8fC0tb3sgRW5yb2xsbWVudCA6IGhhc1xuICAgIEVucm9sbG1lbnQgb3sgLS0gfHwgQ2xhc3M6IGhhc1xuICAgIFxuICAgIEVucm9sbG1lbnR7XG4gICAgICAgIGludCBncmFkZVxuICAgIH1cblxuICAgIFN0dWRlbnQge1xuICAgICAgICBzdHJpbmcgbmFtZVxuICAgICAgICBzdHJpbmcgZW1haWxcbiAgICAgICAgc3RyaW5nIHBob25lTnVtYmVyXG4gICAgICAgIGJvb2xlYW4gaXNSZWxlYXNlZFxuICAgIH1cblxuICAgIENsYXNzIHtcbiAgICAgICBzdHJpbmcgbmFtZVxuICAgICAgIHN0cmluZyBob3VycyBcbiAgICB9XG5cbiAgIiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)
  
# SQL code
## Create Tables
```SQL
create table students(
  student_id integer primary key, email text not null unique, 
  phone_number text not null unique, 
  is_released boolean
);

```
```SQL
create table enrollments(
  enrollment_id integer primary key, 
  enrollment_grade integer, 
  student_id integer not null, 
  foreign key (student_id) references students (student_id)
);

```
```SQL
create table classes(
  class_id integer primary key, 
  class_name text not null unique, 
  class_hours text not null, 
  enrollment_id integer not null, 
  foreign key (enrollment_id) references enrollments(enrollment_id)
);

```
## Insert Values
```SQL
insert into students(email,phone_number,is_released)
values
("kevin@mail.com","+1-202-555-0148 ",True),
("david@gmail.de","+1-202-555-0130",True),
("Tim@gmail.de","+1-202-555-0164",True),
("Pascal@mail.de","+1-202-555-0100",True),
("dielara@kanake.pop","+1-202-555-0154",False);
```
```SQL
insert into enrollments(enrollment_grade, student_id) 
values
(1,2),
(6,2),
(3,3),
(3,4),
(2,5);
```
```SQL
insert into classes(class_name,class_hours,enrollment_id)
values
("Finance","",1),
("Accounting","",2),
("Sport","",3),
("Politics","",4),
("Acting","",5);
```
## query
```SQL
select 
  student_id, email, enrollment_grade, class_name 
from classes 
  join enrollments using (enrollment_id) 
  join students using(student_id)
  order by student_id;
```
```TABLE
student_id    email              enrollment_grade      class_name
2	        david@gmail.de	        1	                Finance
2       	david@gmail.de	        6	                Accounting
3       	Tim@gmail.de	        3	                Sport
4	        Jeremy-Pascal@mail.de	3	                Politics
5	        dielara@kanake.pop	    2               	Acting
```
