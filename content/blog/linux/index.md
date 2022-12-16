---
title: Linux
date: "2022-11-28"
description: "Complete Linux Guide."
tags: ["linux"]
---

- **`cd`** is a command that lets you navigate to a path or a different folder in terminal
- **`ls`** is a command that lets you list all the files and folders in a directory

How to copy only PDF files from one folder to another

```bash
cp <file(s)_to_copy> <destination_folder>
```

How to rename a file in Linux

```bash
mv <existing_file_name> <new_file_name>
```

How to delete a folder completely in Linux (including it's files and sub-folders)

```bash
rm -rf <folder_name>
```

How to Create and Read Files in Linux

How to create a file in Linux

```bash
touch notes.txt
```

**vim** and **nano** are the two well-known text editors available in Linux.

**vim** is an advanced and powerful text editor you can use to perform **complex file operations** and it's what many Linux System Administrators use.

**nano**, ****on the other hand, is a simple text editor which you can use to perform **simple file operations**.

How to read the contents of a file in Linux

- The **`cat`** command displays the entire contents of the file
- The **`head`** command displays the few lines at the top of the file usually used to check if you're about to open the correct file
- And the **`tail`** command displays the bottom few lines of the file usually used to read logs from any process.

```bash
cat notes.txt
head notes.txt
tail notes.txt
```

How to read the contents of a file with line numbers in Linux

```bash
nl notes.txt
```

What's a command to find the properties of a file?

```bash
stat notes.txt
```

Is there a command to find number of words in a file?

```bash
wc notes.txt
```

Can you find the type of the document with a command?

```bash
file notes.txt
```

How can I find the occurrences of a word in a file?

```bash
grep -i "Linux" notes.txt
```

What if I want to find all the lines that don't contain a particular word?

```bash
grep -v "Linux" notes.txt
```
