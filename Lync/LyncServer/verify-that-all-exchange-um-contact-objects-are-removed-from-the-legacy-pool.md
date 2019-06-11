---
title: Comprobar que todos los objetos de contacto de mensajería unificada de Exchange se han quitado del grupo heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0db8f4c55d863221c9a66d33a21bbe073bbc225a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="50ec9-102">Comprobar que todos los objetos de contacto de mensajería unificada de Exchange se han quitado del grupo heredado</span><span class="sxs-lookup"><span data-stu-id="50ec9-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50ec9-103">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="50ec9-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="50ec9-104">Use la herramienta **OCSUmUtil** o el cmdlet **Get-CsExumContact** para comprobar que los objetos de contacto de MU de Exchange se han quitado del grupo heredado de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="50ec9-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="50ec9-105">**OCSUmUtil** se encuentra en la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="50ec9-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="50ec9-106">% Archivos de programa\\% archivos\\comunes de Lync\\Server\\2013 support OcsUMUtil. exe</span><span class="sxs-lookup"><span data-stu-id="50ec9-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="50ec9-107">**OCSUmUtil** debe ejecutarse desde una cuenta de usuario que tenga:</span><span class="sxs-lookup"><span data-stu-id="50ec9-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="50ec9-108">Pertenencia al grupo RTCUniversalServerAdmins y RTCUniversalUserAdmins (que incluye derechos para leer la configuración de mensajería unificada de Exchange Server)</span><span class="sxs-lookup"><span data-stu-id="50ec9-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="50ec9-109">Derechos de dominio para crear objetos de contacto en el contenedor de unidades organizativas (OU) especificadas</span><span class="sxs-lookup"><span data-stu-id="50ec9-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="50ec9-110">Para obtener detalles sobre el uso del cmdlet **Get-CsExumContact** , vea [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50ec9-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

