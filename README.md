using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp18
{
    internal class Program
    {
        static void Main(string[] args)
        {
            //Сделать тестирование  5 листов 1 лист - вопросы 2 лист - правильные ответы 
            //3,4,5 - дополнительные варианты ответов 
            //10 вопросов 
            // в конце тестирования % правильности ответов и оценка 
            int num = 10;

            List<string> testirovanie = new List<string>()
            {
                "Какая главная команда СНГ?",
                "Какие команды существуют в обычном режиме КС?",
                "Сколько всего плентов на карте?",
                "Середина карты называется?",
                "Сколько было мажоров?",
                "Сколько игроков в команде?",
                "Сколько по времени длится перерыв, когда вышел игрок?",
                "Сколько всего раундов?",
                "На сколько дается первая блокировка при выходе?",
                "Какое максимальное звание?"

            };

            List<string> otveti = new List<string>()
            {
                "C9",
                "T и CT",
                "2",
                "MID",
                 "19",
                 "5",
                 "2 минуты",
                 "30",
                 "На 30 минут",
                 "Глобал",

            };

            List<string[]> VseOtveti = new List<string[]>
            {
                new string[] {"NAVI", "C9", "Gambit", "G2", },
                new string[]{ "BB", "T", "CT", "T и CT",},
                new string[]{"0","1", "2", "3", },
                new string[]{ "SUQ", "LONG", "MID", "Plant", },
                new string[]{ "22", "19", "11", "1", },
                new string[]{"2", "5", "10", "11",},
                new string[]{"30 секунд", "Нисколько", "5 минут", "2 минуты",},
                new string[]{"16", "29", "30", "100",},
                new string[]{ "На 30 минут", "на 1 час", "на 7 дней", "Навсегда",},
                new string[]{ "Глобал", "Сильвер", "Калаш", "Звезда",},

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

            if (a >= 9)
            {
                Console.WriteLine("Вы получили 5");


            }
            else
            {
                if (a > 7 || a < 9)
                {
                    Console.WriteLine("Вы получили 4");
                    Console.ReadKey();
                }
                else
                {

                    {
                        if (a > 6 || a < 7)
                        {
                        Console.WriteLine("Вы получили 3");
                            Console.ReadKey();
                        }
                            


                        else
                        {
                            if (a > 6)
                            {
                                Console.WriteLine("Вы получили 2");
                                Console.ReadKey();
                            }
                        }



                       

                    }
                }
            }
                        Console.ReadKey();
                        

                        Console.ReadLine();


        }
    }
}
    
