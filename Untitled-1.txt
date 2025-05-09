import java.util.*;

class Student {
    private String name;
    private String program;
    private int semester;
    private Map<String, Integer> courses; // Course Name -> Marks

    public Student(String name, String program, int semester) {
        this.name = name;
        this.program = program;
        this.semester = semester;
        this.courses = new HashMap<>();
    }

    public void registerCourse(String courseName, int marks) {
        courses.put(courseName, marks);
    }

    public void displayStudentDetails() {
        System.out.println("Student Name: " + name);
        System.out.println("Program: " + program);
        System.out.println("Semester: " + semester);
        System.out.println("Registered Courses: " + courses.keySet());
    }

    public void displayLowMarks() {
        System.out.println("Courses with Marks Below 40:");
        for (Map.Entry<String, Integer> entry : courses.entrySet()) {
            if (entry.getValue() < 40) {
                System.out.println(entry.getKey() + " - " + entry.getValue());
            }
        }
    }

    public static void main(String[] args) {
        Student student = new Student("John Doe", "Computer Science", 3);
        student.registerCourse("Mathematics", 75);
        student.registerCourse("Physics", 35);
        student.registerCourse("Chemistry", 90);
        student.registerCourse("History", 28);

        student.displayStudentDetails();
        student.displayLowMarks();
    }
}