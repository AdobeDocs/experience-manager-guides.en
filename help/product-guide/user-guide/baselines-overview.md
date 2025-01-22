---
title: Using Baseline
description: Learn how to use baselines in Adobe Experience Manager Guides.
feature: Publishing
role: User
---
# Baselines overview 

The Baseline feature allows you to create a version of your topics and assets that can then be used for publishing or translation. For example, if your DITA map has `topicA` and `imageA`, you can create a Baseline to use the 3rd version of `topicA`, but the 4th version of `ImageA`. Once you have a Baseline in place, you can publish or translate topics of different versions with a single click.

Selecting a Baseline is optional for output presets and a DITA map can have more than one Baseline. However, each output preset within a DITA map can be associated with only a single Baseline. If no Baseline is specified at the time of publishing, then the output is published using the latest version of the content.

Similarly, selecting a Baseline to translate content is optional. However, if you choose to translate content using a Baseline, the contents of the Baseline are also saved along with the translated copies. You can then use the translated Baseline to perform further operations like share it with external publishers or archive it. For more information about exporting a translated Baseline, view [Export translated Baseline](#id196SE600GHS).

>[!TIP]
>
> View the *Baseline* section in the Best practices guide for best practices around working with Baselines.

Your administrator can configure the Baseline tab on the map dashboard. For more details, view *Configure Baseline tab on the DITA map dashboard* section in the Installation and Configuration Guide.

## Ways to create and manage Baselines in Experience Manager Guides

There are 2 ways to creat and manage baselines for a DITA map file:

1. *(Recommended)* [Using the Map console](./web-editor-baseline.md)
2. [Using the Assets UI](./generate-output-use-baseline-for-publishing.md)


