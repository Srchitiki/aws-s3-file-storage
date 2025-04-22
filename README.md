# ☁️ AWS S3 Bucket Setup — File Storage & Public Access

This project showcases how to use **Amazon S3** to create a storage solution for a fictional company (**XYZ Corporation**) that requires uploading and publicly sharing files.

---

## 📌 Problem Statement

> XYZ Corporation needs a reliable cloud storage system to upload and store files. Some files must be publicly shareable. As a cloud associate, I implemented this using **Amazon S3**.

---

## 🎯 Tasks Performed

- ✅ Created an S3 bucket
- ✅ Uploaded 5 files of different types (JPG, PDF, TXT, PNG, MP4)
- ✅ Configured bucket to allow public access
- ✅ Verified public access via browser
- ✅ Created this documentation to showcase the process

---

## 🛠️ Steps I Followed

### 1. Login to AWS Console
> ✅ Go to https://console.aws.amazon.com  
> ✅ Search for **S3** in the search bar

🖼️ _Screenshot: AWS Console home_

---

### 2. Create a New S3 Bucket
> - Gave it a unique name (`xyzcorp-file-storage`)
> - Chose region (`Asia Pacific - Mumbai`)
> - Disabled **Block all public access**

🖼️ _Screenshot: Bucket creation settings_

---

### 3. Upload Files
> Uploaded 5 files:
> - image.jpg
> - resume.pdf
> - notes.txt
> - logo.png
> - intro.mp4

🖼️ _Screenshot: Upload screen_

---

### 4. Enable Public Access
> - Edited the bucket **permissions**
> - Disabled “Block all public access”
> - Added the following **bucket policy**:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowPublicReadAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::xyzcorp-file-storage/*"
    }
  ]
}
