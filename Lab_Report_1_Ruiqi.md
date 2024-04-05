
# 1. Share an example of using the command with no arguments.

## Command `cd`
<img width="291" alt="Screen Shot 2024-04-03 at 5 32 21 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/4d3526f6-c0da-4cf6-84b7-5b1a7d66ccc4">

1. Absolute path before command: `/Users/ahri/Desktop`
2. The output is empty because we didn't change any directory in the argument. 
3. This is not an error.

## Command `ls`
<img width="649" alt="Screen Shot 2024-04-03 at 5 55 03 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/21637624-670b-489d-acab-c227c8da7cc1">

1. Absolute path before command: `/Users/ahri/Desktop`
2. The output lists all the files I have in the desktop. 
3. This is not an error.

## Command `cat`
<img width="301" alt="Screen Shot 2024-04-03 at 6 05 00 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/5943c4a6-3381-474c-bf89-1e78885fdccd">

1. Absolute path before command: `/Users/ahri/Desktop`
2. The output is empty and will repeat my inputs because we didn't specify the files we want the command to print. 
3. This is not an error.


# 2. Share an example of using the command with a path to a directory as an argument.

## Command `cd`
<img width="344" alt="Screen Shot 2024-04-05 at 3 40 58 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/6f9606a1-a50c-4f1a-8345-45984b8fe4c8">

1. Absolute path before command: `/Users/ahri/Documents`
2. Output is empty but we changed the current working directory `/Users/ahri/Documents` to `/Users/ahri/Documents/Spring 2024`.
3. Ihis is not an error.

## Command `ls`
<img width="335" alt="Screen Shot 2024-04-05 at 4 10 13 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/5500bd69-9f7e-438e-acc1-1c59f3638965">

1. Absolute path before command: `/Users/ahri/Documents`
2. The output lists all the files I have in the Documents directory.
3. This is not an error.

## Command `cat`
<img width="341" alt="Screen Shot 2024-04-05 at 4 26 27 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/e7c5300c-56ab-4652-85d3-4b364ab4de07">

1. Absolute path before command: `/Users/ahri/Documents`
2. The output has an error because we cannot `cat` an directory.
3. This is an error. The `cat` command expects an file as an argument. When we `cat` directories it don't have raw data this command can read and display.


# 3. Share an example of using the command with a path to a file as an argument.

## Command `cd`
<img width="386" alt="Screen Shot 2024-04-05 at 4 43 25 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/a3bbdcf2-047f-402b-b402-3fc54badf25f">


1. Absolute path before command: `/Users/ahri/Documents/Spring 2024/CSE 12/PA/cse12-pa1-Testing-master/pa1-starter/cse12pa1student`
2. The output has an error because we cannot `cd` a file.
3. This is an error. We cannot change the directory inside a file by using `cd` because the file `BasketTest.java` is not a directory. Instead, we can display the data in a file by using `cat`.

## Command `ls`
<img width="406" alt="Screen Shot 2024-04-05 at 4 44 57 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/b677531e-a274-402c-8d52-61136cdb1e33">


1. Absolute path before command: `/Users/ahri/Documents/Spring 2024/CSE 12/PA/cse12-pa1-Testing-master/pa1-starter/cse12pa1student`
2. The output is `BasketTest.java`. This output indicates that the file `BasketTest.java` exists in the current directory.
3. This is not an error.

## Command `cat`
<img width="864" alt="Screen Shot 2024-04-05 at 4 46 01 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/53a202f1-f16f-4972-babb-4d48524a4f0e">


1. Absolute path before command: `/Users/ahri/Documents/Spring 2024/CSE 12/PA/cse12-pa1-Testing-master/pa1-starter/cse12pa1student`
2. The output displays the content of the file `BasketTest.java`.
3. This is not an error. 


