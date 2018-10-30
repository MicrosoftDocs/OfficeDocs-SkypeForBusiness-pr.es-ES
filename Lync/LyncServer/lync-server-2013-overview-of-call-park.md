---
title: 'Lync Server 2013: Información general del estacionamiento de llamadas'
TOCTitle: Información general del estacionamiento de llamadas
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48276118
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general del estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-29_

Aplicación de estacionamiento de llamadas de Lync Server 2013 permite a los usuarios de Enterprise Voice hace cualquiera de las siguientes tareas:

  - Poner una llamada en espera y recuperar la llamada desde el mismo teléfono o desde otro.

  - Poner una llamada en espera para transferirla a un departamento o área general, por ejemplo, a un departamento de ventas o a un almacén donde hay un teléfono de área común.

  - Poner una llamada en espera y conservar el teléfono original que ha respondido disponible para recibir otras llamadas.

Cuando un usuario estaciona una llamada, Lync Server transfiere la llamada a un número temporal, denominado *órbita* , donde se retiene la llamada hasta que se recupera o transcurre el tiempo de espera. Lync Server envía la órbita al usuario que ha estacionado la llamada. Para recuperar la llamada estacionada, el usuario puede marcar el número de órbita o hacer clic en el botón o vínculo de órbita de la ventana Conversación.

El usuario que estacionó una llamada puede notificar a alguien que recupere la llamada usando un mecanismo externo, como la mensajería instantánea (MI) o un sistema de paginación, para comunicar el número de órbita a otro usuario. El usuario que estacionó la llamada puede dejar la ventana Conversación abierta para recibir una notificación cuando se recupere la llamada.

Como los intervalos de órbita son únicos a nivel global, es posible recuperar llamadas desde cualquier teléfono PBX o sitio de Lync Server si el enrutamiento se ha configurado correctamente. Si nadie recupera la llamada en un período de tiempo configurable, la llamada volverá a sonar para la persona que la estacionó. Si dicha persona no responde esta vez, la llamada se transferirá a un destino de conmutación por error, como un operador, si se ha configurado así. Puede configurar el número de veces que desea que suene la llamada antes de ser transferida de una a diez veces. Si nadie responde a una llamada transferida, la llamada se desconectará. La órbita se libera cuando se recupera la llamada o se desconecta.

Al implementar Estacionamiento de llamadas, deberá reservar intervalos de números de extensión (órbitas) para estacionar llamadas. Estas extensiones deben ser extensiones virtuales: extensiones que no tienen ningún usuario o teléfono asignado. A continuación, deberá configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión y especificar qué servicio de aplicaciones hospeda la aplicación Estacionamiento de llamadas que administra cada intervalo. Cada grupo de servidores front-end dispone de una tabla de estacionamiento de llamadas en el servidor back-end correspondiente que se usa para administrar las llamadas que se estacionan en el grupo de servidores. La lista de intervalos de órbitas se almacena en Almacén de administración central y se usa para enrutar órbitas al grupo de servidores de destino. Cada grupo de servidores de Lync Server donde se implemente y se configure la aplicación Estacionamiento de llamadas puede tener uno o más intervalos de órbitas. Los intervalos de órbitas deben ser únicos a nivel global en toda la implementación de Lync Server.

También configura otras opciones de Estacionamiento de llamadas, como, por ejemplo, el lugar al que se redirigirán las llamadas si transcurre el tiempo de espera y si la persona que está al teléfono oirá música mientras la llamada está estacionada. Asimismo, puede especificar el archivo de música que desea que se reproduzca mientras la llamada está en espera.


> [!NOTE]
> Los archivos de música en espera personalizados para Estacionamiento de llamadas no se incluyen en la copia de seguridad como parte del proceso de recuperación ante desastres de Lync Server 2013 y se perderán si los archivos que se carguen en el grupo resultan dañados o se borran. Guarde siempre una copia de seguridad independiente de los archivos de música en espera que haya cargado para Estacionamiento de llamadas.



La aplicación Estacionamiento de llamadas es un componente de Enterprise Voice. Al implementar Enterprise Voice, la aplicación Estacionamiento de llamadas se instalará y activará de forma automática. Sin embargo, para poder usar el estacionamiento de llamadas, el administrador de Enterprise Voice deberá configurarlo y habilitarlo para los usuarios mediante una directiva de voz.

