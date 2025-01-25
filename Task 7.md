🚀 Enhancing Cybersecurity: A Simple Python Script for Log Analysis 🔍🐍

In today's digital world, keeping systems secure is crucial. 🔒 I just created a Python script that scans log files for failed login attempts to help detect potential security threats.

👨‍💻 Features:

Reads server logs.

Identifies and reports suspicious activities.

Easy to use and customizable!


https://www.linkedin.com/posts/activity-7287779359522705408-V8nc?utm_source=share&utm_medium=member_desktop




CODE:-


     import re

     def analyze_log(file_path):

    try:
    
        # Open the log file with proper encoding
        with open(file_path, 'r', encoding='utf-8', errors='ignore') as file:
            lines = file.readlines()
        
        # Initialize a counter for failed login attempts
        failed_attempts = 0

        # Debug: Check if the file was read correctly
        print(f"Analyzing log file: {file_path}")
        print(f"Successfully read {len(lines)} lines from the log file.")

        # Loop through each line in the log file
        for line in lines:
            # Debug: Print the line being analyzed (optional, remove for large files)
            # print(line.strip())

            # Check if the line contains 'Failed password'
            if "Failed password" in line:
                failed_attempts += 1

        # Output the result
        print(f"Total failed login attempts: {failed_attempts}")

    except FileNotFoundError:
        print(f"Error: The file '{file_path}' does not exist.")
    except PermissionError:
        print(f"Error: Permission denied for file '{file_path}'.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

