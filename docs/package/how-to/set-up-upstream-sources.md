---
title: Set up upstream sources for packages in VSTS and TFS
description: Find out how to configure upstream packages from multiple sources in VSTS and TFS
ms.prod: devops
ms.technology: devops-artifacts
ms.topic: conceptual
ms.manager: douge
ms.author: elbatk
author: elbatk
ms.date: 01/24/2018
monikerRange: '>= tfs-2017'
---

# Configure upstream sources for VSTS and TFS packages

Upstream sources enable you to use a single feed to store both the packages you produce and the packages you consume from "remote feeds": both public feeds (e.g. npmjs.com and nuget.org) and authenticated feeds (i.e. other VSTS feeds in your account or organization). Once you've enabled an upstream source, any user connected to your feed can install a package from the remote feed, and your feed will save a copy.

For more in-depth information on the concepts and best practices regarding upstream sources, check out the [upstream sources concepts documentation](../concepts/upstream-sources.md).

## Create a new feed that uses upstream sources

Navigate to the Package hub and select "New Feed".

Underneath _Upstream Sources_, select _Use packages from public sources through this feed_.

![Add upstream sources when creating feed](_img/us-create-feed.png)

Selecting this option now means **nuget.org** or **npmjs.org** do not have to be included in your nuget.config or npm config files to use packages from there.

> [!NOTE]
> You can add VSTS feeds as upstream sources as well following the directions below.

## Add upstream sources to existing feed

1. From your feed page, go to **Feed settings**
2. On the upstream sources tab, if you don't have any upstream sources you will see the below dialog where you can choose "Add upstream source":

    ![Add upstreams when no upstreams exist](_img/us-no-upstreams.png)

    If you do already have upstreams, you can select "Add upstream source" in the top menu:

    ![Add upstream soures to existing feed](_img/us-upstreams-exist.png)

3. You will see the following menu:

    ![Add upstream sources - choose upstream source type](_img/us-add-new-upstream.png)

    Choose if you'd like to add public sources or VSTS feeds 

    > Public sources may be greyed out if you chose to include public upstream sources when creating the feed and they already exist in your upstream sources.

    For public sources, choose **npmjs** or **nuget**:

    ![Add public upstream sources](_img/us-add-public-source.png)

    For VSTS feeds, select the feed that you would like to configure as an upstream source, and the rest of the fields will populate automatically

    ![Add VSTS upstream sources](_img/us-add-vsts-source.png)

The view we picked is the "default view". The default view is covered in the [views concepts page](../concepts/views.md), but simply put it's the set of packages that the feed owner believes should be consumed and has chosen to release by default.

Once you add an upstream source, you can see it in the list of upstream sources for your feed.

![List of sources](_img/us-with-sources.png)

## Consuming NuGet packages from upstream sources

Now you can open Visual Studio and install packages from the upstream sources you've configured. As covered already on the [consume NuGet packages documentation](../nuget/consume.md), You'll need to use these instructions to install packages from the upstream:

1.	On the upstream source (e.g. nuget.org), copy the Install-Package command
2.	In Visual Studio, open the Package Manager Console from Tools > NuGet Package Manager
3.	Paste the Install-Package command into the Package Manager Console and run it

## Consuming npm packages from upstream sources
Now you can open your favorite shell and install packages from the upstream sources you’ve configured. Just run:

```
npm install --save <package>
```

See the [npm install docs](../npm/install.md) for more details.


