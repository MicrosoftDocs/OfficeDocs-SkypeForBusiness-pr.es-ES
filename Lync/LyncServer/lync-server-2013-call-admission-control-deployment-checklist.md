---
title: 'Lync Server 2013: lista de comprobación de la implementación de control de admisión'
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
ms.openlocfilehash: e768cdd11d92b3aab5ce849f91cc1a422f119407
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Lista de comprobación de la implementación de control de admisión para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Use la siguiente lista de comprobación para comprobar que ha completado todas las tareas de configuración necesarias para implementar el control de admisión de llamadas (CAC).

  - Si se implementan uno o varios servidores perimetrales, cada dirección IP de la interfaz externa debe agregarse a la lista de subred en la configuración de red, con una máscara de bits de 32. También tiene que asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.
    
    <div>
    

    > [!NOTE]  
    > No es necesario que los servidores perimetrales implementen CAC.

    
    </div>

  - Asegúrese de que CAC está habilitado, ya sea mediante el panel de control de Lync Server o mediante la ejecución del cmdlet especificado en [Habilitar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales. Esto se puede hacer a través del generador de topología. Si aparece una advertencia durante la publicación, *no* la ignore.

  - Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red. También es esencial que cada subred esté asociada a un sitio de red, como se explica en [asociar una subred con un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.

</div>

<span> </span>

</div>

</div>

</div>

