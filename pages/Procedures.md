---
alias: subroutines, procedure
---

- Procedures are reusable sections of code that we can call from some location, execute that procedure, and then **return to where we left off**.
- To implement procedures in assembly we need to be able to:
  collapsed:: true
	- Jump to the procedure code, leaving a "return link" to know where to return
	- Find the return address and go back to that location
	- ((615ef242-b422-49f8-ade9-19f945f6ff7c))
-