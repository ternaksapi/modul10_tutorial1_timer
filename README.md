# Tutorial Modul 10 - Timer
---
### Muhammad Yusuf Haikal
### 2206081490
### Pemrograman Lanjut A
---

## 1.2 Understanding How It Works
After putting `println!("Haikal's komputer: hey hey");` right after the spawner, when running the program we can see this sequence of message:
![image](https://github.com/ternaksapi/modul10_tutorial1_timer/assets/116947973/f7efe912-1ee6-4b55-8bdb-8f60a59cf46a)

We can see that the new line we have put is being printed first, and after that then the asychronous message is printed. From this, we can see that after the spawner (`spawner.spawn(async {...})`) is called, our new line is immediately executed synchronously. After that, then the executer calls the asynchronous task that we have made, with a 2 second gap between the first and the second message.

## 1.3 Multiple Spawn and removing drop
Replicating the spawner and removing `drop(spawner)` from the code:
![image](https://github.com/ternaksapi/modul10_tutorial1_timer/assets/116947973/63a6eb6d-bbbc-44aa-8604-fe280db46122)

Here is the result of running the program two different times:
![image](https://github.com/ternaksapi/modul10_tutorial1_timer/assets/116947973/103148ce-f9ba-44f0-8780-4c8bcf1f7cd1)
![image](https://github.com/ternaksapi/modul10_tutorial1_timer/assets/116947973/2903b200-c137-4933-9f5d-7119c062ffcc)

Theres two things we should notice. First, since we replicated the spawner, it is going to print out the statement three times, as seen from the terminal. Second, when all the asynchronous tasks have been finished, the program is still running indefinitely since we dropped the `drop(spawner)`, making the program unable to determine if there are more task to be spawned.
