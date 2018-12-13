---
date: 2018-11-16T00:00:00-00:00
description: "Automated testing made easy and efficient with Robot framework"
featured_image: "/images/nrelabs.png"
tags: [verification, testing]
title: "Using Robot Framework for Automated Testing"
show_reading_time: true
authors:
  - name: Saim Khan
    link: https://github.com/saimkhan92
  - name: Lakshmi Rajan
    link: https://github.com/lara29
---
** “Testing leads to failure, and failure leads to understanding” ** - wisely said by Burt Rutan.

If you take any standard product lifecycle development workflow, you will see that “Testing” is an integral phase in the lifecycle of a product or a solution. However, not many engineers understand the importance of testing their product well enough to ensure that it conforms to the quality standards. I cannot blame them, because testing sounds like a boring, dull, repetitive task. And this is true for manual network testing, where testers would verify the operation by running their test-cases one at a time on individual devices. This was painstakingly slow and also prone to lack of attention errors.

However, the testing phase has now received a facelift, thanks to the latest developments in automation brought in the by DevOps industry. Traditionally, coding and scripting were only handled by programmers, who generally shied away from testing. With the introduction of the concept of reliability engineering, these lines have now been blurred. A programmer is now expected to know testing, and to use test automation frameworks to check their code for reliability. Similarly, network engineers are expected to use scripting or devops frameworks to test as well as deploy their networks.


As a network engineer, suppose you have been assigned a task to setup a data center. You have a hundred devices (can be a mix of switches, routers and firewalls) that you need to have up and running as quickly as possible. The topology has been setup, and all your devices have been configured. Now, you need to verify the operation of your devices to makes sure that your data center is ready for operation. Doing this job manually is simply out of question, as it would take a lot of time, effort and resources which is not feasible for the current demand. What options do you have?

## Robot as a Test Automation Framework
This is where I would like to introduce you all to Robot framework. Robot is a keyword-driven test automation framework which provides a platform where you can write test-cases, run them in a consistent, repeatable manner. It is widely used in many industries to perform acceptance testing. There are several libraries that can be plugged in to Robot for enhancements, and it also has a thriving user community with online support.

<div style="text-align:center;"><a href="/images/robot-fwk-architecture.png"><img src="/images/robot-fwk-architecture.png" style="width: 350px;display: block;margin: 0 auto;" ></a></div>

Robot can be used to test just about any software library - we just need to provide the right hooks to the library that we use. In case of networking devices, Robot framework can interact with your library that interfaces with your devices under test. In case of Junos, we can use the pyez library which is commonly used to interact with Junos devices.

This is where the significance of the feature “keyword-driven” comes into picture. Robot test cases are invoked by means of “keywords” that are used to represent a function being tested. For example, you could define a keyword “Check System Alarms”, and internally this can execute either a Junos specific API or another vendor’s API and perform the necessary check on system alarms. The concept of keywords make Robot framework user-friendly since we can use words that convey a simple meaning to our function, and at the same time it makes Robot vendor agnostic.


Robot also generates detailed html reports that give in-depth view into each test-case that was run, and this makes it easy for you to understand why things went right/wrong. This would assist in going back and making the right changes so that your topology works as intended.

<div style="text-align:center;"><a href="/images/robot-test-results.png"><img src="/images/robot-test-results.png" style="width: 350px;display: block;margin: 0 auto;" ></a></div>

Another nice feature of Robot is the ability to group test cases so that they represent a certain functionality or type of device under test. For example, if you have test cases that run only on firewalls, and another set that would run only on routers, you could categorize them into two “suites” and run them separately.

To summarize, these are the key points about Robot framework:
Robot framework is widely used in acceptance testing.
Keyword driven, need not know programming, simple, only need to understand the results.
Rich ecosystem of libraries that can be used.
Does not care about the underlying system under test, i.e., vendor agnostic.
Generates extensive reports in html format, gives granular view into the tests performed, and the results.

## Stages of Test Creation

1. The first and the most important stage in any testing phase is to come up a plan on what features to test, and how you would like to sequence them. This depends on how well you know the product. Even if you don’t know your product completely, I assure you that at the end of testing, you’ll get to know it well ;)
2. Once your plan is set, go ahead and write your test-cases.
3. Run your test-cases.
4. Review the result of each test-run. See if your test-case produced the intended result. Go back and change the device configuration so that the test passes. Or maybe, your test-case is not valid for a particular scenario - go back and improve your test-case.

Over a period of time, you will understand your product better and be able to finalize on your test-cases. Once this is done, you can run your test-suite on any number of devices multiple times as you wish. There are a multitude of options out there which you can leverage in order to create a test pipeline( for example, integrate it with Docker). 

Whatever means you take, automation testing can significantly reduce the time to deployment of a solution, by giving the ability to identify errors or shortcomings in the design in a much shorter time frame. It also helps ensure quality of your product or solution delivered. In the post-deployment stage, monitoring and testing production networks helps in ensuring smooth operation of your network. Testing is a means to understand your product/solution better, and automated testing frameworks make this process even sweeter.

If automated network testing is something you are interested in, and would like to get a hands on experience, we have created a simple tutorial on Robot framework. There are three chapters in the lesson which guide you through the basics of Robot, and we also provide a live environment where you can execute Robot test-cases. Checkout our tutorial on the NRE-Labs - [Using Robot Framework for Automated Testing](https://labs.networkreliability.engineering/labs/?lessonId=29&lessonStage=1) , and don’t forget to leave your comments and feedback.