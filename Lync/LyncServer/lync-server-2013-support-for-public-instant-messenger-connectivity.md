---
title: Lync Server 2013 soporte para conectividad de mensajería instantánea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c6f21e6a58b9130ab93f827f14aad4bd09cbb33
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>Compatibilidad con la conectividad de mensajería instantánea pública

En este artículo se proporciona información acerca de la compatibilidad con la conectividad de mensajería instantánea pública (PIC). PIC es una característica de Microsoft Lync que permite a las organizaciones habilitar a sus usuarios de Lync para que se conecten con los usuarios de determinados servicios de mensajería instantánea (mi) pública a través de sus clientes e identidades de Lync.

Los usuarios finales se benefician de poder conectar con los clientes, socios y proveedores en sus términos. Se beneficia de la compatibilidad de un solo cliente de comunicaciones en tiempo real a la vez que se mantienen las características de control, cumplimiento y archivado de Lync. Lync: conectividad de Skype, [disponible públicamente en mayo de 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), se basa en el heredado de Lync/Office Communications Server (OCS)/Live Communications Server (LCS) que se estableció por primera vez con PIC en la conexión con MSN/Windows Live, AOL y Yahoo.Para obtener más información sobre la conectividad de Lync y Skype, consulte la [conectividad de Lync y Skype](http://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx). La Federación con Windows Live, AOL y Yahoo se encuentran en una ruta hacia el final de la vida.Esta página documenta el estado de cada servicio.

Para usar PIC, los clientes deben activar el servicio para cada proveedor de servicios de mensajería instantánea pública. Los requisitos y los detalles para hacerlo dependen del proveedor de servicios de mensajería instantánea y del programa de licencias subyacente del cliente.

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft puso a trabajar en Windows Live Messenger y Skype. En abril de 2013, los usuarios de Messenger se migraron a Skype al iniciar sesión. Los clientes de Lync que confían en la Federación con Messenger seguirán pudiendo comunicarse con sus contactos de Messenger, incluso después de que esos contactos se actualicen a Skype. No hay nada que los administradores de Lync o los usuarios finales de Lync deban hacer para mantener la continuidad del servicio, y la administración de esta funcionalidad dentro de Lync sigue siendo la misma que para la comunicación con Messenger. 

Cuando los usuarios de Messenger inician sesión en Skype usando sus cuentas de Microsoft (es decir, las mismas credenciales usadas para Messenger), todos sus contactos de Messenger, incluidos los contactos federados de Lync, las siguen en Skype. El uso compartido de presencia y la mensajería instantánea entre Skype y Lync para estos contactos está disponible. 

Lync: conectividad de Skype: la adición de contactos, el uso compartido de presencia, la mensajería instantánea y las llamadas de audio entre los usuarios de Lync y Skype, también está disponible para todos los clientes de Lync.

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Toolbar\! y AOL Instant Messenger

Federación con Yahoo\! y AOL se encuentran en una ruta hacia el final del ciclo de vida para los clientes de Lync (y Office Communications Server). La capacidad de Microsoft para proporcionar cada uno de estos servicios se ha supeditado al soporte de Yahoo\! y AOL, y los acuerdos subyacentes de estos se liquidan. Para Yahoo\! y AOL, el servicio continuará hasta el 2014 de junio.

  - **Yahoo** -Service seguirá hasta el 2014 de junio y los clientes seguirán teniendo licencia con la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL").A partir del 1 de septiembre de 2012, la capa USL de PIC ya no está disponible para la compra de contratos nuevos o de renovación.Los clientes con licencias adquiridas antes de esta fecha podrán seguir federando a Yahoo.\! hasta la fecha de cierre del servicio o la expiración de la licencia.Lea [el anuncio](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) en el blog del equipo de Lync.Los clientes que tienen licencias PIC en contratos que se extienden más allá del 30 de junio de 2014 recibirán un crédito en proporción a la cantidad de pagos que cubren el período de tiempo posterior al 30 de junio de 2014.

  - **AOL** : el 30 de junio de 2014, el servicio de conectividad de mensajería instantánea ("PIC") de Lync dejará de estar disponible.A fin de limitar la interrupción del cliente cuando el servicio finaliza, hemos dejado de realizar el aprovisionamiento de dominios de cliente adicionales. Hasta el 30 de junio de 2014, los clientes no tienen que hacer nada para seguir admitiendo comunicaciones federadas con AIM. Más allá de esta fecha (o para los clientes que, al mismo modo, desea aprovisionar dominios adicionales), hay disponible un servicio sustituto directamente desde AOL. Para obtener más información sobre el nuevo servicio de AOL, consulte [establecer la Federación directa con AIM](http://aimenterprise.aol.com/pic.php)  (abre una página nueva en AOL.com).  

</div>

<div>

## <a name="public-im-provider-summary"></a>Resumen de proveedor de mensajería instantánea pública

En la siguiente tabla se proporciona un resumen de los proveedores de servicios públicos de mensajería instantánea, las capacidades de Federación con Lync y los requisitos de licencia.


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
<th>Requisitos de licencia</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>MI, presencia, audio</p></td>
<td><p>Licencias de acceso de cliente de Lync Server, plan 1/2/3 de Lync Online</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>MI, presencia, audio/vídeo</p></td>
<td><p>Licencias de acceso de cliente de Lync Server (admitidas siempre que WLM esté en el mercado)</p></td>
</tr>
<tr class="odd">
<td><p>TOTALMENTE</p></td>
<td><p>MI, presencia</p></td>
<td><p>Licencias de acceso de cliente de Lync Server; admitido hasta el 2014 de junio para los clientes existentes.</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>MI, presencia</p></td>
<td><p>Requiere una licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync adicional ("PIC USL"), además de las licencias de acceso de cliente de Lync Server. A partir de la lista de precios de septiembre de 2012, la capa de PIC ya no está disponible para la compra. Los clientes con licencias activas pueden seguir federando a Yahoo! Messenger hasta que se cierre el servicio la fecha del 30 de junio de 2014.</p></td>
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

