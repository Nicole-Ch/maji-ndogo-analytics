# OOP & Analysis Case Study

## 1. The Business Problem

The client is working with an agricultural field survey that is expected to grow toward one million records. At that scale, simply storing the data is not enough. The system must be able to find specific records efficiently, maintain reliable data as more engineers work with it, and provide clear answers to questions about the survey.

The first challenge was searching through a growing collection of field records. With thousands of records, a simple search that checks each record one at a time becomes increasingly expensive. The project therefore explored searching and sorting algorithms, including linear search, binary search, and recursive merge sort, together with Big O analysis to understand how the algorithms behave as the dataset grows.

The second challenge was the structure of the field data itself. The original records were represented as dictionaries, which made the data flexible but fragile. Any engineer working on the project could directly change a value without a built-in mechanism to enforce the rules of the data. With several engineers expected to build on the same system, this could lead to inconsistent or invalid records. The data therefore needed a stronger structure that could keep related information and its rules together.

The final challenge was turning the stored records into information the client could actually use. The purpose of the survey was not only to keep thousands of field records, but to answer questions about them. The system therefore needed a way to load the data, organize it into a registry, and analyze it so that questions about crops, fields, yields, pollution, and other agricultural measurements could be answered.

The overall business problem was therefore to build a data workflow that could handle a large and growing agricultural dataset, protect the integrity of its records, and turn those records into useful answers.

## 2. The Tech Stack

The project was built primarily with Python, using several programming techniques to address different parts of the problem.

**Algorithms:** Search algorithms were used to locate records, while recursive merge sort was used to organize data for efficient searching. `map()`, `filter()`, and `lambda` were also used to transform and select data. Big O analysis was used to evaluate how algorithm performance changes as the number of records increases.

**Object-Oriented Programming:** Python classes were used to replace fragile dictionary-based records with structured objects. Encapsulation was used to control access to important attributes and validate values. Inheritance allowed different crop types to share common field behaviour while providing their own specific behaviour. Polymorphism allowed different crop classes to respond through the same interface. Abstract base classes were used to define common expectations for crop field implementations.

**Data and SQL:** Pandas was used to load and work with tabular data, while SQLAlchemy and SQLite were used to load the survey data from the database. This provided a practical connection between database records and Python analysis.

Together, these technologies created a workflow in which data could be loaded, structured, searched, validated, and analyzed rather than simply stored.

## 3. The Deliverable

The first deliverable was an algorithm-based search and sorting workflow. The dataset contained 5,654 field records, allowing the performance of different approaches to be demonstrated on a realistic collection of records. Merge sort was used to organize the data, making binary search possible on the sorted records. This demonstrated why the way data is organized can affect how quickly a specific record can be found.

![Search and sorting workflow](images/search_and_sorting.png)

The result demonstrates the use of sorting and searching algorithms on the agricultural records and shows how algorithm choice affects the number of operations required to locate information.

The second deliverable was the object-oriented field registry. Instead of keeping each field as an unrestricted dictionary, the records were converted into `Field` objects with defined attributes and validation rules.

![Field class and encapsulation](images/field_class.png)

This demonstrates how the field data was given a consistent structure and how validation can prevent invalid values from entering the model. For example, the pollution level is restricted to the valid range of 0 to 1.

The OOP model was then extended to represent different crop types. Inheritance allowed crop-specific classes to reuse the common field structure while defining their own behaviour.

This demonstrates how the same field model can support different crop types without duplicating the entire implementation.

The completed registry was built from the agricultural survey data and produced a collection of field objects that could be used for further analysis.

This demonstrates the transition from raw database records to a structured Python registry containing the agricultural field objects.

Finally, Pandas and SQL were used to load and analyze the data so that the registry could answer agricultural questions.

This demonstrates the final stage of the workflow: turning the stored agricultural records into information that can be used to answer questions about the survey.

## 4. The "So What?"

The project shows how a growing agricultural dataset can be prepared for scale rather than treated as a collection of isolated records. Efficient searching and sorting provide a way to work with larger datasets, while the object-oriented model gives the records consistent structure and validation as more developers build on the system.

Most importantly, the data becomes useful when it can answer questions. Instead of only storing agricultural records, the completed workflow provides a structured foundation for searching, validating, and analyzing those records so that the client can turn survey data into practical information.

