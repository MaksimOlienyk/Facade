# Facade
```cs
class SubsystemA { public void A()=>Console.WriteLine("A"); }
class SubsystemB { public void B()=>Console.WriteLine("B"); }

class Facade {
    SubsystemA a=new(); SubsystemB b=new();
    public void Operation(){ a.A(); b.B(); }
}

class Program { static void Main()=>new Facade().Operation(); }
