**10 Hands‑On EC2 Exercise Problems**

1. **Launch a Linux EC2 instance with a custom AMI**  
   - Create a new AMI from a running instance that has Apache installed, then launch a new t3.micro using that AMI.

2. **Configure a security group for a web server**  
   - Open ports 80 (HTTP) and 443 (HTTPS) to the world, but restrict SSH (port 22) to your own IP address only. Verify connectivity from a browser.

3. **Set up an Elastic IP and associate it**  
   - Allocate an Elastic IP, attach it to a running instance, then disconnect and reconnect the Elastic IP to a different instance.

4. **Implement user data scripts for automatic configuration**  
   - Write a user‑data script that installs MySQL, creates a database, and starts the service on first boot. Launch an instance with this script and confirm the database exists.

5. **Create an IAM role for EC2 and grant S3 access**  
   - Attach a role that allows `s3:GetObject`/`s3:PutObject` on a specific bucket. From the instance, use the AWS CLI to list and upload a file to that bucket.

6. **Deploy a multi‑AZ load‑balanced web tier**  
   - Launch two EC2 instances in different Availability Zones, install a simple web page on each, place them behind an Application Load Balancer, and test failover by stopping one instance.

7. **Implement instance metadata protection**  
   - Disable IMDSv1, enable IMDSv2, and require a session token. Write a script that retrieves the instance’s ID using the token and verify it works.

8. **Use EC2 Auto Scaling to handle traffic spikes**  
   - Create a launch template, define a scaling policy that adds instances when CPU usage > 70 % and removes them when < 30 %. Simulate load (e.g., with `hey` or `ab`) and observe scaling events.

9. **Encrypt an EBS volume and test data protection**  
   - Attach an encrypted gp3 volume to an instance, write sensitive data, create a snapshot, then launch a new instance from that snapshot and verify the data is still encrypted.

10. **Migrate a running instance to a different instance type**  
    - Change an instance from `t3.micro` to `m5.large` using the “Stop → Change Instance Type → Start” workflow. Measure the difference in CPU performance with `sysbench` before and after.
