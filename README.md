
public class Main {
    public static void main(String[] args) {

        // Sample input
        String vehicleNo = "TN01AB1234";
        int floor = 1;
        int slot = 2;
        int minutes = 90;
        double rate = 30.0;

        // Jagged array: different slots on each floor
        String[][] parking = {
            new String[2],
            new String[3],
            new String[4]
        };

        System.out.println("----- INPUT DETAILS -----");
        System.out.println("Vehicle Number: " + vehicleNo);
        System.out.println("Floor Number: " + floor);
        System.out.println("Slot Number: " + slot);
        System.out.println("Duration: " + minutes + " minutes");
        System.out.println("Hourly Rate: Rs " + rate);

        // Validate floor and slot
        if (floor >= 0 && floor < parking.length &&
            slot >= 0 && slot < parking[floor].length) {

            if (parking[floor][slot] == null) {
                parking[floor][slot] = vehicleNo;
                System.out.println("\nVehicle parked successfully.");
            } else {
                System.out.println("\nSlot is already occupied.");
            }

        } else {
            System.out.println("\nInvalid floor or slot.");
        }

        // Calculate parking fee
        int hours = (minutes + 59) / 60;
        double fee = hours * rate;

        System.out.println("\n----- OUTPUT DETAILS -----");
        System.out.println("Vehicle Number: " + vehicleNo);
        System.out.println("Parking Hours: " + hours);
        System.out.println("Parking Fee: Rs " + fee);

    }
}
