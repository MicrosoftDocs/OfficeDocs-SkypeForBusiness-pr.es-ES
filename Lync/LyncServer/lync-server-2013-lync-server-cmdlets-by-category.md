---
title: 'Lync Server 2013: cmdlets de Lync Server por categoría'
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
ms.openlocfilehash: 68764952ebfe2a45895e480d923d76a108fdda8e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="a1934-102">Cmdlets de Lync Server 2013 por categoría</span><span class="sxs-lookup"><span data-stu-id="a1934-102">Lync Server 2013 cmdlets by category</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1934-103">_**Última modificación del tema:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="a1934-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="a1934-104">Microsoft Lync Server 2013 incluye casi 550 cmdlets diseñados específicamente para que los administradores puedan administrar Lync Server desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a1934-104">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="a1934-105">Puede acceder a los cmdlets desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1934-105">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="a1934-106">Puede obtener ayuda sobre un cmdlet directamente en la línea de comandos escribiendo un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1934-106">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="a1934-107">El comando anterior recuperará toda la ayuda disponible para el cmdlet **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="a1934-107">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="a1934-108">Reemplace la referencia a **New-CsVoicePolicy** por el nombre del cmdlet sobre el que desea recuperar información de ayuda.</span><span class="sxs-lookup"><span data-stu-id="a1934-108">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="a1934-109">Para recuperar una lista completa de los cmdlets disponibles para administrar Microsoft Lync Server 2013, escriba lo siguiente en el símbolo del sistema del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="a1934-109">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="a1934-p103">Si no sabe los cmdlets que necesita, también se proporciona una lista de los cmdlets por categorías y sus temas de ayuda. Verá que algunos de los cmdlets aparecen en varias categorías; eso se debe a que se aplican a distintos ámbitos del producto. A continuación se presenta una lista de categorías:</span><span class="sxs-lookup"><span data-stu-id="a1934-p103">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics. You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product. The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a1934-113">La referencia del cmdlet de Skype empresarial se ha movido a docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a1934-113">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="a1934-114">Al hacer clic en los siguientes vínculos, se le llevará a la nueva página de docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a1934-114">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="a1934-115">El contenido se encuentra ahora abierto y disponible para contribuciones de la comunidad a través de GitHub.</span><span class="sxs-lookup"><span data-stu-id="a1934-115">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="a1934-116">¿Está interesado en colaborar?</span><span class="sxs-lookup"><span data-stu-id="a1934-116">Interested in contributing?</span></span> <span data-ttu-id="a1934-117">Consulte el archivo Léame en el repositorio aquí:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="a1934-117">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a1934-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a1934-118">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1934-119"><a href="lync-server-2013-user-management-cmdlets.md">Cmdlets de administración de usuarios en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-119"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a1934-120"><a href="lync-server-2013-voice-application-cmdlets.md">Cmdlets de aplicación de voz en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-120"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1934-121"><a href="lync-server-2013-client-management-cmdlets.md">Cmdlets de administración de clientes en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-121"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a1934-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Cmdlets avanzados de telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1934-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">Cmdlets de presencia y mensajería instantánea en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a1934-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Cmdlets de conectividad RTC en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1934-125"><a href="lync-server-2013-conferencing-cmdlets.md">Cmdlets de conferencia en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-125"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a1934-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Cmdlets de teléfonos y dispositivos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1934-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Cmdlets de infraestructura e implementación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a1934-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Cmdlets de migración y coexistencia en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1934-129"><a href="lync-server-2013-security-cmdlets.md">Cmdlets de seguridad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-129"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a1934-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Cmdlets de configuración del shell de administración de Lync Server en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1934-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Cmdlets de servicios y roles de servidor en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a1934-132"><a href="lync-server-2013-mobility-cmdlets.md">Cmdlets de movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1934-133"><a href="lync-server-2013-application-management-cmdlets.md">Cmdlets de administración de aplicaciones en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-133"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a1934-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Cmdlets del servidor de chat persistente en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1934-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Cmdlets de Federación y acceso externo en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a1934-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Cmdlets de registro centralizado en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1934-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Cmdlets de telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a1934-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1934-138">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a1934-138">See Also</span></span>


[<span data-ttu-id="a1934-139">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1934-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

