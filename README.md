import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="root",
  port="3307",
  database="arunpractice")

def insert (Name,Department,TamilMark,EnglishMark,MathsMark,ScienceMark,ComputerMark,Total,Average,Grade):
    res=mydb.cursor()
    sql="insert into task1 (Name,Department,TamilMark,EnglishMark,MathsMark,ScienceMark,ComputerMark,Total,Average,Grade) values (%s,%s,%s,%s,%s,%s,%s,%s,%s,%s)"
    task1=(Name,Department,TamilMark,EnglishMark,MathsMark,ScienceMark,ComputerMark,Total,Average,Grade)
    res.execute(sql,task1)
    mydb.commit()
    print("Data Inserted")
    
print("1.Add New Student")
print("2.Get Student")
print("3.Get all Student")
print("4.Delete a Student")
print("5.Exit")
n =int(input("Please Enter the below option : "))

if n==1:
        Name = input("Name : ")
        Department = input("Department : ")
        TamilMark = input("TamilMark : ")
        EnglishMark = input("EnglishMark : ")
        MathsMark = input("MathsMark : ")
        ScienceMark = input("ScienceMark : ")
        ComputerMark = input("ComputerMark : ")
else:
        print("Invalid")

c=int(TamilMark) + int(EnglishMark) + int(MathsMark) +int(ScienceMark) + int(ComputerMark)
d = c / 5
Total = int(c)
print("Total :",c)
Average = int(d)
print("Average :",d)
if Average >= 90:
        Grade = "A"
elif Average <= 90:
        Grade = "B"
else:
        Grade = "F"
print("Grade: ",Grade)
insert(Name,Department,TamilMark,EnglishMark,MathsMark,ScienceMark,ComputerMark,Total,Average,Grade)