# Lab 4 – Working with Amazon Elastic Block Store (EBS)

## Author

* **Name**:AKASH P 
* **Register Number**:212224220006
* **Date of Submission**:29-05-2026

---

## Objective

The objective of this experiment is to understand how Amazon Elastic Block Store (EBS) provides persistent block-level storage for EC2 instances. This lab focuses on creating and attaching an EBS volume, formatting and mounting it on an EC2 instance, storing data, and verifying data persistence after instance reboot.

---

## Prerequisites

* Basic understanding of cloud computing concepts
* AWS account or AWS Academy Lab access
* An existing EC2 instance (Amazon Linux 2 preferred)
* Basic knowledge of Linux commands

---

## Tools Used

* AWS Management Console
* Amazon EC2
* Amazon EBS
* SSH Client (Terminal / PuTTY)

---

## Tasks Performed

### Task 1: Explore Amazon EBS

Explore the Amazon EBS service through the EC2 dashboard. Observe different volume types such as General Purpose SSD (gp2/gp3), Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD.

---

### Task 2: Create an EBS Volume

Create a new EBS volume in the same Availability Zone as the EC2 instance. Choose an appropriate size and volume type.

---

### Task 3: Attach EBS Volume to EC2 Instance

Attach the created EBS volume to the running EC2 instance as an additional block device.

---

### Task 4: Format the EBS Volume

Connect to the EC2 instance using SSH and format the attached volume with a file system (for example, ext4).

---

### Task 5: Mount the EBS Volume

Mount the formatted volume to a directory in the EC2 instance (for example, /data or /mnt/ebs).

---

### Task 6: Store Data in EBS Volume

Create files and directories inside the mounted EBS volume and store sample data.

---

### Task 7: Verify Data Persistence

Reboot the EC2 instance and verify that the data stored in the EBS volume is still available after reboot.

---

## Workflow (Student Explanation)

## Workflow (Student Explanation)
```
1. First, I logged in to the AWS Management Console and opened the EC2 Dashboard. Then I explored the Amazon EBS section and observed the different EBS volume types such as gp2/gp3 SSD, Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD.

2. Next, I created a new EBS volume by selecting the same Availability Zone as my EC2 instance. I chose the required storage size and selected the General Purpose SSD (gp3) volume type.

3. After creating the volume, I attached the EBS volume to my running EC2 instance using the “Attach Volume” option and assigned a device name such as `/dev/xvdf`.

4. I connected to the EC2 instance using SSH and checked the attached storage device using the `lsblk` command. Then I formatted the volume with the ext4 file system using the command:

   sudo mkfs -t ext4 /dev/xvdf
   

5. Then, I created a mount directory and mounted the EBS volume using:

   sudo mkdir /mnt/ebs
   sudo mount /dev/xvdf /mnt/ebs
   

6. After mounting, I stored sample files and folders inside the mounted directory to verify that the storage was working properly.

   echo "Amazon EBS Lab" > /mnt/ebs/sample.txt
   

7. Finally, I rebooted the EC2 instance and checked whether the stored data was still available. The data remained intact after reboot, which confirmed that Amazon EBS provides persistent block storage for EC2 instances.
```

## Output Screenshots (Attach 3)

### Screenshot 1: EBS Volume Created

<img width="1612" height="767" alt="image" src="https://github.com/user-attachments/assets/9dc31e47-c151-40c4-9e75-a8cb8ef629fb" />



### Screenshot 2: EBS Volume Attached to EC2

<img width="1617" height="765" alt="image" src="https://github.com/user-attachments/assets/bb5d8e1e-8745-4ddd-a84e-bfa5df270caf" />



### Screenshot 3: Mounted Volume with Data
<img width="1592" height="745" alt="image" src="https://github.com/user-attachments/assets/62b97ccf-e4c0-4e93-80c4-507b67ad386f" />


## Result / Conclusion

This experiment demonstrated how Amazon EBS provides persistent storage for EC2 instances. By creating, attaching, formatting, and mounting an EBS volume, and by verifying data after reboot, the concept of durable block storage in the cloud was clearly understood.
