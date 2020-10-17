---
title: 'Lync Server 2013: información general sobre el estacionamiento de llamadas'
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
ms.openlocfilehash: 22811a0c55f0e0c7a7bfb7f3aeeb3ab5fcbc2653
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530677"
---
# <a name="overview-of-call-park-in-lync-server-2013"></a>Información general sobre el estacionamiento de llamadas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

La aplicación de estacionamiento de llamadas de Lync Server 2013 permite que los usuarios de Enterprise Voice hagan lo siguiente:

  - Poner una llamada en espera y recuperar la llamada desde el mismo teléfono o desde otro.

  - Poner una llamada en espera para transferirla a un departamento o área general, por ejemplo, a un departamento de ventas o a un almacén donde hay un teléfono de área común.

  - Poner una llamada en espera y conservar el teléfono original que ha respondido disponible para recibir otras llamadas.

Cuando un usuario detiene una llamada, Lync Server transfiere la llamada a un número temporal, denominado *órbita*, donde la llamada se mantiene hasta que se recupera o se agota el tiempo de espera. Lync Server envía la órbita al usuario que ha estacionado la llamada. Para recuperar la llamada estacionada, el usuario puede marcar el número de órbita o hacer clic en el botón o vínculo de órbita de la ventana Conversación.

El usuario que estacionó una llamada puede notificar a alguien que recupere la llamada usando un mecanismo externo, como la mensajería instantánea (MI) o un sistema de paginación, para comunicar el número de órbita a otro usuario. El usuario que estacionó la llamada puede dejar la ventana Conversación abierta para recibir una notificación cuando se recupere la llamada.

Debido a que los intervalos de órbita son únicos globalmente, es posible recuperar las llamadas de cualquier teléfono PBX o sitio de Lync Server si el enrutamiento está configurado correctamente. Si nadie recupera la llamada en un período de tiempo configurable, la llamada volverá a sonar para la persona que la estacionó. Si dicha persona no responde esta vez, la llamada se transferirá a un destino de conmutación por error, como un operador, si se ha configurado así. Puede configurar el número de veces que desea que suene la llamada antes de ser transferida de una a diez veces. Si nadie responde a una llamada transferida, la llamada se desconectará. La órbita se libera cuando se recupera la llamada o se desconecta.

Al implementar Estacionamiento de llamadas, deberá reservar intervalos de números de extensión (órbitas) para estacionar llamadas. Estas extensiones deben ser extensiones virtuales: extensiones que no tienen ningún usuario o teléfono asignado. A continuación, deberá configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión y especificar qué servicio de aplicaciones hospeda la aplicación Estacionamiento de llamadas que administra cada intervalo. Cada grupo de servidores front-end dispone de una tabla de estacionamiento de llamadas en el servidor back-end correspondiente que se usa para administrar las llamadas que se estacionan en el grupo de servidores. La lista de intervalos de órbitas se almacena en el almacén de administración central y se usa para redirigir órbitas al grupo de servidores de destino. Cada grupo de Lync Server en el que se implementa y configura la aplicación de estacionamiento de llamadas puede tener uno o más intervalos de órbitas. Los intervalos de órbitas deben ser únicos en todo el mundo en la implementación de Lync Server.

También configura otras opciones de Estacionamiento de llamadas, como, por ejemplo, el lugar al que se redirigirán las llamadas si transcurre el tiempo de espera y si la persona que está al teléfono oirá música mientras la llamada está estacionada. Asimismo, puede especificar el archivo de música que desea que se reproduzca mientras la llamada está en espera.

<div>


> [!NOTE]  
> No se realiza una copia de seguridad de los archivos de música en espera personalizados para el estacionamiento de llamadas como parte del proceso de recuperación ante desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, dañados o borrados. Guarde siempre una copia de seguridad independiente de los archivos de música en espera que haya cargado para Estacionamiento de llamadas.



</div>

La aplicación Estacionamiento de llamadas es un componente de Enterprise Voice. Al implementar Enterprise Voice, la aplicación Estacionamiento de llamadas se instalará y activará de forma automática. Sin embargo, para poder usar el estacionamiento de llamadas, el administrador de Enterprise Voice deberá configurarlo y habilitarlo para los usuarios mediante una directiva de voz.

</div>

<span> </span>

</div>

</div>

</div>

