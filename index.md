---
marp: true
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
- Frequently asked questions
- Features of Kotlin

---

# History

* Started in  2011
* The first official 1.0 release was in February 2016
* At Google I/O 2017, Google Announced First-class Support For Kotlin On Android.
* Kotlin @ ING 2020

---

# Frequently asked questions

- Is Kotlin an object-oriented language or a functional one?
- What advantages does Kotlin give me over the Java programming language?
- Is Kotlin compatible with Java?
- What is it used for?

---

# Frequently asked questions

- Is Kotlin an object-oriented language or a functional one?
  * Kotlin has both object-oriented and functional constructs

---

# Frequently asked questions

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

# Frequently asked questions

- Is Kotlin compatible with Java?
  * Yes, Kotlin is 100% compatible with Java

---

# Frequently asked questions

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
    String nonNull = "this value is ok";
    String isNull = null;
    var list = List.of(nonNull,isNull);
    var set = list.stream()
        .map(str -> str.toUpperCase())  // <- can't call toUpperCase on null
        .collect(Collectors.toSet());
    set.forEach(System.out::println);
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

<iframe src="https://pl.kotl.in/ntE8RpYjq?from=6&to=11" height="200" width="100%"></iframe>

---

# Immutability

- Makes it easier to reason about the code
- Helps in concurrent environments

<iframe height="200" width="100%" src="https://pl.kotl.in/XjbFZkB-Q?from=2&to=6"></iframe>

---

# Expressions

Flow control structures can be used as expressions which can produce a result. Making the code much more concise and readable.

<!--  Kotlin doesn't have a turnary operator. It's replaced by the if/else expression. -->

<iframe height="450" width="100%" src="https://pl.kotl.in/XsKD_eKsR"></iframe>

---

# Higher order functions

<iframe height="400" width="100%" src="https://pl.kotl.in/TIuJ65oZv"></iframe>

---

# Flow control - loops

<iframe height="150" width="100%" src="https://pl.kotl.in/aVZHGgB8_?from=2&to=4"></iframe>

---

# Flow control - ranges

<iframe height="400" width="100%" src="https://pl.kotl.in/mgyTyVY4L?from=2&to=19"></iframe>

---

# Flow control - Result types

<iframe height="250" width="100%" src="https://pl.kotl.in/neSKuJNRp"></iframe>

---

# Scope functions - let

<iframe height="250" width="100%" src="https://pl.kotl.in/6Dz02Gb1R"></iframe>

---

# Scope functions - run

<iframe height="200" width="100%" src="https://pl.kotl.in/ORn5xVVle"></iframe>

---

# Scope functions - apply

<iframe height="200" width="100%" src="https://pl.kotl.in/4XZbb7TjX"></iframe>

---

# Scope functions - also

<iframe height="200" width="100%" src="https://pl.kotl.in/HeluOyxy6"></iframe>

---

# Scope functions - with

<iframe height="250" width="100%" src="https://pl.kotl.in/7f1_XgSnh?from=7&to=13"></iframe>

---

# Sealed classes

<iframe height="400" width="100%" src="https://pl.kotl.in/V_VTR4xS9"></iframe>

<!-- 
Sealed classes are classes that can only be extended from within the same file.
In some sense, sealed classes are similar to enum classes, they are also called enums with superpowers.
-->

---

# Value classes

> Create wrappers around a type.
<iframe height="250" width="100%" src="https://pl.kotl.in/RIiweQYf6"></iframe>

<!--
Value classes are a way to create a wrapper around a type.
Previously this feature was called a inline class but that has changed recently.
-->
---

# Extension functions

> Kotlin provides the ability to extend a class with new functionality without having to inherit from the class or use design patterns such as Decorator. This is done via special declarations called extensions.

<iframe height="250" width="100%" src="https://pl.kotl.in/fdLjmxenb"></iframe>

---

# Named parameters

<iframe height="200" width="100%" src="https://pl.kotl.in/TuJit_h5d"></iframe>

---

# Generics 

<iframe height="450" width="100%" src="https://pl.kotl.in/-DbSdoPut"></iframe>

---

# Type safe builders (DSL)

<iframe height="500" width="100%" src="https://pl.kotl.in/DxCBgBp3I"></iframe>

---

# Delegation

> The Delegation pattern has proven to be a good alternative to implementation inheritance, and Kotlin supports it natively requiring zero boilerplate code.

<iframe height="500" width="100%" src="https://pl.kotl.in/3AjBfoE7Q"></iframe>

---

