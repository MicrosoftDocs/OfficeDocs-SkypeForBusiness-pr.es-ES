---
title: 'Lync Server 2013: información general sobre la recogida de llamadas de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 222d587f7c4972a8aee313d3d66da578cde08960
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a>Información general sobre la recogida de llamadas grupales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-12_

Recogida de llamadas grupales, una nueva característica de las actualizaciones acumulativas de Lync Server 2013: febrero de 2013, permite a los usuarios responder llamadas entrantes a sus colegas desde sus propios teléfonos. Esta nueva característica aumenta la disponibilidad de la línea de un usuario al permitir que otros usuarios respondan a una llamada entrante marcando un número de grupo de atención de llamadas. Cuando se implementa la recogida de llamadas de grupo, se puede reducir significativamente el número de llamadas entrantes que se redirigen a correo de voz, lo que es especialmente útil para las llamadas de clientes externos a la organización.

La característica de atención de llamadas grupales se ha diseñado en particular para las unidades de negocio en entornos de oficina abiertos. Las llamadas entrantes no son disruptivas porque solo se redirigen al destino previsto. Sin embargo, otros usuarios que escuchan el timbre pueden seguir retomando la llamada simplemente marcando el número de grupo.

En entornos en los que los usuarios no están ubicados en un diseño de oficina abierto o donde los usuarios que comparten una responsabilidad común están distribuidos geográficamente, la llamada de equipo presenta la solución más adecuada. La principal diferencia entre la atención de llamadas de grupo y la llamada de equipo es que, con la atención de llamadas de grupo, una llamada entrante solo suena en el destino deseado, pero cualquiera puede decidir si marca un número de grupo para responderla. Con la llamada de equipo, la llamada suena en todos los teléfonos de los miembros del equipo, y cualquier usuario del equipo puede seleccionar el teléfono para responder a la llamada. Una diferencia adicional entre la atención de llamadas de grupo y la llamada de equipo es que un administrador, a través de Lync Server, administra la recogida de llamadas de grupo. Con la llamada de equipo, los usuarios finales administran la característica mediante el cliente de Lync. Por lo tanto, con la atención de llamadas grupales, este aspecto de la administración de llamadas puede centralizarse.

La recogida de llamadas de grupo está integrada en la aplicación de estacionamiento de llamadas. Cuando se implementa la atención de llamadas grupales, se configura la tabla de órbitas de estacionamiento de llamadas con intervalos separados de números de extensión que se designan como números de grupo de atención de llamadas. Al igual que los números de órbitas de estacionamiento de llamadas, los números de grupo de atención de llamadas deben ser extensiones virtuales que no tengan asignado ningún usuario ni teléfono. Cada grupo de servidores front-end en el que se implementa la recogida de llamadas grupales puede tener uno o más intervalos de números de grupo de atención de llamadas. Los intervalos de números de grupo deben ser únicos en todo el mundo en la implementación de Lync Server.

<div>


> [!NOTE]  
> Los intervalos de números que se designan como números de llamada de grupo en la tabla de órbitas de estacionamiento de llamadas no se pueden administrar ni ver mediante el panel de control de Lync Server. La única forma de ver todos los intervalos de números en la tabla de órbitas del estacionamiento de llamadas es usar el shell de administración de Lync Server. De forma similar, la única forma de agregar, modificar o quitar números de atención de llamadas de grupo es usar el shell de administración de Lync Server.



</div>

Una vez configurados los números de grupo de atención de llamadas, los usuarios se asignan a un grupo de recogida de llamadas. Cualquier usuario que esté asignado a un grupo de recogida de llamadas puede tener respuestas a las llamadas de otros usuarios. Cuando llega una llamada a un usuario asignado a un grupo de atención de llamadas, cualquier otro usuario que note la llamada puede responderla marcando manualmente el número del grupo de recogida de llamadas. No es necesario que el usuario que seleccione la llamada sea miembro del grupo. Cuando otro usuario selecciona una llamada, se envía una notificación al número al que se llamó originalmente.

<div>


> [!NOTE]  
> Un usuario puede ser miembro de un solo grupo de recogida de llamadas.



</div>

<div>


> [!NOTE]  
> Aunque cualquier usuario de la implementación de Lync Server puede responder una llamada a un miembro del grupo de atención de llamadas, la persona que contesta la llamada debe conocer el número de grupo de atención de llamadas correcto para marcar.



</div>

Si un usuario marca un número de grupo de atención de llamadas para responder a una llamada cuando varios teléfonos del grupo están sonando, el usuario responde a la llamada que ha sonado más tiempo.

La configuración de llamadas simultáneas funcionará para los usuarios que tengan llamadas de llamada de grupo. Es decir, una llamada realizada a un usuario que tiene llamada de llamada de grupo sonará para todos los destinos configurados y otro usuario puede responder a la llamada. La excepción a esta regla es cuando el usuario configura la llamada simultánea para llamar a todos los miembros del equipo.

La recopilación de llamadas de grupo no se puede usar para responder a los siguientes tipos de llamadas:

  - Llamadas a una línea privada

  - Llamadas de un contacto al que se le ha asignado la relación de privacidad amigos y familiares
    
    <div>
    

    > [!TIP]  
    > Un usuario que es miembro de un grupo de recogida de llamadas puede evitar que se recuperen determinadas llamadas a través de la llamada de llamada de grupo marcando el contacto como contacto personal en el cliente de Lync. Para marcar un contacto como contacto personal, establezca la relación de privacidad para el contacto en amigos y familiares. Las llamadas entrantes de contactos con la relación de privacidad establecida en amigos y familiares no se pueden recuperar con la atención de llamadas grupales.

    
    </div>

  - Parte de vídeo de las llamadas de audio y vídeo
    
    <div>
    

    > [!NOTE]  
    > Si un usuario responde a una llamada de audio o vídeo, el usuario recibe sólo el audio. La persona que llama o la persona que responde a la llamada puede escalar la llamada para agregar vídeo.

    
    </div>

  - Llamadas simultáneas de llamada que se redirigen a miembros de llamada de equipo

  - Llamadas enrutadas a un delegado

  - Llamadas enrutadas a un grupo de respuesta

Los siguientes tipos de usuarios no pueden participar en la recepción de llamadas grupales. Es decir, no deben incluirse en un grupo de atención de llamadas de grupo y no pueden recoger llamadas para los usuarios que tienen habilitada la recogida de llamadas de grupo.

  - Usuarios hospedados en línea en una implementación híbrida

  - Usuarios que no están hospedados en un grupo de servidores de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: febrero de 2013 en una implementación local

Si nadie responde a una llamada a un miembro de un grupo de atención de llamadas, la llamada se enruta como se especifica en la configuración del cliente. Es decir, la llamada se dirige al correo de voz o se reenvía a otro destino, como se especifica en la configuración del cliente.

</div>

<span> </span>

</div>

</div>

</div>

