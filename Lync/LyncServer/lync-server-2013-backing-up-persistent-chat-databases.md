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

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Copia de seguridad de bases de datos de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-17_

El contenido del salón de chat persistente se almacena en la base de datos de chat persistente (MGC. MDF). Se debería realizar una copia de seguridad de estos datos importantes para la empresa de forma regular. Además del contenido de los salones de chat, la base de datos de chat persistente también almacena información sobre los principales (como usuarios y grupos de usuarios), así como las funciones y el acceso que tienen a los salones de chat y el salón de chat.

Existen dos formas de realizar copias de seguridad de datos persistentes del chat.

  - Copia de seguridad de SQL Server

  - El `Export-CsPersistentChatData` cmdlet, que exporta datos de chat persistentes como un archivo

Los datos que se crean con copia de seguridad de SQL Server requieren significativamente más espacio en el disco (posiblemente 20 veces más `Export-CsPersistentChatData`) que el creado por, pero es más probable que la copia de seguridad de SQL Server sea un procedimiento con el que estén familiarizados los administradores.

</div>

<span> </span>

</div>

</div>

</div>

