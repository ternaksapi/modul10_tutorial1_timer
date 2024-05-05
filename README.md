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
