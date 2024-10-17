---
layout: post
title: How to Upgrade to a New Ubuntu Version
---
Before you begin, know that you can only upgrade one version ahead of what you're currently using. If you're too far behind the newest release, it probably makes more sense to spin up a fresh install. 

In this case, I'm going from Mantic Minotaur to Noble Nombat. Not sure what a nombat is, but more to follow. 

Start with the usual updates:

`sudo apt update`\
`sudo apt upgrade`

Then update to the next release:

`sudo do-release-upgrade`

You'll be prompted to make a couple of decisions, but that's pretty much it. It takes a while because it must download a bunch then install. 

Confirm the version of Ubuntu with this command:

`lsb_release -a`

From https://help.ubuntu.com/community/NobleUpgrades

Run the update-manager application.

In Update Manager, click the Settings... button, and enter your password to start the Software Sources application.

Select the sub menu Updates from the Software Sources application.
Confirm the "Notify me of a new Ubuntu version:" option is set to "For any new version", and change it if otherwise.
Close the Software Sources application and return to Update Manager.

In Update Manager, click the Check button to check for new updates.

If there are any updates to install, use the Install Updates button to install them.

Run update-manager -d.
A message will appear informing you of the availability of the new release.

Click Upgrade.
Follow the on-screen instructions. 