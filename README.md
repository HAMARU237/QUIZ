# QUIZ
Class Diagram ของโปรแกรม
จากโค้ดที่ให้มา โปรแกรมใช้ แนวคิดเชิงวัตถุ (OOP - Object-Oriented Programming) โดยมีคลาสที่เกี่ยวข้องดังนี้:

Form1: เป็น UI ที่แสดงผลข้อมูลของที่ปรึกษาและนักศึกษา
Advisor: เป็นคลาสตัวแทนอาจารย์ที่ปรึกษา ซึ่งมีรายการของนักศึกษาที่ตนดูแล
Student: เป็นคลาสตัวแทนนักศึกษา ซึ่งเก็บข้อมูลเกี่ยวกับชื่อ, รหัสนักศึกษา, สาขาวิชา และเกรด
Class Diagram
+-------------------+
|     Student      |
+-------------------+
| - FirstName: string |
| - LastName: string  |
| - StudentID: string |
| - Major: string     |
| - Grade: double     |
+-------------------+

+-------------------+
|     Advisor      |
+-------------------+
| - FirstName: string |
| - LastName: string  |
| - Students: List<Student> |
+-------------------+

+-------------------+
|      Form1       |
+-------------------+
| - advisor1: Advisor |
| - advisor2: Advisor |
+-------------------+
| + button1_Click() |
| + button2_Click() |
| + button3_Click() |
| + button4_Click() |
+-------------------+
หลักการเขียนโปรแกรมเชิงวัตถุ (OOP) ที่ใช้
✅ 1. Encapsulation (การห่อหุ้มข้อมูล)
คลาส Student และ Advisor มีตัวแปรที่ใช้เก็บข้อมูลส่วนตัวของนักศึกษาและอาจารย์
โปรแกรมไม่ได้ใช้ private fields และ properties อย่างชัดเจน แต่ยังมีการกำหนดโครงสร้างของข้อมูลให้เป็นสัดส่วน
ข้อมูลของนักศึกษาและอาจารย์ถูกจัดเก็บในอ็อบเจ็กต์ Advisor และ Student ซึ่งช่วยให้โปรแกรมมีการจัดการข้อมูลเป็นระบบ
✅ 2. Abstraction (การซ่อนรายละเอียด)
การใช้งาน คลาส Advisor และ Student ช่วยซ่อนรายละเอียดของการเก็บข้อมูล ทำให้โค้ดที่ Form1 ใช้งานสามารถเข้าถึงข้อมูลได้โดยไม่ต้องรู้ว่าแต่ละอ็อบเจ็กต์ทำงานภายในอย่างไร
button3_Click() ใช้วิธี เรียกใช้ Students ของ Advisor โดยไม่ต้องรู้ว่าข้อมูลนักศึกษาเก็บอย่างไรในคลาส Advisor
✅ 3. Inheritance (การสืบทอด)
โค้ดที่ให้มายัง ไม่มีการใช้การสืบทอด (Inheritance) โดยตรง แต่สามารถพัฒนาได้โดยการสร้างคลาส Person ที่มี FirstName และ LastName เพื่อให้ Student และ Advisor สืบทอดคุณสมบัติแทน
✅ 4. Polymorphism (พหุนาม)
ในโค้ดนี้ยังไม่มีการใช้ Polymorphism อย่างชัดเจน แต่สามารถนำไปใช้ได้ เช่น
การสร้างเมธอด GetFullName() ในคลาส Student และ Advisor
ใช้ Interface หรือ Abstract Class สำหรับ Person และให้ Student กับ Advisor Implement
Class Diagram ของโปรแกรม

#โปรแกรมนี้ใช้หลักการ Object-Oriented Programming (OOP) และมีโครงสร้างของคลาสที่สำคัญดังนี้:
Class Diagram
+-------------------+
|     Student      |
+-------------------+
| - FirstName: string |
| - LastName: string  |
| - StudentID: string |
| - Major: string     |
| - Grade: double     |
+-------------------+

+-------------------+
|     Advisor      |
+-------------------+
| - FirstName: string |
| - LastName: string  |
| - Students: List<Student> |
+-------------------+

+-------------------+
|      Form1       |
+-------------------+
| - advisor1: Advisor |
| - advisor2: Advisor |
+-------------------+
| + button1_Click() |
| + button2_Click() |
| + button3_Click() |
| + button4_Click() |
+-------------------+
หลักการเขียนโปรแกรมเชิงวัตถุ (OOP) ที่ใช้ในโปรแกรมนี้
✅ 1. Encapsulation (การห่อหุ้มข้อมูล)
คลาส Student และ Advisor มีการเก็บข้อมูลเป็น Properties (public get; set;)
แม้จะยังไม่มีการใช้ private fields แต่ Properties ก็ช่วยให้เราสามารถควบคุมการเข้าถึงข้อมูลได้
ควรพิจารณาใช้ private set กับบาง Properties เช่น StudentID เพื่อป้องกันการแก้ไขโดยตรง
✅ 2. Abstraction (การซ่อนรายละเอียดที่ไม่จำเป็น)
ผู้ใช้ Form1 ไม่จำเป็นต้องรู้ว่า Advisor หรือ Student เก็บข้อมูลอย่างไร
โปรแกรมสามารถดึงข้อมูลจาก Advisor.Students และใช้ LINQ จัดเรียงข้อมูลโดยไม่ต้องรู้รายละเอียดของการเก็บข้อมูลภายใน
✅ 3. Inheritance (การสืบทอดคุณสมบัติ)
ปัจจุบัน Student และ Advisor เป็นคลาสแยกกัน โดยไม่มีการสืบทอด
สามารถพัฒนาได้โดยสร้าง Person เป็นคลาสแม่
csharp
คัดลอก
แก้ไข
public class Person
{
    public string FirstName { get; set; }
    public string LastName { get; set; }

    public string GetFullName() => $"{FirstName} {LastName}";
}

public class Student : Person
{
    public string StudentID { get; set; }
    public string Major { get; set; }
    public double Grade { get; set; }
}

public class Advisor : Person
{
    public List<Student> Students { get; set; } = new List<Student>();
}
วิธีนี้ช่วยลดโค้ดซ้ำ (FirstName, LastName ไม่ต้องประกาศซ้ำใน Student และ Advisor)
✅ 4. Polymorphism (พหุนาม)
หากมี Person เป็นคลาสแม่ ก็สามารถใช้ Polymorphism ได้ เช่น
csharp
คัดลอก
แก้ไข
public override string ToString()
{
    return $"{FirstName} {LastName}";
}
หรือสร้าง Interface ให้กับ Advisor และ Student หากต้องการขยายฟังก์ชันในอนาคต
สรุป
Encapsulation: มีการใช้ Properties ห่อหุ้มข้อมูลใน Student และ Advisor
Abstraction: คลาส Form1 ใช้งานข้อมูลโดยไม่ต้องรู้รายละเอียดภายใน
Inheritance (แนะนำให้เพิ่ม): สามารถสร้าง Person เป็นคลาสแม่ให้ Student และ Advisor
Polymorphism (ยังไม่มีแต่สามารถเพิ่มได้): เช่น ใช้ ToString() หรือ Interface
โปรแกรมนี้ใช้ OOP ได้ดี แต่สามารถพัฒนาเพิ่มเติมได้โดยการ ใช้ Inheritance และ Polymorphism ให้มากขึ้น

#
Class Diagram ของโปรแกรม
โปรแกรมนี้ใช้แนวคิด Object-Oriented Programming (OOP) โดยมีโครงสร้างของคลาสที่สำคัญดังนี้:

Class Diagram
+-------------------+
|     Person       |
+-------------------+
| - FirstName: string |
| - LastName: string  |
+-------------------+
| + GetFullName(): string |
+-------------------+

        ▲
        │
+-------------------+
|     Student      |
+-------------------+
| - StudentID: string |
| - Major: string     |
| - Grade: double     |
+-------------------+

        ▲
        │
+-------------------+
|     Advisor      |
+-------------------+
| - Students: List<Student> |
+-------------------+
| + GetTopStudent(): Student |
| + GetSecondStudent(): Student |
+-------------------+

+-------------------+
|      Form1       |
+-------------------+
| - advisor1: Advisor |
| - advisor2: Advisor |
+-------------------+
| + button1_Click() |
| + button2_Click() |
| + button3_Click() |
| + button4_Click() |
+-------------------+
หลักการเขียนโปรแกรมเชิงวัตถุ (OOP) ที่ใช้ในโปรแกรมนี้
✅ 1. Encapsulation (การห่อหุ้มข้อมูล)
ใช้ Properties (public get; set;) เพื่อกำหนดค่าของ Student และ Advisor แทนการใช้ตัวแปรแบบเปิด (public field)
คลาส Advisor มีการจัดการ List<Student> และให้เมธอด GetTopStudent() และ GetSecondStudent() เพื่อคืนค่านักศึกษาที่มีเกรดสูงสุดและรองลงมา
ควรปรับปรุงให้ใช้ private set กับ Students เพื่อลดโอกาสในการเปลี่ยนแปลงค่าจากภายนอก เช่น:
csharp
คัดลอก
แก้ไข
public List<Student> Students { get; private set; } = new List<Student>();
✅ 2. Abstraction (การซ่อนรายละเอียดที่ไม่จำเป็น)
คลาส Advisor ซ่อน ตรรกะของการคำนวณนักศึกษาที่มีเกรดสูงสุด ไว้ในเมธอด GetTopStudent() และ GetSecondStudent()
UI (เช่น Form1) สามารถเรียกใช้งานเมธอดเหล่านี้ได้โดยไม่ต้องรู้ว่า ข้อมูลถูกเก็บอย่างไรใน Advisor
นี่เป็นแนวคิดของ Abstraction ที่ช่วยให้โปรแกรมแยกความรับผิดชอบของแต่ละส่วนได้อย่างชัดเจน
✅ 3. Inheritance (การสืบทอดคุณสมบัติ)
สามารถ ปรับปรุงโค้ดให้ใช้การสืบทอดได้ดียิ่งขึ้น โดยการสร้างคลาส Person เพื่อให้ Student และ Advisor สืบทอดข้อมูลพื้นฐาน เช่น:
csharp
คัดลอก
แก้ไข
public class Person
{
    public string FirstName { get; set; }
    public string LastName { get; set; }

    public string GetFullName() => $"{FirstName} {LastName}";
}

public class Student : Person
{
    public string StudentID { get; set; }
    public string Major { get; set; }
    public double Grade { get; set; }
}

public class Advisor : Person
{
    public List<Student> Students { get; private set; } = new List<Student>();

    public Student GetTopStudent() => Students.OrderByDescending(s => s.Grade).FirstOrDefault();
    public Student GetSecondStudent() => Students.OrderByDescending(s => s.Grade).Skip(1).FirstOrDefault();
}
ประโยชน์ของการทำ Inheritance:
ลดการใช้โค้ดซ้ำ (FirstName, LastName ไม่ต้องประกาศซ้ำใน Student และ Advisor)
สามารถใช้ Person ในกรณีที่ต้องการสร้างคลาสใหม่ที่มีคุณสมบัติคล้ายกัน
✅ 4. Polymorphism (พหุนาม)
หากมีการใช้ Inheritance (Person) ก็สามารถใช้ Polymorphism ได้ เช่น:
Override เมธอด ToString() ในคลาสลูก เช่น:
csharp
คัดลอก
แก้ไข
public override string ToString()
{
    return $"{FirstName} {LastName}";
}
ใช้ Interface หรือ Abstract Class ถ้าต้องการให้ Student และ Advisor มีพฤติกรรมที่กำหนดไว้ร่วมกัน
ตัวอย่างการใช้ Interface:
csharp
คัดลอก
แก้ไข
public interface IFullName
{
    string GetFullName();
}

public class Student : IFullName
{
    public string FirstName { get; set; }
    public string LastName { get; set; }

    public string GetFullName() => $"{FirstName} {LastName}";
}
สรุป
Encapsulation ✅: ใช้ Properties เพื่อเก็บข้อมูลและซ่อนรายละเอียดของคลาส Advisor และ Student
Abstraction ✅: Advisor มีเมธอด GetTopStudent() และ GetSecondStudent() ซึ่งช่วยให้ UI ใช้งานโดยไม่ต้องรู้ตรรกะภายใน
Inheritance ✅ (แนะนำให้เพิ่ม): สามารถสร้าง Person เป็นคลาสแม่ให้ Student และ Advisor
Polymorphism ✅ (ยังไม่มีแต่สามารถเพิ่มได้): ใช้ ToString() หรือ Interface (IFullName)
