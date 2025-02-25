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


### <u>Propositional logic</u>
| Symbol | Name         | Example | English equivalent                  |
|--------|--------------|---------|-------------------------------------|
| ∧      | conjunction  | p ∧ q   | p and q                             |
| ∨      | disjunction  | p ∨ q   | p or q                              |
| ¬ or ∼ | negation     | ¬p or ∼p| not p                               |
| ⇒      | implication  | p ⇒ q   | p implies q<br>if p then q          |
| ⟺      | biconditional| p ⟺ q   | p if and only if q<br>p equivalent to q |  

Derivative connective such as __XOR(Exclusive OR)__ and __NOR(Negation of OR)__ are also valid and can be formed using the basic logical operators listed above. 🙂





------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



