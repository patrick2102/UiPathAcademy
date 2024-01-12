In this state the robot reads the configuration file and initializes the applications used in the process.

If success will jump to the [[Get Transaction Data State (REF)]], otherwise throws and exception and jumps to the [[End Process State (REF)]].

The [[Configuration file]] is used to keep key project settings separate from the workflows, thus allowing us to edit them at any point without needing to modify the project.

Invoked workflows:
- InitAllSettings.xaml
	- Reads the settings in the [[Configuration file]].
- KillAllProcesses.xaml
	- This workflow is meant to force close all applications used in the process.
	- We do this to make sure that the robot starts in a clean and controlled environment.
- InitAllApplications
	- Open all applications used during the execution of the process

