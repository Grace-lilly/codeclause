import java.util.*;

class Movie {
    private String title;
    private int duration;
    private String rating;

    public Movie(String title, int duration, String rating) {
        this.title = title;
        this.duration = duration;
        this.rating = rating;
    }

    // Getters and setters
}

class Seat {
    private int row;
    private int seatNumber;
    private boolean available;

    public Seat(int row, int seatNumber, boolean available) {
        this.row = row;
        this.seatNumber = seatNumber;
        this.available = available;
    }

    // Getters and setters
}

class Theater {
    private String name;
    private int rows;
    private int seatsPerRow;
    private Seat[][] seats;

    public Theater(String name, int rows, int seatsPerRow) {
        this.name = name;
        this.rows = rows;
        this.seatsPerRow = seatsPerRow;
        this.seats = new Seat[rows][seatsPerRow];
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < seatsPerRow; j++) {
                seats[i][j] = new Seat(i+1, j+1, true);
            }
        }
    }

    public void displaySeatingChart() {
        System.out.println("Seating Chart:");
        for (Seat[] row : seats) {
            for (Seat seat : row) {
                System.out.print(seat.isAvailable() ? "O " : "X ");
            }
            System.out.println();
        }
    }
}

class BookingSystem {
    private List<Movie> movies;
    private Theater theater;

    public BookingSystem() {
        this.movies = new ArrayList<>();
        this.theater = new Theater("Cinema City", 10, 10); // Example theater with 10 rows and 10 seats per row
    }

    // Methods for booking tickets, selecting movies, choosing seats, etc.
}

public class Main {
    public static void main(String[] args) {
        BookingSystem bookingSystem = new BookingSystem();
        bookingSystem.theater.displaySeatingChart(); // Test output for displaying seating chart
    }
}
