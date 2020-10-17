---
title: 'Lync Server 2013: ver la configuración del servidor perimetral'
description: 'Lync Server 2013: ver la configuración del servidor perimetral.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4318b8c97f53f267bb79953af504977f6437214d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569686"
---
# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="a28e0-103">Ver la configuración del servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a28e0-103">View Edge Server settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a28e0-104">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="a28e0-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="a28e0-105">Las configuraciones de servidor perimetral general deben revisarse en función de los datos de la base de datos de administración de configuración, para ayudar a garantizar que todos los cambios se documentaron según los procedimientos de control de cambios definidos.</span><span class="sxs-lookup"><span data-stu-id="a28e0-105">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="a28e0-106">Las comprobaciones adicionales podrían incluir las que se describen en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a28e0-106">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="a28e0-107">Comprobar las listas de permitidos y bloqueados</span><span class="sxs-lookup"><span data-stu-id="a28e0-107">Verify the Allow and block lists</span></span>

<span data-ttu-id="a28e0-108">Compruebe las listas de URI de SIP "permitir" y "bloquear" para los dominios federados, para determinar si los espacios de nombres enumerados siguen siendo válidos.</span><span class="sxs-lookup"><span data-stu-id="a28e0-108">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="a28e0-109">Puede usar Windows PowerShell para ver las listas permitidas y bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="a28e0-109">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="a28e0-110">Para revisar los dominios en la lista de dominios permitidos, ejecute el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a28e0-110">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="a28e0-111">Ese comando devuelve información similar a la siguiente para los dominios de la lista de dominios permitidos:</span><span class="sxs-lookup"><span data-stu-id="a28e0-111">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="a28e0-112">Identidad: contoso.com</span><span class="sxs-lookup"><span data-stu-id="a28e0-112">Identity : contoso.com</span></span>

<span data-ttu-id="a28e0-113">Dominio: contoso.com</span><span class="sxs-lookup"><span data-stu-id="a28e0-113">Domain : contoso.com</span></span>

<span data-ttu-id="a28e0-114">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="a28e0-114">ProxyFqdn :</span></span>

<span data-ttu-id="a28e0-115">Sin</span><span class="sxs-lookup"><span data-stu-id="a28e0-115">Comment :</span></span>

<span data-ttu-id="a28e0-116">MarkForMonitoring: false</span><span class="sxs-lookup"><span data-stu-id="a28e0-116">MarkForMonitoring : False</span></span>

<span data-ttu-id="a28e0-117">Sin</span><span class="sxs-lookup"><span data-stu-id="a28e0-117">Comment :</span></span>

<span data-ttu-id="a28e0-118">Para revisar los dominios de la lista de dominios bloqueados, use este comando:</span><span class="sxs-lookup"><span data-stu-id="a28e0-118">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="a28e0-119">A su vez, recibirá información como esta para cada dominio bloqueado:</span><span class="sxs-lookup"><span data-stu-id="a28e0-119">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="a28e0-120">Identidad: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="a28e0-120">Identity : tailspintoys.com</span></span>

<span data-ttu-id="a28e0-121">Dominio: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="a28e0-121">Domain : tailspintoys.com</span></span>

<span data-ttu-id="a28e0-122">Windows PowerShell también le permite comprobar si puede conectarse a los dominios de la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="a28e0-122">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="a28e0-123">Por ejemplo, este comando comprueba la conexión entre el servidor perimetral (el TargetFqdn) y el dominio federado contoso.com:</span><span class="sxs-lookup"><span data-stu-id="a28e0-123">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="a28e0-124">Y este comando comprueba la conexión entre el servidor perimetral y todos los dominios que se encuentran en la lista de dominios permitidos:</span><span class="sxs-lookup"><span data-stu-id="a28e0-124">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="a28e0-125">Comprobar que hay varios servidores perimetrales idénticos</span><span class="sxs-lookup"><span data-stu-id="a28e0-125">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="a28e0-126">Si se implementan varios servidores perimetrales en una matriz con equilibrio de carga, se recomienda comprobar que todos los servidores perimetrales de la matriz se configuran de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="a28e0-126">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="a28e0-127">Puede ver la configuración de servidores perimetrales en el panel de detalles de la extensión Lync Server 2013 para el complemento Administración de equipos.</span><span class="sxs-lookup"><span data-stu-id="a28e0-127">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a28e0-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a28e0-128">See Also</span></span>


[<span data-ttu-id="a28e0-129">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="a28e0-129">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="a28e0-130">Get-CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="a28e0-130">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="a28e0-131">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="a28e0-131">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

