---
title: Lync Server 2013 compatibilidad con la conectividad de mensajería instantánea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c89cc911411095034385f7b8ebbe01edddcd20c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>Compatibilidad con la conectividad de mensajería instantánea pública

Este artículo proporciona información acerca de la compatibilidad con la conectividad de mensajería instantánea pública (PIC). PIC es una característica de Microsoft Lync que permite a las organizaciones permitir que sus usuarios de Lync se conecten con los usuarios de determinados servicios de mensajería instantánea (mi) públicos a través de sus clientes e identidades de Lync.

Los usuarios finales se benefician de poder comunicarse con los clientes, socios y proveedores según sus condiciones. Aprovecha la compatibilidad de un solo cliente de comunicaciones en tiempo real y mantiene las características de control, cumplimiento y archivado de Lync. Lync: conectividad de Skype, [disponible públicamente en mayo de 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), depende de la herencia de que Lync/Office Communications Server (OCS)/Live Communications Server (LCS) se estableció por primera vez con PIC al conectar con MSN/Windows Live, AOL y Yahoo.Para obtener más información sobre la conectividad de Skype en Lync, consulte la [conectividad de Skype en Lync](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx). La Federación con Windows Live, AOL y Yahoo se da en cada uno de los paths hacia el final de la vida.Esta página documenta el estado de cada servicio.

Para usar PIC, los clientes deben activar el servicio para cada proveedor de servicios de mensajería instantánea pública. Los requisitos y detalles para hacerlo dependen del proveedor de servicios de mensajería instantánea y del programa de licencias subyacente al cliente.

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft puso Windows Live Messenger y Skype juntos. En abril de 2013, los usuarios de Messenger se migraron a Skype al iniciar sesión. Los clientes de Lync que confían en la Federación con Messenger seguirán pudiendo comunicarse con sus contactos de Messenger, incluso después de que esos contactos se actualicen a Skype. No hay nada que los administradores de Lync o los usuarios finales de Lync tengan que hacer para mantener la continuidad del servicio, y la administración de esta capacidad dentro de Lync sigue siendo la misma que ha sido para las comunicaciones con Messenger. 

Cuando los usuarios de Messenger inician sesión en Skype con sus cuentas de Microsoft (es decir, las mismas credenciales que se usan para Messenger) todos sus contactos de Messenger, incluidos los contactos federados de Lync, les sigue a Skype. Está disponible el uso compartido de presencia y la mensajería instantánea entre Skype y Lync para estos contactos. 

Lync: conectividad de Skype-la adición de contactos, el uso compartido de la presencia, la mensajería instantánea y las llamadas de audio entre usuarios de Lync y Skype, también está disponible para todos los clientes de Lync.

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo\! y AOL Instant Messenger

Federación con Yahoo\! Además, AOL está en camino hacia el fin de la vida de los clientes de Lync (y Office Communications Server). La capacidad de Microsoft para proporcionar estos servicios se ha supeditado al soporte de Yahoo\! y AOL, y los acuerdos subyacentes de estos se liquidan. Para ambos Yahoo\! y AOL, el servicio continuará hasta el 2014 de junio.

  - **Yahoo** : el servicio continuará hasta el 2014 de junio y los clientes continuarán necesitando una licencia con la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL").A partir del 1 de septiembre de 2012, la capa de PIC ya no está disponible para la compra de contratos nuevos o de renovación.Los clientes con licencias compradas antes de esta fecha podrán seguir federando con Yahoo\! hasta el antes de la fecha de cierre del servicio o de la expiración de su licencia.Lea [el anuncio](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) en el blog del equipo de Lync.Los clientes que tienen licencias PIC en acuerdos que extienden el 30 de junio de 2014 recibirán un crédito en proporción a la cantidad de pagos que cubren el período de tiempo posterior al 30 de junio de 2014.

  - **AOL** : el 30 de junio de 2014, el servicio de conectividad de mensajería instantánea ("PIC") de Lync ya no estará disponible.Para limitar la interrupción de los clientes cuando el servicio termina, hemos suspendido el suministro de dominios de clientes adicionales. Hasta el 30 de junio de 2014, los clientes no tienen que hacer nada para continuar brindando comunicaciones federadas con AIM. Más allá de esta fecha (o para aquellos clientes que, mientras tanto, le gustaría aprovisionar dominios adicionales), un servicio de sustitución está disponible directamente desde AOL. Para obtener más información sobre el nuevo servicio de AOL, consulte [establecer la Federación directa con AIM](http://aimenterprise.aol.com/pic.php)  (abre una página nueva en AOL.com).  

</div>

<div>

## <a name="public-im-provider-summary"></a>Resumen de proveedor de mensajería instantánea pública

En la tabla siguiente se proporciona un resumen de los proveedores de servicios de mensajería instantánea pública, las capacidades de Federación con Lync y los requisitos de licencias.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Proveedor de servicios de mensajería instantánea pública</th>
<th>Capacidades federadas</th>
<th>Requisitos de licencias</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>Mensajería instantánea, presencia, audio</p></td>
<td><p>Licencias de acceso de cliente de Lync Server, plan 1/2/3 de Lync Online</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>Mensajería instantánea, presencia, audio y vídeo</p></td>
<td><p>Licencias de acceso de cliente de Lync Server (admitidas siempre que Skype esté en el mercado)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>Mensajería instantánea, presencia</p></td>
<td><p>Licencias de acceso de cliente de Lync Server; compatible hasta el 2014 de junio para clientes existentes.</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>Mensajería instantánea, presencia</p></td>
<td><p>Requiere una licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync adicional ("PIC USL") además de las licencias de acceso de cliente de Lync Server. A partir de la lista de precios de septiembre de 2012, la capa de PIC ya no está disponible para la compra. Los clientes con licencias activas pueden seguir federando a Yahoo! Messenger hasta que el servicio se cierre de la fecha del 30 de junio de 2014.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

