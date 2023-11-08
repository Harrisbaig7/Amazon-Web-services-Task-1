# Amazon-Web-services-Task-1

# Designing a Simple, Scalable, Hosting Architecture 

In this task, imagine you are a solutions architect at AWS. A customer has
contacted you because they are having some problems with the way their web
application is currently hosted.

## Here's what the client has to say:

To: aws@aws.com <br>
From: Lilly.sawyer@fastier.com <br>
Subject: AWS services for Web Application Hosting

Hi, <br>
My name is Lily Sawyer and I am the co-founder and CTO of Fastier, the online
tool that makes organizing things fast.

You may have seen that we have been in the news recently and have been
experiencing some big growth as a result. Unfortunately, this means we’ve been
having some difficulties with our website. The response times can be slow during
peak periods and sometimes we even have server crashes when it runs out of
memory. We also experience some downtime during deployments and don’t
have a disaster recovery plan. Based on our current trajectory, we predict we’re
going to see consistent linear growth for a while.
Our application is a SPA React Application backed by Python and Flask, with
PostgreSQL as a database. It all runs off a single AWS EC2 instance currently
(t3.medium, 4GB of RAM).
Can you design an architecture for us that will alleviate the problems we’re
experiencing? We are not on a strict budget right now, but at the same time, it’s
not unlimited.
Kind regards,
Lilly

## Your task is to draft an email reply to Lilly Sawyer. So, what should we say back?

# Drafting an Email

In the email, you will need to show an architecture diagram and explain:

● what each part of the architecture is, <br>
● why it was chosen, and <br>
● how the costs are calculated and how they may vary month-to-month
remember you don’t need to give concrete numbers, just an overview! <br>

Your team has come together and decided on the architecture approach.
Outlined below is all the information you need to draft your email - you can also
refer back to Step 2 to learn about AWS services.

## First - Your team considers the brief:
When deciding on the right AWS solution, your team considers these points:

● The company is a startup. We are lucky because we can provide more of a
greenfield approach, and they are more likely to be able to make changes to their
application stack. Compared to an enterprise, where change can take a long time,
and they may end up only being able to migrate part of their system at a time. <br>
● Again, being a startup, it is probably easy to migrate their data into AWS. <br>
● They have a single server and already experience downtime, so they are
probably OK with some downtime during migration and setup. <br>
● Being a mixed API and web app they will need to host some static content as
well. <br>

## Second - You decide on the solution:
In this case, we will recommend a solution based on Elastic Beanstalk based on
these requirements:

● The customer has a Python application that Elastic Beanstalk has support for. <br>
● The customer will need to scale, and this is one of the fundamental features of
Elastic Beanstalk. <br>
● They want to remove downtime when deploying and Elastic Beanstalk’s
Blue/Green deployment can assist with this. <br>

The AWS Elastic Beanstalk documentation provides some more information if you
want to learn about it! <br>
(https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/AWSHowTo.html)

## Third - Specify the services:
The services we will use are listed below:

● Route 53 <br>
● Elastic Load Balancing <br>
● Elastic Beanstalk with Auto Scaling EC2 Group <br>
● RDS <br>
● S3 <br>
● CodePipeline <br>

An additional availability zone for redundancy is proposed but is not necessary.

## Fourth - Evaluate!

Importantly, the team recognizes that Elastic Beanstalk is not the only product that
we could recommend for this customer! AWS is an open platform and encourages
creativity when building solutions. We need to be aware of the pros and cons of
each solution and how they will best fit each customer.

Other options like Lambda or Fargate can be more complex to set up. Lightsail and
EC2 can be easy but they don’t provide that automatic scaling; the customer can
end up paying more because they are running virtual machines that are often not
at capacity. However, each of these services also has its own advantages, and
depending on the application that’s being built we can provide different
recommendations and discuss the options more in-depth with the customer
before coming up with the final design.


