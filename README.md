# feereport
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

class Student {
    private String name;
    private int rollNumber;
    private double feePaid;

    public Student(String name, int rollNumber, double feePaid) {
        this.name = name;
        this.rollNumber = rollNumber;
        this.feePaid = feePaid;
    }

    public String getName() {
        return name;
    }

    public int getRollNumber() {
        return rollNumber;
    }

    public double getFeePaid() {
        return feePaid;
    }

    public void setFeePaid(double feePaid) {
        this.feePaid = feePaid;
    }
}

class School {
    private String name;
    private List<Student> students;

    public School(String name) {
        this.name = name;
        this.students = new ArrayList<>();
    }

    public void addStudent(Student student) {
        students.add(student);
    }

    public void generateFeeReport() {
        System.out.println("Fee Report for " + name + "\n");

        for (Student student : students) {
            System.out.println("Name: " + student.getName());
            System.out.println("Roll Number: " + student.getRollNumber());
            System.out.println("Fee Paid: $" + student.getFeePaid());
            System.out.println("-------------------------");
        }
    }
}

public class FeeReportProject {
    public static void main(String[] args) {
        School school = new School("XYZ School");

        // Create student objects and add them to the school
        Student student1 = new Student("John Doe", 1, 500.0);
        Student student2 = new Student("Jane Smith", 2, 750.0);
        Student student3 = new Student("Michael Johnson", 3, 1000.0);

        school.addStudent(student1);
        school.addStudent(student2);
        school.addStudent(student3);

        // Update fee payment for a student
        student1.setFeePaid(600.0);

        // Generate fee report
        school.generateFeeReport();
    }
}
