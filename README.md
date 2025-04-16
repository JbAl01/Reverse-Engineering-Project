We had a course titled Computer Network Attack that included a project component later assessed in the exam. We received a file 24 hours prior to the exam, which we had to analyze and prepare answers for before it began. The task involved reverse-engineering the input to generate our own password that would be accepted as valid by the program.







<img width="600" alt="Backdoor password" src="https://github.com/user-attachments/assets/6c513ad0-a8fc-4dca-8050-386825e62d44" />






Here is a test to see if it accepts anything, which it dont.






<img width="600" alt="Invalid Backdoor" src="https://github.com/user-attachments/assets/6af657bf-1a7b-48e2-b850-31c472d3aaf4" />


First I opened the file with Ghidra, and see if I can find interesting functions. The idea for me was to understand the logic, so that I can replicate it and generate my own password that follows the logic. I found many interesting functions, one that looked similar is the same input page as previous. 

<img width="600" alt="Front page input" src="https://github.com/user-attachments/assets/375224e2-22db-4f94-b44b-5aaef471dcef" />

Inside this I saw a few functions that caught my attention one being this function that contains the whole algorithm for how the password works. 

<img width="700" alt="Function the whole logic" src="https://github.com/user-attachments/assets/9d0a46de-19eb-49a1-9924-c321ec5b6a8f" />

I went through all the functions used in here and got the conclusion that 1. They are using a separate function to calculate something, use that calculation to get an result which grants you access. The code splits the input into segments, processes each phase, it has 2 functions which is a ASCII Value. 

<img width="650" alt="Function ASCII" src="https://github.com/user-attachments/assets/766c8415-49b9-4d73-b36d-d09bbb90002d" />

This is ASCII value of 470, meaning that we can generate one value of 470, and the other one being 488

<img width="500" alt="Function ASCII Part 2" src="https://github.com/user-attachments/assets/e66fd2d6-ade0-4138-85dd-eed9640f9d3a" />

These two are then added side by side, so its total of 12 numbers, 6 on each part.

After calculating the password, I tested it and was in the system :-D

<img width="650" alt="Proof of backdoor (1)" src="https://github.com/user-attachments/assets/97c7e926-1d77-4112-bd56-0cd72a2b4bac" />




