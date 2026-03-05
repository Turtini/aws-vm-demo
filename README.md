# AWS VM Creation Demo

This guide walks through the process of creating a virtual machine (EC2 instance) in Amazon Web Services.

The demo is designed for learning and training purposes and shows the basic workflow used by engineers to launch a virtual machine in AWS.

It is part of the **Turtini Training Loop**, a series of short operational guides focused on building practical infrastructure skills.

---

## Overview

In this demo we will:

1. Log into the AWS Console
2. Navigate to the EC2 service
3. Launch a new virtual machine
4. Configure networking and access
5. Connect to the instance
6. Verify the VM is operational

Estimated time: **10–15 minutes**

---

## Architecture Overview

The virtual machine will run inside a Virtual Private Cloud (VPC) and be accessible via SSH.

```
User
  │
  ▼
AWS Console
  │
  ▼
EC2 Service
  │
  ▼
Virtual Machine (EC2 Instance)
  │
  ▼
Security Group + Networking
```

---

## Step 1 — Log into AWS

1. Open the AWS Console at https://console.aws.amazon.com
2. Sign in with your AWS account credentials
3. From the **Services** menu select **EC2** or in the search bar type:

```
EC2
```

You should now see the EC2 dashboard.

---

## Step 2 — Launch a New Instance

1. Click **Launch Instance**
2. Provide a name for the instance

Example:

```
demo-vm
```

---

## Step 3 — Choose an Operating System

Select an Amazon Machine Image (AMI).

Recommended for this demo:

* **Amazon Linux 2023**
* **Red Hat Enterprise Linux**
* **Ubuntu Server**

---

## Step 4 — Choose Instance Type

Select a small instance type for the demo.

Example:

```
t2.micro
```

This instance type is commonly included in the AWS free tier.

---

## Step 5 — Configure Access

Create or select an SSH key pair.

Example:

```
demo-key.pem
```

Download and store this key securely.

---

## Step 6 — Configure Networking

Use the default VPC settings for the demo.

Recommended settings:

* Allow SSH access (port 22)
* Default VPC
* Default subnet

This creates the necessary **security group rules** to allow access to the VM.

---

## Step 7 — Launch the Instance

Click **Launch Instance**.

AWS will begin provisioning the virtual machine.

Provisioning typically takes **30–60 seconds**.

---

## Step 8 — Connect to the VM

From the EC2 dashboard:

1. Select the instance
2. Click **Connect**
3. Use either:

   * EC2 Instance Connect
   * SSH from your terminal

Example SSH command:

```
ssh -i demo-key.pem ec2-user@<public-ip-address>
```

---

## Step 9 — Verify the VM

Once connected, run:

```
uname -a
```

This confirms the virtual machine is running and accessible.

---

## Demo Complete

You have successfully:

* Created a virtual machine in AWS
* Configured networking and access
* Connected to the instance

---

## Related Demo

The companion guide shows how to create a VM using **OpenShift Virtualization**.

This demonstrates the difference between:

* Public cloud infrastructure
* Virtual machines running inside Kubernetes

---

## About Turtini

Turtini builds operational platforms that make open source delivery seamless for federal teams.

Learn more:

https://turtini.com
