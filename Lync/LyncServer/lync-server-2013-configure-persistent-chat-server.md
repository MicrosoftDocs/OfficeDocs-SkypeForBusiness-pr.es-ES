---
title: 'Lync Server 2013: configurar el servidor de chat persistente'
description: 'Lync Server 2013: configurar el servidor de chat persistente.'
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
ms.openlocfilehash: d45320e1fa6b247f13cfffa9945b45390f2ae6c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564986"
---
# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="b66f2-103">Configurar el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b66f2-103">Configure Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b66f2-104">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="b66f2-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b66f2-105">Para crear una nueva configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b66f2-105">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="b66f2-106">Para obtener la configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b66f2-106">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="b66f2-107">Para quitar la configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b66f2-107">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="b66f2-108">Para establecer la configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b66f2-108">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="b66f2-109">Para Lync Server 2013, el tráfico del servicio Web se admite en los servidores front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b66f2-109">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="b66f2-110">Por lo tanto, la dirección gcweb01 del servidor de chat persistente no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="b66f2-110">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="b66f2-111">Aún admitimos el acceso a servicios web internos, ya que seguimos proporcionando el servicio de carga y descarga de archivos únicamente para el sitio web *interno*; (no para el sitio web *externo* para usuarios remotos).</span><span class="sxs-lookup"><span data-stu-id="b66f2-111">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

