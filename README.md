Have you ever had your smartphone full of trash files that you want to get rid of? Are cleaning apps unreliable to certain trash files?
If only there was a way to customize the files and folders that you want to delete... Oh wait, here's the solution!

These bash scripts allows users to delete their unwanted files (it can be anything) from their android device with one tap. Simply select the functions and the arguments that you want to use and run the script. Easy to use and effective when cleaning!

------

In order for this to work on **Android**, you need:

1. Download and install [Terminal Emulator for Android](https://play.google.com/store/apps/details?id=jackpal.androidterm).
2. Put the folder with the scripts on a directory of your choice.
3. **ONLY MODIFY THE CLEAN_CACHE_USER FILE with the available functions. Also beware that not all text editors for Windows work for this kind of script (It's because of the "Enter" key)!**
4. Put _"bash PATH_TO_LOCATION/clean_cache_debian_android/CLEAN_CACHE_USER.sh"_ as the initial command in the preferences to run the file everytime you open the Terminal.
5. Enjoy!
------

In order for this to work on a **Debian Distribution**, you need:

1. Put the folder with the scripts on a directory of your choice.
2. **ONLY MODIFY THE CLEAN_CACHE_USER FILE with the available functions. Also beware that not all text editors for Windows work for this kind of script (It's because of the "Enter" key)!**
3. Execute _"bash PATH_TO_LOCATION/clean_cache_debian_android/CLEAN_CACHE_USER.sh"_ on the terminal.
4. Enjoy!
------

**Functions:**

* **_remove_folder_**: delete folders.
	* all arguments: full path of the folders.


* **_remove_file_**: delete files.
	* all arguments: full path of the files.


* **_remove_type_**: delete files with the same extension from a certain folder.
	* 1st argument &rarr; directory where the folders are (full path).
	* 2nd argument &rarr; how many layers should the function go. Choose:
		* = 1 &rarr; only the folder itself.
		* \> 1 &rarr; the main folder and subfolders, until they reach the maximum layer given.
		* = 0 &rarr; nothing happens.
		* anything else &rarr; the main folders and all subfolders.
	* 3rd to last arguments &rarr; extension type.


* **_remove_folder_in_folders_**: remove certain folders within a directory.
	* 1st argument &rarr; directory where the folders are (full path).
	* 2nd argument &rarr; how many layers should the function go. Choose:
		* = 1 &rarr; only the folder itself.
		* \> 1 &rarr; the main folder and subfolders, until they reach the maximum layer given.
		* = 0 &rarr; nothing happens.
		* anything else &rarr; the main folders and all subfolders.
	* 3rd to last arguments &rarr; folders to delete (name of the folder).


* **_remove_file_in_folders_**: remove certain files within a directory.
	* 1st argument &rarr; directory where the files are (full path).
	* 2nd argument &rarr; how many layers should the function go. Choose:
		* = 1 &rarr; only the folder itself.
		* \> 1 &rarr; the main folder and subfolders, until they reach the maximum layer given.
		* = 0 &rarr; nothing happens.
		* anything else &rarr; the main folders and all subfolders.
	* 3rd to last arguments &rarr; files to delete (name of the folder).


* **_remove_empty_files_folders_**: delete empty files and folders in the main folders and in all subfolders.
	* 1st argument &rarr; main folder (full path).
	* 2nd argument &rarr; how many layers should the function go. Choose:
		* = 1 &rarr; only the folder itself.
		* \> 1 &rarr; the main folder and subfolders, until they reach the maximum layer given.
		* = 0 &rarr; nothing happens.
		* anything else &rarr; the main folders and all subfolders.
	* 3rd to last arguments (optional) &rarr; folders and files to skip, if any (full path).

------

**WARNING: THESE BASH SCRIPTS CAN DELETE IMPORTANT FILES IF YOU DON'T KNOW HOW TO USE! I WILL NOT TAKE RESPONSIBILITY IF IMPORTANT DATA ON YOUR DEVICE IS LOST! USE IT AT YOUR OWN RISK!**

------

**Future implementations:**

| Priority | Description |
|----------------|:------------|
| Low | Adding counters for the number of files, folders and the total size of everything that was deleted (in a far future). |

------

**Versions:**

| Version number | Description |
|----------------|:------------|
| 3.3 | <ul><li> Removed 2 functions (**_remove_folder_within_folder_** and **_remove_file_within_folder_**) because they were just the two recursive functions (**_remove_folder_within_subfolder_** and **_remove_file_within_subfolder_**) on layer 1.</li><li>  Renamed three functions: <ul><li>**_remove_folder_within_subfolder_** to **_remove_folder_in_folders_**</li><li> **_remove_file_within_subfolder_** to **_remove_file_in_folders_** </li><li> **_remove_folder_within_folder_** to **_remove_type_**.</li></ul></li><li> Warning messages were also improved.</li></ul> |
| 3.2.1 | Rewrite of the displayed error messages, because the **_caller_** function doesn't work on shell. So, instead of showing the line, now it shows the name of the function. |
| 3.2 | Rewrite of the version 3.1.3, to make all functions display error messages when arguments are missing. |
| 3.1.3 | Error message is displayed when the second argument of the last three functions is not an integer and shows the line where the function is called. |
| 3.1.2 | Added another condition to all functions that allow searching in layers to accept only integers on their second argument (**_remove_folder_within_subfolder_**, **_remove_file_within_subfolder_** and **_remove_empty_files_folders_**). |
| 3.1.1 | Added a condition to all functions (except **_remove_file_** and **_remove_folder_**) to skip them if the main folder doesn't exist. |
| 3.1 | Restored two functions where a folders and files can be directly deleted instead of searching for them (**_remove_file_** and **_remove_folder_**). |
| 3.0 | <ul><li>Complete overhaul on the system functions. Many bugs led to the rewrite of all them. All of them were fixed, some of them were renamed and others were created.</li><li>It was also added compatibility between Android and Ubuntu (they both use Shell).</li><li> Performance is lower than the other versions, but reliability was increased.</li></ul> |
| 2.3.2 | Fixed a bug on the last function, where at folders were not skipped. |
| 2.3.1 | Fixed bug in functions where not all arguments were parsed. |
| 2.3 | Altered the first 3 function in order to parse multiple arguments. |
| 2.2.1 | Fixed bug on **_remove_empty_files_folders_** function where it basically skipped the first argument as well. |
| 2.2 | Added the option to skip multiple files and folders in the function **_remove_empty_files_folders_**. |
| 2.1 | Created a **_README_** file. |
| 2.0 | Separating functions and user preferences into two separate files. |
| 1.1 | Resolving problems with permissions. |
| 1.0 | Cleaning some junk code and making it "_look great_". |
| 0.6 | Added a condition in the **_remove_empty_files_folders_** function to skip certain folders. Its not fully implemented yet. |
| 0.5 | **_remove_empty_files_folders_** can now delete empty files and folders from subdirectories. |
| 0.4 | function **_remove_empty_files_folders_** created, but only working in the main folder, not the subfolders. |
| 0.3 | **_remove_type_** was added. |
| 0.2 | implemented function **_remove_folder_**. |
| 0.1.1 | **_echo_** was added to the below function. |
| 0.1 | created **_remove_** function. |
