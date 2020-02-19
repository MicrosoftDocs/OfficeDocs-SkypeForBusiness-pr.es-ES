---
title: 'Lync Server 2013: lista de comprobación para la implementación del control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e5250bf82353876e36109a6b2e34442e5ef7dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Lista de comprobación para la implementación del control de admisión de llamadas para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Use la lista de comprobación proporcionada a continuación para comprobar si ha completado todas las tareas de configuración necesarias para implementar el control de admisión de llamadas.

  - Si implementa uno o más servidores perimetrales, debe agregar cada dirección IP de interfaz externa a la lista de subredes de los parámetros de configuración de red, con una máscara de bits de 32. También debe asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.
    
    <div>
    

    > [!NOTE]  
    > Los servidores perimetrales no son necesarios para implementar CAC.

    
    </div>

  - Asegúrese de que el CAC esté habilitado, ya sea a través del panel de control de Lync Server o mediante la ejecución del cmdlet como se especifica en [Habilitar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales. Esto puede realizarse a través del generador de topologías. Si aparece una advertencia durante la publicación, *no* la ignore.

  - Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red. También es esencial que cada subred esté asociada a un sitio de red, tal como se explica en [Associate a subnet with a Network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.

</div>

<span> </span>

</div>

</div>

</div>

