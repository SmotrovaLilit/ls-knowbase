
# The difference between the go and other programming languages

- Concurrency model. It introduces goroutines (lightweight threads) and channels, which make it easier to write concurrent and parallel programs. Many other languages rely on traditional threading.
- Go is a compiled language, which means that the code is compiled into machine code before execution.
- Static Typing. Go is statically typed, which means that variable types are checked at compile time.
- Garbage Collection: Go incorporates a garbage collector that manages memory automatically. This helps prevent memory leaks and makes memory management less error-prone compared to languages like C or C++.
- No Inheritance: Go does not support traditional class-based inheritance like many object-oriented languages. Instead, it uses composition, embedding and interfaces to achieve code reuse and polymorphism.
```go
package main

type Cat struct {
        Name string
}

func (c Cat) Legs() int { return 4 }

func (c Cat) PrintLegs() {
        fmt.Printf("I have %d legs\n", c.Legs())
}

type OctoCat struct {
        Cat
}

func (o OctoCat) Legs() int { return 5 }

func main() {
        var octo OctoCat
        fmt.Println(octo.Legs()) // 5
        octo.PrintLegs()         // I have 4 legs
}
```
- Standard Library: Go comes with a comprehensive standard library that covers various areas, including networking, web development, and file handling. This reduces the need for third-party libraries in many cases.
- Error handling. Go does not have exceptions like Java or Rust. Instead, it relies on explicit error checking, making it clear when and where errors may occur. 
- Opinionated Design: Go is known for its opinionated design choices, which prioritize simplicity, clarity, and performance. This can be both a strength and a limitation, depending on the developer's preferences and project requirements.
- Ecosystem: While Go's standard library is robust, its ecosystem of third-party libraries and frameworks may be smaller and less mature compared to languages like Python, JavaScript, or Java.
- **No support of enums**.  Go doesn't generate an error when some type is skipped in the switch case. 
```csharp
enum DayOfWeek
{
    Sunday,
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday
}

DayOfWeek day = DayOfWeek.Monday;

switch (day)
{
    case DayOfWeek.Sunday:
        Console.WriteLine("It's Sunday!");
        break;
    case DayOfWeek.Monday:
        Console.WriteLine("It's Monday!");
        break;
    // ... cases for other days ...
    default:
        Console.WriteLine("Invalid day!");
        break;
}
```
In this C# example, the `enum DayOfWeek` defines a set of named constants for the days of the week. When you use an enum type in a switch statement, the C# compiler ensures that you handle all possible enum values. If you miss a case, the compiler generates an error or warning.
```go
package main

import "fmt"

const (
    Sunday = iota
    Monday
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday
)

type Day int

const (
    Sun Day = iota
    Mon
    Tue
    Wed
    Thu
    Fri
    Sat
)

func main() {
    day := Monday

    switch day {
    case Sunday:
        fmt.Println("It's Sunday!")
    case Monday:
        fmt.Println("It's Monday!")
    // ... cases for other days ...
    default:
        fmt.Println("Invalid day!")
    }
}
```
Go does not provide automatic checks to ensure that all values are covered in a switch statement. It is the developer's responsibility to handle all cases properly.

## References
1. https://doc.rust-lang.ru/stable/rust-by-example/std/result.html 
2. https://www.javatpoint.com/exception-handling-in-java