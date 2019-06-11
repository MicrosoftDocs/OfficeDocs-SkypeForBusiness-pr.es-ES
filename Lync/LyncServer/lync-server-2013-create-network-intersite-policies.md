---
title: 'Lync Server 2013: crear directivas de sitios intersitios de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6309b27ddedb37c2c38e7d40e74e427f61b904a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Crear directivas de intersitios de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Una *Directiva de red entre sitios* define limitaciones de ancho de banda entre los sitios que tienen vínculos WAN directos entre ellos.

Para obtener más información, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> Una directiva de red entre sitios <EM>solo</EM> es necesaria si hay un vínculo cruzado directo entre dos sitios de red.



</div>

En la topología de ejemplo de la región de Norteamérica, hay un vínculo directo entre los sitios de Reno y Albuquerque. Estos dos sitios requieren una directiva entre sitios que aplique un perfil de directiva de ancho de banda adecuado. En el siguiente ejemplo se aplica\_el perfil de vínculo de 20 MB.

<div>

## <a name="to-create-a-network-intersite-policy"></a>Para crear una directiva de intersitios de red

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsNetworkInterSitePolicy para crear directivas entre sitios de red y aplicar un perfil de directiva de ancho de banda adecuado para dos sitios que tengan un vínculo cruzado directo. Por ejemplo, ejecute lo siguiente:
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  Repita el paso 2 según sea necesario para crear directivas de intersitios de red para todas las parejas de sitios de red con vínculos cruzados directos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

