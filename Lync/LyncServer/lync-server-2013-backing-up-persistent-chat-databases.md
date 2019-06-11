---
title: 'Lync Server 2013: copia de seguridad de las bases de datos de chat persistentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8ffb99effcf0a42bbddefd7151aa40a8d691d9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="faa3c-102">Copia de seguridad de bases de datos de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faa3c-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faa3c-103">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="faa3c-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="faa3c-104">El contenido del salón de chat persistente se almacena en la base de datos de chat persistente (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="faa3c-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="faa3c-105">Se debería realizar una copia de seguridad de estos datos importantes para la empresa de forma regular.</span><span class="sxs-lookup"><span data-stu-id="faa3c-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="faa3c-106">Además del contenido de los salones de chat, la base de datos de chat persistente también almacena información sobre los principales (como usuarios y grupos de usuarios), así como las funciones y el acceso que tienen a los salones de chat y el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="faa3c-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="faa3c-107">Existen dos formas de realizar copias de seguridad de datos persistentes del chat.</span><span class="sxs-lookup"><span data-stu-id="faa3c-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="faa3c-108">Copia de seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="faa3c-108">SQL Server Backup</span></span>

  - <span data-ttu-id="faa3c-109">El `Export-CsPersistentChatData` cmdlet, que exporta datos de chat persistentes como un archivo</span><span class="sxs-lookup"><span data-stu-id="faa3c-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="faa3c-110">Los datos que se crean con copia de seguridad de SQL Server requieren significativamente más espacio en el disco (posiblemente 20 veces más `Export-CsPersistentChatData`) que el creado por, pero es más probable que la copia de seguridad de SQL Server sea un procedimiento con el que estén familiarizados los administradores.</span><span class="sxs-lookup"><span data-stu-id="faa3c-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

