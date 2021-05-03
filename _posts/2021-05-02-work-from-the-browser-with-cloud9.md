---
toc: true
toc_label: "Creating a Remote Workspace"
toc_icon: "cog"
---
<link rel="apple-touch-icon" sizes="180x180" href="../favicon_io/apple-touch-icon.png">
<link rel="icon" type="image/png" sizes="32x32" href="../favicon_io/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="../favicon_io/favicon-16x16.png">
<link rel="manifest" href="../favicon_io/site.webmanifest">


# Creating a Remote Workspace with AWS Cloud9
`In this post i will demonstrate how to set up a remote workspace using AWS Cloud9 along with configuring a ssh key with github.`
## Introduction
I'd like to think I am not alone when I say my work device is the primary device I use. If there is a side project I plan on pursuing, this is the machine I will likely use. That said, I also hate to add additional projects, dependencies and tools to my machine that I'll inevitably forget to delete and could potentially get in the way of tools i actually use to work. As an attempt to remedy this, I plan to move my personal development environment to the cloud. 

### What's Cloud9
Cloud9 is a remote development environment provided by AWS. It provides you with a fully featured text editor right from within the AWS console. It has several [supported languages](https://docs.aws.amazon.com/cloud9/latest/user-guide/language-support.html) built in, can easily integrate with your existing AWS resources, and offers a wide variety of [other use cases](https://docs.aws.amazon.com/cloud9/latest/user-guide/what-can-i-do.html) as well. 

Behind the scenes, Cloud9 can use EC2 as a backend server or you can decide to configure your own existing server as a backend for cloud9 to connect to. Chosing the latter comes with more customization options, but will require more work to hook up. [Look here for a difference between the two.](https://docs.aws.amazon.com/cloud9/latest/user-guide/ec2-env-versus-ssh-env.html) Ether way, this server will be the home for your new local development environment.

### Working With Others
This walkthrough is intented for the at home hobbyist and not necessarily a team of developers. As such, I will not touch on the features of Cloud9 that facilitate team development other than right here. Like most things in AWS there is some additional Team customization work that can be done via IAM Groups. For the whole Team setup [look here](https://docs.aws.amazon.com/cloud9/latest/user-guide/setup.html).
## Create the Environment
1. To start, be sure you are logged into your AWS account via an IAM user and not as root. Additionally, ensure that this user has Cloud9 permissions.(Disclosure, I am the only user in my account so it has full admin access across the account. If you are less lazy like me and are handling permissions more responsibly, you may have to try a couple of times to get the permissions just right.) 
1. Navigate to https://us-west-2.console.aws.amazon.com/cloud9/ in the console
1. Click **Create Environment** and you will be directed to name your environment. Here I am going with *cloud-playground*. Once filled click next.
![Console pic](../../../assets/2021-05-02-cloud9-with-gitssh/console.png)
1. Next you will need to decide which set up (EC2 or SSH) you wish to use. In this case I am using the EC2 option and staying on the free-tier t2.micro. If you are not using the default VPC and have a preference on what subnet you wish to use, you can set that here as well. Click next.
![Setup pic](../../../assets/2021-05-02-cloud9-with-gitssh/env-setup.png)
1. From here there will be a short wait period while Cloud9 runs a CloudFormation stack in the background to provision your new EC2 instance. Once complete, you will be greated with a fresh IDE and a welcome screen.
![IDE pic](../../../assets/2021-05-02-cloud9-with-gitssh/cloud9-firstview.png)

## Environment Overview
## Set up SSH Key with GitHub
## Pros and Cons of Using a Remote Dev Environment 
NOTE: Using default network settings default vpc and no subnet preference

