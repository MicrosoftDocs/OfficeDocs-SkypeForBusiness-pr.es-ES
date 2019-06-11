---
title: Administración de los parámetros de configuración del servicio de registro centralizado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce13f34a5a48c80c1f825e225a20c96ebfa2db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Administración de la configuración del servicio de registro centralizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El servicio de registro centralizado es controlado y configurado por la configuración y los parámetros creados y usados por el controlador de servicio de registro centralizado (CLSController) para enviar comandos al agente del servicio de registro centralizado ( CLSAgent). El agente procesa los comandos que se le envían y (en el caso de un comando de inicio) usa la configuración de los escenarios, proveedores, tamaño del registro, duración del seguimiento e indicadores para empezar a recopilar registros de seguimiento de acuerdo con la información de configuración proporcionada.

<div>


> [!IMPORTANT]
> No todos los cmdlets de Windows PowerShell enumerados para el servicio de registro centralizado están pensados para su uso con implementaciones locales de Lync Server 2013. Aunque parezca que funcionen, los siguientes cmdlets no están diseñados para funcionar con implementaciones locales de Lync Server 2013: 
> <UL>
> <LI>
> <P><STRONG>Cmdlets de CsClsRegion:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">set-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>y <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</P>
> <LI>
> <P><STRONG>Cmdlets de CsClsSearchTerm:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> y <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">set-CsClsSearchTerm</A>.</P>
> <LI>
> <P><STRONG>Cmdlets de CsClsSecurityGroup:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>y <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</P></LI></UL>La configuración definida en estos cmdlets no obstaculizará ni provocará ningún comportamiento adverso, pero estará diseñado para usarse con Microsoft Office 365 y no producirá los resultados esperados en las implementaciones locales. Esto no significa que estos cmdlets no sirvan para las implementaciones locales, sino que lo cierto es que tienen un uso más avanzado que no se aborda en esta documentación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

En los temas de esta sección se definen las opciones de configuración, los parámetros y la configuración del servicio de registro centralizado. En los siguientes temas se incluye información sobre cómo configurar el servicio de registro centralizado, cómo recuperar la configuración, la creación de escenarios, la administración de grupos de seguridad para el servicio de registro centralizado, la búsqueda y mucho más.

  - [Administración de la configuración del servicio de registro centralizado de equipos, sitios y global en Lync Server 2013](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Configuración de proveedores para el servicio de registro centralizado en Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Configuración de escenarios para el servicio de registro centralizado en Lync Server 2013](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Información general sobre el servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Cmdlets de registro centralizados en Lync Server 2013](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

