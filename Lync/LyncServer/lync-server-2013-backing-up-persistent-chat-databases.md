---
title: 'Lync Server 2013: copia de seguridad de bases de datos de chat persistente'
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
ms.openlocfilehash: 98d4d69a09ad58d4578c0636f7e6bce54497cb9d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Copia de seguridad de bases de datos de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-17_

El contenido del salón de chat persistente se almacena en la base de datos de chat persistente (MGC. MDF). Se trata de datos críticos para la empresa de los que se debe hacer una copia de seguridad de forma regular. Además del contenido del salón de chat, la base de datos de chat persistente almacena información sobre las entidades de identidad (por ejemplo, usuarios y grupos de usuarios), así como las funciones y el acceso que tienen a los salones de chat y al salón de chat.

Hay dos formas de realizar copias de seguridad de los datos del chat persistente.

  - Copia de seguridad de SQL Server

  - El `Export-CsPersistentChatData` cmdlet, que exporta datos de chat persistente como un archivo

Los datos que se crean mediante la copia de seguridad de SQL Server requieren mucho más espacio en disco (posiblemente 20 veces más `Export-CsPersistentChatData`) que el creado por, pero es más probable que la copia de seguridad de SQL Server sea un procedimiento con el que estén familiarizados los administradores.

</div>

<span> </span>

</div>

</div>

</div>

