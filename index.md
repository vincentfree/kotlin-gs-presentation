---
marp: true
# theme: gaia
theme: ing
backgroundImage: url('https://marp.app/assets/hero-background.svg')
# _class: lead

---
<!-- _class: cover -->
# Why Kotlin

![bg right](https://raw.githubusercontent.com/vincentfree/kotlin-gs-presentation/main/images/kotlin-logo.png)

GS Tech Talk | 11-04-2022 | Bart Tegenbosch, Vincent Free

---
![bg left](https://picsum.photos/720?image=29)

# Agenda

- History
- Fequently asked questions
- Features of Kotlin
- why should you care?

---
# History

* Started in  2011
* The first official 1.0 release was in February 2016
* At Google I/O 2017, Google Announced First-class Support For Kotlin On Android.
* Kotlin @ ING 2020

---

# Fequently asked questions

- Is Kotlin an object-oriented language or a functional one?
- What advantages does Kotlin give me over the Java programming language?
- Is Kotlin compatible with Java?
- What is it used for?

---

# Fequently asked questions

- Is Kotlin an object-oriented language or a functional one?
  * Kotlin has both object-oriented and functional constructs

---

# Fequently asked questions

- What advantages does Kotlin give me over the Java programming language?
  * Kotlin is
    - more concise(40% less code with same results)
    - more type-safe(better type system)
    - supports non-nullable types
    - smart casting
    - higher-order functions
    - extension functions 
    - lambdas with receivers
    - the list goes on...

---

# Fequently asked questions

- Is Kotlin compatible with Java?
  * Yes, Kotlin is 100% compatible with Java

---

# Fequently asked questions

- What is it used for?
  * Kotlin is used for
    - Backend development
    - Android development
    - Web development
    - Desktop development
    - Native App development (iOS, Android, Windows, macOS)

---

# Null safety Kotlin

<iframe src="https://pl.kotl.in/Z25c29dSL?from=5&to=12" height="250" width="100%"></iframe>

---

# Null safety Java

```java
public class NullSafety_01 {
    public static void main(String[] args) {
        String nonNull = "this value is ok";
        String isNull = null;
        var list = List.of(nonNull,isNull);
        var set = list.stream()
                .map(str -> str.toUpperCase())
                .collect(Collectors.toSet());
        set.forEach(System.out::println);
    }
}
```

---

# Low boilerplate Kotlin

<iframe src="https://pl.kotl.in/tye-UNrWQ?from=7&to=13" height="200" width="100%"></iframe>

---

# Low boilerplate - Java

```java
import java.util.Objects;

class BoilerPlate_02 {
    //This is actually also part of the boilerplate
    public static void main(String[] args) {
        var person = new SimplePerson("Vincent",
                "Free",
                34
        );
        System.out.println(person);
    }
}

class SimplePerson {
    String firstName;
    String lastName;
    int age;

    public SimplePerson(String firstName, String lastName, int age) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.age = age;
    }

    public String getFirstName() {
        return firstName;
    }

    public SimplePerson setFirstName(String firstName) {
        this.firstName = firstName;
        return this;
    }

    public String getLastName() {
        return lastName;
    }

    public SimplePerson setLastName(String lastName) {
        this.lastName = lastName;
        return this;
    }

    public int getAge() {
        return age;
    }

    public SimplePerson setAge(int age) {
        this.age = age;
        return this;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        SimplePerson that = (SimplePerson) o;
        return age == that.age && firstName.equals(that.firstName) && lastName.equals(that.lastName);
    }

    @Override
    public int hashCode() {
        return Objects.hash(firstName, lastName, age);
    }

    @Override
    public String toString() {
        return "SimplePerson{" +
                "firstName='" + firstName + '\'' +
                ", lastName='" + lastName + '\'' +
                ", age=" + age +
                '}';
    }
}
```

> Pre Java 16

---
# Low boilerplate - Java

```java
import java.util.Objects;

class BoilerPlate_02 {
    public static void main(String[] args) {
        var person = new SimplePerson("Vincent",
                "Free",
                34
        );
        System.out.println(person);
    }
}

class SimplePerson {
    String firstName;
    String lastName;
    int age;

    public SimplePerson(String firstName, String lastName, int age) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.age = age;
    }

    public String getFirstName() {
        return firstName;
    }

    public SimplePerson setFirstName(String firstName) {
        this.firstName = firstName;
        return this;
    }

    public String getLastName() {
        return lastName;
    }

    public SimplePerson setLastName(String lastName) {
        this.lastName = lastName;
        return this;
    }
```

---

# Low boilerplate - Java

```java
    public int getAge() {
        return age;
    }

    public SimplePerson setAge(int age) {
        this.age = age;
        return this;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        SimplePerson that = (SimplePerson) o;
        return age == that.age && firstName.equals(that.firstName) && lastName.equals(that.lastName);
    }

    @Override
    public int hashCode() {
        return Objects.hash(firstName, lastName, age);
    }

    @Override
    public String toString() {
        return "SimplePerson{" +
                "firstName='" + firstName + '\'' +
                ", lastName='" + lastName + '\'' +
                ", age=" + age +
                '}';
    }
}
```

---

# Low boilerplate - Java

```java
public record SimplePerson(String firstName, String lastName, int age) {}
```

> In Java 16 “Record classes” are marked as stable

---

# Final by default - Kotlin

<iframe src="https://pl.kotl.in/ntE8RpYjq?from=6&to=11" height=200px width="100%"></iframe>


---

# Final by default - Java

```java
class ExtendingClass extends AlwaysOpen {
    public static void main(String[] args) {
        System.out.println(TEXT);
    }
}
class AlwaysOpen {
    String text = "Open";
    
    AlwaysOpen(String text) {
        this.text = text;
    }
}
```
---

# Immutability

- Makes it easier to reason about the code
- Helps in concurrent environments

```kotlin
fun main() {
    var a = 1
    a = 1 // OK
    
    val b = 1
    b = 2 // Exception: Val cannot be reassigned
}
```

<iframe height="200" width="100%" src="https://pl.kotl.in/m_LIUqybW"></iframe>

---

# FLow control - when

<iframe height="400" width="100%" src="https://pl.kotl.in/RTKHRE8q8?from=9&to=17"></iframe>

---

# Flow control - loops

<iframe height="400" width="100%" src="https://pl.kotl.in/TnR8o9pne"></iframe>

> This example also shows a feature called operator overloading, here iterator is an operator with a special meaning enabling use to write the `for (animal in zoo) {...}` loop without calling the internal list.

---

# Flow control - ranges

<iframe height="400" width="100%" src="https://pl.kotl.in/mgyTyVY4L?from=2&to=19"></iframe>

---

# Flow control - conditional expressions

<iframe height="400" width="100%" src="https://pl.kotl.in/gA0dO6f1t?from=2&to=3" width="100%"></iframe>

> Kotlin doesn't have a turnary operator, the if/else expression replaced it.
---

# Flow control - try expression

<iframe height="400" width="100%" src="https://pl.kotl.in/8FoD1ngin"></iframe>

---

# Scope functions - let

<iframe height="400" width="100%" src="https://pl.kotl.in/6Dz02Gb1R"></iframe>

---

# sealed classes


<iframe height="400" width="100%" src="https://pl.kotl.in/V_VTR4xS9"></iframe>

---
# Type safe builders

```kotlin
import com.example.html.* // see declarations below

fun result() =
    html {
        head {
            title {+"XML encoding with Kotlin"}
        }
        body {
            h1 {+"XML encoding with Kotlin"}
            p  {+"this format can be used as an alternative markup to XML"}

            // an element with attributes and text content
            a(href = "https://kotlinlang.org") {+"Kotlin"}

            // mixed content
            p {
                +"This is some"
                b {+"mixed"}
                +"text. For more see the"
                a(href = "https://kotlinlang.org") {+"Kotlin"}
                +"project"
            }
            p {+"some text"}

            // content generated by
            p {
                for (arg in args)
                    +arg
            }
        }
    }

```