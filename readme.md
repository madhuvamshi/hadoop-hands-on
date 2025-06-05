

---

## ️ Steps Practiced

### 1. Create Directory

hadoop fs -mkdir /user/cloudera/hdir


### 2. List Directories

hadoop fs -ls /user/cloudera


### 3. Remove Directory

hadoop fs -rmdir /user/cloudera/hdir


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

---

##️ ACL (Advanced)

### Set and Get ACLs
```bash
hadoop fs -setfacl -m user:cloudera:rwx /user/cloudera/mydir
hadoop fs -getfacl /user/cloudera/mydir
```

---



---

**Note:** Never use `echo`, `vi`, or `cat` on HDFS paths directly. First operate on local files, then use `hadoop fs` commands to interact with HDFS.
