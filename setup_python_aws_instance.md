I have a friend who basically said the following: "my next computer will be a chrome book with a Amazon Web Services subscription" In other words, basic activities like email, web surfing are done locally on the chrome book, but all scientific computation would be performed on an AWS EC2 instance.

I'm going to walk through steps to set up an AWS EC2 instance with a python + jupyter setup.

- Set up AWS account. This is straight forward.
- Set up a EC2 instance. All stuff says select the Ubuntu Linux operation system.
- Key step is to SSH into the instance:
- https://medium.com/@GalarnykMichael/aws-ec2-part-2-ssh-into-ec2-instance-c7879d47b6b2

https://hackernoon.com/aws-ec2-part-3-installing-anaconda-on-ec2-linux-ubuntu-dbef0835818a

- Git has the ssh commands. Need to make sure they are available.

- Key step was to modify the security protocol so my computer could log in. I clicked on the security setup, said my ip and it put in automatically my ip. This worked for me

- ```ssh -i mykey.pem ubuntu@public_DNS```
- where the first part is my key, the next is username which is associated with the installation type, then the last part is the public DNS which you can copy from the instance information on the AWS dashboard
- Then in the ubuntu command line I downloaded the anaconda package I want, so I went ``` wget repo.continuum.io/archive/Anaconda3-5.0.1-Linux-x86_64.sh``` and hit enter, then everything went through.
- Then I typed ```bash Anaconda3-5.0.1-Linux-x86_64.sh``` and then followed the instructions on the screen. Be sure to set it up so that the path is modified.

- Somehow the path seemed to change after I was timed out. MTYNT. Ask Chase for help on this if it arises.
