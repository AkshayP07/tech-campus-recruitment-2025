### Solutions Considered
I initially considered a simple line-by-line scan, but that would be too slow for a 1 TB file.
I also looked into building an index for faster lookups, but that added unnecessary complexity for a one-off query.
In the end, I chose a binary search combined with a sequential scan since the logs are sorted by date. 
This method is fast and memory efficient.

### Final Solution Summary
The final solution uses binary search to quickly locate the first log entry for the target date and then reads sequentially until the date changes.
This minimizes disk I/O and keeps memory usage low, making it ideal for processing large files.

### Steps to Run
Clone the repo and go the /tech-campus-recruitment-2025/src path
then in the terminal write the command to compile the code
and then run the binary with a date argument : ./extract_logs 2025-02-26
Detailed steps are below:

### Project Setup:
Organize your project as follows:

tech-campus-recruitment-2025/
├── src/
│   └── extract_logs.cpp
├── log_file.log
└── output/

Compile the Code:
Open a terminal, navigate to the src/ folder, and run:

g++ -o extract_logs extract_logs.cpp
Run the Application:
Execute the binary with a date argument:

./extract_logs 2024-12-01
The output will be saved in output/output_2024-12-01.txt.
