Can you describe the key challenges you encountered during your project and how you addressed them?”

During my Toll Management Project, one of the major challenges I faced was related to transaction posting and balance deduction testing.

🔹 Situation:

The system manages customers, tags, vehicles, and payment processing.
To deduct balance from a customer account, we needed to post transactions using a .tr file format provided by the development team.

🔹 Challenge:

The challenge was:

Each .tr file had to be manually modified for different accounts.

Fields like Tag ID, Subscriber ID, checksum, and file name had to be unique.

Even a small mistake would cause transaction failure.

File names had to be unique.

If transactions were posted within 60 seconds, the system marked them as duplicate transactions.

Files were uploaded manually using FileZilla, which was time-consuming.

Testing multiple accounts manually was very complex and inefficient.

🔹 Action Taken:

To solve this problem:

I carefully studied the ICD document to understand the file structure.

I collaborated with the development team and attended KT sessions.

I wrote a Python script to:

Automatically generate .tr files

Dynamically update Tag ID, Subscriber ID, checksum

Ensure unique file names

I automated the FileZilla upload process using Python.

To solve the duplicate transaction issue, I implemented a 60-second delay (sleep function) between transactions.

I also enhanced the script to support:

T0 to T10 transaction types

Lane-based transaction configuration

Multiple accounts testing

Initially, my first few attempts produced incorrect outputs, but after debugging and validating against expected results, I successfully implemented the correct solution.

🔹 Result:

Reduced manual effort significantly

Enabled bulk transaction posting for multiple accounts

Improved testing efficiency

My entire team started using my automation script

Later, when APIs were introduced for transaction posting, the transition was smooth because we already understood the logic deeply

🎯 Strong Closing Line for Interview:

“This experience improved my automation skills, problem-solving ability, and collaboration with cross-functional teams.”
