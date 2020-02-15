---
title: Información general sobre las conferencias de acceso telefónico local de Lync Server 2013
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
ms.openlocfilehash: 71d6717f183066688fdf94d0fc83e0e662c9a6b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Información general sobre las conferencias de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Si su organización tiene usuarios que necesitan asistir a conferencias locales de Lync Server 2013 cuando están fuera de la oficina o no tienen acceso a un equipo, puede implementar la Conferencia de acceso telefónico local para que puedan unirse a la Conferencia mediante un teléfono conmutado público. teléfono de red (RTC).

La Conferencia de acceso telefónico local es una característica opcional que puede configurar al implementar la Conferencia de Lync Server 2013. Aunque la Conferencia de acceso telefónico local usa algunos de los mismos componentes de Lync Server 2013 que usa la telefonía IP empresarial, puede implementar la Conferencia de acceso telefónico local aunque no implemente la telefonía IP empresarial.

<div>


> [!NOTE]  
> Si implementa la Conferencia de acceso telefónico local, debe implementarla en todos los grupos de servidores en los que implemente Lync Server 2013 conferencias. No es necesario que asigne números de acceso en cada uno de los grupos de servidores, pero deberá implementar la característica de acceso telefónico local en todos ellos. Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso de un grupo de servidores para unirse a una conferencia de 2013 de Lync Server en un grupo de servidores diferente.



</div>

Las conferencias deben estar habilitadas para el acceso telefónico local en la directiva de reunión. De forma predeterminada, las conferencias habilitadas para el acceso telefónico local incluyen la siguiente información en la invitación a la conferencia:

  - Un identificador de conferencia numérico que identifica la conferencia.

  - Uno o más números de acceso de RTC.

  - Un vínculo a una página de configuración de conferencia de acceso telefónico local, que contiene una lista completa de números de acceso con sus idiomas asociados; un espacio para crear, restablecer o desbloquear números de identificación personal (PIN); y otra información, como controles de tono de marcado de frecuencia múltiple (DTMF).

Las conferencias de acceso telefónico local admiten tanto a usuarios de empresa como a usuarios anónimos. Los usuarios empresariales tienen credenciales de servicios de dominio de Active Directory y cuentas de Lync Server 2013 dentro de su organización. Los usuarios anónimos no tienen credenciales de empresa en la organización. En el contexto de una conferencia de acceso telefónico local, un usuario de una organización asociada federada que usa la RTC para conectarse a una conferencia se considera usuario anónimo. A diferencia de lo que ocurre en otros contextos, los usuarios federados no se autentican para la conferencia de acceso telefónico local.

Los usuarios de empresa o coordinadores de la conferencia que se unen a una conferencia habilitada para el acceso telefónico local marcan uno de los números de acceso a la conferencia y, a continuación, se les pide que escriban el identificador de la conferencia. Si todavía no se ha unido a la reunión ningún coordinador, los usuarios pueden escribir su extensión (o número de teléfono completo) de comunicaciones unificadas (UC) y el PIN, o bien esperar a que un coordinador les admita. El organizador de la reunión puede unirse a la reunión como coordinador escribiendo solo el PIN. El servidor front-end usa la combinación de número de teléfono completo o extensión, y PIN, para asignar exclusivamente a los usuarios de la empresa a sus credenciales de Active Directory. Como resultado, los usuarios de empresa se pueden autenticar e identificar por su nombre en la conferencia. Los usuarios de empresa también pueden asumir un rol de conferencia definido previamente por el organizador.

<div>


> [!NOTE]  
> Los usuarios empresariales que llaman desde un teléfono IP de Office o desde un operador de Lync Server 2013 o Lync 2010 no reciben su número de teléfono debido a que ya se han autenticado.



</div>

Los usuarios anónimos que deseen unirse a una conferencia de acceso telefónico local, deben marcar uno de los números de acceso a la conferencia y, a continuación, se les pedirá que escriban el identificador de la conferencia. A los usuarios anónimos sin autenticar también se les pide que registren su nombre. El nombre grabado identifica a los usuarios sin autenticar en la conferencia. No se admiten usuarios anónimos en la conferencia hasta que se haya unido a ella al menos un coordinador o un usuario autenticado, y no se les puede asignar un rol definido previamente.

<div>


> [!NOTE]  
> Los usuarios de empresa que elijan no escribir su número de teléfono y su PIN no se autenticarán. Se les pedirá que registren su nombre y se les considerará usuarios anónimos en la conferencia.



</div>

A la hora programada, el organizador de la reunión puede restringir el acceso a la reunión bloqueándola o cerrándola. En este caso, se solicitará a los usuarios de acceso telefónico local que se autentiquen. Si prefieren no autenticarse o no lo hacen correctamente, se les transferirá a la sala de espera, donde esperarán hasta que el coordinador acepte o rechace su entrada, o bien hasta que se agote el tiempo de espera y sean desconectados. Los usuarios de acceso telefónico local escucharán música mientras esperan su admisión a la conferencia. Una vez admitidos en una conferencia, los usuarios de acceso telefónico local pueden participar en la parte de audio de la conferencia y usar los comandos de tono de marcado de frecuencia múltiple (DTMF) con las teclas del teléfono. Los coordinadores de acceso telefónico pueden usar comandos DTMF para activar o desactivar el audio de los participantes, bloquear o desbloquear la conferencia, admitir a personas de la sala de espera y activar o desactivar los anuncios de entrada y salida. Los coordinadores también pueden usar un comando DTMF para admitir a todas las personas de la sala de espera, lo que modifica los permisos de la reunión para habilitar a todos los que se unan más tarde. Todos los participantes de acceso telefónico pueden usar comandos DTMF para escuchar la Ayuda, escuchar la lista de conferencias y silenciarse.

Los participantes de acceso telefónico (es decir, los participantes que accedan o no desde el RTC) oirán anuncios personales durante la conferencia, como si han sido silenciados o se les ha dado la voz, si la reunión está siendo grabada o si hay alguien esperando en la sala de espera.

<div>


> [!NOTE]  
> Los participantes que se unan a la conferencia haciendo clic en un vínculo, en lugar de acceder mediante el marcado telefónico, no oirán anuncios personales.



</div>

</div>

<span> </span>

</div>

</div>

</div>

