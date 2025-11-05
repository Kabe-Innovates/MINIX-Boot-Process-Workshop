# MINIX System Boot Process

## 🎯 Objective
To understand and modify the MINIX boot process by editing the kernel’s source code to display a custom message during the boot phase.  
This workshop demonstrates how kernel-level source changes affect the operating system startup behavior.

---

## 🧰 Tools Required
- **VirtualBox**  
- **MINIX 3** (installed and configured)  
- **Access to terminal and kernel source** (`/usr/src/kernel`)  
- **Text editor** (`vi`, `nano`, or equivalent)

---

## ⚙️ Procedure / Implementation Steps

1. **Boot into MINIX** inside VirtualBox.  
   Ensure that the environment is properly configured with root privileges.

2. **Navigate to the kernel source directory:**
   ```bash
   cd /usr/src/kernel

3. **Open the `main.c` file:**

   ```bash
   vi main.c
   ```

4. **Locate the line** that displays the standard MINIX message:

   ```c
   printf("MINIX is open source software.\n");
   ```

5. **Insert your custom message** immediately after that line:

   ```c
   printf("Modified by : Kabelan G K\n");
   ```

6. **Save your changes** and exit the editor.

7. **Rebuild the kernel** and prepare a bootable image:

   ```bash
   cd /usr/src/releasetools
   make build
   make hdboot
   ```

8. **Reboot the system** to apply and test the modifications.

9. **Observe the boot sequence** — the new custom line should appear during startup.

---

## 🧩 Source Code Modifications

```c
/* File: /usr/src/kernel/main.c */

printf("MINIX is open source software.\n");
printf("Modified by : Kabelan G K\n");
```
![alt text](<screenshots/main c.png>)
---

## 🖥️ Observation / Output

During the MINIX boot process, the following lines are displayed:

```
MINIX is open source software....
Modified by : Kabelan G K
```
![alt text](<screenshots/boot interface.png>)


---

## 🧾 Conclusion

The MINIX system boot process was successfully modified to include a custom user-defined message.
This demonstrates a practical understanding of:

* The MINIX kernel source structure
* System build and boot image generation (`make build`, `make hdboot`)
* How source-level modifications reflect in system-level behavior

Such exercises strengthen the foundational knowledge of **Operating System internals** and **kernel customization**.

---

