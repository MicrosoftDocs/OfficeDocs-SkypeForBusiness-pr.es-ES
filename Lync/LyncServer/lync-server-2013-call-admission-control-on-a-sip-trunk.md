---
title: 'Lync Server 2013: control de admisión de llamadas en un tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ae55f6146e59931b55ec384d374ea837eeb598c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a>Control de admisión de llamadas en un tronco SIP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

Para implementar el control de admisión de llamadas (CAC) en un tronco SIP, debe crear un sitio de red para representar al proveedor de servicios de telefonía de Internet (ITSP). Para aplicar valores de directivas de ancho de banda al tronco SIP, debe crear una directiva entre el sitio de red de su empresa y el sitio de red que cree para representar al ITSP.

La siguiente ilustración muestra un ejemplo de implementación de CAC en un tronco SIP.

**Configuración de CAC en un tronco SIP**

![Diagrama de enlace troncal SIP de control de admisión de llamadas](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Diagrama de enlace troncal SIP de control de admisión de llamadas")

Para configurar el CAC en un tronco SIP, deberá realizar las siguientes tareas durante la implementación de CAC:

1.  Cree un sitio de red para representar al ITSP. Asocie el sitio de red a una región de red adecuada y asigne un ancho de banda de cero para el audio y el vídeo de este sitio de red. Para obtener más información, consulte [Configure Network Sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) en la documentación sobre implementación.
    
    <div>
    

    > [!NOTE]  
    > Para el ITSP, no funciona esta configuración de sitio de red. Los valores de la directiva de ancho de banda se aplican, en realidad, en el paso 2.

    
    </div>

2.  Cree un vínculo entre sitios para el tronco SIP, usando los valores de los parámetros correspondientes al sitio que creó en el paso 1. Por ejemplo, use el nombre del sitio de red de su empresa como el valor del parámetro NetworkSiteID1 y el sitio de red ITSP como el valor del parámetro NetworkSiteID2. Para obtener más información, consulte [Create Network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) en la documentación sobre implementación. Consulte también la documentación del shell de administración de Lync Server para el cmdlet New-CsNetworkInterSitePolicy.

3.  Consulte a su ITSP la dirección IP del punto de terminación de medios del controlador de borde de sesión (SBC). Agregue esa dirección IP con una máscara de subred de 32 al sitio de red que representa al ITSP. Para obtener más información, consulte [asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

</div>

<span> </span>

</div>

</div>

</div>

