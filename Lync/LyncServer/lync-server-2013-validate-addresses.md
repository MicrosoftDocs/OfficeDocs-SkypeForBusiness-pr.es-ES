---
title: 'Lync Server 2013: validar direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 397c1037937e100f1981a689f0860362d852ed10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="e1844-102">Validar direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1844-102">Validate addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1844-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e1844-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e1844-104">Antes de publicar la base de datos de ubicación, debe validar nuevas ubicaciones en relación con la guía de dirección maestra (MSAG) que mantiene su tronco de SIP o la red de telefonía pública conmutada (RTC) E9-1-1 proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="e1844-104">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="e1844-105">Para obtener más información sobre los proveedores de servicios E9-1-1 de SIP, consulte [elección de un proveedor de servicios de E9-1-1 para Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span><span class="sxs-lookup"><span data-stu-id="e1844-105">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="e1844-106">Para obtener detalles sobre la validación de direcciones, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e1844-106">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="e1844-107">**Get-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="e1844-107">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="e1844-108">**Set-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="e1844-108">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="e1844-109">**Remove-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="e1844-109">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="e1844-110">**Get-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="e1844-110">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="e1844-111">**Prueba-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="e1844-111">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="e1844-112">Para validar direcciones ubicadas en la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="e1844-112">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="e1844-113">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e1844-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e1844-114">Ejecute los cmdlets siguientes para configurar la conexión de proveedor de servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="e1844-114">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="e1844-115">Ejecute el cmdlet siguiente para validar las direcciones en la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="e1844-115">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="e1844-116">También puede usar el cmdlet **Test-CsLisCivicAddress** para validar direcciones individuales.</span><span class="sxs-lookup"><span data-stu-id="e1844-116">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

