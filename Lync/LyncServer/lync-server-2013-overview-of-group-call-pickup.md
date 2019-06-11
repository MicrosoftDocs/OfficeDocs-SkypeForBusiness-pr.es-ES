---
title: 'Lync Server 2013: información general sobre la recogida de llamadas grupales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 132d987b7d8007873a27cd74aacfc11e0c882c39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a>Descripción general de la recogida de llamadas grupales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-12_

Recogida de la llamada grupal, una nueva característica de las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero, permite a los usuarios contestar las llamadas entrantes a sus colegas desde sus propios teléfonos. Esta nueva característica aumenta la disponibilidad de la línea de un usuario al permitir que otros usuarios respondan a una llamada entrante marcando un número de grupo de recogida de llamadas. Cuando se implementa la recogida de llamadas grupales, el número de llamadas entrantes que se dirigen al correo de voz se puede reducir significativamente, lo cual es especialmente útil para llamadas de clientes externos a su organización.

La característica de recogida de llamadas grupales está diseñada especialmente para las unidades de negocio en entornos de Office abiertos. Las llamadas entrantes no resultan molestas porque solo suenan en el destino previsto. Pero los otros usuarios que escuchan el timbre pueden atender la llamada muy fácilmente al marcar el número del grupo.

In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution. La principal diferencia entre la recogida de llamadas Grupals y la llamada de equipo es que, con la recogida de llamadas grupales, las llamadas entrantes solo suenan en el destino previsto, pero cualquier persona puede responderla marcando un número de grupo. With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call. Una diferencia adicional entre la recogida de llamadas Grupals y la llamada de equipo es que un administrador administra a través de Lync Server la recogida de llamadas grupales. Con la llamada de equipo, los usuarios finales administran la característica con el cliente de Lync. Con la recogida de llamadas grupales, este aspecto de la administración de llamadas puede centralizarse.

La recogida de llamadas grupales está integrada en la aplicación de estacionamiento de llamadas. Cuando se implementa la recogida de llamadas grupales, se configura la tabla de llamadas en órbita con distintos intervalos de números de extensión que se designan como números de grupo de recogida de llamadas. Al igual que los números de órbita del estacionamiento de llamadas, los números de grupo de atención de llamadas necesitan ser extensiones virtuales que no tengan asignado ningún usuario o teléfono. Cada grupo de servidores front-end en el que se implementa la recogida de llamadas grupales puede tener uno o más intervalos de números de grupo de recogida de llamadas. Los intervalos de números de grupo deben ser únicos globalmente en la implementación de Lync Server.

<div>


> [!NOTE]  
> Los intervalos de números que se designan como números de recogida de llamadas grupales en la tabla llamada en órbita de la llamada no se pueden administrar ni ver mediante el panel de control de Lync Server. La única forma de ver todos los intervalos de números en la tabla llamada de la órbita de la tabla de la órbita es usar el shell de administración de Lync Server. De forma similar, la única forma de agregar, modificar o quitar números de recogida de llamadas de grupo es usar el shell de administración de Lync Server.



</div>

Una vez configurados los números de grupo de atención de llamadas, necesitas asignar los usuarios a un grupo de atención de llamadas. Las llamadas de un usuario asignado a un grupo de atención de llamadas pueden responderlas otros usuarios. Cuando entra una llamada para un usuario asignado a un grupo de atención de llamadas, cualquier otro usuario que escuche la llamada puede atenderla marcando de forma manual el número del grupo de atención de llamadas. No es necesario que el usuario que atiende la llamada sea miembro del grupo. Cuando otro usuario atiende una llamada, se envía una notificación al número al que se llamó originalmente.

<div>


> [!NOTE]  
> Un usuario solo puede pertenecer a un grupo de atención de llamadas.



</div>

<div>


> [!NOTE]  
> Aunque cualquier usuario de la implementación de Lync Server puede contestar una llamada a un miembro del grupo de recogida de llamadas, la persona que contesta la llamada debe conocer el número de grupo de recogida de llamadas correcto para marcar.



</div>

Si un usuario marca el número de un grupo de atención de llamadas para responder una llamada cuando suenan varios teléfonos del grupo, atenderá la llamada que ha sonado por más tiempo.

La configuración de llamadas simultáneas resulta útil para los usuarios que disponen de la atención de llamadas grupales. Es decir, una llamada realizada a un usuario que tiene la característica de recogida de llamadas de grupo sonará para todos los destinos configurados y otro usuario podrá contestar la llamada. La excepción a esta regla es cuando un usuario configura las llamadas simultáneas para llamar a todos los miembros del grupo.

La recogida de llamada grupal no se puede usar para responder a los siguientes tipos de llamadas:

  - Llamadas a una línea privada

  - Llamadas de un contacto al que se ha asignado la relación de privacidad Amigos y familiares
    
    <div>
    

    > [!TIP]  
    > Un usuario que sea miembro de un grupo de recogida de llamadas puede impedir que se recuperen determinadas llamadas a través de la recogida de llamadas grupales marcando el contacto como contacto personal en el cliente de Lync. Para marcar un contacto como contacto personal, establece la relación de privacidad del contacto en Amigos y familiares. Las llamadas entrantes de contactos con la relación de privacidad establecida a amigos y familiares no se pueden recuperar mediante la recogida de llamadas grupales.

    
    </div>

  - Parte de vídeo de llamadas de audio y vídeo
    
    <div>
    

    > [!NOTE]  
    > Si un usuario responde una llamada de audio y vídeo, solo recibe el audio. La persona que llama o la persona que responde la llamada puede escalarla para agregar vídeo.

    
    </div>

  - Llamadas simultáneas redirigidas a miembros de llamada de equipo

  - Llamadas redirigidas a un delegado

  - Llamadas redirigidas a un grupo de respuesta

Los siguientes tipos de usuarios no pueden participar en la recogida de llamadas grupales. Es decir, no deben incluirse en un grupo de recogida de llamadas Grupals y no pueden atender llamadas de usuarios que tienen habilitada la recogida de llamadas grupales.

  - Usuarios alojados en línea en una implementación híbrida

  - Usuarios que no están alojados en un grupo de servidores de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013:2013 de febrero en una implementación local

Si nadie atiende una llamada realizada a un miembro de un grupo de atención de llamadas, la llamada se redirige según lo especificado en la configuración del cliente. Es decir, la llamada se desvía al correo de voz o se reenvía a otro destino, tal como se especifique en la configuración del cliente.

</div>

<span> </span>

</div>

</div>

</div>

