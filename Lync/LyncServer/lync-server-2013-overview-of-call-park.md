---
title: 'Lync Server 2013: información general sobre la llamada en estacionamiento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5deeff873b37c0056bf03c598c39e448cba4379
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Información general sobre el parque de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

La aplicación de Parque de llamadas de Lync Server 2013 permite a los usuarios de Enterprise Voice realizar cualquiera de las siguientes acciones:

  - Poner una llamada en espera y recuperar la llamada desde el mismo teléfono o desde otro.

  - Poner una llamada en espera para transferirla a un departamento o área general, por ejemplo, a un departamento de ventas o a un almacén donde hay un teléfono de área común.

  - Poner una llamada en espera y conservar el teléfono original que ha respondido disponible para recibir otras llamadas.

Cuando un usuario detiene una llamada, Lync Server transfiere la llamada a un número temporal, denominado *órbita*, en el que se mantiene la llamada hasta que se recupera o se agota el tiempo de espera. Lync Server envía la órbita al usuario que detuvo la llamada. Para recuperar la llamada estacionada, el usuario puede marcar el número de órbita o hacer clic en el botón o vínculo de órbita de la ventana Conversación.

El usuario que estacionó una llamada puede notificar a alguien que recupere la llamada usando un mecanismo externo, como la mensajería instantánea (MI) o un sistema de localización, para comunicar el número de órbita a otro usuario. El usuario que estacionó la llamada puede dejar la ventana Conversación abierta para recibir una notificación cuando se recupere la llamada.

Dado que los intervalos de órbita son únicos globalmente, es posible recuperar las llamadas de cualquier sitio de Lync Server o de un teléfono PBX si el enrutamiento está configurado correctamente. Si nadie recupera la llamada en un período de tiempo configurable, la llamada volverá a sonar para la persona que la estacionó. Si dicha persona no responde esta vez, la llamada se transferirá a un destino de conmutación por error, como un operador, si se ha configurado así. Puedes configurar el número de veces que deseas que suene la llamada antes de ser transferida de una a diez veces. Si nadie responde a una llamada transferida, la llamada se desconectará. La órbita se libera cuando se recupera la llamada o se desconecta.

Al implementar el estacionamiento de llamadas, necesitarás reservar intervalos de números de extensión para estacionar llamadas. Estas extensiones necesitan ser extensiones virtuales: extensiones que no tienen ningún usuario o teléfono asignado. Luego, necesitarás configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión y especificar qué servicio de aplicaciones hospeda la aplicación Estacionamiento de llamadas que administra cada intervalo. Cada grupo de servidores front-end tiene una tabla de estacionamiento de llamadas en el servidor back end correspondiente que se usa para administrar las llamadas que se aparcarán en el grupo. La lista de intervalos de órbita se almacena en el almacén de administración central y se usa para enrutar órbitas hasta el grupo de destino. Cada grupo de Lync Server en el que se implementa y configura la aplicación de estacionamiento de llamadas puede tener uno o más intervalos Orbitantes. Los intervalos de órbita deben ser únicos globalmente en la implementación de Lync Server.

También configuras otras opciones de estacionamiento de llamadas, como, por ejemplo, el lugar al que se redirigirán las llamadas si transcurre el tiempo de espera y si la persona que está al teléfono oirá música mientras la llamada está estacionada. Asimismo, puedes especificar el archivo de música que deseas que se reproduzca mientras la llamada está en espera.

<div>


> [!NOTE]  
> No se realiza una copia de seguridad de los archivos de música personalizada que se encuentran en espera para el servicio de recuperación de desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, dañados o borrados. Guarda siempre una copia de seguridad independiente de los archivos de música en espera personalizados que haya cargado para el estacionamiento de llamadas.



</div>

La aplicación Estacionamiento de llamadas es un componente de la telefonía IP empresarial. Al implementar la telefonía IP empresarial, la aplicación de estacionamiento de llamadas se instala y activa automáticamente. Sin embargo, antes de poder usar el parque de llamadas, el administrador de telefonía IP debe configurarlo y habilitarlo para los usuarios mediante la Directiva de voz.

</div>

<span> </span>

</div>

</div>

</div>

