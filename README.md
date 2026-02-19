// Abstract class demonstrating Abstraction
abstract class Person {
    protected String name;

    public Person(String name) {
        this.name = name;
    }

    // Abstract method to be implemented by subclasses
    public abstract void displayDetails();
}

// Student class demonstrating Inheritance, Encapsulation, and Polymorphism
class Student extends Person {
    private int studentId;
    private int marks;
    private Course course;

    public Student(int studentId, String name, int marks, Course course) {
        super(name);
        this.studentId = studentId;
        this.marks = marks;
        this.course = course;
    }

    // Encapsulation: Getters and Setters
    public int getStudentId() { return studentId; }
    public void setStudentId(int studentId) { this.studentId = studentId; }

    public int getMarks() { return marks; }
    public void setMarks(int marks) { this.marks = marks; }

    public Course getCourse() { return course; }
    public void setCourse(Course course) { this.course = course; }

    // Grade calculation
    public String getGrade() {
        if (marks >= 70) return "A";
        else if (marks >= 60) return "B";
        else if (marks >= 50) return "C";
        else return "Fail";
    }

    // Polymorphism: Overriding abstract method
    @Override
    public void displayDetails() {
        System.out.println("ID: " + studentId);
        System.out.println("Name: " + name);
        System.out.println("Course: " + course.getCourseName());
        System.out.println("Marks: " + marks);
        System.out.println("Grade: " + getGrade());
    }
}

// Course class
class Course {
    private String courseName;

    public Course(String courseName) {
        this.courseName = courseName;
    }

    public String getCourseName() { return courseName; }
    public void setCourseName(String courseName) { this.courseName = courseName; }
}

// Main Application class
public class Main {
    public static void main(String[] args) {
        Course course1 = new Course("Computer Science");
        Student student1 = new Student(101, "Alice", 75, course1);

        Course course2 = new Course("Mathematics");
        Student student2 = new Student(102, "Bob", 55, course2);

        // Display student details
        student1.displayDetails();
        System.out.println("-------------------");
        student2.displayDetails();
    }
}
