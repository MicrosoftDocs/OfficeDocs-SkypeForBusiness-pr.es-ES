---
title: 'Lync Server 2013: configurar sitios de red para CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e24932b23b1a9168ed64279f98db125f06ad0e2e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520527"
---
# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Configurar sitios de red para CAC en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Si ya ha creado sitios de red para el desvío de E9-1-1 o medios, puede modificar los sitios de red existentes para aplicar un perfil de directiva de ancho de banda mediante el cmdlet <STRONG>set-CsNetworkSite</STRONG> . Para ver un ejemplo sobre cómo modificar un sitio de red, vea <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>.



</div>

Los *sitios de red* son las oficinas o ubicaciones dentro de cada región de red de las implementaciones de desvío de medios, E9-1-1 y control de admisión de llamadas.  Use los procedimientos siguientes con el fin de crear sitios de red que alineen a sitios de red en la topología de red de ejemplo para el control de admisión de llamadas. Estos procedimientos muestran cómo crear y configurar sitios de red restringidos por el ancho de banda de la WAN y que, por tanto, requieren directivas de ancho de banda que limiten el flujo de tráfico de audio o vídeo en tiempo real.

En la implementación del control de admisión de llamadas de ejemplo, la región de Norteamérica tiene seis sitios. Tres de estos sitios están restringidos por el ancho de banda de la WAN: Reno, Portland y Albuquerque. Los tres sitios restantes que *no* están restringidos por el ancho de banda de la WAN son: Nueva York, Chicago y Detroit. Para ver un ejemplo sobre cómo crear o modificar estos otros sitios de red, vea [crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Para ver la topología de red de ejemplo, consulte [ejemplo: recopilación de los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación referente a la planeación.

<div class=" ">


> [!NOTE]  
> En el siguiente procedimiento, se usa el shell de administración de Lync Server para crear un sitio de red. Para obtener información detallada sobre cómo usar el panel de control de Lync Server para crear un sitio de red, vea <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>Para crear sitios de red para el control de admisión de llamadas

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet **New-CsNetworkSite** para crear sitios de red y aplicar un perfil de directiva de ancho de banda adecuado en cada sitio. Por ejemplo, ejecute lo siguiente:
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Para terminar de crear sitios de red para la topología de ejemplo completa, repita el paso 2 para los sitios de red restringidos por el ancho de banda en las regiones EMEA y APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

