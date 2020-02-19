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
ms.openlocfilehash: c84c6519ab561fef034fbe0990854087f22b2e41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

Antes de configurar Microsoft Lync Server 2013 para E9-1-1, debe planear la implementación de E9-1-1. Algunas de las preguntas que se deben tener en cuenta son:

  - **¿Cuáles son las obligaciones legales y la Directiva de su organización con respecto a E9-1-1?**  
    Los requisitos legales de E9-1-1 para PBX (llamados sistemas telefónicos de varias líneas o MLTS, en lenguaje E9-1-1) difieren de un estado a un estado. Debe consultar a su equipo jurídico para conocer las obligaciones que se pueden aplicar a su implementación de Lync Server en las ubicaciones geográficas pertinentes.

<!-- end list -->

  - **¿Qué áreas de la empresa deben estar habilitadas para E9-1-1?**  
    Puede habilitar E9-1-1 para toda la empresa o para ubicaciones seleccionadas. Por ejemplo, puede que tenga que variar E9-1-1 requisitos para oficinas en diferentes Estados o puede que desee excluir sitios de fuera de Estados Unidos.

<!-- end list -->

  - **¿Cómo implementará E9-1-1 en los sitios de sucursal?**  
    La resistencia de voz es un concepto importante que debe comprender al implementar E9-1-1 en un sitio de sucursal. Si tiene troncos E-9-1-1 SIP centralizados y se produce una interrupción de la WAN, es posible que los clientes que inicien sesión no puedan obtener una ubicación del servicio de información de ubicaciones o para conectarse al proveedor de servicios de emergencias. Lync Server ofrece varias estrategias para controlar la resistencia de voz en las sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o presionar llamadas de emergencia a la puerta de enlace local durante las interrupciones. Para obtener más información, consulte [Planning for Branch-site Voice Resiliency en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **¿Se habilitará E9-1-1 para los usuarios que trabajan fuera de la red?**  
    La adquisición de ubicación automática solo está disponible para los clientes que se encuentran dentro de la red de la organización, por lo que su organización debe decidir si será compatible con las llamadas de E9-1-1 realizadas desde los clientes de Lync mientras se encuentran fuera del entorno. Por ejemplo, ¿permitirá que los usuarios realicen llamadas de emergencia si están trabajando desde casa o desde un sitio del cliente? Si un cliente se encuentra fuera de la red de la empresa, se puede configurar el cliente para que solicite una ubicación al usuario. Sin embargo, debido a que estas ubicaciones proporcionadas por el usuario no se pueden prevalidar con respecto a la guía de dirección principal (MSAG), el distribuidor de proveedores de servicios de emergencias deberá confirmar la validez de la ubicación verbalmente con la persona que realiza la llamada antes de la distribución la llamada al punto de respuesta de seguridad pública (PSAP).
    
    <div>
    

    > [!NOTE]  
    > Los clientes de Lync de los usuarios que se conectan a la red de su organización mediante VPN pueden recoger la información de dirección IP interna, pero debido a que estas direcciones no se pueden usar para identificar la ubicación real del usuario, es esencial que las subredes VPN se excluyan del Servicio de información de ubicación.

    
    </div>

<!-- end list -->

  - **¿Desea proporcionar el enrutamiento de llamadas de emergencia a sitios fuera de Estados Unidos?**  
    Es posible que desee proporcionar enrutamiento de emergencia a áreas de su compañía que no atienda un proveedor de servicios de emergencia (por ejemplo, ubicaciones internacionales). Para ello, cree un nuevo sitio y, a continuación, asigne directivas de voz a los sitios que hacen referencia a un uso de RTC que enruta la llamada a través de la puerta de enlace RTC local.

</div>

<span> </span>

</div>

</div>

</div>

