# **📌 vmstat Command in Linux**

## **📖 Command Name & Purpose**

🔹 **vmstat (Virtual Memory Statistics)** is a Linux command-line tool used to monitor **system performance**.

🔹 It provides real-time statistics on **CPU usage, memory, processes, disk activity, and system I/O**.

---

## **🌟 Key Features**

✅ Displays **CPU usage**, **memory statistics**, and **processes**.

✅ Helps in **performance monitoring and troubleshooting**.

✅ Shows **disk and I/O activity**.

✅ Provides **real-time updates** at specified intervals.

✅ Lightweight compared to other monitoring tools like `top`.

---

## **📝 Basic Syntax**

```
vmstat [options] [delay] [count]

```

🔹 **`options`** → Modify output format.

🔹 **`delay`** → Interval (in seconds) between updates.

🔹 **`count`** → Number of updates before stopping.

---

## **⚙️ Common Options and Their Descriptions**

| **🔹 Command** | **📌 Description** |
| --- | --- |
| `vmstat` | 📊 Displays a one-time summary of system performance. |
| `vmstat 2 5` | ⏳ Updates statistics **every 2 seconds** for **5 iterations**. |
| `vmstat -s` | 📜 Shows detailed system statistics in a **human-readable format**. |
| `vmstat -d` | 💽 Displays **disk statistics**. |
| `vmstat -p <device>` | 🔍 Shows **partition-specific** statistics (e.g., `/dev/sda`). |
| `vmstat -a` | 🔥 Displays **active and inactive memory** details. |
| `vmstat -t` | 🕒 Adds a **timestamp** to the output. |
| `vmstat -w` | 🖥️ Provides **wide output** format for better readability. |

---

## **📌 Examples for All Switches with Explanation**

### **1️⃣ Basic System Performance Statistics**

📌 **Command:**

```
vmstat

```

📌 **Description:**

🔹 Displays a **snapshot** of system performance, including **CPU, memory, processes, and disk activity**.

📌 **Output:**

```
\e[1;36mprocs -----------memory---------- ---swap-- -----io---- --system-- -----cpu-----\e[0m
\e[1;33mr     b     swpd   free   buff  cache   si   so    bi    bo   in    cs  us  sy  id  wa  st\e[0m
\e[1;32m1     0        0  50234  12948  178920    0    0     1     5  1234  1456   2   1  96   1   0\e[0m

```

📌 **Explanation:**

- **Processes (`procs`)**: `r` (running), `b` (blocked).
- **Memory (`memory`)**: Swap (`swpd`), Free (`free`), Buffer (`buff`), Cache (`cache`).
- **CPU Usage (`cpu`)**: `us` (user), `sy` (system), `id` (idle), `wa` (waiting).

---

### **2️⃣ Real-Time Performance Monitoring**

📌 **Command:**

```
vmstat 2 5

```

📌 **Description:**

🔹 Updates system statistics **every 2 seconds**, repeating **5 times**.

📌 **Output:**

```
\e[1;36mprocs -----------memory---------- ---swap-- -----io---- --system-- -----cpu-----\e[0m
\e[1;33mr     b     swpd   free   buff  cache   si   so    bi    bo   in    cs  us  sy  id  wa  st\e[0m
\e[1;32m1     0        0  50234  12948  178920    0    0     1     5  1234  1456   2   1  96   1   0\e[0m
\e[1;32m0     0        0  50012  13010  178000    0    0     3     8  1240  1460   3   2  94   1   0\e[0m

```

📌 **Explanation:**

- Helps **track system changes** over time.
- If **CPU idle (`id`) is low**, the system might be overloaded.
- If **swap (`swpd`) increases**, the system is using virtual memory due to low RAM.

---

### **3️⃣ Display System Memory Statistics**

📌 **Command:**

```
vmstat -s

```

📌 **Description:**

🔹 Displays **detailed memory statistics** in a **human-readable format**.

📌 **Output:**

```
\e[1;33m       16 GB total memory\e[0m
\e[1;32m       12 GB used memory\e[0m
\e[1;31m        4 GB free memory\e[0m
\e[1;36m       512 MB buffer memory\e[0m
\e[1;33m       10 GB swap total\e[0m
\e[1;32m        1 GB swap used\e[0m
\e[1;31m        9 GB swap free\e[0m

```

📌 **Explanation:**

- **Total Memory** → Physical RAM installed.
- **Used Memory** → Memory actively used by processes.
- **Free Memory** → Available RAM.
- **Swap Memory** → Virtual memory usage.

---

### **4️⃣ Show Disk Statistics**

📌 **Command:**

```
vmstat -d

```

📌 **Description:**

🔹 Displays **disk reads, writes, and activity statistics**.

📌 **Output:**

```
\e[1;36m    disk      reads   writes   sectors_read  sectors_written\e[0m
\e[1;33m    sda      10453   7890     10832040      20154321\e[0m

```

📌 **Explanation:**

- **Reads/Writes** → Number of disk operations.
- **Sectors Read/Written** → Amount of data processed.

---

### **5️⃣ Show Active and Inactive Memory**

📌 **Command:**

```
vmstat -a

```

📌 **Description:**

🔹 Displays **active and inactive memory** usage.

---

### **6️⃣ Add Timestamp to Output**

📌 **Command:**

```
vmstat -t

```

📌 **Description:**

🔹 Shows the **current date and time** in the output.

---

### **7️⃣ Wide Output for Better Readability**

📌 **Command:**

```
vmstat -w

```

📌 **Description:**

🔹 Expands output columns **to improve readability** on wide screens.

---

### **8️⃣ Show Partition-Specific Statistics**

📌 **Command:**

```
vmstat -p /dev/sda

```

📌 **Description:**

🔹 Displays **disk I/O statistics** for a specific partition (`/dev/sda`).

---

## **💡 Use Cases**

🔹 **Monitor CPU Usage** → Detect high CPU consumption with `vmstat 1 10`.

🔹 **Check Memory Usage** → Find low memory issues with `vmstat -s`.

🔹 **Analyze Disk Performance** → View disk read/write stats using `vmstat -d`.

🔹 **Troubleshoot System Lag** → Identify **high CPU load, swap usage, or disk I/O bottlenecks**.
