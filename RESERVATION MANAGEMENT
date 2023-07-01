import java.util.ArrayList;
import java.util.List;
class Reservation {
    private String reservationId;
    private String passengerName;
    private String flightNumber;
    private String seatNumber;
    private boolean isConfirmed;

    public Reservation(String reservationId, String passengerName, String flightNumber, String seatNumber) {
        this.reservationId = reservationId;
        this.passengerName = passengerName;
        this.flightNumber = flightNumber;
        this.seatNumber = seatNumber;
        this.isConfirmed = false;
    }

    public String getReservationId() {
        return reservationId;
    }

    public String getPassengerName() {
        return passengerName;
    }

    public String getFlightNumber() {
        return flightNumber;
    }

    public String getSeatNumber() {
        return seatNumber;
    }

    public boolean isConfirmed() {
        return isConfirmed;
    }

    public void confirmReservation() {
        isConfirmed = true;
    }

    public void cancelReservation() {
        isConfirmed = false;
    }

    @Override
    public String toString() {
        return "Reservation ID: " + reservationId +
                ", Passenger Name: " + passengerName +
                ", Flight Number: " + flightNumber +
                ", Seat Number: " + seatNumber +
                ", Confirmation Status: " + (isConfirmed ? "Confirmed" : "Not Confirmed");
    }
}

class ReservationManager {
    private List<Reservation> reservations;

    public ReservationManager() {
        reservations = new ArrayList<>();
    }

    public void addReservation(Reservation reservation) {
        reservations.add(reservation);
    }

    public void confirmReservation(String reservationId) {
        for (Reservation reservation : reservations) {
            if (reservation.getReservationId().equals(reservationId)) {
                reservation.confirmReservation();
                System.out.println("Reservation with ID: " + reservationId + " is confirmed.");
                return;
            }
        }
        System.out.println("Reservation with ID: " + reservationId + " not found.");
    }

    public void cancelReservation(String reservationId) {
        for (Reservation reservation : reservations) {
            if (reservation.getReservationId().equals(reservationId)) {
                reservation.cancelReservation();
                System.out.println("Reservation with ID: " + reservationId + " is cancelled.");
                return;
            }
        }
        System.out.println("Reservation with ID: " + reservationId + " not found.");
    }

    public void viewAllReservations() {
        if (reservations.isEmpty()) {
            System.out.println("No reservations found.");
        } else {
            System.out.println("All Reservations:");
            for (Reservation reservation : reservations) {
                System.out.println(reservation.toString());
            }
        }
    }
}

public class ReservationManagementSystem {
    public static void main(String[] args) {
        ReservationManager reservationManager = new ReservationManager();

        // Adding sample reservations
        Reservation reservation1 = new Reservation("001", "Sony", "CDA211", "B1");
        Reservation reservation2 = new Reservation("002", "Loukya", "NUH321", "D3");
        reservationManager.addReservation(reservation1);
        reservationManager.addReservation(reservation2);

        // Confirming and cancelling reservations
        reservationManager.confirmReservation("001");
        reservationManager.cancelReservation("002");

        // Viewing all reservations
        reservationManager.viewAllReservations();
    }
}
