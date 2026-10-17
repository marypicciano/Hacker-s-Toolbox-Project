# Hacker-s-Toolbox-Project
This project includes documentation about various cybersecurity tools, their similairities and differences, and a demonstration of how to use the tool Cewl in Kali Linux.

By: Mary Picciano

# User Handbook of Cewl

# Introduction 
Purpose of the Tool: Cewl (Custom Word List Generator) is an open-source cybersecurity tool that can be used to create word lists from websites. It is a Ruby app, meaning the software is written using Ruby programming and requires a Ruby environment to actually execute the tool. The wordlists created by Cewl can then be used by password cracking tools such as John the Ripper. By collecting wordlists that are relevant to a particular website, cybersecurity professionals can use Cewl to exploit any potential password weaknesses.
Intended Audience: Cewl was created with the intended audience being cybersecurity professionals, penetration testers, system administrators, and any other job titles that would perform security assessments on passwords. Additionally, it can also be used by cybersecurity students to understand how hackers get password lists to use for brute force attacks, as well as practice ethical hacking. It is important to use tools such as Cewl ethically and not for performing malicious attacks. While some unethical hackers may try to use this to generate a password list, cybersecurity professionals can use this tool to their advantage to spot any weak passwords before the hackers do. 
Common Cybersecurity Applications: Cewl is used for password auditing and penetration testing primarily. Security professionals use Cewl to generate common words used on an organization’s website. These lists can then be used in password assessments to identify passwords that may be based on public information, including the company name, a product it may sell, or any other terms associated with the organization. By creating these lists, it makes password assessments more relevant to the company or organization that is being evaluated. However, it is important to note that Cewl is not used for the actual act of password cracking, but rather creates the list to use for it. 

# Installation 
System Requirements: Cewl is compatible with Linux, Windows, and macOS. So, in order to use this tool, it needs to be done in one of these operating systems.
Installation Steps: Since this a ruby app, there are certain gems that need to be installed for Cewl to run, including mime, mime-types, mini_exiftool, nokogiri, public_suffix, rubyzip, spider, and getoptlong. The easiest way to install these is to run the Linux command : 
gem install bundler 
bundle install
Additionally, it could be installed manually with the command gem install xxx
Once that is done, you can install Cewl with the following steps and commands.
1. Clone the github respiratory:
git clone https://github.com/digininja/CeWL.git
cd CeWL
2. Install dependencies:
bundle install
3. Make the script executable: 
chmod u+x ./cewl.rb
4. Make Cewl available system wide (this is optional but beneficial):
sudo ln -s $(pwd)/cewl.rb /usr/local/bin/cewl
5. Verify that the installation was successful:
** # Check if the script runs (should show version and usage)
**./cewl.rb --version
**# If you created a symlink or added to PATH, test the cewl command
**cewl --version
If you are using Kali Linux, Cewl is pre-installed, so they only command you have to run is sudo apt update && apt install cewl if for some reason it was not installed. To check if it is installed, run the command cewl -h. If an options list of appears of several commands you can use within cewl, that means it is installed on your Kali Linux.
Initial Configuration: Once Cewl is installed, there are several other commands you can use to set preferences for when generating your word list. There is not extensive configuration that is needed once installed, but there are several functionalities of this tool that can be used on a website. 

# Usage Guide 

Primary Function: The primary function of Cewl is to provide a custom wordlist by reading a website and extracting common words used on it. The wordlist can then be saved as a text file and used during authorized password assessments to look for weak passwords. There are multiple functions within Cewl that allow users to set preferences of how Cewl analyzes a website and provides a Wordlist. 
Step-by-Step Procedure:
1. Open Kali Linux or the macOS terminal.
2. Run the command cewl [options] [URL] to display all of the options cewl has that you can adjust to create a word list to your preferences. 
<img width="886" height="877" alt="Screenshot 2026-10-08 at 11 25 16 PM" src="https://github.com/user-attachments/assets/14e9b896-fc7e-4e2c-9b3f-73c40dd9de43" />

All of these commands can be used to specify to Kali Linux what type of wordlist you want from the website.

3. To create a wordlist, you can use a direct URL in the Linux command line. Then, it will provide an output of words most directly associated with the website. 
<img width="795" height="293" alt="Screenshot 2026-10-08 at 11 35 11 PM" src="https://github.com/user-attachments/assets/4a010d61-41e5-42dd-b156-d857ebe7e75c" />

4. As shown in the image of commands, you can just the minimum length of words to your preference. It defaults to three characters, but you can technically choose any number. For example, if you wanted words with a minimum of 6 characters, you could run the following command and receive an output similar to the one below.
<img width="787" height="257" alt="Screenshot 2026-10-08 at 11 49 39 PM" src="https://github.com/user-attachments/assets/e02bade9-aa38-4a24-bc94-1eb2d00f5bab" />

5.  Also shown in the image of commands you can adjust the depth of crawling on a website, which essentially measures how many web pages Cewl will look for words in. For example, if you set the depth to 2, Cewl would look for words you could find in two clicks on the webpage.
<img width="792" height="304" alt="Screenshot 2026-10-08 at 11 49 48 PM" src="https://github.com/user-attachments/assets/5f1e2b15-8f11-4515-80e5-0d06c80e361d" />

6. You can also save these word lists into text files which can then be used for password auditing. The command below would create a file named wordlist.txt
<img width="784" height="56" alt="Screenshot 2026-10-08 at 11 49 57 PM" src="https://github.com/user-attachments/assets/f37852f6-ad03-4b1b-93ee-086370c959ee" />

7. You can also run a command to extract data from a website into readable information as shown below.
<img width="781" height="247" alt="Screenshot 2026-10-08 at 11 50 25 PM" src="https://github.com/user-attachments/assets/5d18961a-66cd-46d9-a697-304c514d36c2" />

8. Finally, you can combine all of these commands to run one command to generate a wordlist from a website that meets your requirements as shown below.
<img width="836" height="172" alt="Screenshot 2026-10-09 at 12 30 21 AM" src="https://github.com/user-attachments/assets/7428a5c4-9e50-4245-a0a9-ca82cbe2e747" />

# Common Errors and Troubleshooting Tips:
Cewl is better at creating small lists than larger ones, so it may struggle to create a large wordlist.
Cewl can crawl through public websites, but may be denied access to a private website. However, this can be resolved by using the command to authenticate a website, as shown in the image below. 
<img width="779" height="68" alt="Screenshot 2026-10-08 at 11 51 10 PM" src="https://github.com/user-attachments/assets/19702aee-c4ef-4423-a46a-77edf9be44b4" />

# Best Practices

Ethical Considerations: Cewl should only be used on websites that a user owns, or has permission to access or authorize. While generating a wordlist is not the same as password cracking, it is often used for password cracking, so it is important that it is only used for security password assessments and not for unethical hacking schemes. Users should always follow an organization's rules and requirements, avoiding gathering unnecessary personal information, and never use a website they do not have authorized access to.

Security Considerations: These wordlists often contain personal information, including email addresses and full names. When these lists are saved to textfiles, they should be stored securely and only shared with those who have authorized access. As shown in the usage guide, you can adjust the depth of website crawling, so users should minimize the amount of crawling they do on a website for only the necessary information they need. Finally, once the wordlists have served their purpose and are not needed anymore, they should be deleted. 

Professional Recommendations: Cybersecurity professionals should understand the concept of getting authorized access to websites they need permission for. Additionally, they should understand how to use the various settings in a respectful manner, such as minimizing depth crawl to only what is necessary. They should be able to articulate the purpose for each assessment they are doing and justify the need for a wordlist. If a wordlist is being used in a password assessment, they should be using only approved procedures for the assessment. 

# Video Demonstation: https://drive.google.com/file/d/1WFWXxxA0FJq0fIGe1cAWkndiuqdJuJAA/view?usp=drive_link 

# Links Used in Video:
https://github.com/digininja/Cewl

https://en.wikipedia.org/wiki/Computer_security

# References:
Kali Editors. (2025a, December 9). CEWL: Kali Linux Tools. Kali Linux. https://www.kali.org/tools/cewl/  
Wood, R. (2024). Digininja/CEWL: CeWL is a custom word list generator. GitHub. https://github.com/digininja/Cewl  
