<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Cloud Security with AWS IAM

**Project Link:** [View Project](https://nextwork.ai/projects/51a5fd24-7458-58a6-8653-9b90119a0e4a)

**Author:** MatthewHarris

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to set up services to control authentication in an AWS account.  I'm doing this project to learn how to properly use AWS Identity and Access Management to secure access to an account.

### Tools and concepts

Services I used were EC2 and IAM.  Key concepts I learnt include launching EC2 Instances and configuring access through AWS IAM policies.  I also learned how to create an AWS Account Alias to make remembering and assigning login details easier.

### Project reflection

This project took me approximately 50 minutes.  The most challenging part was navigating some of the menus because they did not match the instructions.  It was most rewarding to complete this project and do so with the confidence of navigating the dashboards outside of the instruction set.

### ❤️ Thanks for doing this project!

I chose to do this project today because IAM is important to become familiar with and I hope to continue growing more comfortable assigning policies and writing JSON policies. Something that would make learning with NextWork even better is ensure that the screenshots are up to date with the AWS tools such as the IAM Policy Simulator.  Otherwise this is a great project to get under your belt.

## Tags

### What I did in this step

In this step, I will launch two Amazon EC2 instances because they will increase my computing power.

### Understanding tags

Tags are similar to labels that can be attached to AWS resources.  Tagging helps us indentify all of the resources with the same tag at once which makes filtering easier.  Cost, allocation and policies can be based on environment tags.

### My tag configuration

The tag I’ve used on my EC2 instances is called Env.  The value I’ve assigned for my instances are production and development.

![Tags](https://nextwork.ai/matthewharris/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_2e0e5a5d)

## IAM Policies

### What I did in this step

In this step, I will create an IAM policy because I want to control access and give access to the development instance.

### Understanding IAM policies

IAM Policies are rules that control the permissions of who is or is not allowed to do certain things with the AWS resources.

### The policy I set up

For this project, I’ve set up a policy using the JSON editor to have granular control of the policy and permissions.

### Policy effect

I’ve created a policy that allows some actions like starting, stopping, and describing EC2 instances for instances taggged with Env = development.  The action of creating or deleting tags for all instances.

### Understanding Effect, Action, and Resource

The Effect, Action, and Resource attributes of a JSON policy means that you can allow or deny an action of a resource.  Effect is either allowing or denying an action which is a list of actions.  Resrource determines which resources the policy is applied to.

## My JSON Policy

![My JSON Policy](https://nextwork.ai/matthewharris/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_1c864649)

## Account Alias

### What I did in this step

In this step, I will create an Alias because it makes it easier to share remember and share the AWS console's login URL with others..

### Understanding account aliases

An account alias is a friendly name that users can use instead of an account ID number to sign in to the AWS Management Console.

### Setting up my account alias

Creating an account alias took me 2 minutes. Now, my new AWS console sign-in URL is https://nextwork-alias-matt.signin.aws.amazon.com/console

![Account Alias](https://nextwork.ai/matthewharris/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_0eb4439b)

## IAM Users and User Groups

### What I did in this step

In this step, I will set up a dedicated IAM group and user because I can allow controlled access to instances.

### Understanding user groups

IAM user groups are a collection or folder of IAM users.

### Attaching policies to user groups

I attached the policy I created to this user group, which means the users in that group will have permissions associated with policies attached to the group.

### Understanding IAM users

IAM users are the people who will get access to the resources and AWS account.

## Logging in as an IAM User

### Sharing sign-in details

The first way is to create an AWS account alias, which makes it easier to remember and share.  The second way is to use the email sign-in instructions button after creating the user.

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed that access was denied to several dashboard panels.  This was because the new IAM user account does not have access to those panels.

![Logging in as an IAM User](https://nextwork.ai/matthewharris/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_6f2ab446)

## Testing IAM Policies

### What I did in this step

In this step, I will log in to AWS using the intern's IAM user credentials because I need to verify the correct access before passing them their login details.

### Testing policy actions

I tested my JSON IAM policy by logging with the IAM user and tresting the access between each instance to ensure the IAM policy was working correctly.

### Stopping the production instance

When I tried to stop the production instance I unable to.  This was because the user account does not have access to the production instance.

![Testing IAM Policies](https://nextwork.ai/matthewharris/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance I was able to.  This was because the IAM policy allows the user to do so in the development instance.

![Testing IAM Policies](https://nextwork.ai/matthewharris/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_1811801c)

## IAM Policy Simulator

To extend my project, I'm going to test the IAM policy with the Policy Simulator tool.  I'm doing this because shutting down EC2 instances can be disruptive for users.

### Understanding the IAM Policy Simulator

The IAM Policy Simulator is a special IAM tool.  It's useful for validating policies without dissrupting uers.

### How I used the simulator

I set up a simulation for StopInstances and DeleteTags. The results were both denied initially.  I had to adjust adjust the environment to development to get accurate results.

![IAM Policy Simulator](https://nextwork.ai/matthewharris/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_069d8a621)
