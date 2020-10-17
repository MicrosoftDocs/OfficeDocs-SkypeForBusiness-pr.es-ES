---
title: 'Lync Server 2013: configurar el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a9661c3e9695bde240225b7d0bcd8ca1e54df09
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520447"
---
# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="bc5b2-102">Configurar el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc5b2-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc5b2-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="bc5b2-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="bc5b2-104">Para crear una nueva configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="bc5b2-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="bc5b2-105">Para obtener la configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="bc5b2-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="bc5b2-106">Para quitar la configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="bc5b2-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="bc5b2-107">Para establecer la configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="bc5b2-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="bc5b2-108">Para Lync Server 2013, el tráfico del servicio Web se admite en los servidores front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc5b2-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="bc5b2-109">Por lo tanto, la dirección gcweb01 del servidor de chat persistente no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="bc5b2-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="bc5b2-110">Aún admitimos el acceso a servicios web internos, ya que seguimos proporcionando el servicio de carga y descarga de archivos únicamente para el sitio web *interno*; (no para el sitio web *externo* para usuarios remotos).</span><span class="sxs-lookup"><span data-stu-id="bc5b2-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

