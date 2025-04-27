# Equals_HashCode_Override

    import java.util.Objects;
    
    public class Employee {
        private int id;
        private String name;
        private String department;

    // Constructor
    public Employee(int id, String name, String department) {
        this.id = id;
        this.name = name;
        this.department = department;
    }

    // Override equals
    @Override
    public boolean equals(Object o) {
        if (this == o) return true;          // same object
        if (o == null || getClass() != o.getClass()) return false; // not same type
        Employee employee = (Employee) o;    // cast
        return id == employee.id &&
                Objects.equals(name, employee.name) &&
                Objects.equals(department, employee.department);
    }

    // Override hashCode
    @Override
    public int hashCode() {
        return Objects.hash(id, name, department);
    }
    }
