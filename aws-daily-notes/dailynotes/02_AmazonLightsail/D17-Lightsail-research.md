# Lightsail Reasearch

## Day 17

- [ ] Understand Lightsail research
- [ ] How to create a VM in Lightsail research
- [ ] Raising a support ticket

## What is LFR?

With Amazon Lightsail for Research, academics and researchers can create powerful virtual computers in the Amazon Web Services (AWS) Cloud. These virtual computers come with pre-installed research applications, such as RStudio and Scilab.

With Lightsail for Research, you can upload data directly from a web browser to begin your work. You can create and delete your virtual computers at any time, which gives you on-demand access to powerful computing resources.

You pay only for as long as you need the virtual computer. Lightsail for Research offers budgeting controls that can automatically stop your computer when it reaches a preconfigured cost limit, so you don't have to worry about overage charges.

Everything you do in the Lightsail for Research console is backed by a publicly available API. Learn how to install and use the AWS CLI and API for Amazon Lightsail.

## Applications

Amazon Lightsail for Research provides and manages machine images that contain the application and operating system required to launch a virtual computer. You choose from a list of applications when you create a virtual computer in Lightsail for Research. All Lightsail for Research application images use the Ubuntu (Linux) operating system.

The following applications are available in Lightsail for Research:

- JupyterLab – JupyterLab is a web-based Integrated Development Environment (IDE) for notebooks, code, and data. With its flexible interface you can configure and arrange workflows in data science, scientific computing, computational journalism, and machine learning. For more information, see the Jupyter Project Documentation
- RStudio – RStudio is an open-source Integrated Development Environment (IDE) for R, a programming language for statistical computing and graphics, and Python. It combines a source code editor, build automation tools and a debugger, as well as tools for plotting and workspace management. For more information, see the RStudio IDE
- VSCodium – VSCodium is a community-driven, binary distribution of Microsoft’s editor VS Code. For more information, see VSCodium
- Scilab – Scilab is an open source numerical computational package, and a high-level, numerically oriented programming language. For more information, see Scilab
- Ubuntu 20.04 LTS – Ubuntu is an open source Linux distribution based on Debian. Lean, fast and powerful, Ubuntu Server delivers services reliably, predictably and economically. It's a great base on which to build your virtual computers. For more information, see Ubuntu releases


## Create a rule

Sign in to the Lightsail for Research console

- Choose Cost control in the navigation pane.
- Choose Create rule.
- Select the resource to apply the rule to.
- Specify the CPU utilization percentage and time period at which the rule should run.
