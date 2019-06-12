---
title: Comprobar la información de la topología
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7657bb80d7acb6d48a4027c665fae70e469bb236
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>Comprobar la información de la topología

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

El primer paso para comprobar que la combinación se completó correctamente es ver la información de topología de Office Communications Server 2007 R2 que combinó con Lync Server 2013. En el generador de topologías, el nodo **BackCompatSite** muestra el nombre de dominio completo (FQDN) de cada grupo de servidores de Office Communications Server 2007 R2 y servidor que haya combinado.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>Para ver BackCompatSite en el generador de topología

1.  En el entorno de Office Communications Server 2007 R2, abra la herramienta administrativa de Office Communications Server 2007 R2 y anote los FQDN de los grupos y servidores heredados.

2.  En el entorno de Lync Server 2013, abra Topology Builder y, a continuación, expanda el nodo **BackCompatSite** .

3.  Compruebe que se muestran los FQDN de los grupos de servidores y los servidores que combina.
    
    <div>
    

    > [!NOTE]  
    > No verá ninguna información en <STRONG>BackCompatSite</STRONG> para los roles de servidor que se colocan en un servidor front-end o un servidor Standard Edition. Solo se muestran los roles de servidor necesarios para la interoperabilidad entre Office Communications Server 2007 R2 y Lync Server 2013.

    
    </div>

![Cuadro de diálogo BackCompatSite del generador de topología] (images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Cuadro de diálogo BackCompatSite del generador de topología")

También puede usar el panel de control de Lync Server 2013 para ver la topología combinada. En el panel de control de Lync Server 2013, puede ver cada FQDN del servidor, FQDN del grupo y nombre del sitio de la topología de la combinación. Los servidores combinados tienen un nombre de **sitio** de **BackCompatSite**.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Para ver la topología combinada en el panel de control de Lync Server 2013

1.  Abra el panel de control de Lync Server 2013.

2.  Haga clic en **topología**.

3.  En la pestaña **Estado** , compruebe que los servidores y las agrupaciones que ha combinado aparecen en la columna **sitio** de **BackCompatSite** .

![Panel de control de Lync Server que muestra una topología combinada] (images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Panel de control de Lync Server que muestra una topología combinada")

Para ver más detalles sobre una agrupación combinada, use el cmdlet **Get-CsPool** . Además de la información que está disponible en el generador de topología y el panel de control de Lync Server 2013, este cmdlet muestra los servicios que se ejecutan en el grupo de servidores de Lync Server 2013.

<div>


> [!NOTE]  
> Al publicar la topología después de ejecutar el Asistente de combinación en el generador de topología, los directorios de conferencia se combinan con Lync Server 2013. Los directorios de conferencia se pueden comprobar ejecutando el cmdlet <STRONG>Get-CsConferenceDirectory</STRONG> .



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>Para ver los servicios de un grupo combinado

1.  Abra el shell de administración de Lync Server 2013.

2.  En la línea de comandos, escriba:
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Por ejemplo:
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>Para comprobar los directorios de las conferencias combinados

1.  Abra el shell de administración de Lync Server 2013.

2.  En la línea de comandos, escriba:
    
        Get-CsConferenceDirectory

3.  Compruebe que todos los directorios de conferencia para el grupo de servidores o el servidor que está combinando estén ahora en Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

