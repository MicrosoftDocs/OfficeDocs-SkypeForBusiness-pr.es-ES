---
title: Introducción a las conferencias de acceso telefónico local de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a126e7e1ee61f48ff8857553b7677abf813a25e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Información general sobre las conferencias de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Si su organización tiene usuarios que necesitan asistir a conferencias locales de Lync Server 2013 cuando están fuera de la oficina o no tienen acceso a un equipo, puede implementar la Conferencia de acceso telefónico local para que puedan unirse a la Conferencia mediante un teléfono público con conmutación teléfono de red (RTC).

Las conferencias de acceso telefónico local son una característica opcional que puede configurar al implementar conferencias de 2013 de Lync Server. Aunque las conferencias de acceso telefónico local usan algunos de los mismos componentes de Lync Server 2013 que usa Enterprise Voice, puede implementar la Conferencia de acceso telefónico local incluso si no implementa la telefonía IP empresarial.

<div>


> [!NOTE]  
> Si implementa una conferencia de acceso telefónico local, debe implementarla en todos los grupos donde implementará la Conferencia de 2013 de Lync Server. No es necesario asignar números de acceso en todos los grupos, pero debe implementar la característica de acceso telefónico en cada grupo. Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso desde un grupo para unirse a una conferencia de 2013 de Lync Server en un grupo diferente.



</div>

Las conferencias deben estar habilitadas para el acceso telefónico en la Directiva de reunión. De forma predeterminada, las conferencias habilitadas para el acceso telefónico local incluyen la siguiente información en la invitación a la conferencia:

  - Un identificador numérico de conferencia que identifica la Conferencia.

  - Uno o más números de acceso de la RTC.

  - Un vínculo a una página de configuración de conferencias de acceso telefónico local, que contiene una lista completa de números de acceso con sus idiomas asociados; un lugar para crear, restablecer o desbloquear números de identificación personal (PIN); y otra información, como controles de multifrecuencia de tono dual (DTMF).

Las conferencias de acceso telefónico local admiten tanto a usuarios de empresa como a usuarios anónimos. Los usuarios empresariales tienen credenciales de servicios de dominio de Active Directory y cuentas de Lync Server 2013 dentro de su organización. Los usuarios anónimos no tienen credenciales de empresa en la organización. En el contexto de una conferencia de acceso telefónico local, un usuario de una organización asociada externa que usa la RTC para conectarse a una conferencia se considera usuario anónimo. A diferencia de lo que ocurre en otros contextos, los usuarios federados no se autentican para la conferencia de acceso telefónico local.

Los usuarios de empresa o coordinadores de la conferencia que se unen a una conferencia habilitada para el acceso telefónico local, marcan uno de los números de acceso a la conferencia y, luego, se les pide que escriban el identificador de la conferencia. Si todavía no se ha unido a la reunión ningún coordinador, los usuarios pueden escribir su extensión (o número de teléfono completo) de comunicaciones unificadas (UC) y el PIN, o bien esperar a que un coordinador les admita. El organizador de la reunión puede unirse a la reunión como coordinador escribiendo solo el PIN. El servidor front-end usa la combinación de la extensión o número de teléfono completo y el PIN para asignar únicamente usuarios de empresa a sus credenciales de Active Directory. Como resultado, los usuarios de empresa se pueden autenticar e identificar por su nombre en la conferencia. Los usuarios de empresa también pueden asumir un rol de conferencia definido previamente por el organizador.

<div>


> [!NOTE]  
> Los usuarios de la empresa que llamen desde un teléfono de Office IP o desde el operador de Lync Server 2013 o de Lync 2010 no se les pedirá su número de teléfono porque ya están autenticados.



</div>

Los usuarios anónimos que deseen unirse a una conferencia de acceso telefónico local, necesitan marcar uno de los números de acceso a la conferencia y, luego, se les pedirá que escriban el identificador de la conferencia. A los usuarios anónimos sin autenticar también se les pide que registren su nombre. El nombre grabado identifica a los usuarios sin autenticar en la conferencia. No se admiten usuarios anónimos en la conferencia hasta que se haya unido a ella al menos un coordinador o un usuario autenticado, y no se les puede asignar un rol definido previamente.

<div>


> [!NOTE]  
> Los usuarios de empresa que elijan no escribir su número de teléfono y su PIN no se autenticarán. Se les pedirá que registren su nombre y se les considerará usuarios anónimos en la conferencia.



</div>

En el momento de la programación, el organizador de la reunión puede elegir restringir el acceso a la reunión haciendo que la reunión se cierre o se bloquee. En este caso, se solicitará a los usuarios de acceso telefónico local que se autentiquen. Si los usuarios de acceso telefónico no tienen éxito o elige no autenticar, se transfieren a la sala de recepción. Esperan en la sala de espera hasta que un líder los acepta o rechaza, o el tiempo de espera y se desconectan. Los usuarios de acceso telefónico escuchan música si están esperando ser admitidos en la Conferencia. Una vez admitidos en una conferencia, los usuarios de acceso telefónico local pueden participar en la parte de audio de la conferencia y usar los comandos de tono de marcado de frecuencia múltiple (DTMF) por medio de las teclas del teléfono. Los coordinadores de acceso telefónico pueden usar comandos DTMF para activar o desactivar el audio de los participantes, bloquear o desbloquear la conferencia, admitir a personas de la sala de espera y activar o desactivar los anuncios de entrada y salida. Los coordinadores también pueden usar un comando DTMF para admitir a todas las personas de la sala de espera, lo que modifica los permisos de la reunión para habilitar a todos los que se unan más tarde. Todos los participantes de acceso telefónico pueden usar comandos DTMF para escuchar la Ayuda, escuchar la lista de conferencias y silenciarse.

Los participantes de acceso telefónico (es decir, si llaman o no desde la RTC) escuchan anuncios personales durante la Conferencia, por ejemplo, si se han silenciado o reactivado, si la reunión se está grabando o si alguien está en espera en la sala de espera.

<div>


> [!NOTE]  
> Los participantes que se unan a la conferencia haciendo clic en un vínculo, en lugar de acceder por medio del marcado telefónico, no oirán anuncios personales.



</div>

</div>

<span> </span>

</div>

</div>

</div>

