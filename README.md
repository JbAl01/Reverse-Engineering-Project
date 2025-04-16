We had a course titled Computer Network Attack that included a project component later assessed in the exam. We received a file 24 hours prior to the exam, which we had to analyze and prepare answers for before it began. The task involved reverse-engineering the input to generate our own password that would be accepted as valid by the program.







<img width="600" alt="Backdoor password" src="https://github.com/user-attachments/assets/6c513ad0-a8fc-4dca-8050-386825e62d44" />






Here is a test to see if it accepts anything, which it dont.






<img width="600" alt="Invalid Backdoor" src="https://github.com/user-attachments/assets/6af657bf-1a7b-48e2-b850-31c472d3aaf4" />


First I opened the file with Ghidra, and see if I can find interesting functions. The idea for me was to understand the logic, so that I can replicate it and generate my own password that follows the logic. I found many interesting functions, one that looked similar is the same input page as previous. 

<img width="600" alt="Front page input" src="https://github.com/user-attachments/assets/375224e2-22db-4f94-b44b-5aaef471dcef" />

Inside this I saw a few functions that caught my attention one being this function that contains the whole algorithm for how the password works. 

<img width="700" alt="Function the whole logic" src="https://github.com/user-attachments/assets/9d0a46de-19eb-49a1-9924-c321ec5b6a8f" />

