# Pool-calculation-program-code-
# A small program will be designed for MC Build that will calculate the area and volume of the rectang
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Alhamzah
{
    class Program
    {
        static void Main(string[] args)
        {
            string poolType,option;

            for (;;)
            {
                Console.Write("Enter R for Rectangular or C for Circular Pool: ");
                poolType = Console.ReadLine();
                switch (poolType.ToUpper())
                {
                    case "R":
                        recPool();
                        break;
                    case "C":
                        cirPool();
                        break;
                    default:
                        Console.WriteLine("Invalid Character");
                        break;
                }

                Console.Write("Enter M for More or E for Exit: ");
                option = Console.ReadLine();
                option = option.ToUpper();
                if (option == "M")
                {
                    continue;
                }
                else
                {
                    break;
                }
            }
             
            Console.ReadLine();
        }

        public static void recPool()
        {
            string name, option;
            int i = 1;
            double area, volume, width, height, lenght;
            Console.Write("Enter your name: ");
            name = Console.ReadLine();
            Console.WriteLine("\nUsername: " + name);
            Console.WriteLine("Rectangular Pool\n");

            Console.WriteLine("\t\t\t\tNo.\tWidth\tHeight\tLenght\tArea\tVolume");

            for (;;)
            {
                Console.Write("Enter width: ");
                width = Convert.ToDouble(Console.ReadLine());

                Console.Write("Enter height: ");
                height = Convert.ToDouble(Console.ReadLine());

                Console.Write("Enter lenght: ");
                lenght = Convert.ToDouble(Console.ReadLine());

                area = width * height;
                volume = lenght * height * width;

                Console.WriteLine("\t\t\t\t{0}\t{1}\t{2}\t{3}\t{4}\t{5}", i, width, height, lenght, string.Format("{0:0.00}", area), string.Format("{0:0.00}", volume));
                i++;
                Console.Write("\nMore? Y/N: ");
                option = Console.ReadLine();
                option = option.ToUpper();
                if (option == "Y")
                {
                    continue;
                }else
                {
                    break;
                }
            }
        }

        public static void cirPool()
        {
            int i = 1;
            string name, option;
            double area, volume, radius;

            Console.Write("Enter your name: ");
            name = Console.ReadLine();

            Console.WriteLine("\nUsername: " + name);
            Console.WriteLine("Circular Pool\n");


            Console.WriteLine("\t\t\t\tNo.\tRadius\tPI\tArea\tVolume");

            for (;;)
            {
                Console.Write("Enter radius: ");
            radius = Convert.ToDouble(Console.ReadLine());

            area = Math.PI * radius * radius;
            volume = 4 / 3 * Math.PI * radius * radius * radius;

            Console.WriteLine("\t\t\t\t{0}\t{1}\t{2}\t{3}\t{4}", i, radius, string.Format("{0:0.00}", Math.PI), string.Format("{0:0.00}", area), string.Format("{0:0.00}", volume));
            i++;
            Console.Write("\nMore? Y/N: ");
            option = Console.ReadLine();
            option = option.ToUpper();
            if (option == "Y")
            {
                continue;
            }
            else
            {
                break;
            }
        }
    }
    }
}
