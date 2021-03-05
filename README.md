using System;
using System.Collections;
using System.Collections.Generic;
namespace Dj
{
    class Program
    {
        static void Main(string[] args)
        {
            Stek<int> a = new Stek<int>();
            a.Push(2);
            Console.WriteLine(a.Peek());
            a.Push(3);
            Console.WriteLine(a.Pop());
            Console.WriteLine(a.Pop());
        }
        public class Stek<T>
        {
            static int last { get; set; }
            static T[] steckarray = new T[1];
            public void Push(T value)
            {
                last++;
                Array.Resize(ref steckarray, steckarray.Length + 1);
                steckarray[last] = value;
            }
            public T Pop()
            {
                T a = steckarray[last]; 
                Array.Resize(ref steckarray, steckarray.Length - 1);
                last--;
                return a;
            }
            public T Peek()
            {
                return steckarray[last];
            }
        }
    }
}
