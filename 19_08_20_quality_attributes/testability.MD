# Testability

30-50% of the cost of developing well-engineered systems is taken up by testingTESTABILITY
* The ease with which software can be made to demonstrate its faults through testing
* Testability refers to the probability, assuming that the software has at least one fault, that it will fail on its next test execution
* capacidade de detectar erros rapidamente através de testes

### Definitions
* Oracle: an agent (human or mechanical) that decides whether the output is correct (comparação com especificação)
  * Estar certo não precisa se referir apenas ao resultado - pode ter a ver com outros quality attributes (tempo para gerar resultado etc) ou estado interno de execução

###  Requirements for testable system
* it must be possible to
  * control each component’s inputs (and maybe manipulate its internal state)
  * to observe its outputs (and possibly its internal state)

### Response measures for testability
* how effective the tests are in discovering faults
* how long it takes to perform the tests to some desired level of coverage
* the ease at which the system can be brought into a specific state, etc


# Tacticts for Testability
## 1. Adding controllability and observability to the system

State information - allow to assign value, make information accessible, etc


### Specialized interfaces
* Get/Set for important variables
* Report method - returns the full state of the object
* Reset method - set the internal state (ex: class attributes) to a specified value
* Methods for verbose output / logging


### Abstract data sources
* Make it easy to point to a test database or files of test data without changing the code


### Sandbox
* Isolate an instance of the system from the real world to enable experimentation, without worrying about consequences
  * Ex:
    * Make rollback of tests at the end
    * Virtualize resources - ex: virtualize system clock to emulate time of day, virtualize battery, etc
    	* Stubs / mocks / dependency injection


### Executable assertions
* The assertions are often designed to check that data values satisfy specified constraints
* pre- and post- conditions



## 2. Limiting complexity in the system’s design

### Complex software is harder to testLimit structural complexity
* avoiding or resolving cyclic dependencies between components
* isolating and encapsulating dependencies on the external environment
* reducing dependencies between components in general
* Object-oriented software
  * Limit the depth of the inheritance tree
  * Limit polymorphism and dynamic calls
* Separation of concerns - class has focused task with limited interaction with other elements
* some architectural styles lend themselves to testability - ex: layers

### Limit nondeterminism
* Diminuir não-determinismo (ex: multithreading systems that respond to unpredictable events)

# Checklist for testability
* Allocation of Responsibilities: most critical responsabilities need to be most thoroughly tested
* Coordination Model: Ensure the system’s coordination and communication mechanisms
* Data Model: Determine the major data abstractions to be tested
* Resource Management: Ensure there are sufficient resources available to execute the test, ensure that your test environment is similar/identical to real environment.
* Choice of Technology: Determine what technologies are available to help achieve the testability scenarios that apply to your architecture

## Extra:
* how to create large, consistent and useful test data sets -> integration / performance tests
  * write a system to generate your test data (comprehensive, but takes longer)
  * you capture a representative data set from the production environment and anonymize it as necessary ("easier" but may not cover all edge cases)

# NETFLIX CASE
* high availability is important to Netflix
* Simian Army - part of testing process
  * Chaos Monkey - randomly kills processes in the running system
  	* Monitor the effect of failed process
  	* Ensure the system does not fail / suffer serious degradation as a result of a process failure
  * The Latency Monkey - induces artificial delays in the client-server communication layer
  * The Conformity Monkey - finds instances that don’t adhere to best practices and shuts them down
  * The Doctor Monkey - execute health checks on instances
  * The Janitor Monkey - It searches for unused resources and disposes of them
  * The Security Monkey (extension of Conformity Monkey) - It finds security violations or vulnerabilities, such as improperly configured security groups, and terminates the offending instances
  * The 10-18 Monkey - detects configuration and runtime problems with internationalization
