/*
1. Crie um programa para calcular o salário dos funcionários de uma empresa. O salário é baseado no valor hora e quantidade de horas trabalhadas no mês. Porém, para algumas funções existe uma bonificação. Para os líderes, o salário é incrementado em 2% e para os gerentes em 5%. Desenvolva o diagrama de classe da UML.
*/
import java.util.Scanner;

class Employee {
    protected String name;
    protected double hourlyRate;
    protected int hoursWorked;

    public Employee(double hourlyRate, int hoursWorked) {
        this.hourlyRate = hourlyRate;
        this.hoursWorked = hoursWorked;
    }

    // calcular o salário base
    public double calculateBaseSalary() {
        return hourlyRate * hoursWorked;
    }
}

class Leader extends Employee {
    public Leader(double hourlyRate, int hoursWorked) {
        super(hourlyRate, hoursWorked);
    }

    // bonificação de 2%
    @Override
    public double calculateBaseSalary() {
        return super.calculateBaseSalary() * 1.02;
    }
}

class Manager extends Employee {
    public Manager(double hourlyRate, int hoursWorked) {
        super(hourlyRate, hoursWorked);
    }

    // bonificação de 5%
    @Override
    public double calculateBaseSalary() {
        return super.calculateBaseSalary() * 1.05;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);


        System.out.println("Digite sua taxa horária:");
        double hourlyRate = scanner.nextDouble();
        System.out.println("Digite suas horas trabalhadas:");
        int hoursWorked = scanner.nextInt();

        System.out.println("Digite o seu cargo:");
        String role = scanner.next();

        // Fecha o scanner
        scanner.close();

        Employee employee;
        switch (role.toLowerCase()) {
            case "líder":
                employee = new Leader(hourlyRate, hoursWorked);
                break;
            case "gerente":
                employee = new Manager(hourlyRate, hoursWorked);
                break;
            default:
                employee = new Employee(hourlyRate, hoursWorked);
                break;
        }

        // Calcula e exibe o salário do funcionário
        System.out.println("Salário do funcionário: R$" + employee.calculateBaseSalary());
    }
}
