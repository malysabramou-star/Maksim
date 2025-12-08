Задание 1. Класс Book
public class Book  
{  
    public string Title { get; set; }  
    public string Author { get; set; }  
    public int Year { get; set; }  
  
    public void ShowInfo()  
    {  
        Console.WriteLine($"Название: {Title}, Автор: {Author}, Год: {Year}");  
    }  
}  
Задание 2. Класс Account
public class Account  
{  
    private decimal _balance;  
    public decimal Balance => _balance;  
  
    public void Deposit(decimal amount)  
    {  
        if (amount > 0)  
            _balance += amount;  
    }  
  
    public void Withdraw(decimal amount)  
    {  
        if (amount > 0 && amount <= _balance)  
            _balance -= amount;  
    }  
}  
Задание 3. Транспорт
public class Transport  
{  
    public virtual void Move() => Console.WriteLine("Транспорт движется.");  
}  
  
public class Car : Transport  
{  
    public override void Move() => Console.WriteLine("Машина едет по дороге");  
}  
  
public class Boat : Transport  
{  
    public override void Move() => Console.WriteLine("Лодка плывёт по воде");  
}  
  
public class Plane : Transport  
{  
    public override void Move() => Console.WriteLine("Самолёт летит в небе");  
}  
Задание 4. Животные
public class Animal  
{  
    private int _energy = 100;  
  
    public void Eat() => ChangeEnergy(10);  
      
    public void ShowEnergy() => Console.WriteLine($"Энергия: {_energy}");  
      
    protected void ChangeEnergy(int value)  
    {  
        _energy += value;  
        if (_energy > 100) _energy = 100;  
        if (_energy < 0) _energy = 0;  
    }  
}  
  
public class Dog : Animal  
{  
    public void Run() => ChangeEnergy(-20);  
}  
  
public class Cat : Animal  
{  
    public void Sleep() => ChangeEnergy(5);  
}  
Задание 5. Фигуры
public abstract class Shape  
{  
    public virtual double GetArea() => 0;  
}  
  
public class Circle : Shape  
{  
    public double Radius { get; set; }  
      
    public override double GetArea() => Math.PI * Radius * Radius;  
}  
  
public class Rectangle : Shape  
{  
    public double Width { get; set; }  
    public double Height { get; set; }  
      
    public override double GetArea() => Width * Height;  
}  
Задание 6. Работники
public abstract class Worker  
{  
    public string Name { get; set; }  
      
    public abstract void Work();  
      
    public void ShowInfo() => Console.WriteLine($"Работник: {Name}");  
}  
  
public class Manager : Worker  
{  
    public override void Work() => Console.WriteLine("Планирует задачи");  
}  
  
public class Developer : Worker  
{  
    public override void Work() => Console.WriteLine("Пишет код");  
}  
Задание 7. Музыкальные инструменты
public interface IPlayable  
{  
    void Play();  
}  
  
public class Guitar : IPlayable  
{  
    public void Play() => Console.WriteLine("Струны звенят: дзинь-дзинь");  
}  
  
public class Piano : IPlayable  
{  
    public void Play() => Console.WriteLine("Клавиши звучат: дон-дон");  
}  
  
public class Drum : IPlayable  
{  
    public void Play() => Console.WriteLine("Барабаны бьют: бум-бум");  
}  
Задание 8. Многофункциональное устройство
public interface IPrinter  
{  
    void Process();  
}  
  
public interface IScanner  
{  
    void Process();  
}  
  
public class MultifunctionDevice : IPrinter, IScanner  
{  
    void IPrinter.Process() => Console.WriteLine("Печать документа...");  
      
    void IScanner.Process() => Console.WriteLine("Сканирование документа...");  
}  
Задание 9. Экспорт документов
public interface IDocumentExporter  
{  
    string FormatName { get; }  
    void Export(string content);  
      
    void ShowInfo(string content) => Console.WriteLine($"Экспорт в формат
