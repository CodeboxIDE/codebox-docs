---
layout: default
title: Getting Started
---

Getting Started
============

Below you'll find tutorials that will teach you how to use Codebox, and reference documentation for all the moving parts.

Sign up and create an account on Codebox at https://www.codebox.io. There are different ways for creating boxes using Codebox:

* Using your dashboard at https://www.codebox.io
* Using the command line tool
* Using the REST API
* Using some librairies for Javascript, Python or Ruby


Each account has an unique **API Token**, we will use this token during the next step for creating and managing Boxes from outside the Dashboard.

## Configure your account

Each boxes who created use the SSH key of your account, you can add the public key to your GitHub, Bitbucket or GitLab account to use private git hosting.

## Using the dashboard

It's very simple to create coding environment using the web dashboard. Simply go to https://www.codebox.io and log in. Click on *"Create a new box"* and follow the instructions.

You can also manage your differents boxes and access reports about usage and collaborators.

The dashboard is also use to manage credit.

## Using the command line tool

Install Node.js and NPM for your system (Mac, Windows or Linux). And install the command lien tool using:

```
$ npm install codebox-io -g
```

You can now authorize the client using your **API Token**:

```
$ codebox-io auth <your api token>
```

Creating boxes is really easy:

```
$ codebox-io create type1 TestBox --stack="node" --git="https://github/FriendCode/codebox-client.git"
```

Download a box content

```
$ codebox-io download 57f06d2e-05d6-4745-b9f4-6b0c9ef417c8 ./content.gz
```