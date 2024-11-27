# AWS_Python_Boto
In this project, I set out to create a EC2 instance monitor that will restart instances when they are stopped. I set up the monitor using a Lambda function, written in Python and Boto.
I used EventBridge to set up an hourly trigger to run the Lambda function and check for stopped instances.

# Pseudocode
To set up this project, we will need to set up several EC2 instances to monitor. Then we will set up a Lambda function that uses Boto to monitor the instances and check to make sure they are running. Then we will set up an EventBridge event to trigger the Lambda function every hour.
![Instance monitor pseudocode](https://github.com/user-attachments/assets/c29f5eba-2985-429b-a51d-bc9fe30befb8)


# Setup
First, I set up five instances through EC2. They were just blank instances to test my Lambda.
![Instances](https://github.com/user-attachments/assets/d60cf6b4-a6f8-4acc-ac3e-29bd6e9d3656)
Next, I set up my Lambda function. I wrote the code in Python, imported Boto, and set a for loop to check for stopped instances. This led to a try function to try to restart any stopped instance.
![Lambda python code](https://github.com/user-attachments/assets/1aa2fe36-2bb8-4060-bc94-4f60f6340542)
Finally, I set up a trigger through EventBridge to trigger the Lambda function every hour.
![EC2 with EventBridge](https://github.com/user-attachments/assets/2cc0f292-5368-469e-8810-77d9a704665b)
To test the trigger and function, I started up my five instances, then stopped two of them. Next, I ran my test and monitored the instances to see if they were restarted. Success!
![Instances](https://github.com/user-attachments/assets/2545f5bf-45f3-4cd2-9583-38fbaff7b2e5)
