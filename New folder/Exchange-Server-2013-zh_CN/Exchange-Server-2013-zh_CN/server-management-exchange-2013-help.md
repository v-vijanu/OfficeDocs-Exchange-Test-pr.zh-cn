﻿---
title: '服务器管理: Exchange 2013 Help'
TOCTitle: 服务器管理
ms:assetid: 30cbc4de-adb3-42e8-922f-7661095bdb8c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dd876866(v=EXCHG.150)
ms:contentKeyID: 50490146
ms.date: 01/11/2018
mtps_version: v=EXCHG.150
ms.translationtype: HT
---

# 服务器管理

 

_**适用于：** Exchange Server 2013_

_**上一次修改主题：** 2015-03-09_

服务器管理 管理角色组是组成 Microsoft Exchange Server 2013 中基于角色的访问控制 (RBAC) 权限模型的多个内置角色组之一。角色组会分配给一个或多个管理角色，这些管理角色拥有执行一组给定任务所需的权限。角色组的成员会获得访问角色组所分配的管理角色的权限。有关角色组的详细信息，请参阅[了解管理角色组](understanding-management-role-groups-exchange-2013-help.md)。

属于此角色组成员的管理员可以配置诸如数据库副本、证书、传输队列和发送连接器、虚拟目录和客户端访问协议这样的传输客户端访问和邮箱功能的特定于服务器的配置。

此角色组类似于 Microsoft Exchange 中的 Exchange Server 2007 服务器管理员角色。它授予管理物理服务器配置的访问权限。但是，与 Exchange 中的 Exchange 2007 服务器管理员角色不同，因为通过该角色只能访问运行 Exchange 2007 的本地服务器，而通过服务器管理角色组可以查看和配置组织中所有的 Exchange Server 2010 服务器。

如果希望管理员仅管理组织中的特定服务器，则可以更改应用于此角色组的管理作用域。或者，可以创建一个以服务器管理角色组为基础的角色组，并在新角色组上自定义管理作用域。有关详细信息，请参阅本主题后面的“角色组自定义”部分。

有关 RBAC 的详细信息，请参阅[了解基于角色的访问控制](understanding-role-based-access-control-exchange-2013-help.md)。

## 角色组成员身份

如果要向此角色组中添加或从中删除成员，请参阅[管理角色组成员](manage-role-group-members-exchange-2013-help.md)。

默认情况下，只有 Organization Management 角色组的成员可以向此角色组中添加或从员删除成员。有关如何添加其他角色组委派的详细信息，请参阅[管理角色组](manage-role-groups-exchange-2013-help.md)中的“添加或删除角色组委派”一节。

可以使用以下命令查看作为此角色组成员的用户或通用安全组 (USG) 的列表。

    Get-RoleGroupMember "Server Management"

有关角色组的成员的详细信息，请参阅[管理角色组成员](manage-role-group-members-exchange-2013-help.md)中的[View the members of a role group](manage-role-group-members-exchange-2013-help.md)。

## 角色组自定义

此角色组默认分配管理角色。“分配给此角色组的管理角色”一节列出了所包括的角色。您可以向此该角色组中添加或从中删除角色分配，以满足您组织的需要。

Exchange 2013 附带的角色组旨在匹配更精细的任务。通过将角色分配到角色组，就可以使该角色组的成员能够执行与该角色相关联的任务。例如，Journaling 角色可以管理日记代理和日记规则。有关如何将角色分配给角色组的详细信息，请参阅[了解管理角色分配](understanding-management-role-assignments-exchange-2013-help.md)。

分配给此角色组的角色拥有默认管理作用域。管理作用域确定可以由角色组成员查看或修改的 Exchange 对象。可以更改与角色和角色组之间的分配相关联的作用域。例如，如果仅希望角色组的成员能够更改特定组织单位下或特定位置中的收件人，则可能要执行此操作。有关管理作用域的详细信息，请参阅[了解管理角色作用域](understanding-management-role-scopes-exchange-2013-help.md)。

有关如何自定义该角色组的详细信息，请参阅下列主题：

  - [管理角色组](manage-role-groups-exchange-2013-help.md)

  - [管理角色组成员](manage-role-group-members-exchange-2013-help.md)

如果要创建角色组并将部分已分配到该角色组的角色分配到新的角色组，请参阅[管理角色组](manage-role-groups-exchange-2013-help.md)中的“创建角色组”一节。

## 分配给此角色组的管理角色

下表列出了分配给此角色组的所有管理角色，以及每个角色分配的下列属性：

  - **常规分配：** 使角色组成员能够访问由关联管理角色提供的管理角色条目。

  - **委派分配：** 使角色组成员能够将指定角色分配给其他角色组、角色分配策略、用户或 USG。

  - **收件人读取作用域：** 确定角色组成员允许从 Active Directory 读取的收件人对象。

  - **收件人写入作用域：** 确定角色组成员允许在 Active Directory 中修改的收件人对象。

  - **配置读取作用域：** 确定角色组成员允许从 Active Directory 读取的配置和服务器对象。

  - **配置写入作用域：** 确定角色组成员允许在 Active Directory 中修改的组织对象和服务器对象。

有关角色分配和管理作用域的详细信息，请参阅下列主题：

  - [了解管理角色分配](understanding-management-role-assignments-exchange-2013-help.md)

  - [了解管理角色作用域](understanding-management-role-scopes-exchange-2013-help.md)

### 分配给此角色组的管理角色

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>管理角色</th>
<th>常规分配</th>
<th>委派分配</th>
<th>收件人读取作用域</th>
<th>收件人写入作用域</th>
<th>配置读取作用域</th>
<th>配置写入作用域</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="database-copies-role-exchange-2013-help.md">数据库副本角色</a></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
</tr>
<tr class="even">
<td><p><a href="databases-role-exchange-2013-help.md">数据库角色</a></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
</tr>
<tr class="odd">
<td><p><a href="exchange-connectors-role-exchange-2013-help.md">Exchange 连接器角色</a></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
</tr>
<tr class="even">
<td><p><a href="exchange-server-certificates-role-exchange-2013-help.md">Exchange Server 证书角色</a></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
</tr>
<tr class="odd">
<td><p><a href="exchange-servers-role-exchange-2013-help.md">Exchange 服务器角色</a></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
</tr>
<tr class="even">
<td><p><a href="exchange-virtual-directories-role-exchange-2013-help.md">Exchange 虚拟目录角色</a></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoring-role-exchange-2013-help.md">监视角色</a></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
</tr>
<tr class="even">
<td><p><a href="pop3-and-imap4-protocols-role-exchange-2013-help.md">POP3 和 IMAP4 协议角色</a></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
</tr>
<tr class="odd">
<td><p><a href="receive-connectors-role-exchange-2013-help.md">接收连接器角色</a></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
</tr>
<tr class="even">
<td><p><a href="transport-queues-role-exchange-2013-help.md">传输队列角色</a></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>Organization</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
<td><p><code>OrganizationConfig</code></p></td>
</tr>
</tbody>
</table>

