# Map

## Learning Goals

- Understand the Map interface
- Use different implementations of the Map interface

## Map Interface

While Lists are ordered collections of items that are referenced by their
position in the list, Maps are lists of what are known as "key/value" pairs,
where a specific "key" is mapped to a specific "value". Duplicate keys are not
allowed and a key can only map to one value.

## Map Implementations

Like the `List` interface, the `Map` interface has multiple implementations that
focus on different aspects of maps. The following are the most commonly used
implementations:

1. `HashMap`: permits null keys and null values, and makes no guarantee on the
   order of the elements - this is the implementation we will focus on in this
   section
2. `TreeMap`: is a sorted map, based on the natural ordering of the keys (or
   based on a custom sort, which is beyond the scope of this module)

Considering our list of students, let's imagine we want to keep track of their
letter grade in a specific class. Instead of keeping up with two lists, one for
students and one for grades, and coming up with a mechanism to match them up, we
can instead use a `HashMap` where our key is the student's name and our value is
the student's letter grade:

```java
HashMap<String, String> studentGrades = new HashMap<String, String>();
```

Like `ArrayList`, `HashMap` supports generic types, so our `HashMap` definition
can specify the type of both the keys and the values. We can then use the
`put()` method to add items to our map:

```java
studentGrades.put("Jamaal", "A+");
studentGrades.put("Jennifer", "A");
studentGrades.put("Jules", "B-");
```

There are 3 main ways to access the values in a map:

1. By the key: `studentGrades.get("Jamaal");`
2. Through a list of all the keys: `studentGrades.keySet()`
3. Through a list of all the values: `studentGrades.values()`

Here is code that shows how to access the values in the map using the 3 methods
outlined above:

```java
    // get the grade for a specific student
    System.out.println("Jamaal's grade is " + studentGrades.get("Jamaal"));

    // get all the grades for all the students
    System.out.println("List of grades:");
    for (String grade: studentGrades.values()) {
        System.out.println(grade);
    }

    // get all the student grades, student by student
    System.out.println("List of students and their grades:");
    for (String student: studentGrades.keySet()) {
        System.out.println(student);
        System.out.println(studentGrades.get(student));
    }

    // get all the student and their grades using each entry
    System.out.println("List of students and their grades:");
    for (Map.Entry<String, String> studentGrade: studentGrades.entrySet()) {
        System.out.println(studentGrade.getKey() + "'s grade is " + studentGrade.getValue());
    }
```
