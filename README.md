# Calculate-GPA-of-students
using System;
using System.Collections.Generic;

namespace student_data_by_list
{
    internal class Program
    {
      
        public List<string> SubjectName(int TotalSubjects)
        {
            List<string> Subjects = new List<string>();
            for (int i = 1; i <= TotalSubjects; i++)
            {
                Console.Write("Enter subject Names :");
                string subject = Console.ReadLine();
                Subjects.Add( subject);
            }
            return Subjects;
        }
        public List<int> MarksOfSubject(List<string> Sub)
        {
            int length = Sub.Count;
            List<int> marks = new List<int>();
            for (int i = 0; i < length; i++)
            {
                Console.Write($"Enter Marks Of {Sub[i]} : ");
                int mark = Convert.ToInt32(Console.ReadLine());
                marks.Add(mark);
            }
            return marks;
        }
        public void CalculateGPA(List<string> Sub, List<int> numbers)
        {
            Console.WriteLine($"Subject Number Grade");
            
            for (int i = 0; i < numbers.Count; i++)
            {
                 if (numbers[i] < 0 && numbers[i] > 100)
                {
                   
                    Console.WriteLine($"invalid number {i} ");
                }
                else if (numbers[i] >= 85 && numbers[i] <=100)
                {
                    Console.WriteLine($"{i + 1}  {Sub[i]} {numbers[i]}/100 A GRADE");
                }
                else if (numbers[i] >= 76 && numbers[i] <= 84)
                {
                    Console.WriteLine($"{i + 1}  {Sub[i]} {numbers[i]}/100  B GRADE");
                }
                else if (numbers[i] >= 66 && numbers[i] <= 75)
                {
                    Console.WriteLine($"{i + 1}  {Sub[i]} {numbers[i]}/100  C GRADE");
                }
                else if (numbers[i] >= 50 && numbers[i] <= 65)
                {
                    Console.WriteLine($"{i + 1}  {Sub[i]} {numbers[i]}/100  D GRADE");

                }
                
                else
                {
                    Console.WriteLine($"Invalid numbers  {i + 1}  {Sub[i]} {numbers[i]}/100  F GRADE");
                }

            }
          
        }
        static void Main(string[] args)
        {
            Program obj = new Program();
            int totalsubjects;
            Console.WriteLine("ENTER TOTAL SUBJECTS");
            totalsubjects = Convert.ToInt32(Console.ReadLine());
            List<string> sub = obj.SubjectName(totalsubjects);
            List<int> numbers = obj.MarksOfSubject(sub);
            obj.CalculateGPA(sub, numbers);
        }
    }
}
