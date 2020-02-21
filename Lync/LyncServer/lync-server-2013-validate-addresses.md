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
ms.openlocfilehash: cb35c064c304360adb27ecae73dd93c0e616711a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="4f6b0-102">Validar direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f6b0-102">Validate addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f6b0-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="4f6b0-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="4f6b0-104">Antes de publicar la base de datos de las ubicaciones, debe validar las nuevas ubicaciones comparándolas con la guía de direcciones que mantiene el proveedor de servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="4f6b0-104">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="4f6b0-105">Para obtener más información acerca de los proveedores de servicios E9-1-1 de tronco SIP, consulte [elección de un proveedor de servicios E9-1-1 para Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4f6b0-105">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="4f6b0-106">Para obtener más información sobre la validación de direcciones, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="4f6b0-106">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="4f6b0-107">**Get-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="4f6b0-107">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="4f6b0-108">**Set-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="4f6b0-108">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="4f6b0-109">**Remove-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="4f6b0-109">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="4f6b0-110">**Get-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="4f6b0-110">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="4f6b0-111">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="4f6b0-111">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="4f6b0-112">Para validar direcciones ubicadas en la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="4f6b0-112">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="4f6b0-113">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f6b0-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4f6b0-114">Para configurar la conexión de proveedor de servicios de emergencia, ejecute los siguientes cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4f6b0-114">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="4f6b0-115">Para validar las direcciones en la base de datos de ubicaciones, ejecute el siguiente cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4f6b0-115">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="4f6b0-116">También puede usar el cmdlet **Test-CsLisCivicAddress** para validar direcciones individuales.</span><span class="sxs-lookup"><span data-stu-id="4f6b0-116">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

