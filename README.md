using System;

class Program
{
    static void Main(string[] args)
    {
        Random random = new Random();
        int numeroAleatorio = random.Next(1, 11);
        int tentativas = 0;

        Console.WriteLine("Bem-vindo ao jogo de adivinhação!");
        Console.WriteLine("Estou pensando em um número entre 1 e 10.");

        while (true)
        {
            Console.Write("Digite sua tentativa: ");
            string? input = Console.ReadLine();

            if (int.TryParse(input, out int tentativa))
            {
                tentativas++;
                if (tentativa < numeroAleatorio)
                {
                    Console.WriteLine("Muito baixo! Tente novamente.");
                }
                else if (tentativa > numeroAleatorio)
                {
                    Console.WriteLine("Muito alto! Tente novamente.");
                }
                else
                {
                    Console.WriteLine($"Parabéns! Você acertou o número em {tentativas} tentativas.");
                    break;
                }
            }
            else
            {
                Console.WriteLine("Valor inválido! Por favor, digite um número.");
            }
        }
    }
