Simple Agent-Speak
=========================================

You are required to implement in Prolog the following two systems:
• A simple forward chaining expert system shell
• A simple interpreter for the agent programming language AgentSpeak. The interpreter will rely on the expert system shell for querying the beliefs of an agent. Both of the above will rely on a restricted propositional language. The expert system knowledge-base will consist of facts and rules. Facts will be represented via a unary predicate f(Fact) where Fact is necessarily an atomic proposition. Rules will be represented by a binary predicate r(Antecedent, Consequent) where Antecedent is a list of atomic propositional facts while Consequent is a single atomic propositional fact. Thus the knowledge base below: 
a
b
a AND b IMPLIES c
is encoded as follows: 
f(a).
f(b).
r([a, b], c). 
(Since this is propositional Horn clause reasoning, ask yourself why we cannot encode knowledge bases directly in Prolog). Ensure that your system satisfies the property of refraction (a rule does not fire more than once for the same set of facts). Assume that the shell supports two kinds of queries:
• q(Proposition) where Proposition is an atomic proposition. The query is evaluated with respect to a knowledge base consisting of facts and rules represented as above (these may be loaded as separate file) and returns true if Propositionis a consequence of the knowledge-base (as determined by forward chaining).
• explain(Proposition, Explainlist) which returns a list of facts and rules used in deriving Proposition (contained in Explainlist) in the event that q(Proposition) returns true. If q(Proposition) returns false, so does explain(Proposition,Explainlist).

An AgentSpeak agent's beliefs will be represented in a knowledge-based as described above. Its plans will be represented using a ternary predicate p(Trigger, Context, Body). Context is a list consisting of either atomic propositions or elements of the form [not p] where p is an atomic proposition. We will treat not p to be true if q(p) turns out to be false. Trigger is one of the following:
• [addbelief, Proposition]
• [deletebelief, Proposition]
• [addgoal, Proposition]
• deletegoal, Proposition.
Body is a list consisting of the following two kinds of elements:
• [goal, Proposition]
• action, Proposition.
An agent is invoked via binary predicate agent(EventQueue, ActionList) where EventQueue is a list of Triggers, and ActionList is a list of actions represented as atomic propositions. When an agent is invoked, EventQueue is instantiated, while ActionList is uninstatiated. The query is evaluated with respect to an agent program represented as above (this may be loaded as a separate file), and the output (implicitly) is the sequence of actions that the variable ActionList is instantiated with. 
Notice that AgentSpeak has been further simplified by doing away with test goals (the only goals considered are achievement goals).
