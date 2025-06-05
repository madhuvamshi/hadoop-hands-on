

---

## ️ Steps Practiced

### 1. Create Directory

hadoop fs -mkdir /user/cloudera/hdir


### 2. List Directories

hadoop fs -ls /user/cloudera


### 3. Remove Directory

hadoop fs -rmdir /user/cloudera/hdir

![create remove_directories](https://github.com/user-attachments/assets/3665489f-c011-4cff-9fe1-95275d1723cd)


##  File Operations

### 1. Create a Local File
```bash
echo "This is a test file" > /home/cloudera/file11.txt
```

### 2. Upload File to HDFS
```bash
hadoop fs -put /home/cloudera/file11.txt /user/cloudera/
```

### 3. Download File from HDFS to Local
```bash
hadoop fs -get /user/cloudera/file11.txt /home/cloudera/
```

### 4. Copy File within HDFS
```bash
hadoop fs -cp /user/cloudera/file11.txt /user/cloudera/file11_backup.txt
```

### 5. Move File in HDFS
```bash
hadoop fs -mv /user/cloudera/file11.txt /user/cloudera/archive/
```

### 6. Delete File in HDFS
```bash
hadoop fs -rm /user/cloudera/file11_backup.txt
```
![FileOperations1](https://github.com/user-attachments/assets/dc1ddb88-2a5e-4d66-945c-3fe8acc166e6)

![FileOperations2](https://github.com/user-attachments/assets/e5256e4a-8765-4840-a731-7894a3907e71)

---

##  Directory Operations

### 1. Create Nested Directory
```bash
hadoop fs -mkdir -p /user/cloudera/project/input/data
```

### 2. Remove Non-Empty Directory
```bash
hadoop fs -rm -r /user/cloudera/project
```
![DirectoryOperations](https://github.com/user-attachments/assets/ab309876-5f2c-417f-946c-2c6972c9dccc)

---

##  File Viewing

### 1. View File Content
```bash
hadoop fs -cat /user/cloudera/archive/file11.txt
```

### 2. Tail Last Bytes of File
```bash
hadoop fs -tail /user/cloudera/archive/file11.txt
```
![FileViewing](https://github.com/user-attachments/assets/b07091fb-c700-4a13-8266-b42a7351687a)

---

##  Disk Usage and Quotas

### 1. Show Disk Usage
```bash
hadoop fs -du -h /user/cloudera/
```



---

##  Permissions

### 1. Change Permissions
```bash
hadoop fs -chmod 755 /user/cloudera/archive/file11.txt
```

### 2. Change Ownership
```bash
hadoop fs -chown cloudera:cloudera /user/cloudera/archive/file11.txt
```

---

##  File Check

### Check If File Exists in HDFS
```bash
hadoop fs -test -e /user/cloudera/archive/file11.txt && echo "Exists" || echo "Not Found"
```
![permision2](https://github.com/user-attachments/assets/c0415db3-2109-4064-b424-4bc2d200d7bd)

---

##ACL (Advanced)

### Set and Get ACLs
```bash
hadoop fs -setfacl -m user:cloudera:rwx /user/cloudera/mydir
hadoop fs -getfacl /user/cloudera/mydir
```

---



---

**Note:** Never use `echo`, `vi`, or `cat` on HDFS paths directly. First operate on local files, then use `hadoop fs` commands to interact with HDFS.
