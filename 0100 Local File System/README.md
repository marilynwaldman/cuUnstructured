##  MAC OS FILE SYSTEM COMMANDS

* pwd   - Present Working Directory
* mkdir - Make Directory
* cd    - Change Directory
* \>\>    - Append to a file (redirect output)
* ls    - List the contents of a file
* cat   - List the contents of a file
* cp    - Copy a file
* mv    - Rename or move a file
* rm    - Remove a file or a directory

## Exercies

1. Find the TERMINAL icon on the bottom toolbar.

![Screenshot](images/findterminalwindow.png) 

2. Open a terminal

![Screenshot](images/terminalwindow.png) 

3. Copy and paste the following commands

  ```bash
  pwd
  ```

   ![Screenshot](images/pwd.png) 

4. Copy and paste the following commands

  ```bash
  mkdir mydir
  ```
5. Copy and paste the following commands

  ```bash
  cd mydir
  ```
5. Copy and paste the following commands

  ```bash
  pwd
  ls
  ls -l
  ```

![Screenshot](images/mkdirCdLs.png)


6. Append some lines to an empty file 

  ```bash
  echo "The quick brown fox " >> myfile
  ```
  ```bash
  cat myfile
  ```

![Screenshot](images/echomyfile.png)

7. Append two more lines

  ```bash
  echo "jumped over  " >> myfile
  ```
  ```bash
  echo "the lazy dog's back." >> myfile
  ```
  ```bash
  cat myfile
  ```

![Screenshot](images/lazydog.png)

7. Copy myfile to myfile_copy

  ```bash
  cp myfile myfile_copy
  ```
  ```bash
  ls -l
  ```
  ```bash
  cat myfile_copy
  ```

![Screenshot](images/copy.png)

7. Move or rename myfile_copy

  ```bash
  mv myfile_copy old
  ```
  ```bash
  ls -l
  ```
  ```bash
  cat old
  ```

![Screenshot](images/move.png)

7. Delete old

  ```bash
  rm old
  ```
  ```bash
  ls -l
  ```
  ```bash
  cat old
  ```

![Screenshot](images/remove.png)

8. Move up on level in the directory tree - back to your home directory or where you started

  ```bash
  cd ..
  ```
  ```bash
  pwd
  ```

![Screenshot](images/uponelevel.png)

8. Delete directory mydir and all files in it

  ```bash
  rm -rf mydir
  ```
  ```bash
  ls -l
  ```

![Screenshot](images/remove.png)


 





