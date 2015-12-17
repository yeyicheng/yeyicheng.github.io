---
layout: post
title: "Win10 Start Menu Not Show Up"
date: 2015-12-17 04:40:57 -0800
comments: true
categories: Windows 10
---
### Step 1 Right click task bar and click Task Manager
### Step 2 Choose File -> Run new task
### Step 3 Run powershell with administrative privileges
### Step 4 Run 
{% codeblock lang:bash %}
Get-AppXPackage -AllUsers | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register "$($_.InstallLocation)\AppXManifest.xml"} 
{% endcodeblock %} 
### Step 5 Wait until all the fixes end

