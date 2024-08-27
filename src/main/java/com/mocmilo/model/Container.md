## Documentation of `Container.java`

**Overview:**

This Java class, `Container`, represents a simple container for holding a list of `Person` objects. It provides a getter method to access the list of people and a constructor to initialize the container with a given list of people.

**Detailed Explanation:**

* **`private List<Person> peopleList;`**: This is a private member variable that stores a list of `Person` objects.

* **`public List<Person> getPeopleList()`**: This method returns the list of `Person` objects stored in the container.
    * **Return Value**: A `List` of `Person` objects.

* **`public Container(List<Person> peopleList)`**: This is the constructor for the `Container` class. It takes a list of `Person` objects as input and initializes the `peopleList` member variable with the provided list.
    * **Parameters**:
        * `peopleList`: A `List` of `Person` objects.

**Key Variables and Data Structures:**

* **`List<Person>`**: A list of `Person` objects, representing the people contained within the container.

**Dependencies:**

* **`com.mocmilo.model.Person`**: This class represents a single person and is used to populate the `peopleList`.



**Pseudo Code:**

```
Container()
  // Create a new empty list of Person objects
  peopleList = new ArrayList<Person>()

Container(peopleList)
  // Assign the input list of Person objects to the peopleList member variable
  this.peopleList = peopleList



getPeopleList()
  // Return the peopleList member variable
  return peopleList



```



