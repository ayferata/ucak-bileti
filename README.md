# ucak-bileti
import java.util.Scanner;
public class Main {
    public static void main (String[]args) {
        int mesafe, yas, tip;
        double yasİndirimOrani;
        Scanner inp = new Scanner(System.in);

        System.out.println("yaşınız: ");
        yas = inp.nextInt();

        System.out.println("Güzergah: ");
        mesafe = inp.nextInt();

        System.out.println("Tek yön ise 1 çift yön ise 2 giriniz");
        tip = inp.nextInt();
        if ((mesafe > 0) && (yas > 0) && (tip == 1 || tip == 2)) {

            if (yas < 12) {
                yasİndirimOrani = 0.50;

            } else if (yas > 12 && yas < 24) {
                yasİndirimOrani = 0.10;

            } else if (yas > 65) {
                yasİndirimOrani = 0.30;

            } else {
                yasİndirimOrani = 0;
            }
            double normalTutar = mesafe * 0.10;
            double yasİndirimi = normalTutar * yasİndirimOrani;
            double indirimliTutar = normalTutar - yasİndirimi;
            double toplamTutar;
            if (tip == 2) {

                double gidisDonusİndirimi = indirimliTutar * 0.20;
                toplamTutar = (indirimliTutar - gidisDonusİndirimi) * 2;
            } else {
                toplamTutar = indirimliTutar;
            }
            System.out.println("Toplam Tutar : " + toplamTutar);
        } else {
            System.out.println(" Hatalı ");}

        }
    }
