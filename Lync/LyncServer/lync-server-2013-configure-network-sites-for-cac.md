---
title: 'Lync Server 2013: configuración de sitios de red para CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 528ed67243fb0ab0451abf504a458afc420d94ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Configurar sitios de red para CAC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Si ya ha creado sitios de red para la omisión de E9-1-1 o multimedia, puede modificar los sitios de red existentes para aplicar un perfil de directiva de ancho de banda mediante el cmdlet <STRONG>set-CsNetworkSite</STRONG> . Para obtener un ejemplo de cómo modificar un sitio de red, vea <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>.



</div>

Los *sitios de red* son las oficinas o ubicaciones dentro de cada región de la red de control de admisión de llamadas (CAC), E9-1-1 y las implementaciones por omisión de medios. Use los procedimientos siguientes para crear sitios de red que se alineen con los sitios de red en la topología de red de ejemplo de CAC. Estos procedimientos muestran cómo crear y configurar sitios de red que están limitados por el ancho de banda WAN y, por lo tanto, requieren directivas de ancho de banda que limitan el flujo de tráfico de audio o vídeo en tiempo real.

En el ejemplo CAC Deployment, la región de Norteamérica tiene seis sitios. Tres de estos sitios están limitados por el ancho de banda WAN: Reno, Portland y Albuquerque. Los otros tres sitios, que *no* están limitados por el ancho de banda de WAN: Nueva York, Chicago y Detroit. Para obtener un ejemplo de cómo crear o modificar esos otros sitios de red, consulte [crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Para ver la topología de red de ejemplo, vea [ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación de planeación.

<div class=" ">


> [!NOTE]  
> En el siguiente procedimiento, se usa el shell de administración de Lync Server para crear un sitio de red. Para obtener detalles sobre el uso del panel de control de Lync Server para crear un sitio de red, consulte <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>Para crear sitios de red para el control de admisión de llamadas

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet **New-CsNetworkSite** para crear sitios de red y aplicar un perfil de directiva de ancho de banda adecuado a cada sitio. Por ejemplo, ejecute lo siguiente:
    
       ```
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Para finalizar la creación de sitios de red para la topología de ejemplo completa, repita el paso 2 para los sitios de red con limitaciones de ancho de banda de las regiones EMEA y APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

