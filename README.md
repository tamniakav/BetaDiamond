using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Diamond
{
    class Diamond
    {
        static void Main(string[] args)
        {
            int n = int.Parse(Console.ReadLine());

            if (n <= 2)
            {
                Console.WriteLine(new string('*', n));
            }
            else
            {
                int middle = 0;
                int side = (n - 2) / 2;
                int top = n / 2;

                if (n % 2 == 1)
                {
                    Console.WriteLine("{0}*{0}", new string('-', (n - 1) / 2));
                    middle = 1;
                }
                for (int row = 0; row < top; row++)
                {
                    Console.WriteLine("{0}*{1}*{0}", new string('-', side), new string('-', middle));

                    side--;
                    middle += 2;
                }

                side = 1;
                middle = n - 4;

                for (int row = top - 1; row >= 1; row--)
                {
                    Console.WriteLine("{0}*{1}*{0}", new string('-', side), new string('-', middle));

                    side++;
                    middle -= 2;
                }

                if (n % 2 != 0)
                {
                    Console.WriteLine("{0}*{0}", new string('-', (n - 1) / 2));
                    middle = 1;
                }
            }
        }
    }
}

