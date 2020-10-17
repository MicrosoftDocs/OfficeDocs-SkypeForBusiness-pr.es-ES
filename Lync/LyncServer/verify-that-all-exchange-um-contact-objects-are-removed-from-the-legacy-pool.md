---
title: Comprobar que todos los objetos de contacto de mensajería unificada de Exchange se han quitado del grupo heredado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae8f82016f8dd78c3ecd568e34c3cc408a204ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515957"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="2f55d-102">Comprobar que todos los objetos de contacto de mensajería unificada de Exchange se han quitado del grupo heredado</span><span class="sxs-lookup"><span data-stu-id="2f55d-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f55d-103">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="2f55d-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="2f55d-104">Use la herramienta **OCSUmUtil** o el cmdlet **Get-CsExumContact** para comprobar que los objetos de contacto de mensajería unificada de Exchange se han quitado del grupo de Office Communications Server 2007 R2 heredado.</span><span class="sxs-lookup"><span data-stu-id="2f55d-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="2f55d-105">**OCSUmUtil** se encuentra en la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="2f55d-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="2f55d-106">% Program Files% \\ archivos comunes \\ Lync Server 2013 \\ soporte \\OcsUMUtil.exe</span><span class="sxs-lookup"><span data-stu-id="2f55d-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="2f55d-107">**OCSUmUtil** debe ejecutarse desde una cuenta de usuario que tenga:</span><span class="sxs-lookup"><span data-stu-id="2f55d-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="2f55d-108">Pertenencia a los grupos RTCUniversalServerAdmins y RTCUniversalUserAdmins (que incluyen derechos para leer la configuración de mensajería unificada de Exchange Server)</span><span class="sxs-lookup"><span data-stu-id="2f55d-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="2f55d-109">Derechos de dominio para crear objetos de contacto en el contenedor especificado de la unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="2f55d-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="2f55d-110">Para obtener información detallada sobre cómo usar el cmdlet **Get-CsExumContact** , vea [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f55d-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

