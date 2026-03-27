# Clean-Code-book-review.

Book Review

## Chapter 2: Meaningful Names
Good naming is one of the most important things in programming. Names should reveal intention, be searchable, and free of unnecessary encoding. In the name, nothing should add mental overhead without value.
Some ground rules: 
Classes should use noun phrases, methods should use verb phrases, and a consistent vocabulary should be maintained across the codebase, avoid synonyms like fetch, retrieve, and get, pick one and remain consistent with it. Clarity always beats cleverness, and good naming is a mark of professional, reader-focused and clean code.

#### Naming Rules

Use intention-revealing names
Make names searchable 
Avoid encodings like Hungarian Notation or m_ prefixes
Avoid mental mapping -dont't make it such that readers have to scratch their head all over
Class names should be nouns or noun phrases
Method names should be verbs or verb phrases
Don't use jokes/slang as names
Pick one word per concept and use it consistently (Don'y mix synonyms)
Prefer domain names where applicable
Use problem domain names when no technical term exists
Add meaningful context through classes, functions, or namespaces
Don't add unnecessary prefixes to names



## Chapter 3: Functions
Commands and queries should be clearly separated, and exceptions are prefered to returning error codes since it forces callers to handle errors immediately and create deeply nested hard-to-read code. Error handling should be extracted into its own functions, keeping the "happy path" logic clean and separate.

Duplication is one of the greatest evils in programming. 

Good functions emerge through drafting, refactoring, and refinement and not perfection on first attempt.

#### Rules for Writing Clean Functions
Separate commands from queries (a function should either do something or answer something, not do both).
Prefer exceptions over returning error codes
Extract try/catch blocks into their own dedicated functions
Don't repeat yourself (DRY) (eliminate duplication wherever possible).
Keep functions small enough. 
Avoid goto statements.


## Chapter 4: Comments
Bad comments are worse than no comments. They clutter the code, mislead readers, and tend to become inaccurate over time. Attributions, commented-out code, HTML in comments, and comments that describe distant parts of the system rather than the local code are all harmful practices and should be completely avoided. Well-named functions and clean structure can greatly eliminate the need for comments.

#### Rules for Comments
Never comment out code, just delete it.
Keep comments local (In scope)
Don't include excessive historical or irrelevant detail in comments
Ensure the connection between a comment and its code is immediately obvious
Short, well-named functions don't need comment headers

## Chapter 6: Objects
Objects hide data behind abstractions and expose behaviour, while data structures expose their data and have no meaningful behaviour. There is a law called the Law of Demeter, which warns against modules knowing too much about the internals of other objects, and cautions against "train wreck" method chains and hybrid structures that try to be both objects and data structures. The choice between objects and data structures is not really beacuse one is better but rather is need based.

#### Core Concepts
###### Objects vs Data Structures

Objects hide data and expose functions that operate on it
Data structures expose data and have no meaningful behaviour

The Trade-off

Procedural/data structure code: easy to add new functions but hard to add new data types
Object code: easy to add new data types but hard to add new functions
Neither is always better just choose whichever fits per time

###### The Law of Demeter

A method should only call methods on: its own class, objects it created, objects passed as arguments, or objects held as instance variables
Never call methods on objects returned by other method calls
In short, talk to friends, not strangers


#### Rules & Pitfalls to Avoid

Don't expose internal data through blind getters and setters, instead, use meaningful abstractions
Avoid "train wreck" method chains like ctxt.getOptions().getScratchDir().getAbsolutePath()
Never create hybrid structures that are half object, half data structure
Don't add business logic methods to Active Records or DTOs
Prefer telling an object to do something rather than asking it for its internals
Don't use Javadoc-style comments for non-public internal code


The "everything is an object" mindset is a myth, sometimes simple data structures with procedures are the right tool for the job
