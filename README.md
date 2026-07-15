package calculator;

public class ScientificCalculator {

    public double square(double n) {
        return n * n;
    }

    public double cube(double n) {
        return n * n * n;
    }
}


package app;

import calculator.Calculator;
import calculator.ScientificCalculator;

public class Main {

    public static void main(String[] args) {

        Calculator c = new Calculator();

        ScientificCalculator s = new ScientificCalculator();

        System.out.println("Addition = " + c.add(20,10));
        System.out.println("Multiplication = " + c.multiply(20,10));

        System.out.println("Square = " + s.square(5));

        System.out.println("Cube = " + s.cube(3));
    }

}
