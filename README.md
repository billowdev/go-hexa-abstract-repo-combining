# go-repo-abstract-repo-combining
Abstract Repository Combining Two/Multiple Repositories (OrderDocumentRepo)

## Abstract Repository Combining Two/Multiple Repositories (OrderDocumentRepo)
In this approach, you create an OrderDocumentRepo that combines both the OrderRepo and DocumentRepo into a single abstract repository, managing the transaction within this repository.

`Pros`:

- Single Responsibility: Encapsulates the entire transaction logic related to both orders and documents within a single repository, making it easy to manage.
- Consistency: Ensures that both order and document operations are tightly coupled within the same transaction scope, reducing the risk of partial failures.

`Cons`:

- Complexity: The repository becomes more complex as it handles more than one entity, potentially leading to a violation of the Single Responsibility Principle.
Tight Coupling: Tightly couples OrderRepo and DocumentRepo, making it harder to reuse or test them independently.
- Scalability: If more repositories need to be added to the transaction, the OrderDocumentRepo would have to be modified, reducing flexibility.

`Best Practice`:

- This approach is suitable when the operations on orders and documents are always tied together and never operate independently.
- It can be useful when you need to ensure consistency between two repositories that are closely related and where changes are always made in tandem.
