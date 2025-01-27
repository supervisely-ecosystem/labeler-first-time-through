<div align="center" markdown>

<img src="https://user-images.githubusercontent.com/106374579/187230447-a62c5dc2-4f03-40a8-863b-e825799960c2.png"/>

# First Time Through (FTT) metric for labeler

<p align="center">

  <a href="#Overview">Overview</a> •
  <a href="#How-To-Run">How To Run</a> •
  <a href="#History-Of-Runs">History of runs</a>
</p>

[![](https://img.shields.io/badge/slack-chat-green.svg?logo=slack)](https://supervisely.com/slack)
![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/supervisely-ecosystem/labeler-first-time-through)
[![views](https://app.supervisely.com/img/badges/views/supervisely-ecosystem/labeler-first-time-through.png)](https://supervisely.com)
[![runs](https://app.supervisely.com/img/badges/runs/supervisely-ecosystem/labeler-first-time-through.png)](https://supervisely.com)

</div>

## Overview
First Time Through (FTT) metric (in percentage) shows how many items labeler annotated right the first time (i.e. reviewer accepted his work on first round). This metric helps to find accurate labelers (i.e. reviewers accepts many of their annotations).

`FTT (%) = ACCEPTED * 100 / LABELED`

Application shows the table of all labeling jobs in the team that were assigned to specific member and calculates FTT metric for every job (last column). Also it produces average FTT for all non-zero values.

<img src="https://i.imgur.com/mkbxGDX.png"/>

# How to Run

## Step 1. (Optional) Add app to your team from Ecosystem
Log in to the team, then go to `Ecosystem`->`Apps` page. Find app and press `Get` button. Now app is added to your team.

## Step 2. Open context menu of team member

<img src="https://i.imgur.com/7UXftxr.png"/>

Enable checkbox if you want to use also archived (disabled) jobs. 
<img src="https://i.imgur.com/7p5MjwJ.png" width="400px"/>

## Step 3. Wait util report is created. App shuts down automatically

Done!

## Special case

<img src="https://i.imgur.com/Vha8y0z.png"/>

Apps calculates FTT metric for all jobs. If job has rejected images, these images can be separated to another new labeling job by clicking `Restart rejected` button. And then labeler will correct his mistakes. 

The problem here is that supervisely do not track such new jobs and `AVG FTT` metric will be slightly incorrect. In best case such new jobs (`Restart rejected`) have to be ignored. 

Now Application provides FTT for every job. And it helps to get main idea how labeler performs. To distinguish jobs (created with `Restart rejected` button) from the original ones we recommend the following workaround: to name labeling jobs with suffix `round-XX` (for example `labeling job #01 round-01`, `labeling job #01 round-02`, etc...). But in the future versions of the app it will be fixed and the metric will be completely correct.  


## History of runs

To see history of runs go to `Apps` page, click to applications sessions. In front of every session you can see buttons (`View` and `Logs`). Press `View` button to open stopped application session in `Read Only` mode.

<img src="https://i.imgur.com/woqPetm.png"/>
