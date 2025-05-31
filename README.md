# Day-16

# 🔁 Multi-Process Number Operations using `fork()` in C

This C program demonstrates **process creation using `fork()`** to execute **different mathematical operations** in parallel via a structured process tree.

---

## 📌 Features

🧠 Based on user input of 3 numbers:
- 🧒 Child B (of A): Calculates **factorial** of the first number.
- 🧒 Child C (of A):
  - 👶 Child D (of C): Generates **Fibonacci series** up to the second number.
  - 👶 Child E (of C): Checks if the third number is **prime**.

🧵 This results in **5 total processes**:
- Parent (A)
- Child B
- Child C
- Child D (C’s child)
- Child E (C’s child)

---

## 🧾 Code Structure

```c
fork();          // A creates B
fork();          // A creates C
fork();          // C creates D
fork();          // C creates E
Each child does a different task:

✅ B → factorial of number 1

✅ D → fibonacci of number 2

✅ E → prime check of number 3

💻 Program Flow
🔷 Input
bash
Copy
Edit
Enter the first number: 5
Enter the second number: 2
Enter the third number: 3
🔷 Sample Output
bash
Copy
Edit
Parent (A)
Id: 19062

Child of A(B)
Parent Id: 19062
Factorial of first number: 120

Child of A(C)
Parent Id: 1

Child of C(D)
Fibonacci Series: 0, 1

Parent (C)
Id: 19070

Child of C(E)
Parent Id: 19070
The number 3 is prime.
⚙️ How to Run
Compile

bash
Copy
Edit
gcc exe1.c -o exe1
Run

bash
Copy
Edit
./exe1
Observe Output
Outputs may appear in varying orders due to concurrent execution.

🧠 Concepts Demonstrated
Concept	Description
fork()	Creates child processes
getpid()	Gets current process ID
getppid()	Gets parent process ID
for loop	Used for factorial and Fibonacci generation
bool logic	Checks for prime number using loop and modulus operation
