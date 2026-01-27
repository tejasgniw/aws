# EC2

- EC2: Elastic cloud compute

- Login with key pair

```
    For WSL: If the path starts with /mnt/c/, permissions will NOT change — Windows forces them to appear as 777 in WSL.

    chmod 600 ec2.pem works but nothing chnages

    Follow the steps in case of /mnt/c path

    mkdir -p ~/.ssh
    mv ec2.pem ~/.ssh/

    sudo chown $USER:$USER ~/.ssh/ec2.pem
    chmod 600 ~/.ssh/ec2.pem

    ls -l ~/.ssh/ec2.pem

    ssh -i ~/.ssh/ec2.pem ubuntu@<Public Ipv4 address>

    Don’t keep keys under /mnt/c in WSL
```

- Update the packages (Ubuntu Image EC2)

```
    sudo apt update
    sudo apt upgrade
```

- Deploy a sample application [jenkins](https://www.jenkins.io/doc/book/installing/linux/)

```
    sudo apt update
    sudo apt install fontconfig openjdk-21-jre
    java -version

    sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
    https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
    echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
    sudo apt update
    sudo apt install jenkins

    # Validate id Jenkins is up and running.
    systemctl status jenkins

    Access Jenkins at http://<Ipv4 address>:8080 (default Jenkins port is 8080)

```

- Fix issue if http://<Ipv4 address>:8080 isn't accessible:

Since we haven't added Inbound traffic rules in the security groups, the access to the port isn't by default.

Add Custom TCP with port 8080 from any IPv4 as a new Inbound rule in the EC2's Security group.

```
    Access Jenkins at http://<Ipv4 address>:8080

    # To login
    
    Password: sudo cat /var/lib/jenkins/secrets/initialAdminPassword

```