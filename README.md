# 📝## **64×8 Single-Port RAM – Verilog HDL Implementation**


---

# 📘 Project Description  

This project implements a **64-byte (64×8) single-port RAM** using Verilog HDL.  
The memory supports **synchronous write** and **asynchronous read** operations.

### **RAM Features**

- 64 memory locations  
- Each location stores **8-bit data**  
- Write operation occurs on **positive clock edge**  
- Read operation is asynchronous through an address register  
- Fully working Verilog testbench included  

This design is useful for beginners learning memory modeling in Verilog.

---

# 🚀 General Procedure for Any Quartus HDL Project  

*(This flow applies to this project and any other HDL design.)*

---

## **1️⃣ Create a New Project**

- Open **Intel Quartus Prime**  
- Go to **File → New Project Wizard**  
- Choose a workspace folder  
- Enter project name (example: `single_port_ram_project`)  
- Complete the setup  

---

## **2️⃣ Create Design File (HDL Source)**

Create a new **Verilog file** and add:

- `port_ram.v`

This file contains:

- RAM array (`reg [7:0] ram_memory [63:0]`)  
- Address register  
- Synchronous write logic  
- Asynchronous read logic  

Save the file.

---

## **3️⃣ Create Testbench File**

Create another **Verilog HDL file**:

- Paste the testbench: `port_ram_tb.v`

The testbench performs:

### **Write Operations**
- Writes values to addresses 0, 2, and 7  

### **Read Operations**
- Reads back data from the same addresses  

A 20ns clock period (`#10`) is used.

Save the testbench file.

---

## **4️⃣ Add Required Files to the Project**

Go to:  
**Project → Add/Remove Files in Project**

Add:

- `port_ram.v`  
- `port_ram_tb.v`  

---

## **5️⃣ Set the Top-Level Entity**

Go to **Assignments → Settings**

Set:


Click **OK**.

---

## **6️⃣ Compile the Project**

- Go to **Processing → Start Compilation**  
- Ensure compilation completes with 0 errors  

---

# 🧪 Simulation Procedure  

You may use:

- **ModelSim / QuestaSim**  
- **Quartus Native RTL Simulator**

---

## **1️⃣ Launch Simulation**

Go to:  
**Tools → Run Simulation Tool → RTL Simulation**

---

## **2️⃣ Load the Testbench**

Your testbench module should be:


ModelSim will compile:

- RAM module  
- Testbench  

---

## **3️⃣ Run Simulation & View Waveforms**

Inside ModelSim:

- Run simulation  
- Add all signals to waveform  
- Observe write and read operations  

### **Expected Waveform Behavior**

- During write:
  - `write_enable = 1`
  - Data stored at given `ram_address` on the rising clock edge  

- During read:
  - `write_enable = 0`
  - Changing `ram_address` outputs the stored value  

Example expected results:

| Address | Written Data | Read-back Data |
|---------|---------------|----------------|
| 0       | 0x10          | 0x10           |
| 2       | 0x11          | 0x11           |
| 7       | 0xAF          | 0xAF           |

---

# 🔌 (Optional) FPGA Pin Assignment  

Only required for real hardware testing.

Assign:

- `clk`  
- `write_enable`  
- `ram_address[5:0]`  
- `data_in[7:0]`  
- `data_out[7:0]`  

Recompile → Program FPGA

---

# 📁 Recommended Folder Structure


---

# 🧩 What You Can Customize

- RAM size (e.g., 128×8, 256×8)  
- Data width (e.g., 16-bit, 32-bit)  
- Read type (synchronous vs asynchronous)  
- Write enable bursting  
- Clock speed  
- Initial memory values  

---

# ⭐ This README format can be used for ANY memory-based Verilog project!


