The trouble is, TDD is careful to be ambiguous about technical details. As a result, the code produced will only be as good as the definition of the test allows. By contrast, BDD has strict rules on how to write and define features. These are designed to ensure the tests align properly with the needs of the business. It does this using a domain-specific language. Several of these exist, but probably the most popular is [[Gherkin]], which is used by the [Cucumber](https://cucumber.io/) BDD software.

Having defined your features, BDD uses its tools to create the method that will implement the test for each feature. The language used for these methods will depend on the language supported by the tool. Cucumber was designed for Ruby, but you can also use Gherkin to generate Java, JavaScript or Python methods.

Cucumber reads Gherkin tests and validates that the code performs as it should. It does this by working through Gherkin scenarios and steps. (More on this below). Cucumber will then create a report showing of each step and scenario was successful or if it fails.














#### References
[YouTube](https://www.youtube.com/watch?v=ydddSkVz_a8)
[Functionize.com](https://www.functionize.com/blog/behavior-driven-development-without-the-pain)
