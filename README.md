if (locale.getCountry().equals("IN")) {

    NumberFormat nf = NumberFormat.getCurrencyInstance(new Locale("en", "IN"));
    System.out.println("Salary : " + nf.format(1000000));

} else {

    NumberFormat nf = NumberFormat.getCurrencyInstance(locale);
    System.out.println("Salary : " + nf.format(1000000));

}




app=Java Resource Bundle Demo
welcome=Welcome!
greeting=Hope you are having a wonderful day.
language=English
country=India
thankyou=Thank you for watching the demo.
goodbye=Have a Nice Day!


app=Java Resource Bundle Demo
welcome=Welcome!
greeting=Hope you are having a wonderful day.
language=English
country=India
thankyou=Thank you for watching the demo.
goodbye=Have a Nice Day!

app=\u091C\u093E\u0935\u093E \u0930\u093F\u0938\u094B\u0930\u094D\u0938 \u092C\u0902\u0921\u0932 \u0921\u0947\u092E\u094B
welcome=\u0938\u094D\u0935\u093E\u0917\u0924 \u0939\u0948
greeting=\u0906\u092A\u0915\u093E \u0926\u093F\u0928 \u092E\u0902\u0917\u0932\u092E\u092F \u0939\u094B
language=\u0939\u093F\u0928\u094D\u0926\u0940
country=\u092D\u093E\u0930\u0924
thankyou=\u0921\u0947\u092E\u094B \u0926\u0947\u0916\u0928\u0947 \u0915\u0947 \u0932\u093F\u090F \u0927\u0928\u094D\u092F\u0935\u093E\u0926
goodbye=\u0906\u092A\u0915\u093E \u0926\u093F\u0928 \u0936\u0941\u092D \u0939\u094B

app=Démonstration Java Resource Bundle
welcome=Bienvenue !
greeting=Nous sommes heureux de vous accueillir.
language=Français
country=France
thankyou=Merci d'avoir regardé cette démonstration.
goodbye=Bonne journée !



package pkg1;

import java.text.DateFormat;
import java.text.NumberFormat;
import java.time.ZoneId;
import java.time.ZonedDateTime;
import java.time.format.DateTimeFormatter;
import java.util.Date;
import java.util.Locale;
import java.util.ResourceBundle;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.println("========================================");
        System.out.println("     JAVA RESOURCE BUNDLE DEMO");
        System.out.println("========================================");

        System.out.println("Choose Language");
        System.out.println("1. English");
        System.out.println("2. Hindi");
        System.out.println("3. French");

        int choice = sc.nextInt();

        Locale locale;

        switch (choice) {

        case 2:
            locale = new Locale("hi", "IN");
            break;

        case 3:
            locale = Locale.FRANCE;
            break;

        default:
            locale = new Locale("en", "IN");
        }

        ResourceBundle bundle = ResourceBundle.getBundle("pkg1.message", locale);

        System.out.println("\n========================================");
        System.out.println(bundle.getString("app"));
        System.out.println("========================================");

        System.out.println(bundle.getString("welcome"));
        System.out.println(bundle.getString("greeting"));

        System.out.println();

        System.out.println("Language : " + bundle.getString("language"));
        System.out.println("Country  : " + bundle.getString("country"));

        System.out.println();

        Date today = new Date();

        DateFormat df = DateFormat.getDateInstance(DateFormat.FULL, locale);

        System.out.println("Today's Date : " + df.format(today));

        NumberFormat nf = NumberFormat.getCurrencyInstance(locale);

        System.out.println("Salary : " + nf.format(50000));

        System.out.println();

        DateTimeFormatter formatter =
                DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss");

        System.out.println("Current Time in Different Time Zones");

        System.out.println("--------------------------------------");

        System.out.println("India   : "
                + ZonedDateTime.now(ZoneId.of("Asia/Kolkata"))
                        .format(formatter));

        System.out.println("USA     : "
                + ZonedDateTime.now(ZoneId.of("America/New_York"))
                        .format(formatter));

        System.out.println("France  : "
                + ZonedDateTime.now(ZoneId.of("Europe/Paris"))
                        .format(formatter));

        System.out.println();

        System.out.println(bundle.getString("thankyou"));
        System.out.println(bundle.getString("goodbye"));

        sc.close();
    }

}
