# Chapter 1: First Order Logic and Expert Systems

## What is Logic ?!?!

+ Logic is a systematic representation of information and knowledge to be communicated to machine.
+ It is expressed using specific <span style="color:green;">syntax</span> of the representation language to define the <span style="color:green;">semantics</span> of the sentences.
+ __<span style="color:green;">syntax</span>__ : identify if an expression is well formed
+ __<span style="color:green;">semantics</span>__ : identify the meaning of an expression

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Logic Languages 
<div align="center">
  <img src="https://github.com/JoshuaOhYQ/etc2073/blob/66ede6480a5ce33042dff7d743daafd6379a4d4d/LogicLanguage.png?raw=true" alt="Logic Language">
</div>


| Language            | What Exists Within the Language (Ontological Commitment) | What an agent believes about facts (Epistemological commitment) |
|---------------------|---------------------------------|----------------------------|
| Propositional logic | Facts                           | True/False                 |
| First order logic   | Facts, objects, relations       | True/False                 |
| Temporal logic      | Facts, objects, relations, time| True/False                 |
| Probability theory  | Facts                           | Degree of belief ∈ [0, 1]  |
| Fuzzy logic         | Facts with degree of truth ∈ [0, 1] | Known interval value       |

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Propositional logic

####Logical connective:
| Symbol | Name         | Example | English equivalent                  |
|--------|--------------|---------|-------------------------------------|
| ∧      | conjunction  | p ∧ q   | p and q                             |
| ∨      | disjunction  | p ∨ q   | p or q                              |
| ¬ or ∼ | negation     | ¬p or ∼p| not p                               |
| ⇒      | implication  | p ⇒ q   | p implies q<br>if p then q          |
| ⟺      | biconditional| p ⟺ q   | p if and only if q<br>p equivalent to q |  

Derivative connective such as __XOR(Exclusive OR)__ and __NOR(Negation of OR)__ are also valid and can be formed using the basic logical operators listed above. 🙂

#### Antecedent and consequence:
+ Antecedent: The "IF" part of a conditional statement
+ Consequent: The "Then" part of a conditional statement
+ Example:<br>If __r__ and __p__ then __q__<br>__r__ ∧ __p__ ⇒ __q__<br>Antecedent (IF) = __r__ ∧ __p__<br>Consequent (Then) = __q__
+ Antecedent and consequence is used to describe components of a conditional statement, often referred to as an __implication__ (only __FALSE__ when antecedent is true and consequent is false, otherwise it is __TRUE__) ❗❗❗
  
#### Syntax:
+ Syntax is how an expression (statement) can be formed
+ A correctly formed statement has a meaning within the definition of the language
+ In simple words, syntax is the way to write the statements
+ Examples:<br>

  | Statements | Comment  |   
  |------------|----------|
  | p   | a fact  | 
  | p ∧ q  | a conjunction of 2 facts |
  | x4y + =  | not a well-formed expression |
  | 3x + y  | a well-formed arithmetic expression |
  | 3x + y > 2  | a valid mathematical inequality |
  
+ __Correct syntax__ : p ∧ q<br>__Incorrect syntax__: p ∧ (incomplete statement)
+ Statements also called sentences in logic
  
#### Semantics:
+ Semantics defines the meaning of the sentences within the language it is defined in.
+ can be TRUE or FALSE in propositional logic
+ In logic, semantics provides the rules for interpreting the symbols and sentences of a formal language.
+ Examples:<br>

  | Statements | Comment  |   
  |------------|----------|
  | __p__   | This is a simple propositional statement. The meaning of p depends on the interpretation assigned to it.  | 
  | __p__ ∧ __q__ if __p__ is true and __q__ is true  | This is a conjunction in propositional logic. The statement __p__ ∧ __q__ means ''both __p__ and __q__ are true'' ( __p__ ∧ __q__  is true if and only if both __p__ and __q__ are true. If either __p__ or __q__ is false, the entire statement is false) |
  |3 __x__ + __y__ > 2 if __x__ is 2 and __y__ is 1| This is a mathematical inequality involving variables __x__ and __y__. The statement is a predicate logic expression. The truth of this statement depends on the values assigned to __x__ and __y__.  |

#### CheckPoint 1 🎆🎆 (Conjunction, Disjunction and Negation):
  | p     | q     | p ∧ q | p ∨ q | ∼p   | ∼q   |
 |-------|-------|-------|-------|------|------|
 | false | false | false | false | true | true |
 | true  | false | false | true  | false| true |
 | false | true  | false | true  | true | false|
  | true  | true  | true  | true  | false| false|

#### Implications:
+ Let say, <br> __p__ ⇒ __q__<br> __p__ implies q<br> if __p__ (if true) then __q__ (is true)
+ Same with __<span style="color:red;">antecedent</span>__ and __<span style="color:red;">consequent</span>__, __implication__ is only _FALSE_ when the __<span style="color:red;">antecedent</span>__ __(IF)__ is _TRUE_ and the __<span style="color:red;">consequent</span>__ __(THEN)__ is _FALSE_, otherwise it is _TRUE_
+ Example:<br>

  | __p__ = it rains    | __q__ = ground is wet | __p__ ⇒ __q__ <br>if it rains, then ground is wet|
  |-------|-------------|-------|
  | False | False       | True  |
  | False | True        | True  |
  | True  | False       | False |
  | True  | True        | True  |

#### Biconditional:
+ Let say, <br> __p__ ⟺ __q__<br> __p__ if and only if __q__ (is true)
+ So, if __p__ is _TRUE_, then __q__ is _TRUE_ ; __q__ is _TRUE_, then __p__ is _TRUE_
+ Basically, __p__ ⟺ __q__ is true only when both __p__ and __q__ have the same truth value (__BOTH__ _True_ or __BOTH__ _False_):<br>

    | __p__ | __q__ | __p__ ⇒ __q__  | __q__ ⇒ __p__   | __p__ ⟺ __q__    |
  |-----------|---------------|-------------------|-------------------|-------------------|
  | false     | false         | true              | true              |true               |
  | false     | true          | true              | false             |false               |
  | true      | false         | false             | true              |false              |
  | true      | true          | true              | true              |true                |

+ So, how can we prove that the statement __p__ ⟺ __q__ is correct or wrong?<br>
  <u>We can show that __p__ and __q__ are logically equivalent (p implies q and q implies p), if both implications hold then __p__ ⟺ __q__ is correct, otherwise it is wrong!</u>
+ Example:<br>

  | __p__ <br> it rains         | __q__ <br> ground is wet             | __p__ ⇒ __q__ <br> if it rains<br> then ground is wet            | __q__ ⇒ __p__ <br> if ground is wet<br> then it rains            | __p__ ⟺ __q__    |
  |-----------|---------------|-------------------|-------------------|-------------------|
  | false     | false         | true              | true              |true               |
  | false     | true          | true              | false             |false               |
  | true      | false         | false             | true              |false              |
  | true      | true          | true              | true              |true                |

#### CheckPoint 2 🎆🎆 (Implication and Biconditional):

  | __p__ <br> x is divisible by 2      | __q__ <br> x is even             | __p__ ⇒ __q__  | __q__ ⇒ __p__   | __p__ ⟺ __q__    |
  |-----------|---------------|-------------------|-------------------|-------------------|
  | false     | false         | true              | true              |true               |
  | false     | true          | true              | false             |false               |
  | true      | false         | false             | true              |false              |
  | true      | true          | true              | true              |true                |

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### First Order Logic (FOL) 

- It is also called **predicate logic** due to the addition of predicate variables.
- FOL adds **3** more concepts to the syntax on top of those in **propositional logic**, there are:  
  a. **<span style="color:red;">Predicate Variables</span>**  
  b. **<span style="color:red;">Universal Quantifier ∀</span>**  
  c. **<span style="color:red;">Existential Quantifier ∃</span>**  
- There are **3** types of symbols in FOL:  
  a. **<span style="color:red;">Constant Symbols for Objects</span>** (represent specific, fixed objects in the domain such as names or fixed objects in the domain that do not change).  
  b. **<span style="color:red;">Predicate Symbols for Relations</span>** (represent relations or properties that can be **true or false** about objects in the domain & they also help describe the characteristics of objects or define relationships between them).  
  c. **<span style="color:red;">Function Symbols for Functions</span>** (represent mappings from one or more objects to another object; they can take constants, variables, or other functions as arguments and functions **return a specific object**, unlike predicates which return true or false values).
+ Example of First Order Logic (FOL):<br>
  <div align="center">
  <img src="https://raw.githubusercontent.com/JoshuaOhYQ/etc2073/935fa3309d1d28db5159194c0b977558bb5a50b7/FOL.png" alt="FOL">
</div> <br>What are the Constant symbols, Predicate symbols, and Function symbols from the image above?<br><br>

__<span style="color:red;"> Constant Symbols:</span>__ <br>
- **Richard** and **John** (represents 2 specific individuals).  
- **K** (represents the crown as a specific object).  

__<span style="color:red;"> Predicate Symbols:</span>__<br>
- `Person(R)` -> Richard is a person. <span style="color:green;">**(TRUE)**</span>  
- `Person(J)` -> John is a person. <span style="color:green;">**(TRUE)**</span>  
- `King(J)` -> John is a king. <span style="color:green;">**(TRUE)**</span>  
- `Brother(R,J)` -> Richard is John's brother. <span style="color:green;">**(TRUE)**</span>  
- `OnHead(K, J)` -> The crown (K) is on John's head. <span style="color:green;">**(TRUE)**</span>  
- `Crown(K)` -> K is a crown. <span style="color:green;">**(TRUE)**</span>  

__<span style="color:red;"> Function Symbols:</span>__<br>
- `LeftLeg(R)` -> refers to Richard's left leg.  
- `LeftLeg(J)` -> refers to John's left leg.  

#### Predicate symbols 
+ Predicate symbol represents a property or relation, for instance from the image above, brother, person, king.
+ When we apply arguments to a predicate, it forms a predicate expression, for instance Brother(Richard, John)
+ Predicate expression can be evaluated as either true or false in a given context, for instance Brother(Richard, John) will return true as the statement based on the image above is true.
- **Arity of a predicate** helps determine how many objects are involved in the property or relationship it describes:  
  1. **<span style="color:red;">Unary Relations (Arity = 1)</span>**  
     - Takes one argument (property of a single object).  
     - Examples:  
       - `Person(Richard)`: Richard is a person.  
       - `King(John)`: John is a king.  
       - `Crown(K)`: K is a crown.  

  2. **<span style="color:red;">Binary Relations (Arity = 2)</span>**  
     - Takes two arguments (relationships between 2 objects).  
     - Examples:  
       - `Brother(Richard, John)`: Richard is the brother of John.  
       - `OnHead(K, John)`: Object K is on John's head.  

  3. **<span style="color:red;">Higher-Arity Relations</span>**  
     - Predicates can also have higher arities.  
     - Example: Ternary relations with arity 3.  
       - `Between(x, y, z)`: Object y is between objects x and z.
       
+ **Examples (from previous image):**

| Symbol   | Arity | Example           |
|:--------:|:-----:|:-----------------:|
| Brother  | 2      | Brother(Richard, John) |
| OnHead   | 2      | OnHead(K, John)   |
| Person   | 1      | Person(Richard)   |
| King     | 1      | King(John)        |
| Crown    | 1      | Crown(K)          |

#### Function symbols 
+ Represents a mapping from one or more input objects (arguments) to an output object.
+ Unlike predicates (which evaluate to true or false), functions will return objects as their output.
+ In mathematical sense, a function maps an object to another object.
+ **Example**:  
  - `LeftLeg(Richard)` = Richard's left leg  
  - ⟨Richard⟩ LeftLeg ⟶ Richard’s left leg  
  - Function symbol `LeftLeg` is used to map a person (input) to their left leg (output).  

  **Basically**:  
  - **Richard**: Input (argument) to the function.  
  - **LeftLeg**: Function symbol.  
  - **Richard's left leg**: Output (result) of the function.

+ **Concept of arity also applies to function symbols**:  
  1. **Unary function (arity 1)**: Takes one argument.  
     - Example: `LeftLeg(Richard)` → Refers to Richard's left leg.  

  2. **Binary function (arity 2)**: Takes two arguments.  
     - Example: `Sum(x, y)` → Returns the sum of `x` and `y`.  

  3. **Higher arities**: Functions can also have arities greater than 2.  
     - Example: A ternary function (arity 3) could be `Combine(x, y, z)` → Combines `x`, `y`, and `z` into a single result.

#### Universal quantifier, ∀
+ It means __for all__ or __for every__.
+ Statement that follows applies to all members of the domain that is being considered.
+ It is used to make general statements about all elements in a domain.
+ Typically written as ∀x, where x is a variable (expression after ∀x applied to all possible values of x in the domain)
+ **Examples**:  
  1. `∀x King(x) ⇒ Person(x)`  
     - **Translation**: For all `x`, if `x` is a king, then `x` is a person.  

  2. `∀x, y Brother(x, y) ⇒ Person(x) ∧ Person(y)`  
     - **Translation**: For all `x` and `y`, if `x` is the brother of `y`, then `x` is a person and `y` is a person.
     
#### Existential quantifier, ∃
+ It means __there exists__ or __for some__.
+ There exists at least one member of the domain for which the statement that follows is true.
+ It is used to make statements about the existence of at least one element in the domain that satisfies a given condition.
+ Typically written as ∃x, where x is a variable (expression after ∃x only holds true for some of x)
+ **Examples**: <br> `∃x Crown(x) ∧ OnHead(x, John)` <br> **Translation**: There exists an `x` such that `x` is a crown and x is on John's head .

#### Nested quantifier
+ Can involve the same type of quantifier or different types.
+ The order of quantifiers is crucial as it affects the meaning of the statement 
+ **Examples**:  
  1. `∀x∀y Brother(x, y) ⇒ Sibling(x, y)`
     `∀x, y Brother(x, y) ⇒ Sibling(x, y)` 
     - **Translation**: For all `x` and `y`, if `x` is the brother of `y`, then `x` is a sibling of `y`, basically brothers are siblings. 

  2. `∀x∀y Loves(x, y)`  
     - **Translation**: For all `x`, there exists a `y` such that `x` loves `y`, basically everybody loves somebody. 
      
  3. `∀y∀x Loves(x, y)`  
     - **Translation**: There exists a `y` such that for all `x`, `x` loves `y`, basically there is someone who is loved by everyone.

#### De Morgan's Laws
+ Fundamental rules in logic that describe the relationship between conjuntion (∧) and disjunction (∨) , AND universal (∀) and existential (∃) quantifier under negation (¬).
+ Allow us to change from ∧ to ∨, vice versa AND from ∀ to ∃, vice versa. 
+ **∧ and ∨** :
   1. `¬(P ∧ Q) ≡ ¬P ∨ ¬Q`
     - **Translation**: Negation of (`P` and `Q`) is equivalent to not `P` or not `Q`

  2. `¬(P ∨ Q) ≡ ¬P ∧ ¬Q`  
     - **Translation**: Negation of (`P` or `Q`) is equivalent to not `P` and not `Q`
      
  3. `P ∨ Q ≡ ¬(¬P ∧ ¬Q)`  
     - **Translation**: `P` or `Q` is equivalent to not (not `P` and not `Q`) 
    
  4. `P ∧ Q ≡ ¬(¬P ∨ ¬Q)`  
     - **Translation**: `P` and `Q` is equivalent to not (not `P` or not `Q`)
           
+ **∀ and ∃** :
   1. `∀x ¬P ≡ ¬∃x P`
     - **Translation**: For all `x`, `P` is not true is equivalent to it is not the case that there exists an `x` for which P is true

  2. `¬∀x P ≡ ∃x ¬P`  
     - **Translation**: It is not the case that for all `x`, `P` is true is equivalent to there exists an `x` for which `P` is not true
      
  3. `∀x P ≡ ¬∃x ¬P`  
     - **Translation**: For all `x`, `P` is true is equivalent to there does not exist an `x` for which `P` is false."
    
  4. `∃x P ≡ ¬∀x ¬P`  
     - **Translation**: There exists an `x` such that `P` is true is equivalent to it is not the case that for all `x`, `P` is not true.
       
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    
## Expert Systems
  + Programs that mimic decision-making and problem solving thought processes of human experts
  + It uses production rules (IF-THEN) as knowledge representation
  + **Structure of expert system**:<br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/JoshuaOhYQ/etc2073/da5c9daa11eb89a40525006353b6da337bfd0070/Structure.png" alt="Structure">
  </div> <br><br>
  
  + __Inference methods__ are methods used by the inference engine to reason through the knowledge base and derive conclusion
  + The two __inference methods__ are __forward chaining__ and __backward chaining__

### Forward Chaining
  + Data-driven reasoning
  + known data/facts → rules → conclusion
  + Basically, the system begins with the known facts in the working memory, it then apply the rules whose __IF__ conditions match the known facts, when a rule fires, its __THEN__ conclusion is added to the working memory as a new fact. This process repeats until no more rule can be applied or a specific goal has been reached.
  + This method is useful when the goal is to explore all possible conclusions from the avalaible data or to generate a wide range of outcomes (explore all possible conclusions)
+ **Rule Interpreter**:<br>
  <div align="center">
    <img src="https://raw.githubusercontent.com/JoshuaOhYQ/etc2073/bb4006ade3e69d7ee87bf8af546f625cfd213c4f/Forward%20Chaining%20formula.png" alt="Forward Chaining Formula">
  </div> <br><br>


**How the Algorithm Works:**

1. **Start from the first rule**  
   The algorithm begins by checking the first rule in the rule list.

2. **Is this rule active?**  
   a) If the rule is **"Active"**, move to the next step.  
   b) If the rule is **not "Active"**, proceed to the next rule.

3. **Fire the rule**  
   If the rule is active, it is fired (executed).

4. **Remove the rule from the list**  
   The fired rule is removed from the list to avoid reprocessing.

5. **End of rule list?**  
   a) If all rules have been checked, proceed to the next step.  
   b) If there are more rules left, continue checking them.

6. **Any rule in this cycle was activated?**  
   a) If at least one rule was activated, repeat the process from the first rule.  
   b) If no rules were activated, the algorithm ends.

+ Example (Please click this link): 

### Conflict Resolution  
+ When multiple rules can be fired at the same time, a conflict resolution strategy determines which rule to execute first.  
+ Priorities are set based on:  

  **a) Sequence of the rule list**  
  - Assumes rules are arranged according to importance.  
  - Rules are prioritized based on their order in the list.  

  **b) Specificity of the rule**  
  - More specific rules (rules with more antecedents or conditions) are given higher priority.  

  **c) Parameters in the environment**  
  - Context or external conditions influence which rule is prioritized.  
  - Ensures the system adapts to real-life situations.  

  **d) Recency of the rule being added**  
  - Recently used rules are considered more significant as they have proven valuable.  
  - These rules are given priority for faster access.  

  **e) Recency addition of the rule**  
  - New rules are prioritized.  

  **f) Redundancy**  
  - Ignore rules that have already been fired.  

---

**Example: Traffic Light Rules**  
Here’s an example of rules and how conflicts might arise:

```plaintext
Rule 1    IF    traffic_light is green
    THEN    action is go

Rule 2    IF    traffic_light is amber
    THEN    action is slow-down

Rule 3    IF    traffic_light is amber
    THEN    action is speed_up

Rule 4    IF    traffic_light is red
    THEN    action is stop 
```

For this case we will consider **parameters in the environment** for conflict resolution ❗❗❗

---

### Backward Chaining
  + Goal-driven reasoning
  + goal/hypothesis → rules → data to support → rules → conclusion
  + Basically, the system starts with a goal, then it looks for rules whose __THEN__ (conclusion) match the goal. It then checks whether the __IF__ conditions of those rules are satisfied by the facts in the working memory. If the conditions are not satisfied, the system treats them as sub-goals and repeats the process.
  + This method is useful when the goal is specific, and the system needs to determine whether it is supported by the avalaible facts or when the system needs to answer a specific question or hypothesis. Basically, veryfying a specific goal or hypothesis.
  + **Rule Interpreter**:<br>
  <div align="center">
    <img src="https://github.com/JoshuaOhYQ/etc2073/blob/0b73fd44b4842e8f67489f00fa84ac59f54021a7/Backward%20Chaining%20formula.png" alt="Backward Chaining Formula">
  </div> <br><br>


**How the Algorithm Works:**

1. **Identify the hypothesis or goal**  

2. **Check if there is a rule that establishes the goal**  
   a) If yes, then proceed  
   b) If no, then check if the goal is a fact in the database

3. **Check if any rule is active**  
   a) If yes, add sub-goal to the database
   b) If no, derive a new sub-goal from rule's antecedent
   
4. **Check for any preceding sub-goal**  
   a) If yes, then use the preceding sub-goal as the new sub-goal (system takes the preceeding sub-goal and treats it as the new hypothesis/goal to be proven and repeat 
   b) If no, then goal is proven 

6. **End of rule list?**  
   a) If all rules have been checked, proceed to the next step.  
   b) If there are more rules left, continue checking them.

7. **Any rule in this cycle was activated?**  
   a) If at least one rule was activated, repeat the process from the first rule.  
   b) If no rules were activated, the algorithm ends.

