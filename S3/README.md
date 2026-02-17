# Overview of AWS S3

Amazon Simple Storage Service (Amazon S3) is a highly popular object storage service designed to handle vast amounts of data such as database backups, application logs, and configuration files.

## Key Concepts

### Objects and Buckets

* Data in S3 is stored as **objects** inside **buckets**.
* There is **no limit** to the total data a bucket can store.
* A **single object** can be up to **5 TB** in size.

### Global Uniqueness

* Buckets are created in a specific **AWS Region** to reduce latency.
* Bucket names must be **globally unique** across all AWS accounts.

### Durability and Reliability

* S3 provides **99.999999999% (11 nines) durability**.
* This durability is achieved through automatic replication across multiple data centers and Availability Zones.

## Core Characteristics

### 1. Scalability

* Upload unlimited data as storage needs grow without capacity planning.

### 2. Security

* Server-side encryption enabled by default.
* Fine-grained access control using:

  * IAM policies
  * Bucket policies
  * Access Control Lists (ACLs)

### 3. Cost Efficiency

* Pricing depends on **Storage Classes**.
* Common options include:

  * **S3 Standard** for frequent access
  * **Glacier Deep Archive** for rarely accessed data with very low storage cost

### 4. Performance

* **Multipart uploads** allow large files to be uploaded in chunks.
* Improves reliability during network interruptions.

### 5. Availability and Durability

* Designed to remain operational even if an entire Availability Zone fails.

## Key Features and Management

### Versioning

* Maintains multiple versions of an object.
* Allows recovery from accidental deletion or overwrite.

### Logging and Notifications

* **Access logging** tracks requests made to S3 objects.
* **Event notifications** can trigger AWS Lambda functions when objects are created or deleted.

### Object Locking

* Prevents objects from being deleted or overwritten.
* Useful for compliance and highly sensitive data (e.g., legal or financial records).