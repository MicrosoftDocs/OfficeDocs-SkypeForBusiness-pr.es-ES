---
title: 'Lync Server 2013: cmdlets de Lync Server por categoría'
description: 'Lync Server 2013: cmdlets de Lync Server por categoría.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df562bd11d54c9ecda4fe3d6172ed1d8bd2627d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571876"
---
# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="4ee8d-103">Cmdlets de Lync Server 2013 por categoría</span><span class="sxs-lookup"><span data-stu-id="4ee8d-103">Lync Server 2013 cmdlets by category</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ee8d-104">_**Última modificación del tema:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="4ee8d-104">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="4ee8d-105">Microsoft Lync Server 2013 incluye casi 550 cmdlets diseñados específicamente para que los administradores puedan administrar Lync Server desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-105">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="4ee8d-106">Puede acceder a los cmdlets desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-106">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="4ee8d-107">Puede obtener ayuda sobre un cmdlet directamente en la línea de comandos escribiendo un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ee8d-107">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="4ee8d-108">El comando anterior recuperará toda la ayuda disponible para el cmdlet **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-108">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="4ee8d-109">Reemplace la referencia a **New-CsVoicePolicy** por el nombre del cmdlet sobre el que desea recuperar información de ayuda.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-109">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="4ee8d-110">Para recuperar una lista completa de los cmdlets disponibles para administrar Microsoft Lync Server 2013, escriba lo siguiente en el símbolo del sistema del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4ee8d-110">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="4ee8d-p103">Si no sabe los cmdlets que necesita, también se proporciona una lista de los cmdlets por categorías y sus temas de ayuda. Verá que algunos de los cmdlets aparecen en varias categorías; eso se debe a que se aplican a distintos ámbitos del producto. A continuación se presenta una lista de categorías:</span><span class="sxs-lookup"><span data-stu-id="4ee8d-p103">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics. You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product. The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4ee8d-114">La referencia del cmdlet de Skype empresarial se ha movido a docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-114">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="4ee8d-115">Al hacer clic en los siguientes vínculos, se le llevará a la nueva página de docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-115">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="4ee8d-116">El contenido se encuentra ahora abierto y disponible para contribuciones de la comunidad a través de GitHub.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-116">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="4ee8d-117">¿Está interesado en colaborar?</span><span class="sxs-lookup"><span data-stu-id="4ee8d-117">Interested in contributing?</span></span> <span data-ttu-id="4ee8d-118">Consulte el archivo Léame en el repositorio aquí: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="4ee8d-118">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4ee8d-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4ee8d-119">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ee8d-120"><a href="lync-server-2013-user-management-cmdlets.md">Cmdlets de administración de usuarios en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-120"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4ee8d-121"><a href="lync-server-2013-voice-application-cmdlets.md">Cmdlets de aplicación de voz en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-121"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ee8d-122"><a href="lync-server-2013-client-management-cmdlets.md">Cmdlets de administración de clientes en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-122"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4ee8d-123"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Cmdlets avanzados de telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-123"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ee8d-124"><a href="lync-server-2013-im-and-presence-cmdlets.md">Cmdlets de presencia y mensajería instantánea en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-124"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4ee8d-125"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Cmdlets de conectividad RTC en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-125"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ee8d-126"><a href="lync-server-2013-conferencing-cmdlets.md">Cmdlets de conferencia en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-126"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4ee8d-127"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Cmdlets de teléfonos y dispositivos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-127"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ee8d-128"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Cmdlets de infraestructura e implementación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-128"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4ee8d-129"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Cmdlets de migración y coexistencia en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-129"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ee8d-130"><a href="lync-server-2013-security-cmdlets.md">Cmdlets de seguridad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-130"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4ee8d-131"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Cmdlets de configuración del shell de administración de Lync Server en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-131"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ee8d-132"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Cmdlets de servicios y roles de servidor en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-132"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4ee8d-133"><a href="lync-server-2013-mobility-cmdlets.md">Cmdlets de movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-133"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ee8d-134"><a href="lync-server-2013-application-management-cmdlets.md">Cmdlets de administración de aplicaciones en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-134"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4ee8d-135"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Cmdlets del servidor de chat persistente en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-135"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ee8d-136"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Cmdlets de Federación y acceso externo en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-136"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4ee8d-137"><a href="lync-server-2013-centralized-logging-cmdlets.md">Cmdlets de registro centralizado en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-137"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ee8d-138"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Cmdlets de telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4ee8d-138"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4ee8d-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ee8d-139">See Also</span></span>


[<span data-ttu-id="4ee8d-140">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ee8d-140">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

