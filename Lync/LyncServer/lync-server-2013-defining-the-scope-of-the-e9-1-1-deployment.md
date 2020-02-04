---
title: 'Lync Server 2013: definir el ámbito de la implementación de E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96f5ac1fb747a3e64be6cc84c44b390de8ce821c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

Antes de configurar Microsoft Lync Server 2013 para E9-1-1, necesita planear la implementación de E9-1-1. Algunas de las cuestiones que necesitas tener en cuenta son:

  - **¿Cuáles son las obligaciones legales y la directiva de su organización con respecto a E9-1-1?**  
    Los requisitos legales de E9-1-1 para sistemas PBX (llamados sistemas telefónicos de varias líneas o MLTS, en la terminología de E9-1-1) difieren de un estado a otro. Debe consultar a su equipo legal para comprender las obligaciones que se pueden aplicar a su implementación de Lync Server en las geografías relevantes.

<!-- end list -->

  - **¿Qué áreas de la empresa necesitan habilitarse para E9-1-1?**  
    Puedes habilitar E9-1-1 para determinadas ubicaciones o para toda la empresa. Por ejemplo, puedes tener distintos requisitos de E9-1-1 para oficinas en diferentes estados o quizás desee excluir sitios fuera de EE. UU.

<!-- end list -->

  - **¿Cómo implementará E9-1-1 en las sucursales?**  
    La resistencia de voz es un concepto que es importante tener en cuenta al implementar E9-1-1 en un sitio de sucursal. Si tienes troncos de E-9-1-1 SIP centralizados y se produce una interrupción de la WAN, es posible que los clientes que inicien sesión no puedan obtener una ubicación del servicio de información de ubicación o para conectar con el proveedor de servicios de servicios de emergencias. Lync Server proporciona varias estrategias para manejar la resistencia de voz en sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o presionar llamadas de emergencia a la puerta de enlace local durante las interrupciones. Para obtener más información, vea [planeamiento de la resistencia de voz de un sitio de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **¿Se habilitará E9-1-1 para los usuarios que trabajan fuera de la red?**  
    La adquisición de ubicación automática solo está disponible para los clientes que se encuentran dentro de la red de la organización, por lo que su organización debe decidir si será compatible con las llamadas de E9 de Lync realizadas desde los clientes de Lync cuando no estén locales. Por ejemplo, ¿permitirás a los usuarios realizar llamadas de emergencia si trabajan desde casa o desde un sitio del cliente? Si un cliente se encuentra fuera de la red empresarial, puede configurarse para solicitar al usuario una ubicación. Pero como estas ubicaciones proporcionadas por el usuario no pueden validarse previamente con la Guía de calles maestra (MSAG), el distribuidor del proveedor de servicios de emergencia tendrá que confirmar la validez de la ubicación verbalmente con el autor de la llamada antes de redirigir la llamada al punto de respuesta de seguridad pública (PSAP).
    
    <div>
    

    > [!NOTE]  
    > Los clientes de Lync que se conectan a la red de la organización mediante VPN pueden recopilar información sobre la dirección IP interna, pero como estas direcciones no se pueden usar para identificar la ubicación real del usuario, es esencial que las subredes VPN se excluyan de la Servicio de información de ubicación.

    
    </div>

<!-- end list -->

  - **¿Desea proporcionar el enrutamiento de llamadas de emergencia a sitios de fuera de Estados Unidos?**  
    Puede que quieras proporcionar el enrutamiento de emergencia en áreas de la compañía donde no sirve el proveedor de servicios de emergencia (por ejemplo, en ubicaciones internacionales). Para ello, crea un sitio y luego asigna directivas de voz a los sitios que hagan referencia a un uso de RTC que redirige la llamada a través de la puerta de enlace RTC local.

</div>

<span> </span>

</div>

</div>

</div>

