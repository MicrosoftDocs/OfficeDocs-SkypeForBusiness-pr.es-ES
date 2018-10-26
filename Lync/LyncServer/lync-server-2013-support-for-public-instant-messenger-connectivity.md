---
title: "Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013"
TOCTitle: "Pr. en ch. de la connect. PIC (Public IM Connectivity) dans Lync Server 2013"
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59602843
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

## Compatibilidad con conectividad de mensajería instantánea pública

En este artículo se proporciona información sobre la compatibilidad con la conectividad de mensajería instantánea pública (PIC). PIC es una característica de Microsoft Lync que permite a las organizaciones habilitar la conexión de sus usuarios de Lync con usuarios de ciertos servicios de mensajería instantánea (MI) con sus clientes e identidades de Lync.

La ventaja de los usuarios finales es que pueden conectarse con clientes, socios y proveedores a su manera. La ventaja de los profesionales de TI es que pueden admitir un único cliente de comunicaciones en tiempo real y, a la vez, mantener el control, el cumplimiento y el archivado de las características de Lync. La conectividad Lync-Skype, [disponible para el público en general en mayo de 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), se basa en el hito marcado por Lync, el servidor Office Communications Server (OCS) y Live Communications Server (LCS) con PIC al establecer una conexión con MSN/Windows Live, AOL y Yahoo. Para más información, vea el tema sobre la [conectividad Lync-Skype](http://office.microsoft.com/es-es/lync/lync-skype-connectivity-fx103789635.aspx). La federación con Windows Live, AOL y Yahoo está llegando a su fin. En esta página se documenta el estado de cada servicio.

Para usar PIC, los clientes han tenido que activar el servicio para cada proveedor de servicios de mensajería instantánea pública. Los requisitos y detalles para hacerlo dependen del proveedor de servicios de mensajería instantánea y del programa de licencia subyacente del cliente.

## Windows Live Messenger

Microsoft unió Windows Live Messenger y Skype. En abril de 2013, los usuarios de Messenger migraron a Skype al iniciar sesión. Los clientes de Lync que tienen federación con Messenger podrán seguir comunicándose con sus contactos de Messenger, incluso una vez actualizados a Skype. Los administradores y usuarios finales de Lync no tienen que realizar ninguna acción para mantener la continuidad del servicio, y la administración de esta función en Lync sigue siendo igual a la de las comunicaciones en Messenger.

Cuando los usuarios de Messenger inician sesión en Skype con sus cuentas Microsoft (es decir, con las mismas credenciales que usan para Messenger), todos sus contactos de Messenger (incluidos los contactos de Lync federados) también migran a Skype. Estos contactos pueden usar el uso compartido de presencia y la mensajería instantánea entre Skype y Lync.

Conectividad Lync-Skype: ahora también están disponibles las funciones de adición de contactos, uso compartido de presencia, mensajería instantánea y llamadas de audio entre usuarios de Lync y Skype para todos los clientes de Lync.

## Yahoo\! y AOL Instant Messenger

La federación con Yahoo\! y AOL está llegando a su fin para los clientes de Lync (y Office Communications Server). La posibilidad de Microsoft de proporcionar cada uno de estos servicios ha dependido del respaldo de Yahoo\! y AOL, pero sus acuerdos subyacentes están en las últimas instancias. Tanto para Yahoo\! como para AOL, el servicio continuará hasta junio de 2014 inclusive.

  - **Yahoo:** el servicio continuará hasta junio de 2014 inclusive y los clientes seguirán necesitando la licencia de suscripción del usuario de conectividad de mensajería instantánea pública (PIC USL) de Microsoft Lync. A partir del 1 de septiembre de 2012, la licencia PIC USL ya no está disponible para la adquisición de acuerdos nuevos ni para la renovación de acuerdos existentes. Los clientes que tengan licencias compradas con anterioridad a esta fecha seguirán federados con Yahoo\! hasta la fecha de finalización del servicio mencionada anteriormente o hasta la expiración de su licencia. Lea [el anuncio](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) en el blog del equipo de Lync. Los clientes que tengan licencias PIC en acuerdos que se prolongan más allá del 30 de junio de 2014 recibirán una nota de crédito proporcional al monto cubierto por el período de tiempo posterior al 30 de junio de 2014.

  - **AOL:** el 30 de junio de 2014, el servicio de conectividad de mensajería instantánea (PIC) de Lync dejará de estar disponible. Para limitar las interrupciones que experimentarán los clientes cuando finalice el servicio, hemos discontinuado el aprovisionamiento de dominios de cliente adicionales. Hasta el 30 de junio de 2014, los clientes no tienen que realizar ninguna acción para seguir admitiendo comunicaciones federadas con AIM. Pasada esa fecha (o para los clientes que quieran aprovisionar dominios adicionales entretanto), se encontrará disponible un servicio sustituto directamente desde AOL. Para más información sobre el nuevo servicio de AOL, vea el tema acerca de cómo [establecer federación directa con AIM](http://aimenterprise.aol.com/pic.php) (se abre una página nueva en AOL.com).

## Resumen de proveedores de mensajería instantánea pública

La siguiente tabla ofrece un resumen de los proveedores de servicios de mensajería instantánea pública, las capacidades de federación con Lync y los requisitos de licencia.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Proveedor de servicios de mensajería instantánea pública</th>
<th>Capacidades de federación</th>
<th>Requisitos de licencia</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>MI, presencia, audio</p></td>
<td><p>Licencias de acceso del cliente de Lync Server, Lync Online (planes 1, 2 y 3)</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>MI, presencia, audio y vídeo</p></td>
<td><p>Licencias de acceso del cliente de Lync Server (compatibles siempre que WLM se encuentre disponible en el mercado)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>MI, presencia</p></td>
<td><p>Licencias de acceso del cliente de Lync Server (compatibles hasta junio de 2014 inclusive para clientes existentes)</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>MI, presencia</p></td>
<td><p>Es necesaria una licencia de suscripción del usuario de conectividad de mensajería instantánea pública (PIC USL) de Microsoft Lync además de las licencias de acceso del cliente de Lync Server. A partir de la lista de precios de septiembre de 2012, la licencia PIC USL ya no está disponible para la compra. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de finalización del servicio programada para el 30 de junio de 2014.</p></td>
</tr>
</tbody>
</table>

