## Documentation of `ContainerBuilder.java`

**Overview:**

This Java class, `ContainerBuilder`, provides a simple way to construct a `Container` object. It creates three `Person` objects and then uses them to initialize a `Container`.

**Detailed Explanation:**

* **`public Container build()`:** This is the main method of the `ContainerBuilder` class. It creates three `Person` objects with predefined names, ages, and genders and then returns a new `Container` object containing these persons.

    * **Logic:**
        1.  Three `Person` objects are created: `person1`, `person2`, and `person3`, each with a name, age, and gender.
        2.  These three `Person` objects are added to a list using `Arrays.asList()`.
        3.  A new `Container` object is created using the list of `Person` objects.
        4.  The `Container` object is returned.

**Key Variables and Data Structures:**

* **`Container`:** A class representing a collection of `Person` objects (defined in a separate file `com.mocmilo.model.Container.java`).

* **`Person`:** A class representing an individual with a name, age, and gender (defined in a separate file `com.mocmilo.model.Person.java`).


**Dependencies:**

* **`com.mocmilo.model.Container.java`:** This class defines the `Container` object.
* **`com.mocmilo.model.Person.java`:** This class defines the `Person` object.

**Pseudo Code:**

```
buildContainer()
  // Create three Person objects:
  person1 = new Person("Tom", 27, M)
  person2 = new Person("Alice", 24, W)
  person3 = new Person("Dominica", 28, W)

  // Create a list of persons
  personsList = [person1, person2, person3]

  // Create a Container object using the list of persons
  container = new Container(personsList)

  // Return the Container object
  return container
```



