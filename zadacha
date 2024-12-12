using System;
using System.Collections.Generic;
using System.Linq;

namespace BookExpertSystem
{
    // Класс для представления книги
    public class Book
    {
        public string Title { get; set; }
        public string Author { get; set; }
        public string Genre { get; set; }
        public int Pages { get; set; }
        public int Year { get; set; }
    }

    class Program
    {
        // База данных книг
        static List<Book> books = new List<Book>
        {
            new Book { Title = "Гарри Поттер и философский камень", Author = "Дж.К. Роулинг", Genre = "Фэнтези", Pages = 320, Year = 1997 },
            new Book { Title = "1984", Author = "Джордж Оруэлл", Genre = "Дистопия", Pages = 328, Year = 1949 },
            new Book { Title = "Властелин колец", Author = "Дж. Р. Р. Толкин", Genre = "Фэнтези", Pages = 1200, Year = 1954 },
            new Book { Title = "Мастер и Маргарита", Author = "Михаил Булгаков", Genre = "Роман", Pages = 450, Year = 1967 },
            new Book { Title = "Убить пересмешника", Author = "Харпер Ли", Genre = "Драма", Pages = 281, Year = 1960 },
            new Book { Title = "Джейн Эйр", Author = "Шарлотта Бронте", Genre = "Роман", Pages = 500, Year = 1847 },
            new Book { Title = "Анна Каренина", Author = "Лев Толстой", Genre = "Роман", Pages = 850, Year = 1878 },
            new Book { Title = "Грозовой перевал", Author = "Эмили Бронте", Genre = "Роман", Pages = 500, Year = 1847 },
            new Book { Title = "Шерлок Холмс", Author = "Артур Конан Дойл", Genre = "Детектив", Pages = 350, Year = 1892 }
        };

        static void Main(string[] args)
        {
            Console.WriteLine("Добро пожаловать в экспертную систему для выбора книг!");
            Console.WriteLine("Выберите критерий для поиска книги:");
            Console.WriteLine("1 - Жанр");
            Console.WriteLine("2 - Количество страниц");
            Console.WriteLine("3 - Автор");
            Console.WriteLine("4 - Год издания");

            string choice = Console.ReadLine();

            switch (choice)
            {
                case "1":
                    SearchByGenre();
                    break;
                case "2":
                    SearchByPages();
                    break;
                case "3":
                    SearchByAuthor();
                    break;
                case "4":
                    SearchByYear();
                    break;
                default:
                    Console.WriteLine("Некорректный ввод. Попробуйте снова.");
                    break;
            }
        }

        // Поиск по жанру
        static void SearchByGenre()
        {
            Console.Write("Введите жанр (например, Фэнтези, Роман, Детектив): ");
            string genre = Console.ReadLine();

            var results = books.FindAll(b => b.Genre.Equals(genre, StringComparison.OrdinalIgnoreCase));
            DisplayResults(results);
        }

        // Поиск по количеству страниц
        static void SearchByPages()
        {
            Console.Write("Введите минимальное количество страниц: ");
            if (int.TryParse(Console.ReadLine(), out int minPages))
            {
                var results = books.FindAll(b => b.Pages >= minPages);
                DisplayResults(results);
            }
            else
            {
                Console.WriteLine("Некорректный ввод страниц.");
            }
        }

        // Поиск по автору
        static void SearchByAuthor()
        {
            Console.Write("Введите имя автора: ");
            string author = Console.ReadLine();

            var results = books.FindAll(b => b.Author.IndexOf(author, StringComparison.OrdinalIgnoreCase) >= 0);
            DisplayResults(results);
        }

        // Поиск по году издания
        static void SearchByYear()
        {
            Console.Write("Введите год издания: ");
            if (int.TryParse(Console.ReadLine(), out int year))
            {
                var results = books.FindAll(b => b.Year == year);
                DisplayResults(results);
            }
            else
            {
                Console.WriteLine("Некорректный ввод года.");
            }
        }

        // Отображение результатов поиска
        static void DisplayResults(List<Book> results)
        {
            if (results.Count > 0)
            {
                Console.WriteLine("\nНайденные книги:");
                foreach (var book in results)
                {
                    Console.WriteLine($"\nНазвание: {book.Title}");
                    Console.WriteLine($"Автор: {book.Author}");
                    Console.WriteLine($"Жанр: {book.Genre}");
                    Console.WriteLine($"Количество страниц: {book.Pages}");
                    Console.WriteLine($"Год издания: {book.Year}");
                }
            }
            else
            {
                Console.WriteLine("\nКниг по заданному критерию не найдено.");
            }
        }
    }
}
