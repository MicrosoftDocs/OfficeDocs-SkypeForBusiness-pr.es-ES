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
ms.openlocfilehash: 97797500bab9b6c0ed7dc2c79e603d84e819df5e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="97fe1-102">Configurar el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97fe1-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97fe1-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="97fe1-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="97fe1-104">Para crear una nueva configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="97fe1-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="97fe1-105">Para obtener la configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="97fe1-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="97fe1-106">Para quitar la configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="97fe1-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="97fe1-107">Para establecer la configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="97fe1-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="97fe1-108">Para Lync Server 2013, el tráfico del servicio Web se admite en los servidores front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97fe1-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="97fe1-109">Por lo tanto, la dirección gcweb01 del servidor de chat persistente no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="97fe1-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="97fe1-110">Aún admitimos el acceso a servicios web internos, ya que seguimos proporcionando el servicio de carga y descarga de archivos únicamente para el sitio web *interno*; (no para el sitio web *externo* para usuarios remotos).</span><span class="sxs-lookup"><span data-stu-id="97fe1-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

