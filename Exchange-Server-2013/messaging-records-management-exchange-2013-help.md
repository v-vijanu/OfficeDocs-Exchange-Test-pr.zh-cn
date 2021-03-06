﻿---
title: '邮件记录管理: Exchange Online Help'
TOCTitle: 邮件记录管理
ms:assetid: 0dd92e9c-881e-43c0-9bbf-f41fdc9dfd87
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dd335093(v=EXCHG.150)
ms:contentKeyID: 50489907
ms.date: 05/23/2018
mtps_version: v=EXCHG.150
ms.translationtype: MT
---

# 邮件记录管理

 

_**适用于：** Exchange Online, Exchange Server 2013_

_**上一次修改主题：** 2016-02-01_

用户每天均会收发电子邮件。如果不进行管理，则每天生成和接收的电子邮件数量可能会使用户难以应付、影响用户工作效率并使组织暴露在风险之下。因此，电子邮件的生命周期管理对于大多数组织来说是一项至关重要的任务。

邮件传递记录管理 (MRM) 是 Exchange Server 2013 和 Exchange Online 中的记录管理技术，可帮助组织管理电子邮件生命周期并降低与电子邮件有关的法律风险。部署 MRM 可通过以下几种方式帮助您的组织：

  - **满足业务要求**   根据贵组织的邮件策略，您可能需要将重要的电子邮件保留一段时间。例如，用户邮箱可能会包含与业务策略、事务、产品开发或客户交互相关的关键邮件。

  - **满足法律和法规要求**   许多组织都具有法律或法规要求，以将邮件存储一段指定时间并在超过该时间段后删除邮件。存储邮件的时间超过所需时间可能会增加组织的法律或财务风险。

  - **提高用户工作效率**   如果不进行管理，则用户邮箱中数量不断增加的电子邮件也可能会影响用户工作效率。例如，尽管新闻稿订阅和自动通知在用户收到时可能具有信息价值，但用户在阅读之后（通常他们从不阅读）可能并没有将其删除。许多这类邮件过几天后便没有保留价值。使用 MRM 删除此类邮件有助于减少用户邮箱中的待筛选邮件，从而提高工作效率。

  - **改进存储管理**   由于免费客户电子邮件服务所推动的预期，许多用户会将旧邮件保留较长时间，或是从不删除邮件。大型邮箱助长了这一标准操作，不应基于限制性邮箱配额来强制用户更改其工作习惯。但是，邮件的保留时间超过由于业务、法律或法规原因而需要保留的时间也会增加存储成本。

借助 MRM，您可以灵活实现最能满足您组织需求的记录管理策略。清楚了解 MRM、就地存档和就地保留之后，便有助于您实现管理邮箱存储和满足法规保留要求的目标。

若要了解与 MRM 相关的管理任务，请参阅[邮件记录管理程序](messaging-records-management-procedures-exchange-2013-help.md)。

## Exchange Server 2013 和 Exchange Online 中的 MRM

在 Exchange Server 2013 和 Exchange Online 中，MRM 通过保留标记和保留策略实现。该版本使用保留标记将保留设置应用于整个邮箱和默认邮箱文件夹（如\&quot;收件箱\&quot;和\&quot;已删除邮件\&quot;）。还可以创建和部署保留标记，Outlook 2010 及更高版本和 Outlook Web App 用户可以使用这些保留标记应用于文件夹或各个邮件。创建之后，可将保留标记添加到保留策略，然后将该策略应用于用户。托管文件夹助理负责处理邮箱，并应用用户保留策略中的保留设置。有关保留策略的详细信息，请参阅[保留标记和保留策略](retention-tags-and-retention-policies-exchange-2013-help.md)。

当邮件达到适用保留标记中指定的保留时间时，托管文件夹助理会采取标记指定的保留操作。然后，您可以永久删除邮件，也可在删除时保留恢复邮件的功能。如果已为用户设置存档，则您还可以使用保留标记将项目移动到用户的就地存档。

## MRM 策略

可以使用保留策略对整个邮箱或特定的默认文件夹强制执行基本邮件保留。尽管部署 MRM 的策略多种多样，但我们在本文中仅阐述几种最常见的策略：

**在指定的时间段后删除所有邮件：** 在此策略中，您实现的是一个在一段时间后删除所有邮件的 MRM 策略。在此策略中，不对邮件进行分类。可以通过为邮箱创建单个默认策略标记 (DPT) 来实现此策略。但是，这并不确保在指定时间段内保留邮件。用户仍可以在到达保留期之前删除邮件。

**将邮件移到存档邮箱中：** 在此策略中，您实现的是将项目移到用户存档邮箱中的 MRM 策略。存档邮箱为用户提供额外存储空间来维护旧内容和很少访问的内容。可移动项目的保留标记也称为\&quot;归档策略\&quot;。在同一保留策略中，可以将 DPT 与个人标记进行组合以移动项目，并将 DPT、RPT 和个人标记进行组合以删除项目。若要详细了解存档策略，请参阅：

  - **Exchange Server 2013:**  [Exchange 2013 中的就地存档](in-place-archiving-in-exchange-2013-exchange-2013-help.md)

  - **Exchange Online:**  [Exchange Online 中的存档邮箱](https://technet.microsoft.com/zh-cn/library/dn922147\(v=exchg.150\))

> [!NOTE]  
> 在 Exchange 混合部署中，您可以为内部部署主邮箱启用基于云的存储邮箱。如果向内部部署邮箱分配存档策略，项目将移动到基于云的存档。如果将某个项目移动到存档邮箱，不会在内部部署邮箱中保留它的副本。如果将内部部署邮箱置于保留状态，存档策略仍会将项目移动到基于云的存档邮箱，项目将在其中保存保留指定的时间。


**根据文件夹位置删除邮件：** 在此策略中，您实现的是基于电子邮件位置的 MRM 策略。例如，您可以指定收件箱中的邮件保留一年，\&quot;垃圾邮件\&quot;文件夹中的邮件保留 60 天。可以对要为其配置的每个默认文件夹使用保留策略标记 (RPT) 并对整个邮箱使用 DPT，通过这种结合使用来实现此策略。DPT 适用于未应用 RPT 的所有自定义文件夹和所有默认文件夹。

> [!NOTE]  
> 在 Exchange 2013 中，可以为&amp;quot;日历&amp;quot;和&amp;quot;任务&amp;quot;文件夹创建 RPT。如果不希望这些文件夹或其他默认文件夹中的项目过期，则可以为该默认文件夹创建已禁用的保留标记。


**允许用户对邮件分类：** 在此策略中，您实现的是包含所有邮件的基线保留设置，但允许用户根据业务或法规要求对邮件进行分类的 MRM 策略。在这种情况下，用户将成为记录管理策略的重要部分，因为通常只有用户最了解邮件的保留价值。

用户可以将不同的保留设置应用于需要较长或较短的保留时间的邮件。可以使用以下各项的组合来实现此策略：

  - 用于邮箱的 DPT

  - 用户可以应用于自定义文件夹或各个邮件的个人标记

  - （可选）额外添加 RPT 以使特定默认文件夹中的项目过期

例如，使用的保留策略可以包含具有较短保留期（如两天、一周或一个月）的个人标记，以及具有较长保留期（如一年、两年或五年）的个人标记。对于新闻稿订阅等在收到后几天内便有可能失去其价值的邮件，用户可以应用保留期较短的个人标记。而对于具有较高业务价值的邮件，用户可以应用保留期较长的个人标记。他们也可以使用 Outlook 中的收件箱规则使流程实现自动化，将个人标记应用到匹配规则条件的邮件。

**保留邮件以用于电子数据展示：** 在此策略中，您实现的是在指定的时间段后从邮箱中删除邮件，但同时会将这些邮件保留在\&quot;可恢复的项目\&quot;文件夹中以用于[就地电子数据展示](in-place-ediscovery-exchange-2013-help.md)（即使用户或其他进程已删除这些邮件）的 MRM 策略。

您可以使用保留策略和[就地保留和诉讼保留](in-place-hold-and-litigation-hold-exchange-2013-help.md)或诉讼保留的组合，以满足此要求。保留策略会在指定时间段之后将邮件从邮箱中删除。基于时间的就地保留或诉讼保留会保留在该时间段之前删除或修改的邮件。例如，若要将邮件保留七年，您可以创建一个保留策略，其中包含在七年后删除邮件的 DPT，并创建将邮件保留七年的诉讼保留。用户未删除的邮件会在七年之后删除；用户在满七年之前删除的邮件会在\&quot;可恢复的项目\&quot;文件夹中保留七年。若要了解有关此文件夹的详细信息，请参阅[\&quot;可恢复的项目\&quot;文件夹](recoverable-items-folder-exchange-2013-help.md)。

或者，您可以使用 RPT 和个人标记支持用户清理邮箱。不过，就地保留和诉讼保留会继续保留已删除的邮件，直到保留期到期为止。

> [!NOTE]  
> 基于时间的就地保留或诉讼保留类似于 Exchange 2010 中非正式名称为&amp;quot;滚动法定保留&amp;quot;的功能。滚动法定保留通过为邮箱数据库或各个邮箱配置已删除项目保留期来实现。但是，删除项目保留可基于删除日期保留已删除项目和已修改项目。就地保留和诉讼保留根据项目的接收或创建日期保留项目。这样可确保邮件至少保留一段指定的时间。


## 详细信息

[邮件记录管理术语在 Exchange 2013](messaging-records-management-terminology-in-exchange-2013-exchange-2013-help.md)

[保留标记和保留策略](retention-tags-and-retention-policies-exchange-2013-help.md)

