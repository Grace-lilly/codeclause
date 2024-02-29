import java.util.*;

class Patient {
    private String name;
    private int age;
    private String gender;
    private String address;
    private String phoneNumber;
    private String medicalHistory;

    public Patient(String name, int age, String gender, String address, String phoneNumber, String medicalHistory) {
        this.name = name;
        this.age = age;
        this.gender = gender;
        this.address = address;
        this.phoneNumber = phoneNumber;
        this.medicalHistory = medicalHistory;
    }
}

class Appointment {
    private Patient patient;
    private Date date;
    private String doctorName;
    private String purpose;

    public Appointment(Patient patient, Date date, String doctorName, String purpose) {
        this.patient = patient;
        this.date = date;
        this.doctorName = doctorName;
        this.purpose = purpose;
    }
}

class Hospital {
    private List<Patient> patients;
    private List<Appointment> appointments;

    public Hospital() {
        this.patients = new ArrayList<>();
        this.appointments = new ArrayList<>();
    }

    public void addPatient(Patient patient) {
        patients.add(patient);
    }

    public void scheduleAppointment(Appointment appointment) {
        appointments.add(appointment);
    }
}

public class Main {
    public static void main(String[] args) {
        Hospital hospital = new Hospital();

        Patient patient1 = new Patient("John Doe", 35, "Male", "123 Main St", "123-456-7890", "None");
        hospital.addPatient(patient1);

        Date appointmentDate = new Date();
        Appointment appointment1 = new Appointment(patient1, appointmentDate, "Dr. Smith", "Routine Checkup");
        hospital.scheduleAppointment(appointment1);

        // Implement user interaction and interface here
    }
}
