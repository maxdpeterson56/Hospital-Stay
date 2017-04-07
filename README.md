# Hospital-Stay
* Program used to determine the total cost of medications based on customer input. 
/*
 * This challenge computes and displays the total charges for a hospital stay
 * The patient might be admitted overnight.  For an overnight stay, we need: 
 *   The number of days spent in the hospital
 *   The daily rate
 *   Medication charges
 *   Lab service charges
 * If it is not overnight, we only need: 
 *   Medication charges
 *   Lab service charges
 */
package hospitalstay;
import java.util.Scanner;
/**
 *
 * @author Max Peterson
 */
public class HospitalStay {

    /**
     */
    public static void main(String[] args) {
    Scanner in = new Scanner(System.in);    
    double overnightStay, medication, lab, totalCharges;
    String response = "";
    do {
     if (checkForOvernight() == true)   
            {
                System.out.println("What are the overnight stay charges?");
                overnightStay = in.nextDouble();
            }
            else 
            {
                overnightStay = 0;
            }
    System.out.println("What are the medication charges?");
    medication = in.nextDouble();
    System.out.println ("What are the lab charges?");
    lab = in.nextDouble();
    totalCharges = overnightStay + medication + lab;
    System.out.printf("The total charges for an overnight stay are: $%5.2f", totalCharges);
    System.out.println();
    System.out.println();
    System.out.println("Do you have another patient (y/n)");
    response = in.next();
    } while (response.equalsIgnoreCase ("y"));
           
    }
    public static boolean checkForOvernight ()
    {
        Scanner in = new Scanner (System.in);
        String response = "";
        System.out.println("Is this an overnight stay? (y/n) ");
        response = in.next();
        if (response.equalsIgnoreCase("y"))
            return true;
        else
            return false;
        
    }
    
}
