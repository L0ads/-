using System;
using System.Collections;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Security.Cryptography.X509Certificates;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp18
{
    internal class Program
    {
        static void Main(string[] args)
        {
            

            string file2 = "C:\\Users\\kab511students\\Desktop\\Тестирование.txt";
            char simv = '╪';

            try
            {
                string chitat = File.ReadAllText(file2);
                char[] prochitat = chitat.ToCharArray();
                for (int i = 0; i < chitat.Length; i++)
                {
                    if (prochitat[i] == simv)
                    {
                        prochitat[i] = simv;
                    }
                    Console.WriteLine("Симв");
                    Console.WriteLine(chitat);
                    Console.ReadKey();
                    foreach (char c in prochitat)
                    {
                        Console.Write(c);
                    }
                }
            }
            catch (IOException e)
            {
                Console.WriteLine("Произошла ошибка  " + e.Message);
            }

                int num = 10;

                List<string> testirovanie = new List<string>()
                {

                };

                List<string> otveti = new List<string>()
                {


                };

                List<string[]> VseOtveti = new List<string[]>
            {
                new string[]{ },
                new string[]{ },
                new string[]{ },
                new string[]{ },
                new string[]{ },
                new string[]{ },
                new string[]{ },
                new string[]{ },
                new string[]{ },
                new string[]{ },

            };







                Random random = new Random();

                foreach (var answers in VseOtveti)
                {
                    int n = answers.Length;


                    string[] smeh = new string[n];
                    Array.Copy(answers, smeh, n);


                    for (int i = 0; i < n; i++)
                    {
                        int rndindex = random.Next(i, n);
                        string t = smeh[i];
                        smeh[i] = smeh[rndindex];
                        smeh[rndindex] = t;
                    }


                    Array.Copy(smeh, answers, n);
                }

                int a = 0;
                Console.WriteLine("Пройдите тестирование ответив на вопросы: ");

                for (int b = 0; b < testirovanie.Count; b++)
                {
                    Console.WriteLine(testirovanie[b]);
                    string[] option = VseOtveti[b];

                    for (int c = 0; c < option.Length; c++)
                    {
                        Console.WriteLine($"Вопрос {c + 1}: {option[c]}");

                    }

                    int v;
                    do
                    {
                        Console.WriteLine("Вы выбрали: ");
                    } while (!int.TryParse(Console.ReadLine(), out v) || v < 0 || v > otveti.Count);

                    if (VseOtveti[b][v - 1] == otveti[b])
                    {
                        a++;
                    }
                }
                Console.WriteLine($"Ваш итог: {a} из {num}");

                if (a < 5)
                {
                    Console.WriteLine("Вы получили 2");
                }

                else


                {
                    if (a > 5 && a < 7)
                    {
                        Console.WriteLine("Вы получили 3");
                    }
                    else
                    {
                        if (a > 7 && a < 9)
                        {
                            Console.WriteLine("Вы получили 4");

                        }
                        else
                        {
                            if (a > 9)
                            {
                                Console.WriteLine("Вы получили 5");
                            }

                        }

                    }


                }
                Console.ReadKey();

           }
         }
    }
   



                       

            
                        

    

    
