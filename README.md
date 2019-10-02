using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Baljinder_Singh
{
    public class TriangleSolver
    {
        static int first_side;
        static int second_side;
        static int third_side;

        public static string Analyze(int side1, int side2, int side3)
        {
            string resultString = "";

            first_side = side1;
            second_side = side2;
            third_side = side3;

            if (((first_side + second_side) > third_side) && ((second_side + third_side) > first_side) && ((first_side + third_side) > second_side))
            {
                string triangleCategory;

                if (first_side == second_side && second_side == third_side)
                {
                    triangleCategory = "Equilateral";

                }
                else if (first_side == second_side || second_side == third_side || first_side == third_side)
                {
                    triangleCategory = "Isosceles";
                }
                else
                {
                    triangleCategory = "Scalene";
                }

                switch (triangleCategory)
                {
                    case "Equilateral":
                        resultString = "An Equilateral triangle will be formed";
                        break;

                    case "Isosceles":
                        resultString = "An Isosceles triangle will be formed";
                        break;

                    case "Scalene":
                        resultString = "A Scalene triangle will be formed";
                        break;
                }

            }

            else
            {
                resultString = "\n\nNo, triangle formation is not possible with the given sides";
            }

            return resultString;
        }


    }
}
