Simple Prolog
=========================================

Some simple PROLOG programming exercises, mostly involving recursion and list operations. This assignment is due in labs in Week 8. The hardcopy listing of the code must be submitted and the running code must be demonstrated in the lab.


- (ass11) Define the flatten(X, Y) relation that holds when Y is a list structure that contains the same elements as X, in the same order, but with no nested lists. 
Hence,


  `|?- flatten( [a, b, [c,d], [[e]]], Y). `
  `Y = [ a, b, c, d, e]. `
  `no`


  `|?- flatten( [a,[b],[[[c]]], [d,e]], X). `
  `X = [a,b,c,d,e]. `
  `no`

  You may use the code 


  `non_nil_atom(X) :- X \== [ ], atomic(X). `


  to test if a component is an atom that is not [ ]. The flatten predicate must also replace any single digit    number in the alphabet (you may assume that these would be the only numbers that would appear in the input     list) with the letter in the corresponding position in the input list (i.e., 1 with a, 2 with b and so on).


- Write a Prolog program that defines a predicate `intersects(List1, List2)` which evaluates to true if List1 and List2 have at least one element in common. The elements of these lists may themselves be lists.


- (ass12) Write a Prolog program that defines a predicate no-repetition`(N, List1, List2)` that removes any N-repetitions from List1 (i.e., members that appear N times) to generate List2. For instance, if the input list List1 is `[1, 5, 5, 3, 3, 3, 4]`, and N=2, then the output list List2 must be `[1, 5, 3, 3, 3, 4]`.


- (ass13) Write a Prolog program that defines a predicate merge`(List1, List2, MergedList)` that takes two lists List1 and List2 that are sorted in ascending order and generates MergedList which contains all of the elements of List1 and List2 and is also sorted in ascending order. Assume that the merging process eliminates duplicates. Thus, if List1 is `[1, 3, 5]` and List2 is `[2, 4, 5],` then MergedList must be `[1, 2, 3, 4, 5]`.


- (ass14) Explain how the AgentSpeak agent programming language might be extended to enable a broader, more practical set of applications. You may want to address crowdsourcing, socio-technical systems, gamification or other ideas. Provide your answer in less than a page of text. The idea is to do some creative thinking on agent programming languages.
