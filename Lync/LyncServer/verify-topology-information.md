---
title: Comprobación de la información de topología
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69add03365fa55ba3b08ac4c6b7a1dd60a6294f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>Comprobación de la información de topología

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

El primer paso para comprobar que la combinación se completó correctamente es ver la información de topología de Office Communications Server 2007 R2 que se combinó con Lync Server 2013. En el generador de topologías, el nodo **BackCompatSite** muestra el nombre de dominio completo (FQDN) de cada grupo y servidor de Office Communications Server 2007 R2 que ha combinado.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>Para ver BackCompatSite en el Generador de topologías

1.  En el entorno de Office Communications Server 2007 R2, abra la herramienta administrativa de Office Communications Server 2007 R2 y observe los FQDN de los servidores y grupos de servidores heredados.

2.  En el entorno de Lync Server 2013, abra el generador de topologías y, a continuación, expanda el nodo **BackCompatSite** .

3.  Compruebe que se muestren los FQDN de los servidores y grupos de servidores que desea combinar.
    
    <div>
    

    > [!NOTE]  
    > En <STRONG>BackCompatSite</STRONG>, no verá ninguna información sobre roles del servidor instalados en un servidor front-end o en un servidor Standard Edition. Solo se muestran los roles de servidor necesarios para la interoperabilidad entre Office Communications Server 2007 R2 y Lync Server 2013.

    
    </div>

![Cuadro de diálogo BackCompatSite del generador de topologías](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Cuadro de diálogo BackCompatSite del generador de topologías")

También puede usar el panel de control de Lync Server 2013 para ver la topología combinada. En el panel de control de Lync Server 2013, puede ver el FQDN de cada servidor, el FQDN del grupo de servidores y el nombre del sitio de la topología combinada. Los servidores combinados tienen un nombre de **Sitio** de **BackCompatSite**.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Para ver la topología combinada en el panel de control de Lync Server 2013

1.  Abra el panel de control de Lync Server 2013.

2.  Haga clic en **Topología**.

3.  En la pestaña **Estado**, busque **BackCompatSite** en la columna**Sitio** para confirmar que aparecen los servidores y grupos que ha combinado.

![Panel de control de Lync Server donde se muestra la topología combinada](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Panel de control de Lync Server donde se muestra la topología combinada")

Para ver información más detallada sobre un grupo combinado, use el cmdlet **Get-CsPool**. Además de la información disponible en el generador de topologías y el panel de control de Lync Server 2013, este cmdlet muestra los servicios que se ejecutan en el grupo de servidores de Lync Server 2013.

<div>


> [!NOTE]  
> Al publicar la topología después de ejecutar el Asistente de combinación en el generador de topologías, los directorios de conferencia se combinan en Lync Server 2013. Los directorios de conferencia se pueden comprobar mediante la ejecución del cmdlet <STRONG>Get-CsConferenceDirectory</STRONG> .



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>Para ver los servicios de un grupo combinado

1.  Abra el shell de administración de Lync Server 2013.

2.  Escriba lo siguiente en la línea de comandos:
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Por ejemplo:
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>Para comprobar los directorios de conferencia combinados

1.  Abra el shell de administración de Lync Server 2013.

2.  Escriba lo siguiente en la línea de comandos:
    
        Get-CsConferenceDirectory

3.  Compruebe que todos los directorios de conferencia del servidor o grupo de servidores que está combinando estén ahora en Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

