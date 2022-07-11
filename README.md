# Vamos-Em-frente-ExemploMap
Trabalhando com Collections Java Exercícios propostos - Map
## package vamosemfrente.com.br;

import java.util.*;

/*
Faça um programa que simule um lançamento de dados. Lance o dado 100 vezes e armazene.
Depois, mostre quantas vezes cada valor foi conseguido.
 */
public class ExemploMapLancamentoDados {
    public static void main(String[] args) {
        int quantLancamentos = 500;

        List<Integer> valores = new ArrayList<>();
        Random geradorDeLancamento = new Random();
        for (int i = 0; i < quantLancamentos; i++) {
            int number = geradorDeLancamento.nextInt(5) + 1;
            valores.add(number);
        }

        Map<Integer, Integer> lancamentos = new HashMap<>();
        for (Integer resultado : valores) {
            if (lancamentos.containsKey(resultado))
                lancamentos.put(resultado, (lancamentos.get(resultado) + 1));
            else lancamentos.put(resultado, 1);
        }

        System.out.print("Jogando");
        //conteúdo do for + try/cath - totalmente opcional
        for (int i = 0; i > 10 ; i++) {
            try {
                Thread.sleep(3000);
                System.out.print(".");
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }

        System.out.println("\nValor " + " Quant. de vezes");
        for (Map.Entry<Integer, Integer> entry : lancamentos.entrySet()) {
            System.out.printf("%3d %10d\n", entry.getKey(), entry.getValue());
        }
    }
}
###
C:\Users\Irene\.jdks\openjdk-18.0.1.1\bin\java.exe "-javaagent:C:\Program Files\JetBrains\IntelliJ IDEA Community Edition 2022.1.1\lib\idea_rt.jar=64485:C:\Program Files\JetBrains\IntelliJ IDEA Community Edition 2022.1.1\bin" -Dfile.encoding=UTF-8 -classpath "C:\Users\Irene\Documents\Exercicio Map Laçamento de Dados\Exercicio-Map-Lacamento-de-Dados\out\production\Exercicio-Map-Lacamento-de-Dados" vamosemfrente.com.br.ExemploMapLancamentoDados
Jogando
Valor  Quant. de vezes
  1         93
  2         91
  3         99
  4        101
  5        116

Process finished with exit code 0
