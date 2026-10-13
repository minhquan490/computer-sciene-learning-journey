---

title: "Baseline Test A — Programming and CS Foundations"
date: 2026-10-14
type: checkpoint
status: completed
tags:

- checkpoint
- baseline-assessment
- java
- computer-science

---

Baseline Test A — Programming and CS Foundations

1. Purpose

This checkpoint records the initial assessment of my Computer Science foundations.

The goal is to identify demonstrated strengths and knowledge gaps before creating a more detailed learning plan.

Assessment principle: Conclusions must be based on demonstrated evidence. A small baseline test cannot establish mastery of an entire subject.

2. Assessment Results

Q1 — Primitive Value Assignment

int a = 10;
int b = a;
b = 20;

System.out.println(a);
System.out.println(b);

- My answer: "10", "20".
- Result: Correct output.
- Concept demonstrated: Assigning a primitive variable copies its value.
- Area to reinforce: Explain Java's language-level semantics precisely instead of assuming a specific physical RAM layout.

Q2 — Array References

int[] a = {10};
int[] b = a;
b[0] = 20;

System.out.println(a[0]);
System.out.println(b[0]);

- My answer: "20", "20".
- Result: Correct.
- Concept demonstrated: Both variables refer to the same array object.
- Additional point: If "b = new int[]{30}" is executed, only the local variable "b" is reassigned. The original variable "a" still refers to the original array.

Q3 — Java Pass-by-Value

static void change(int[] arr) {
    arr[0] = 99;
    arr = new int[]{50};
}

public static void main(String[] args) {
    int[] numbers = {10};
    change(numbers);
    System.out.println(numbers[0]);
}

- My answer: "50".
- Correct answer: "99".
- Result: Incorrect.
- Misconception to address: Confusing reassignment of a method parameter with reassignment of the caller's variable.
- Core concept: Java uses pass-by-value. When an array is passed, the value copied into the parameter is the reference to the array.
- Mutating the shared array is visible to the caller. Reassigning the local parameter does not change the caller's variable.

Priority: High. Revisit with tracing diagrams and exercises.

Q4 — Scope and Shadowing

static int x = 10;

static void test() {
    int x = 20;
    System.out.println(x);
}

public static void main(String[] args) {
    test();
    System.out.println(x);
}

- My answer: "20", "10".
- Result: Correct output.
- Concept demonstrated: A local variable can shadow a class field within its scope.
- Area to reinforce: Explain variable lookup and scope boundaries precisely.

Q5 — Exception Flow

try {
    int x = 10 / 0;
    System.out.println("A");
} catch (ArithmeticException e) {
    System.out.println("B");
}

System.out.println("C");

- My answer: "B", "C".
- Result: Correct output.
- Concept demonstrated: Handling an "ArithmeticException".
- Area to reinforce: The exception occurs inside "try"; the remaining statements in that "try" block are skipped, execution enters the matching "catch", then continues after the try-catch statement.

Q6 — Nested Loops and Complexity

Two nested loops each iterate over an array of length "n".

- My answer for "n = 4": 16 iterations.
- Complexity answer: "O(n²)".
- Result: Correct for the stated example.
- Evidence limit: This does not yet establish mastery of Big-O analysis for more complex algorithms.

Q7 — Linear Search

int[] numbers = {3, 7, 11, 15, 19};
int target = 15;

for (int i = 0; i < numbers.length; i++) {
    if (numbers[i] == target) {
        System.out.println(i);
        break;
    }
}

- My answer: Output "3"; four elements are checked.
- Result: Correct.
- Concept demonstrated: Array indexing, linear search, and the behavior of "break".
- Additional point: "break" exits the nearest enclosing loop or switch, not the entire method or program.

Q8 — Database Transaction and Atomicity

Scenario: Transfer 100 units from account A (500) to account B (200) using two database updates.

- My answer: Both updates should succeed together or be rolled back together. Without a shared transaction, the first update could remain committed if the second fails.
- Result: Correct understanding of the core issue.
- Concept demonstrated: Atomicity in ACID transactions.
- Nuance: If both updates are part of one active transaction and the transaction has not committed, a rollback can undo the first update as well.

3. Evidence-Based Summary

Demonstrated strengths

- Basic Java code tracing.
- Basic primitive assignment behavior.
- Recognizing shared array references and object mutation.
- Simple nested-loop iteration counting.
- Basic Big-O reasoning for nested loops.
- Linear search and array indexing.
- Basic exception-flow tracing.
- Understanding the purpose of database transaction atomicity.

Topics requiring reinforcement

1. Java pass-by-value, especially when passing object references.
2. Difference between mutating an object and reassigning a reference.
3. Scope, shadowing, and variable lookup.
4. Precise reasoning about exception propagation and control flow.
5. Java execution semantics versus assumptions about physical memory.

Not yet assessed

This baseline does not establish proficiency in:

- Data structures and advanced algorithms.
- Recursion and algorithm correctness.
- Discrete mathematics and formal logic.
- Computer architecture and operating systems.
- Networking and distributed systems.
- Database indexing, query planning, and concurrency internals.
- Linear algebra, calculus, probability, and statistics.
- Machine learning internals or AI agent architecture.

Do not label these areas as weaknesses yet. They have not been sufficiently tested.

4. Initial Learning Roadmap

This is a provisional roadmap, not a rigid prerequisite chain.

1. Programming Semantics: values, references, object identity, mutability, scope, lifetime, exceptions, JVM basics.
2. Data Structures and Algorithms: complexity, arrays, linked structures, stacks, queues, hash tables, trees, graphs, sorting, searching, recursion, correctness.
3. Discrete Mathematics: logic, sets, relations, functions, proof techniques, combinatorics, graph theory.
4. Computer Architecture and Operating Systems: binary representation, CPU, memory hierarchy, processes, threads, virtual memory, synchronization.
5. Networks, Databases, and Distributed Systems: TCP/IP, HTTP, transactions, indexing, isolation, consistency, replication, fault tolerance.
6. Mathematics for AI/ML: algebra and functions, calculus, linear algebra, probability, statistics, optimization.
7. Machine Learning and AI Systems: model fundamentals, training and evaluation, inference, tool use, agent loops, memory, orchestration, reliability, and research paper reproduction.

Topics may overlap where appropriate. Completing every CS topic is not a strict requirement before beginning introductory AI/ML study.

5. Next Study Session

Topic: Java Value Semantics and Object References.

Learning objectives:

- Distinguish a primitive value from an object reference.
- Draw a variable/reference/object diagram.
- Explain Java pass-by-value accurately.
- Predict the effects of object mutation versus reference reassignment.
- Trace method calls without guessing.

Recommended teaching sequence:

1. Active Recall: Explain why Q3 prints "99", not "50".
2. Clarify the mental model.
3. Work through simple examples.
4. Attempt exercises independently.
5. Review errors and their causes.
6. Record mastery evidence and unresolved questions.

6. Study Preferences and Constraints

- Teach concepts before asking me to memorize rules.
- Progress from easy to difficult.
- Use explanation → worked examples → exercises → my answer → detailed feedback.
- Do not reveal an exercise's answer before I attempt it.
- When I make a mistake, identify exactly where my reasoning failed.
- Use Active Recall and spaced review.
- Pair technical terms as English term (Vietnamese meaning).
- Prefer durable understanding over rushing through the roadmap.
- Adapt study load to my energy and health. If I have a headache or feel unwell, prioritize rest or a lighter review.

7. Checkpoint Update Protocol

After each meaningful learning milestone, update or create a checkpoint containing:

- Date and topic.
- Concepts studied.
- Exercises attempted and results.
- Mistakes and corrected reasoning.
- Concepts I can explain independently.
- Concepts still requiring hints or review.
- Evidence supporting the mastery assessment.
- Next recommended step.

Do not mark a topic as mastered merely because I recognize an explanation or answer one easy question correctly.

8. Session Handoff

For the next session, begin from this checkpoint and ask one short recall question about Q3.

Wait for my explanation before teaching the solution. Evaluate my reasoning, not only the final output.
