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

+ It is also called __predicate logic__ due to the addition of predicate variables
+ FOL adds _3_ more concepts to the syntax on top of those in __propositional logic__, there are: <br>
  1. __<span style="color:red;"> Predicate Variables</span>__
  2. __<span style="color:red;"> Universal Quantifier ∀</span>__
  3. __<span style="color:red;"> Existential Quantifier ∃</span>__
+ There are _3_ types of symbols in FOL:
  1. __<span style="color:red;"> Constant Symbols for Objects</span>__ (represent specific, fixed objects in the dommain such as names or fixed objects in the domain that do not change)
  2. __<span style="color:red;"> Predicate Symbols for Relations</span>__ (represent relations or properties that can be __true or false__ about objects in the domain & it also help describe the characteristics of objects or define relationships between them)
  3. __<span style="color:red;"> Function Symbols for Functions</span>__ (represent mappings from one or more objects to another object, it can take canstants, variables or other functions as arguments and functions __return a specific object__, unlike predicates which return true or false values)

