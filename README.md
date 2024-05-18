## GoPortScanner

**GoPortScanner** is a lightweight and efficient command-line tool written in Go for scanning TCP ports on a target host. It allows you to scan a range of ports concurrently, identify open ports, and optionally report errors for failed connections.

**Features**

-   **Cross-Platform:** Runs on various operating systems like Linux, macOS, and Windows.
-   **Platform Support:** The tool can be run on Linux, Windows, and macOS. It also supports both 32-bit and 64-bit machines.
-   **Concurrent Scanning:** Improves performance for large port ranges by utilizing multiple goroutines.
-   **Timeout Control:** Limits the connection attempt duration for each port.
-   **Flexible Port Range:** Supports single ports, comma-separated lists, or port ranges using a hyphen (-).
-   **Error Reporting:** Displays detailed error messages for failed connections (optional).
-   **Clear Output:** Provides a concise output indicating open ports and any encountered errors.

**Notes**

The compiled binary is available in the [Releases](https://github.com/yoruakio/goportscan/releases) section for convenience. and The windows version are currently not be able run it right now, you can build it by yourself. I will fix it ASAP.

**Getting Started**

**Prerequisites**

-   Go 1.17 or later (https://go.dev/doc/install)

**Installation**

1. Clone this repository:

```bash
git clone https://github.com/yoruakio/goportscan.git
```

2. Navigate to the project directory:

```bash
cd goportscan
```

3. Build the project:

```bash
go build # Output: goportscan (or goportscan.exe on Windows)
```

4. Run the executable:

```bash
./goportscan -host example.com -range 80-85 -threads 100 -timeout 20
```

**Usage**

```bash
Usage of ./goportscan:
  -host string
    	Host or IP to scan (default "localhost")
  -range string
    	Port ranges e.g. 80,443,200-1000,8000-9000 (default "80,443")
  -threads int
    	Threads to use (default 100)
  -timeout duration
    	Timeout per port (default 1s)
  -verbose
    	Show errors for failed ports
```

**Examples**

-   Scan a single port (e.g., 80) on localhost:

```bash
./goportscan -host localhost -range 80
```

-   Scan multiple ports (e.g., 80, 443, 8080) on a remote host:

```bash
./goportscan -host example.com -range 80,443,8080
```

-   Scan a range of ports (e.g., 2000-3000) with verbose output:

```bash
./goportscan -host localhost -range 2000-3000 -verbose
```

**Contributing**

Contributions are welcome! Feel free to open issues or submit pull requests to improve the tool.

**License**

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
