# Facade - Патерн Проєктування

Патерн Facade спрощує взаємодію з підсистемами, пропонуючи єдиний інтерфейс для виконання операцій.  
Він приховує складність внутрішньої логіки, зменшуючи залежність клієнтського коду від деталей реалізації.

## Ідея
Зробити роботу з декількома класами простішою, об'єднавши їхні виклики в одному фасадному класі.

## Структура

| Елемент     | Опис |
|-------------|------|
| `SubsystemA`, `SubsystemB` | Підсистеми з власною логікою |
| `Facade`    | Надає простий інтерфейс для використання підсистем |
| Клієнт      | Використовує фасад, не звертаючись безпосередньо до підсистем |

## Код

```csharp
class SubsystemA {
    public void A() => Console.WriteLine("A");
}

class SubsystemB {
    public void B() => Console.WriteLine("B");
}

class Facade {
    SubsystemA a = new();
    SubsystemB b = new();

    public void Operation() {
        a.A();
        b.B();
    }
}

class Program {
    static void Main() => new Facade().Operation();
}

