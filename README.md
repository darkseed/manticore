Manticore
----------


Usage:

	$ ./manticore [CSV-FILE] [LAST-N-LINES]

	
Example:

Unix likes OS:

	$ ./manticore data.csv 20
	
Windows:

	> manticore.bat data.csv 20

Output example:

	$ ./manticore ~/Downloads/data.csv 20
	 + data source: CSV: /Users/robin/Downloads/data.csv

	 + padding...

	   0|17 0|18 1|19 X|20
	   0|14 0|16 0|18 X|20
	   0|11 0|14 0|17 X|20
	   1|08 0|12 0|16 X|20
	   0|05 1|10 0|15 X|20
	   1|02 1|08 0|14 X|20


	 + breaking down...

	   --------------- 0|17 0|18 1|19 X|20 -----------
	   01 01 01 00
	   00 01 01 01
	   01 00 01 01
	   01 01 00 01
	   01 01 01 00
	   01 01 01 01
	   01 01 01 01
	   00 01 01 01
	   00 00 01 01 +
	   00 00 00 01
	   00 00 00 00
	   00 00 00 00
	   00 00 00 00
	   00 00 00 00
	   00 00 00 00
	   01 00 00 00
	   --------------- 0|14 0|16 0|18 X|20 -----------
	   01 00 01 00
	   01 01 01 01
	   01 01 00 01
	   01 01 01 01
	   00 01 01 00
	   00 01 01 01
	   00 00 01 01 +
	   00 00 01 01 +
	   00 00 00 01
	   00 00 00 01
	   00 00 00 00
	   00 00 00 00
	   01 00 00 00
	   --------------- 0|11 0|14 0|17 X|20 -----------
	   01 01 01 00
	   00 01 00 01
	   00 01 01 01
	   00 01 01 01
	   00 00 01 00 -
	   00 00 01 01 +
	   00 00 01 01 +
	   00 00 00 01
	   00 00 00 01
	   01 00 00 01
	   --------------- 1|08 0|12 0|16 X|20 -----------
	   00 01 00 00
	   00 01 01 01
	   00 00 01 01 +
	   00 00 01 01 +
	   00 00 01 00 -
	   00 00 01 01 +
	   01 00 00 01
	   --------------- 0|05 1|10 0|15 X|20 -----------
	   00 00 01 00 -
	   00 00 01 01 +
	   00 00 01 01 +
	   01 00 01 01
	   --------------- 1|02 1|08 0|14 X|20 -----------
	   01 00 01 00

	 + result:

	   Positives: 10, Negatives: 3
	   Probability:
	               ▲ 76%
	               ▼ 23%