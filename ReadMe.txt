DLP 15.1
	Windows Login
	ServerUser
	ServerP@ss!123
	
	oracle home - oracle OraclePass123
	SYS, SYSTEM - OraclePass123
	protect - OraclePass123
	SymantecDLP - OraclePass123
	SymantecDLPUpdate - OraclePass123
	Enforce Administrator Account - Administrator OraclePass123
	
	
	
	1. You will need to import a solution pack before instaliing the detection server. Only 1 solution pack can be installed, once it is installed you cannot change it.
	The solutions packs are located C:\Users\ServerUser\Downloads\Symantec_DLP_15.1_Solution_Packs.zip
	
	To Import a solution pack:
	
	You import a Symantec Data Loss Prevention solution pack on the Enforce Server computer.
	The following rules apply when you import a solution pack:
	* 	You must import the solution pack immediately after you install the Enforce Server and
		before you install any detection server. (If you performed a single-tier installation, you must
		import the solution pack immediately after the installation is complete.)

	* 	Only import a solution pack that was created for the specific Enforce Server version you
		installed. Do not import a solution pack that was released with a previous version of the
		Symantec Data Loss Prevention software.

		For example, do not import a version 14.6 solution pack on a version 15.1 Enforce Server.

	* 	Do not attempt to import more than one solution pack on the same Enforce Server, as the
		solution pack import fails.
	* 	Do not import a solution pack on an Enforce Server that was modified after the initial
		installation; the solution pack import fails.
	* 	After you import a solution pack, you cannot change the installation to use a different
		solution pack at a later time.

	1. Decide which solution pack you want to use.

	Note: You must use a version 15.1 solution pack; earlier versions are not supported.
	
	2. Log on (or remote log-on) as Administrator to the Enforce Server computer.
	3. Copy the solution pack file from DLPDownloadHome\DLP\15.1\Solution_Packs\ to an easily accessible local directory.
	4. In Windows Services, stop the SymantecDLPManager service.
	5. Copy the Classpath.txt file located at DLPDownloadHome\DLP\15.1\Solution_Packs\	
	   and use it to replace (overwrite) the Classpath.txt file located at c:\Program
	   Files\Symantec\Data Loss Prevention\EnforceServer\15.1\Protect\Config\SolutionPackInstaller.
	6. From the command-line prompt, change to the \Program Files\Symantec\Data LossPrevention\Enforce Server\15.1\protect\bin directory on the Enforce Server. 
	   This directory contains the SolutionPackInstaller.exe application. 
	   For example:
	   cd c:\Program Files\Symantec\Data Loss Prevention\Enforce Server\15.1\protect\bin
	7. Import the solution pack by running SolutionPackInstaller.exe from the command line and specifying the solution pack directory path and file name. 
	   The solution pack directory must not contain spaces.

	For example, if you placed a copy of the Financial_v15.1.vsp solution pack in the
	\Program Files\Symantec\Data Loss Prevention directory of the Enforce Server, you would enter:
	
	SolutionPackInstaller.exe import c:\Program Files\Symantec\Data Loss Prevention\Financial_v15.1.vsp

	8. Check the solution pack installer messages to be sure that the installation succeeded without error.
	9. Restart the SymantecDLPManager service.
	10. After you have completed importing the solution pack, do one of the following depending on the type of installation:

	* On a single-tier installation register a detection server.
	See “Registering a detection server” on page 51 of Symantec™ Data Loss Prevention Installation Guide for Windows.
	See “Verifying a detection server installation” on page 50 of Symantec™ Data Loss Prevention Installation Guide for Windows.