## Documentation of `Person.java`

**Overview:**

This Java class, `Person`, represents a single person with attributes for name, age, and gender. It provides getter and setter methods to access and modify these attributes.

**Detailed Explanation:**

* **`private String name;`**: A private member variable storing the person's name as a String.

* **`private int age;`**: A private member variable storing the person's age as an integer.

* **`private Gender gender;`**: A private member variable storing the person's gender as an instance of the `Gender` enum.

* **`public String getName()`**: This method returns the person's name.
    * **Return Value**: A `String` representing the person's name.

* **`public void setName(String name)`**: This method sets the person's name.
    * **Parameters**:
        * `name`: A `String` representing the new name for the person.

* **`public int getAge()`**: This method returns the person's age.
    * **Return Value**: An `int` representing the person's age.

* **`public void setAge(int age)`**: This method sets the person's age.
    * **Parameters**:
        * `age`: An `int` representing the new age for the person.

* **`public Gender getGender()`**: This method returns the person's gender.
    * **Return Value**: A `Gender` enum representing the person's gender.

* **`public void setGender(Gender gender)`**: This method sets the person's gender.
    * **Parameters**:
        * `gender`: A `Gender` enum representing the new gender for the person.

* **`public Person()`**: This is the default constructor for the `Person` class. It initializes a new `Person` object with default values.

* **`public Person(String name, int age, Gender gender)`**: This is a parameterized constructor for the `Person` class. It initializes a new `Person` object with the provided name, age, and gender.

**Key Variables and Data Structures:**

* **`String`**: Used to store the person's name.
* **`int`**: Used to store the person's age.
* **`Gender`**: An enum representing the person's gender (e.g., Male, Female).

**Dependencies:**

* **`com.mocmilo.model.Gender`**: This class defines the `Gender` enum used to represent person's gender.



**Pseudo Code:**

```
Person()
  // Initialize name, age, and gender to default values

Person(name, age, gender)
  // Assign the input name, age, and gender to the respective member variables

getName()
  // Return the value of the name member variable

setName(name)
  // Assign the input name to the name member variable

getAge()
  // Return the value of the age member variable

setAge(age)
  // Assign the input age to the age member variable

getGender()
  // Return the value of the gender member variable

setGender(gender)
  // Assign the input gender to the gender member variable



```



