---
title: 'Lync Server 2013: copia de seguridad de bases de datos de chat persistente'
description: 'Lync Server 2013: copia de seguridad de las bases de datos de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9885eaf0065f5b558922c056fb1f669a5b821460
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563296"
---
# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="692d4-103">Copia de seguridad de bases de datos de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="692d4-103">Backing up Persistent Chat databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="692d4-104">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="692d4-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="692d4-105">El contenido del salón de chat persistente se almacena en la base de datos de chat persistente (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="692d4-105">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="692d4-106">Se trata de datos críticos para la empresa de los que se debe hacer una copia de seguridad de forma regular.</span><span class="sxs-lookup"><span data-stu-id="692d4-106">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="692d4-107">Además del contenido del salón de chat, la base de datos de chat persistente almacena información sobre las entidades de identidad (por ejemplo, usuarios y grupos de usuarios), así como las funciones y el acceso que tienen a los salones de chat y al salón de chat.</span><span class="sxs-lookup"><span data-stu-id="692d4-107">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="692d4-108">Hay dos formas de realizar copias de seguridad de los datos del chat persistente.</span><span class="sxs-lookup"><span data-stu-id="692d4-108">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="692d4-109">Copia de seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="692d4-109">SQL Server Backup</span></span>

  - <span data-ttu-id="692d4-110">El `Export-CsPersistentChatData` cmdlet, que exporta datos de chat persistente como un archivo</span><span class="sxs-lookup"><span data-stu-id="692d4-110">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="692d4-111">Los datos que se crean mediante la copia de seguridad de SQL Server requieren mucho más espacio en disco (posiblemente 20 veces más) que el creado por `Export-CsPersistentChatData` , pero es más probable que la copia de seguridad de SQL Server sea un procedimiento con el que estén familiarizados los administradores.</span><span class="sxs-lookup"><span data-stu-id="692d4-111">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

