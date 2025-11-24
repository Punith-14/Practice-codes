# Unit 3: Knowledge Representation and Logic - Complete Exam Guide

---

## PART 1: KNOWLEDGE REPRESENTATION FUNDAMENTALS

### 1. INTRODUCTION TO KNOWLEDGE REPRESENTATION

**What is Knowledge Representation (KR)?**
- Process of converting real-world information, facts, and relationships into a format that an AI system can understand, store, and reason with.
- Bridges the gap between how humans think and how computers process information.

**Why is Knowledge Representation Important?**
- Enables AI systems to reason about the world
- Stores domain-specific expertise
- Allows automated decision-making
- Essential for expert systems and intelligent agents

**Key Challenge:** Real-world knowledge is often vague, incomplete, uncertain, and dynamic.

---

## 2. REPRESENTATION AND MAPPINGS

### Definition:
**Representation** is the encoding of knowledge using specific symbols, structures, and formats.
**Mapping** is the translation between the real world and the internal representation (and vice versa).

### The Representation Problem:
```
Real World (Facts, Objects, Relationships)
            ↓ (Mapping)
Internal Representation (Symbols, Structures)
            ↓ (Processing)
Conclusions and Actions
```

### Example:
**Real World:** "John is a student who studies Computer Science"
**Representation:** Student(John), Studies(John, ComputerScience)
**Mapping Process:** Extract relevant facts and encode them in predicate logic

### Good Representation Must:
- Be **complete** - capture all relevant information
- Be **concise** - avoid redundancy
- Support efficient **reasoning and inference**
- Be **domain-appropriate** - suited to the problem

---

## 3. DIFFERENT APPROACHES TO KNOWLEDGE REPRESENTATION

### 1. **Logical Representation**
- Uses formal logic (propositional, predicate logic)
- Facts and rules expressed as logical formulas
- Supports rigorous inference
- **Example:** ∀x (Student(x) → EnrolledInSchool(x))

### 2. **Procedural Representation**
- Knowledge encoded as procedures/algorithms
- "How to do something" rather than "what is true"
- Efficient for certain types of problems
- **Example:** A sorting algorithm encodes knowledge about ordering

### 3. **Semantic Networks**
- Knowledge represented as graphs with nodes (concepts) and edges (relationships)
- Visual and intuitive
- Supports inheritance and property propagation
- **Example:** 
```
Dog ──is-a──> Animal
     ──has──> Four_Legs
     ──has──> Tail
```

### 4. **Frames (Structured Objects)**
- Knowledge organized as structured records with attributes and values
- Similar to objects in programming
- Supports defaults and inheritance
- **Example:** 
```
Frame: Dog
  - species: Canine
  - legs: 4
  - canEat: [meat, kibble]
  - sound: bark
```

### 5. **Production Rules**
- Knowledge as IF-THEN rules
- Simple and intuitive for expert systems
- **Example:** IF (temperature > 100°C) THEN (water_boils = true)

### 6. **Ontologies**
- Formal specification of concepts, properties, and relationships
- Machine-readable and shareable
- Used in semantic web and knowledge graphs

---

## 4. ISSUES IN KNOWLEDGE REPRESENTATION

### Issue 1: **Expressiveness**
- **Problem:** Can the system represent all necessary concepts and relationships?
- **Challenge:** Some real-world facts are hard to encode formally
- **Solution:** Choose representation that captures domain requirements

### Issue 2: **Efficiency**
- **Problem:** How fast can the system retrieve and reason about knowledge?
- **Challenge:** Large knowledge bases can be slow to search
- **Solution:** Use indexing, caching, and optimized data structures

### Issue 3: **Incompleteness**
- **Problem:** Real-world knowledge is often incomplete
- **Challenge:** System must handle missing information gracefully
- **Solution:** Use defaults, assumptions, or probabilistic reasoning

### Issue 4: **Ambiguity and Vagueness**
- **Problem:** Natural language concepts are often vague ("tall", "hot", "nearby")
- **Challenge:** Hard to encode precisely in formal systems
- **Solution:** Use fuzzy logic or multiple interpretations

### Issue 5: **Frame Problem**
- **Problem:** How to represent what changes and what doesn't when an action occurs?
- **Challenge:** Keeping track of all effects of actions is complex
- **Solution:** Use situation calculus or event logic

### Issue 6: **Reasoning with Uncertainty**
- **Problem:** Real-world knowledge involves uncertainty and probability
- **Challenge:** Pure logic assumes certainty
- **Solution:** Use Bayesian networks, probabilistic logic, or fuzzy logic

### Issue 7: **Scalability**
- **Problem:** As knowledge bases grow, reasoning becomes slower
- **Challenge:** Maintaining consistency in large systems
- **Solution:** Use modular representations and hierarchical reasoning

---

---

## PART 2: PROPOSITIONAL LOGIC

### 1. WHAT IS PROPOSITIONAL LOGIC?

**Definition:**
Propositional logic (also called Boolean logic) is a formal system that deals with **propositions** - statements that are either **true (T) or false (F)**.

**Historical Importance:**
- Foundation of classical logic
- Fundamental to algorithms and software verification
- Building block for more complex logical systems

**Examples of Propositions:**
- "It is raining." ✓ (can be true or false)
- "The earth is flat." ✓ (can be true or false)
- "What time is it?" ✗ (not a proposition - it's a question)
- "x > 5" ✗ (not a proposition - depends on x's value)

---

## 2. REPRESENTATION IN PROPOSITIONAL LOGIC

### Syntax (Formal Structure):

**Propositions (Atomic Formulas):**
- Represented by lowercase letters: p, q, r, s, ...
- Each proposition represents a basic fact
- Example: p = "It is raining"

**Logical Connectives (Operators):**
- Combine propositions to form complex formulas

| Connective | Symbol | Name | Meaning |
|-----------|--------|------|---------|
| AND | ∧ | Conjunction | Both must be true |
| OR | ∨ | Disjunction | At least one must be true |
| NOT | ¬ or ~ | Negation | Reverses truth value |
| IF-THEN | → | Implication | If premise then conclusion |
| IF AND ONLY IF | ↔ | Biconditional | Both have same truth value |

**Truth Tables for Connectives:**

**Conjunction (AND): p ∧ q**
| p | q | p ∧ q |
|---|---|-------|
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | F |

**Disjunction (OR): p ∨ q**
| p | q | p ∨ q |
|---|---|-------|
| T | T | T |
| T | F | T |
| F | T | T |
| F | F | F |

**Negation (NOT): ¬p**
| p | ¬p |
|---|-----|
| T | F |
| F | T |

**Implication (IF-THEN): p → q**
| p | q | p → q |
|---|---|-------|
| T | T | T |
| T | F | F |
| F | T | T |
| F | F | T |

**Biconditional (IF AND ONLY IF): p ↔ q**
| p | q | p ↔ q |
|---|---|-------|
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | T |

### Semantics (Meaning):

**Truth Values:** Each proposition has exactly one truth value: True or False

**Interpretation:** Assignment of truth values to all propositions in a formula
- Example: For formula (p ∧ q) → r
- One interpretation: p=T, q=F, r=T
- Another interpretation: p=F, q=F, r=F

**Satisfiability:**
- A formula is **satisfiable** if there exists an interpretation that makes it true
- A formula is **unsatisfiable** (contradictory) if no interpretation makes it true
- A formula is **valid** (tautology) if all interpretations make it true

### Examples of Propositional Representation:

**Example 1:** "If it rains, the ground will be wet"
- p = "It rains"
- q = "The ground is wet"
- Representation: p → q

**Example 2:** "Either the light is on or the light is off (but not both)"
- p = "Light is on"
- q = "Light is off"
- Representation: (p ∨ q) ∧ ¬(p ∧ q)

**Example 3:** "If both Mary and John come to the party, then it will be fun"
- p = "Mary comes"
- q = "John comes"
- r = "Party is fun"
- Representation: (p ∧ q) → r

---

## 3. INFERENCE IN PROPOSITIONAL LOGIC

**Definition:** Logical inference is the process of deriving **new conclusions** from **given premises** (known facts).

### Methods of Inference:

#### 1. **Truth Tables Method:**
- Create a table showing truth values of formula for all possible interpretations
- Check if conclusion is true whenever all premises are true
- **Advantage:** Complete and guaranteed to work
- **Disadvantage:** Becomes impractical with many propositions (2^n rows)

**Example:**
To prove: From (p → q) and p, infer q

| p | q | p → q | Premises True? | q |
|---|---|-------|----------------|---|
| T | T | T | Yes | T |
| T | F | F | No | - |
| F | T | T | No | - |
| F | F | T | No | - |

✓ Whenever premises are true (row 1), conclusion is true. Inference is valid.

#### 2. **Natural Deduction Method:**
- Use logical rules of inference to derive conclusions step by step
- More efficient than truth tables for complex formulas
- Based on intuitive reasoning patterns

---

## 4. REASONING PATTERNS IN PROPOSITIONAL LOGIC

### 1. **Modus Ponens (Affirming the Antecedent)**

**Rule:** 
```
Premise 1: p → q  (If p then q)
Premise 2: p      (p is true)
___________________
Conclusion: q     (Therefore q is true)
```

**Explanation:** If we know a rule (p → q) and the condition (p) is true, we can conclude the consequence (q).

**Real-World Example:**
```
Premise 1: If it rains, the ground will be wet.
Premise 2: It is raining.
___________________
Conclusion: The ground is wet.
```

**Another Example:**
```
Premise 1: If you study hard, you will pass. (study → pass)
Premise 2: You are studying hard. (study = true)
___________________
Conclusion: You will pass. (pass = true)
```

---

### 2. **Modus Tollens (Denying the Consequent)**

**Rule:**
```
Premise 1: p → q     (If p then q)
Premise 2: ¬q        (q is false)
___________________
Conclusion: ¬p       (Therefore p is false)
```

**Explanation:** If we know a rule and the consequence is false, we can conclude the antecedent must be false.

**Real-World Example:**
```
Premise 1: If it rains, the ground will be wet.
Premise 2: The ground is not wet.
___________________
Conclusion: It is not raining.
```

**Another Example:**
```
Premise 1: If you study hard, you will pass. (study → pass)
Premise 2: You did not pass. (pass = false)
___________________
Conclusion: You did not study hard. (study = false)
```

---

### 3. **Disjunctive Syllogism (Eliminating Alternatives)**

**Rule:**
```
Premise 1: p ∨ q    (Either p or q is true)
Premise 2: ¬p       (p is false)
___________________
Conclusion: q       (Therefore q is true)
```

**Explanation:** If we have two possibilities and one is eliminated, the other must be true.

**Real-World Example:**
```
Premise 1: Either it is raining or it is sunny.
Premise 2: It is not raining.
___________________
Conclusion: It is sunny.
```

**Another Example:**
```
Premise 1: The animal is either a cat or a dog.
Premise 2: It is not a cat.
___________________
Conclusion: It is a dog.
```

---

### 4. **Hypothetical Syllogism (Chaining Implications)**

**Rule:**
```
Premise 1: p → q  (If p then q)
Premise 2: q → r  (If q then r)
___________________
Conclusion: p → r (Therefore if p then r)
```

**Explanation:** We can chain implications together.

**Real-World Example:**
```
Premise 1: If it rains, the ground gets wet.
Premise 2: If the ground is wet, plants grow.
___________________
Conclusion: If it rains, plants grow.
```

---

### 5. **Conjunction (Combining Propositions)**

**Rule:**
```
Premise 1: p       (p is true)
Premise 2: q       (q is true)
___________________
Conclusion: p ∧ q  (Therefore both are true)
```

**Real-World Example:**
```
Premise 1: John is intelligent.
Premise 2: John is hardworking.
___________________
Conclusion: John is both intelligent and hardworking.
```

---

### 6. **Simplification (Extracting From Conjunction)**

**Rule:**
```
Premise 1: p ∧ q  (Both p and q are true)
___________________
Conclusion: p     (Therefore p is true)
```

OR

```
Premise 1: p ∧ q  (Both p and q are true)
___________________
Conclusion: q     (Therefore q is true)
```

**Real-World Example:**
```
Premise 1: The car is red and fast.
___________________
Conclusion: The car is red.
```

---

## 5. RESOLUTION IN PROPOSITIONAL LOGIC

### Definition:
**Resolution** is a rule of inference that leads to a **refutation proof by contradiction**. It's particularly useful for automated theorem proving.

### Core Concept:
- Convert propositions to **Conjunctive Normal Form (CNF)** - a standard form
- Apply resolution rule repeatedly to derive contradictions
- If a contradiction is found, the original statement is unsatisfiable

### Conjunctive Normal Form (CNF):
A formula in CNF is a conjunction (AND) of disjunctions (OR).
- **Clause:** A disjunction of literals (e.g., p ∨ ¬q ∨ r)
- **CNF Formula:** (p ∨ ¬q) ∧ (q ∨ r) ∧ (¬p ∨ s)

### The Resolution Rule:

**Basic Resolution:**
```
Clause 1: (p ∨ A)      (Contains p)
Clause 2: (¬p ∨ B)     (Contains ¬p)
__________________________________________________________
Resolvent: (A ∨ B)     (Both p and ¬p canceled out)
```

**Explanation:** If two clauses contain opposite literals (p and ¬p), we can combine the remaining parts.

### Worked Examples:

**Example 1: Simple Resolution**
```
Given Clause 1: (p ∨ q)       "Either p or q"
Given Clause 2: (¬q ∨ r)      "Either not q or r"
__________________________________________________________
Resolution Step: (p ∨ r)      "Either p or r"

Why? If q is true, then from Clause 2, r must be true.
     If q is false, then from Clause 1, p must be true.
     So either p or r must be true.
```

**Example 2: Multiple Resolution Steps**
```
Given:
1. p ∨ q          "Either p or q"
2. ¬p ∨ r         "Either not p or r"
3. ¬r             "Not r"

Prove: q

Step 1: Resolve clauses 2 and 3
        (¬p ∨ r) with (¬r) → ¬p
        
Step 2: Resolve clause 1 with ¬p
        (p ∨ q) with ¬p → q
        
Conclusion: q ✓
```

**Example 3: Proving by Contradiction**
```
Goal: Prove (p → q) from premises (p → q)

To prove by resolution:
1. Assume the negation of the goal
2. Goal: p → q  (equivalent to ¬p ∨ q)
3. Negation: ¬(¬p ∨ q) = (p ∧ ¬q)
4. Add to premises
5. Derive contradiction (empty clause)
6. If contradiction found, original goal is true
```

### Process for Proof by Resolution:

1. **Convert all formulas to CNF**
   - Example: p → q becomes ¬p ∨ q

2. **Negate the goal** and add to premises
   - Example: To prove q, add ¬q

3. **Apply resolution rule repeatedly**
   - Pick two clauses with opposite literals
   - Create resolvent
   - Add to clause set

4. **Stop when:**
   - Empty clause is derived (contradiction found) → Goal is true
   - No more resolutions possible → Goal cannot be proven

### Advantages of Resolution:
- ✓ Systematic and complete
- ✓ Works well for automated theorem proving
- ✓ Single rule of inference needed
- ✓ Can prove unsatisfiability

### Disadvantages of Resolution:
- ✗ Can generate many unnecessary clauses
- ✗ Less intuitive than natural deduction
- ✗ Requires converting to CNF

---

## 6. COMPLEX EXAMPLE IN PROPOSITIONAL LOGIC

**Problem:**
Given premises:
1. p → q  (If p then q)
2. q → r  (If q then r)
3. ¬r     (r is false)

Prove: ¬p (Prove that p is false)

**Solution Using Modus Tollens:**

Step 1: From premise 2 (q → r) and premise 3 (¬r), apply Modus Tollens
```
q → r  and  ¬r  →  ¬q
(If q then r, and r is false, so q must be false)
```

Step 2: From premise 1 (p → q) and derived ¬q, apply Modus Tollens
```
p → q  and  ¬q  →  ¬p
(If p then q, and q is false, so p must be false)
```

**Conclusion: ¬p is true** ✓

**Solution Using Resolution:**

Convert to CNF:
- p → q becomes ¬p ∨ q
- q → r becomes ¬q ∨ r
- ¬r stays ¬r

Prove ¬p by assuming p and deriving contradiction:

1. ¬p ∨ q
2. ¬q ∨ r
3. ¬r
4. p (assumption to prove by contradiction)

Resolutions:
- Clause 2 (¬q ∨ r) with Clause 3 (¬r) → ¬q
- Clause 1 (¬p ∨ q) with derived ¬q → ¬p
- Clause 4 (p) with derived ¬p → □ (empty clause, contradiction)

Since assuming p leads to contradiction, ¬p must be true. ✓

---

---

## PART 3: PREDICATE LOGIC

### 1. WHAT IS PREDICATE LOGIC?

**Definition:**
Predicate logic (First-Order Logic, FOL) extends propositional logic by dealing with **objects**, their **properties**, and **relationships** between them. It uses **predicates**, **variables**, and **quantifiers**.

**Key Differences from Propositional Logic:**

| Aspect | Propositional Logic | Predicate Logic |
|--------|-------------------|-----------------|
| Basic Units | Simple propositions | Predicates with arguments |
| Variables | None | x, y, z, ... represent objects |
| Quantifiers | None | ∀ (for all), ∃ (there exists) |
| Expressiveness | Limited to propositions | Can express about objects and properties |
| Reasoning | Modus Ponens, etc. | + Unification and instantiation |

**Why Use Predicate Logic?**
- Can express relationships between multiple objects
- Can express generalizations (e.g., "All humans are mortal")
- More powerful than propositional logic
- Foundation of logic programming (Prolog)

---

## 2. REPRESENTATION IN PREDICATE LOGIC

### Syntax (Formal Structure):

#### 1. **Predicates**
- Symbols representing properties or relationships
- Examples: Student(x), Teaches(x, y), Color(x, red)
- **Arity:** Number of arguments
  - Arity 1: Student(John) - unary predicate
  - Arity 2: Teaches(Alice, CS101) - binary predicate
  - Arity 3: Gives(John, Book, Mary) - ternary predicate

#### 2. **Variables**
- Represent objects in the domain
- Lowercase letters: x, y, z, ...
- Example: Student(x) - "x is a student" (x can be any object)

#### 3. **Constants**
- Specific objects in the domain
- Uppercase letters or proper nouns: John, Mary, CS101, red
- Example: Student(John) - "John is a student"

#### 4. **Functions**
- Map objects to other objects
- Notation: f(x), father(John), sqrt(x)
- Example: Father(x) - "the father of x"

#### 5. **Quantifiers**

**Universal Quantifier (∀):** "For all" or "every"
```
∀x Student(x) → EnrolledInSchool(x)
"For all x, if x is a student, then x is enrolled in school"
"All students are enrolled in school"
```

**Existential Quantifier (∃):** "There exists" or "some"
```
∃x Student(x) ∧ GradesA(x)
"There exists an x such that x is a student and x gets A grades"
"Some students get A grades"
```

### Semantics (Meaning):

#### 1. **Domain of Discourse**
- The set of all possible objects the variables can refer to
- Examples: 
  - {1, 2, 3, 4, 5} (numbers)
  - {John, Mary, Bob} (people)
  - {All animals}

#### 2. **Interpretation**
- Assigns meaning to predicates and constants
- Example for domain {John, Mary}:
  - Student(John) = true
  - Student(Mary) = true
  - Teaches(John, Mary) = true

#### 3. **Truth Value**
- A FOL formula is true if it holds under the interpretation

### Examples of Predicate Logic Representation:

**Example 1: Simple Facts**
- Real world: "John is a student"
- Representation: Student(John)
- Domain: {John, Mary, Bob} (students)
- Predicate: Student(_)

**Example 2: Relationships**
- Real world: "Alice teaches Computer Science to Bob"
- Representation: Teaches(Alice, Bob, ComputerScience)
- Predicates: Teaches(_, _, _)

**Example 3: Universal Statements**
- Real world: "All humans are mortal"
- Representation: ∀x (Human(x) → Mortal(x))
- Domain: {all living things}
- Predicates: Human(_), Mortal(_)

**Example 4: Existential Statements**
- Real world: "Some students passed the exam"
- Representation: ∃x (Student(x) ∧ Passed(x, Exam))
- Domain: {all people}
- Predicates: Student(_), Passed(_, _)

**Example 5: Complex Statements**
- Real world: "Every student has a teacher who teaches them"
- Representation: ∀x (Student(x) → ∃y (Teacher(y) ∧ Teaches(y, x)))
- Domain: {all people}
- Predicates: Student(_), Teacher(_), Teaches(_, _)

**Example 6: Combining Quantifiers**
- Real world: "There is a professor who teaches all students"
- Representation: ∃y (Professor(y) ∧ ∀x (Student(x) → Teaches(y, x)))
- Domain: {all people}
- Predicates: Professor(_), Student(_), Teaches(_, _)

---

## 3. SIMPLE FACTS IN LOGIC

### Definition:
Simple facts are basic assertions about objects and their properties or relationships.

### Types of Simple Facts:

#### 1. **Property Facts** (Unary Predicates)
Express that an object has a property.

```
Predicate(object)
```

Examples:
- Red(car) - "The car is red"
- Student(John) - "John is a student"
- Tall(Mary) - "Mary is tall"
- Prime(7) - "7 is prime"

#### 2. **Relationship Facts** (Binary and Higher Predicates)
Express relationships between objects.

```
Predicate(object1, object2, ...)
```

Examples:
- Likes(John, Mary) - "John likes Mary"
- Teaches(Professor, Course) - "Professor teaches Course"
- Gives(John, Book, Mary) - "John gives Book to Mary"
- Between(A, B, C) - "B is between A and C"

#### 3. **Negative Facts**
Express what is not true.

```
¬Predicate(object)
```

Examples:
- ¬Likes(John, Vegetables) - "John doesn't like vegetables"
- ¬Student(Bob) - "Bob is not a student"

---

## 4. REPRESENTING INSTANCE AND ISA RELATIONSHIPS

### ISA Relationship (Classification):

**Definition:** Represents **class membership** - an object is an instance of a class.

**Syntax:**
```
Isa(object, class)  or  object ∈ class
```

**Examples:**
- Isa(Tweety, Bird) - "Tweety is a bird"
- Isa(John, Human) - "John is a human"
- Isa(Car, Vehicle) - "A car is a vehicle"

### Instance Relationship:

**Definition:** Represents specific **property instances** for individual objects.

**Syntax:**
```
PropertyOf(object, property, value)
```

**Examples:**
- Color(Ferrari, Red) - "The Ferrari is red"
- Age(John, 25) - "John is 25 years old"
- Capital(Paris, France) - "Paris is the capital of France"

### Inheritance in ISA Relationships:

ISA relationships support **inheritance** - properties of a class apply to all instances.

**Example:**
```
∀x (Isa(x, Bird) → CanFly(x))
"All birds can fly"

Isa(Tweety, Bird)
"Tweety is a bird"

Therefore: CanFly(Tweety)
"Tweety can fly"
```

### Combining ISA with Instances:

```
∀x (Isa(x, Human) → HasHearts(x))
"All humans have hearts"

Isa(John, Human)
"John is a human"

Therefore: HasHearts(John)
"John has a heart"
```

### Complete Example:

**Real World Scenario:** 
"Tweety is a bird. Birds can fly. Therefore, Tweety can fly."

**Representation:**
1. Isa(Tweety, Bird) - Instance: Tweety is a bird
2. ∀x (Isa(x, Bird) → CanFly(x)) - Rule: All birds can fly
3. Isa(Tweety, Bird) → CanFly(Tweety) - Instantiate with Tweety
4. CanFly(Tweety) - Conclusion: Tweety can fly

---

## 5. COMPUTABLE FUNCTIONS AND PREDICATES

### Computable Functions:

**Definition:** Functions that compute new values from given inputs.

**Syntax:**
```
FunctionName(arguments) = result
```

**Examples:**

1. **Arithmetic Functions:**
   ```
   Father(x) = the biological father of x
   Age(x) = the age of x
   Add(a, b) = a + b
   ```

2. **List Functions:**
   ```
   Head([H|T]) = H
   Tail([H|T]) = T
   Length([1,2,3]) = 3
   ```

3. **Date/Time Functions:**
   ```
   Year(Date) = the year component of Date
   Month(Date) = the month component of Date
   ```

### Properties of Computable Functions:

1. **Deterministic:** Same input always produces same output
2. **Total:** Defined for all valid inputs
3. **Computable:** Can be computed by an algorithm

### Computable Predicates:

**Definition:** Predicates that can be evaluated through computation.

**Examples:**

1. **Comparison Predicates:**
   ```
   GreaterThan(x, y) = true if x > y
   LessThan(x, y) = true if x < y
   Equal(x, y) = true if x = y
   ```

2. **Arithmetic Predicates:**
   ```
   Prime(n) = true if n is prime
   Even(n) = true if n is even
   Perfect(n) = true if n is a perfect number
   ```

3. **List Predicates:**
   ```
   Member(x, List) = true if x is in List
   Sorted(List) = true if List is sorted
   ```

### Example Combining Functions and Predicates:

```
Problem: "John's father is older than John"

Representation:
Age(Father(John)) > Age(John)

Evaluation:
1. Compute Father(John) = David (the function)
2. Compute Age(David) = 55
3. Compute Age(John) = 25
4. Evaluate 55 > 25 = true (the predicate)

Conclusion: The statement is true
```

---

## 6. INFERENCE IN FIRST-ORDER LOGIC

**Definition:** Logical inference in FOL is the process of deriving new conclusions from axioms and rules using formal methods.

### Key Inference Techniques:

#### 1. **Unification**

**Definition:** Process of finding a substitution that makes two terms identical.

**Notation:** σ = [x/a, y/b] means substitute x with a and y with b

**Example 1:**
```
Goal: Find substitution to make P(x) and P(John) identical
Solution: σ = [x/John]
Result: P(John) and P(John) are identical
```

**Example 2:**
```
Goal: Find substitution to make Teaches(x, y) and Teaches(Alice, CS101) identical
Solution: σ = [x/Alice, y/CS101]
Result: Teaches(Alice, CS101) and Teaches(Alice, CS101) are identical
```

**Example 3:**
```
Goal: Find substitution to make Likes(x, x) and Likes(John, y) identical
Solution: Impossible - x cannot be both John and y
Result: These don't unify
```

#### 2. **Universal Instantiation**

**Definition:** From a universally quantified statement, derive a specific instance.

**Rule:**
```
From: ∀x P(x)
Derive: P(a) for any specific constant a
```

**Examples:**

**Example 1: Simple Case**
```
Given: ∀x (Human(x) → Mortal(x))
         "All humans are mortal"
         
Instantiate with x = Socrates:
Result: Human(Socrates) → Mortal(Socrates)
        "If Socrates is human, then Socrates is mortal"
```

**Example 2: With Multiple Variables**
```
Given: ∀x ∀y (Parent(x, y) → Loves(x, y))
       "For all x and y, if x is parent of y, then x loves y"
       
Instantiate with x = John, y = Mary:
Result: Parent(John, Mary) → Loves(John, Mary)
        "If John is parent of Mary, then John loves Mary"
```

#### 3. **Existential Instantiation**

**Definition:** From an existentially quantified statement, introduce a witness.

**Rule:**
```
From: ∃x P(x)
Derive: P(c) for some specific constant c (called Skolem constant)
```

**Examples:**

**Example 1:**
```
Given: ∃x (Student(x) ∧ Grades(x, A))
       "There exists a student with grade A"
       
Instantiate with x = John (a witness):
Result: Student(John) ∧ Grades(John, A)
        "John is a student with grade A"
```

**Example 2:**
```
Given: ∃x (Loves(Mary, x))
       "Mary loves someone"
       
Instantiate with x = John (a witness):
Result: Loves(Mary, John)
        "Mary loves John"
```

#### 4. **Generalization (Reverse of Instantiation)**

**Definition:** From a specific instance, derive a universal statement.

**Rule:**
```
From: P(x) where x is arbitrary
Derive: ∀x P(x)
```

**Example:**
```
Given: P(x) holds for arbitrary x (not specifically John, just any x)
We can generalize: ∀x P(x)
```

---

## 7. REASONING PATTERNS IN FIRST-ORDER LOGIC

### 1. **Universal Instantiation with Modus Ponens**

**Pattern:**
```
Rule 1: ∀x (P(x) → Q(x))
Fact 1: P(a)
_________________________________
Conclusion: Q(a)
```

**Process:**
1. Instantiate the universal rule with specific object a: P(a) → Q(a)
2. Apply Modus Ponens with fact P(a): Derive Q(a)

**Real-World Example:**
```
Rule 1: ∀x (Student(x) → CanEnroll(x, Courses))
        "All students can enroll in courses"

Fact 1: Student(John)
        "John is a student"

Conclusion: CanEnroll(John, Courses)
           "John can enroll in courses"
```

### 2. **Universal Instantiation with Modus Tollens**

**Pattern:**
```
Rule 1: ∀x (P(x) → Q(x))
Fact 1: ¬Q(a)
_________________________________
Conclusion: ¬P(a)
```

**Real-World Example:**
```
Rule 1: ∀x (Bird(x) → CanFly(x))
        "All birds can fly"

Fact 1: ¬CanFly(Penguin)
        "A penguin cannot fly"

Conclusion: ¬Bird(Penguin)
           "Penguin is not a bird" (or we need to revise the rule)
```

### 3. **Instantiation with Existential Elimination**

**Pattern:**
```
Rule 1: ∀x (P(x) → Q(x))
Fact 1: ∃y P(y)
_________________________________
Conclusion: ∃y Q(y)
```

**Process:**
1. From ∃y P(y), introduce witness: P(c) for some c
2. Instantiate rule with c: P(c) → Q(c)
3. Apply Modus Ponens: Q(c)
4. Generalize back: ∃y Q(y)

**Real-World Example:**
```
Rule 1: ∀x (Student(x) → CanEnroll(x, Courses))
        "All students can enroll in courses"

Fact 1: ∃y Student(y)
        "There exists someone who is a student"

Conclusion: ∃y CanEnroll(y, Courses)
           "Someone can enroll in courses"
```

### 4. **Substitution and Inference**

**Pattern:**
```
Rule 1: ∀x P(x, f(x))
Fact 1: A particular relationship about f and objects
_________________________________
Conclusion: Derived fact
```

**Real-World Example:**
```
Rule 1: ∀x (Person(x) → HasParents(x, Father(x), Mother(x)))
        "Every person has a father and mother"

Fact 1: Person(John)
        "John is a person"

Conclusion: HasParents(John, Father(John), Mother(John))
           "John has a father and mother"
```

---

## 8. RESOLUTION IN FIRST-ORDER LOGIC

### Definition:
**Resolution in FOL** is a rule of inference used for proving **unsatisfiability** of a set of FOL clauses. It extends propositional resolution by incorporating **unification**.

### Key Difference from Propositional Resolution:
- Propositional: Directly match opposite literals
- First-Order: Use **unification** to find matching patterns

### The Resolution Rule for FOL:

**Basic Rule:**
```
Clause 1: P(x) ∨ A
Clause 2: ¬P(a) ∨ B
_________________________________
Resolvent: A[x/a] ∨ B   (where σ = [x/a] is the unifier)
```

**Explanation:**
1. Find two clauses with opposite literals
2. Find a unification that makes them match
3. Combine the remaining parts

### Worked Examples:

**Example 1: Simple Unification**
```
Given Clause 1: P(x) ∨ Q(x)        "P(x) or Q(x)"
Given Clause 2: ¬P(John) ∨ R       "Not P(John) or R"

Unification: x = John
Resolvent: Q(John) ∨ R             "Q(John) or R"

Why? If x is John:
  - If P(John) is false, then Q(John) must be true (from Clause 1)
  - So either Q(John) or R is true (from Clause 2)
```

**Example 2: With Functions**
```
Given Clause 1: P(f(x)) ∨ Q(x)
Given Clause 2: ¬P(f(a)) ∨ R(a)

Unification: x = a
Resolvent: Q(a) ∨ R(a)
```

**Example 3: Multiple Variables**
```
Given Clause 1: Teaches(x, y) ∨ Studies(x)
Given Clause 2: ¬Teaches(Alice, CS101) ∨ Passes(Alice)

Unification: x = Alice, y = CS101
Resolvent: Studies(Alice) ∨ Passes(Alice)
           "Alice studies or Alice passes"
```

### Process for Proof by Resolution:

1. **Convert all formulas to Conjunctive Normal Form (CNF)**
   - Express as conjunction (AND) of clauses
   - Each clause is a disjunction (OR) of literals

2. **Negate the goal** and add to premise clauses

3. **Apply FOL resolution repeatedly:**
   - Find two clauses with opposite literals
   - Find a unification that matches them
   - Create resolvent
   - Add resolvent to clause set

4. **Terminate when:**
   - Empty clause (□) is derived → Goal is proven
   - No more resolutions possible → Goal cannot be proven

### Example: Proof by FOL Resolution

**Problem:**
```
Rule 1: ∀x (Student(x) → CanEnroll(x))
Rule 2: ∀x (CanEnroll(x) → InSchool(x))
Fact 1: Student(John)

Prove: InSchool(John)
```

**Solution:**

Step 1: Convert to CNF
- Rule 1: ¬Student(x) ∨ CanEnroll(x)
- Rule 2: ¬CanEnroll(x) ∨ InSchool(x)
- Fact 1: Student(John)
- Negation of goal: ¬InSchool(John)

Step 2: Resolution
```
1. ¬Student(x) ∨ CanEnroll(x)     [Rule 1]
2. ¬CanEnroll(y) ∨ InSchool(y)   [Rule 2]
3. Student(John)                   [Fact 1]
4. ¬InSchool(John)                [Negation of goal]

Resolution of 3 and 1 (unify x with John):
5. CanEnroll(John)

Resolution of 5 and 2 (unify y with John):
6. InSchool(John)

Resolution of 6 and 4:
7. □ (Empty clause - contradiction!)
```

Since assuming ¬InSchool(John) leads to a contradiction, **InSchool(John) must be true**. ✓

---

## 9. ADVANCED EXAMPLE IN FIRST-ORDER LOGIC

**Complex Problem:**
```
Given Premises:
1. ∀x (Parent(x, y) → Loves(x, y))
   "All parents love their children"

2. ∀x ∀y (Loves(x, y) ∧ Loves(y, x) → Friends(x, y))
   "If two people love each other, they are friends"

3. Parent(Alice, Bob)
   "Alice is a parent of Bob"

4. Loves(Bob, Alice)
   "Bob loves Alice"

Prove: Friends(Alice, Bob)
```

**Solution:**

Step 1: Instantiate Rule 1 with x = Alice, y = Bob
```
Parent(Alice, Bob) → Loves(Alice, Bob)
Since Parent(Alice, Bob) is true:
→ Loves(Alice, Bob)
```

Step 2: We now know:
- Loves(Alice, Bob) ✓ (from Step 1)
- Loves(Bob, Alice) ✓ (given Fact 4)

Step 3: Instantiate Rule 2 with x = Alice, y = Bob
```
(Loves(Alice, Bob) ∧ Loves(Bob, Alice)) → Friends(Alice, Bob)
Since both conditions are true:
→ Friends(Alice, Bob) ✓
```

**Conclusion: Friends(Alice, Bob)** ✓

---

---

## EXAM SUMMARY TABLE

| Concept | Type | Definition | Example |
|---------|------|-----------|---------|
| Knowledge Representation | General | Encoding knowledge in format AI can use | Predicate logic, semantic networks |
| Representation | General | Encoding of facts using structures | Facts + Rules |
| Mapping | General | Translation between real world and internal form | Object → Predicate |
| Proposition | Propositional | Statement that is true or false | "It is raining" |
| Logical Connective | Propositional | Operator combining propositions | AND, OR, NOT, →, ↔ |
| Interpretation | Both | Assignment of truth values to propositions | p=T, q=F |
| Modus Ponens | Propositional | If p→q and p, then q | Valid inference rule |
| Resolution | Both | Refutation proof by contradiction | Combine clauses |
| Predicate | First-Order | Symbol representing property/relationship | Student(x), Teaches(x,y) |
| Variable | First-Order | Represents object in domain | x, y, z |
| Universal Quantifier | First-Order | "For all" | ∀x Student(x) |
| Existential Quantifier | First-Order | "There exists" | ∃x Student(x) |
| Unification | First-Order | Finding substitution to match terms | σ = [x/John] |
| ISA Relationship | First-Order | Class membership | Isa(John, Human) |
| Instance | First-Order | Specific property value | Age(John, 25) |
| Computable Function | First-Order | Function computing new values | Father(John) = David |
| Computable Predicate | First-Order | Predicate evaluated by computation | Prime(7) = true |

---

## IMPORTANT POINTS TO REMEMBER FOR EXAM

1. **Knowledge Representation:** Converts real-world facts into format AI systems can process and reason with

2. **Representation approaches:** Logical, procedural, semantic networks, frames, production rules, ontologies

3. **Propositional Logic:** Deals with simple true/false propositions and logical connectives

4. **Five logical connectives:** AND (∧), OR (∨), NOT (¬), IF-THEN (→), IF AND ONLY IF (↔)

5. **Inference methods:** Truth tables, natural deduction, modus ponens, modus tollens, disjunctive syllogism

6. **Reasoning patterns:** Formal ways to derive new conclusions from given premises

7. **Resolution:** Rule of inference for automated proof by contradiction

8. **Conjunctive Normal Form:** Standard form for resolution (AND of ORs)

9. **First-Order Logic:** Extends propositional logic with predicates, variables, and quantifiers

10. **Predicates:** Symbols representing properties (unary) or relationships (n-ary)

11. **Two quantifiers in FOL:** Universal (∀ = "for all") and Existential (∃ = "there exists")

12. **ISA relationships:** Express class membership (Isa(object, class))

13. **Instance relationships:** Express specific properties (Color(Car, Red))

14. **Unification:** Process of finding substitution to make terms identical

15. **Universal Instantiation:** From ∀x P(x), derive P(a) for specific a

16. **Existential Instantiation:** From ∃x P(x), derive P(c) for witness c

17. **FOL Resolution:** Resolution with unification for first-order clauses

18. **Domain of discourse:** The set of objects variables can refer to

19. **Computable functions:** Functions that compute new values (e.g., Father(x))

20. **Computable predicates:** Predicates evaluated through computation (e.g., Prime(n))

---

## SAMPLE EXAM QUESTIONS & ANSWERS

### Q1: Define Knowledge Representation and explain why it is important in AI.

**Answer:**
Knowledge Representation (KR) is the process of converting real-world information, facts, relationships, and expertise into a format that an AI system can understand, store, and reason with. It bridges the gap between how humans think and how computers process information.

Importance in AI:
- Enables reasoning and decision-making
- Stores domain expertise for expert systems
- Supports inference and automated problem-solving
- Allows knowledge reuse across systems
- Fundamental to all intelligent systems

---

### Q2: Explain the main approaches to knowledge representation with examples.

**Answer:**
Main approaches:

1. **Logical Representation:** Using formal logic
   - Example: ∀x (Student(x) → Enrolled(x))

2. **Procedural:** Knowledge as algorithms
   - Example: Sorting algorithm

3. **Semantic Networks:** Graph with nodes and edges
   - Example: Dog ──is-a──> Animal

4. **Frames:** Structured objects with attributes
   - Example: Class Dog with properties: legs=4, canEat=[meat]

5. **Production Rules:** IF-THEN rules
   - Example: IF sick THEN prescribe_medicine

6. **Ontologies:** Formal concept specifications
   - Example: OWL Web Ontology Language

---

### Q3: What is propositional logic? Explain with examples of propositions and non-propositions.

**Answer:**
Propositional logic is a formal system dealing with propositions - statements that are either true or false. Also called Boolean logic.

**Propositions (can be true or false):**
- "It is raining" ✓
- "The earth is round" ✓
- "2 + 2 = 4" ✓

**Non-propositions (cannot be assigned true/false):**
- "What time is it?" - Question
- "x > 5" - Depends on x's value
- "Please sit down" - Imperative
- "This statement is false" - Paradox

---

### Q4: Create truth tables for the five main logical connectives.

**Answer:**
See truth tables section (AND, OR, NOT, IF-THEN, IF AND ONLY IF)

---

### Q5: Explain Modus Ponens, Modus Tollens, and Disjunctive Syllogism with real-world examples.

**Answer:**

**Modus Ponens (Affirming the Antecedent):**
- Rule: From (p → q) and p, infer q
- Example: If it rains, ground gets wet. It is raining. Therefore, ground is wet.

**Modus Tollens (Denying the Consequent):**
- Rule: From (p → q) and ¬q, infer ¬p
- Example: If you study hard, you pass. You didn't pass. Therefore, you didn't study hard.

**Disjunctive Syllogism:**
- Rule: From (p ∨ q) and ¬p, infer q
- Example: The animal is cat or dog. It's not a cat. Therefore, it's a dog.

---

### Q6: Explain resolution and show how it works with an example.

**Answer:**
Resolution is a rule of inference that derives new clauses from existing clauses. If two clauses contain opposite literals (p and ¬p), we can combine the remaining parts.

**Rule:**
```
(p ∨ A) and (¬p ∨ B) → (A ∨ B)
```

**Example:**
```
Clause 1: (p ∨ q)       "p or q"
Clause 2: (¬q ∨ r)      "not q or r"
Resolvent: (p ∨ r)      "p or r"
```

Used for automated theorem proving and proof by contradiction.

---

### Q7: What is first-order logic and how does it extend propositional logic?

**Answer:**
First-Order Logic (FOL) extends propositional logic by introducing:
- **Predicates:** Represent properties and relationships (Student(x), Teaches(x,y))
- **Variables:** Represent objects in domain (x, y, z)
- **Quantifiers:** Express generalizations
  - Universal (∀): "for all"
  - Existential (∃): "there exists"

**Example of FOL:**
```
∀x (Student(x) → CanEnroll(x))
"All students can enroll"
```

This cannot be expressed in simple propositional logic.

---

### Q8: Explain Universal Instantiation and Existential Instantiation with examples.

**Answer:**

**Universal Instantiation:**
From ∀x P(x), infer P(a) for specific constant a.

Example:
```
∀x (Bird(x) → CanFly(x))        "All birds can fly"
Instantiate x = Tweety:
Bird(Tweety) → CanFly(Tweety)  "If Tweety is a bird, it can fly"
```

**Existential Instantiation:**
From ∃x P(x), infer P(c) for witness constant c.

Example:
```
∃x (Student(x) ∧ GradesA(x))    "Some student gets A"
Instantiate x = John:
Student(John) ∧ GradesA(John)   "John is that student"
```

---

### Q9: Explain ISA and Instance relationships in predicate logic.

**Answer:**

**ISA Relationship:** Represents class membership
```
Isa(object, class)
Example: Isa(John, Human) - "John is a human"
```

Supports inheritance:
```
∀x (Isa(x, Bird) → CanFly(x))
"All birds can fly"
```

**Instance Relationship:** Represents specific properties
```
PropertyOf(object, property, value) or Predicate(object, value)
Example: Age(John, 25) - "John is 25 years old"
```

Complete example:
```
Rule: ∀x (Isa(x, Bird) → CanFly(x))
Fact: Isa(Tweety, Bird)
Conclusion: CanFly(Tweety)
```

---

### Q10: Explain unification and show how it's used in first-order resolution.

**Answer:**
**Unification** is finding a substitution (variable binding) that makes two terms identical.

**Notation:** σ = [x/a, y/b] means substitute x with a, y with b

**Example 1:** Make P(x) and P(John) identical
```
Unifier: σ = [x/John]
Result: P(John) = P(John) ✓
```

**Example 2:** Make Teaches(x, y) and Teaches(Alice, CS101) identical
```
Unifier: σ = [x/Alice, y/CS101]
Result: Teaches(Alice, CS101) = Teaches(Alice, CS101) ✓
```

**In FOL Resolution:**
```
Clause 1: P(x) ∨ Q(x)
Clause 2: ¬P(a) ∨ R(a)
Unifier: σ = [x/a]
Resolvent: Q(a) ∨ R(a)
```

---

This comprehensive guide covers **all topics** from your Unit 3 syllabus on Knowledge Representation, Propositional Logic, Predicate Logic, and First-Order Logic, with clear explanations, examples, and exam-ready definitions. Use this to write your answers in the end-sem exam!
