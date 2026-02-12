Challenge Faced in the Project – Electronic Toll System Automation

Background 
While working on the Electronic Toll Collection (ETC) system, one of the core components of our project is the transaction processing engine. When a customer travels on our/partner roads a trip will be generated and posted through a .tr file to our toll authority. These files are critical because they contain complete trip information like at trip time, which lane, which plaza , occupant LOV/HOB , vehicle class, fare.
Each .tr file includes:
A Header record (file generation date, checksum, file size, etc.)


A Pre-processing record


A Transaction record containing 50+ comma-separated fields (such as lane number, transaction date and time, tag ID, charging amount, discount amount, image count, timestamps, and more)


Initially, the process of creating and posting .tr files was done manually by the team. We have to:
Enter specific fields in the file manually


Recalculate checksum and file size


Use FileZilla to upload/post the file


This process took more than one hour just to post a single transaction for a specific vehicle. During testing, this became a major bottleneck because validating transaction processing required multiple file updates, and each change consumed significant time and effort.
The Challenge
The main challenge I faced was reducing the time required to test transaction processing. Our team was spending over an hour for a single transaction update, which slowed down the overall testing cycle.
Additionally:
The .tr file structure was complex, with more than 50 fields


Each field had a specific format and validation rule as per the ICD (Interface Control Document)


The file required accurate checksum and file size calculation


Even a small formatting error would cause transaction rejection


Understanding every field and its significance took considerable effort.

The Solution
To overcome this problem, I decided to automate the entire process using Python.
I referred to the ICD documentation in detail and:
Analyzed each field in the .tr file structure


Understood the validation rules and formatting standards


Wrote Python scripts to dynamically generate valid .tr files


Implemented logic to automatically calculate checksum and file size


Automated the posting process instead of manually using FileZilla


My first attempt did not produce the exact expected output.
 The second attempt gave partial results.
 After refining the logic and correcting formatting issues, the third iteration successfully generated valid .tr files.
It took me more than three days of continuous effort to fully automate the process.

Impact
After implementing the automation:
The team can now post a transaction for any vehicle within 1 minute


Multiple transactions can now be generated and posted in under a minute


Manual dependency was eliminated


Testing efficiency improved drastically


Overall project turnaround time was significantly reduced


This experience not only improved our workflow but also enhanced my understanding of structured file processing, checksum logic, and automation using Python.
