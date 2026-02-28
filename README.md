📊 Nginx Log Analyser :
A lightweight Bash script to quickly analyze Nginx access logs and extract useful insights such as:

🔝 Top 5 IP addresses with the most requests

📂 Top 5 most requested paths

📡 Top 5 HTTP response status codes

🌐 Top 5 user agents

This tool is ideal for Linux administrators, DevOps engineers, and security analysts who need quick command-line insights without installing heavy log analysis tools.

🚀 Features

✅ Pure Bash script (no external dependencies)

✅ Fast log parsing using awk, sort, uniq, and head

✅ Works on standard Nginx access log format

✅ Simple and easy to extend

✅ Lightweight alternative to full log analysis platforms

📁 Project Structure
.
├── nginx-log-analyser.sh
└── README.md
🛠 Requirements

Linux / Unix-based OS

Bash shell

Standard CLI utilities:

awk

sort

uniq

head

These are pre-installed on most Linux distributions.

⚙️ Installation

Clone the repository:

git clone https://github.com/kpratikshak/nginx-log-analyser.git
cd nginx-log-analyser

Make the script executable:

chmod +x nginx-log-analyser.sh
▶️ Usage
./nginx-log-analyser.sh <nginx-access-log>
Example:
./nginx-log-analyser.sh /var/log/nginx/access.log
📌 Sample Output
Top 5 IP addresses with the most requests:
192.168.1.10 - 150 requests
10.0.0.5 - 120 requests
172.16.0.3 - 98 requests
...

Top 5 most requested paths:
/index.html - 200 requests
/api/login - 150 requests
/images/logo.png - 130 requests
...

Top 5 response status codes:
200 - 450 requests
404 - 30 requests
500 - 5 requests
...

Top 5 user agents:
Mozilla/5.0 - 300 requests
curl/7.68.0 - 50 requests
PostmanRuntime/7.28.4 - 20 requests
...
🧠 How It Works

The script processes the Nginx log file using standard Unix text-processing tools:

Extracts specific fields using awk

Sorts entries

Counts occurrences with uniq -c

Sorts numerically in descending order

Displays top 5 results

Field Mapping (Standard Nginx Log Format)
Field	Description
$1	Client IP Address
$7	Requested Path
$9	HTTP Status Code
$6	User Agent (via double-quote delimiter)
🔒 Error Handling

The script handles:

❌ Missing log file argument

❌ Non-existent log file

Example error:

Usage: ./nginx-log-analyser.sh <nginx-access-log>
Error: Log file not found!
📈 Use Cases

Detect suspicious IP traffic

Identify high-traffic endpoints

Monitor error response trends (404, 500, etc.)

Analyze crawler/bot activity

Quick production troubleshooting
