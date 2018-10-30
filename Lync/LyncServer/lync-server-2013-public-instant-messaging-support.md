---
title: 'Lync Server 2013: Compatibilidad de mensajería instantánea pública'
TOCTitle: Compatibilidad de mensajería instantánea pública
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48274649
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad de mensajería instantánea pública en Lync Server 2013

 

_**Última modificación del tema:** 2013-10-07_

Lync Server 2013 admite el uso de los proveedores de conectividad de mensajería instantánea (MI) pública con licencia, así como el uso del Protocolo extensible de mensajería y presencia (XMPP) para implementar un tipo especial de federación que permite a un Lync Server tener acceso a los socios de dominio XMPP configurado a través del cliente de Lync 2013.

## Soporte de proveedor de conectividad de mensajería instantánea pública

Los socios de conectividad de mensajería instantánea pública admitidos actualmente son:

  - America Online

  - Windows Live

  - Yahoo\!

Para las comunicaciones con los usuarios de Windows Live, Lync Server 2013 admite la mensajería instantánea punto a punto y las llamadas de audio y vídeo. Para las comunicaciones con AOL y Yahoo\!, Lync Server 2013 admite la mensajería instantánea punto a punto. Podrá exigirse una licencia independiente.

> [!IMPORTANT]  
> <ul>
> <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
> <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
> <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
> </ul>


## Compatibilidad con la federación XMPP

La federación XMPP admite la comunicación de los usuarios de Lync con usuarios del dominio XMPP configurados que usan un proveedor público, como GTalk. Las comunicaciones con estos usuarios pueden incluir lo siguiente:

  - Presencia y mensajería instantánea punto a punto

  - Creación de contactos federados de XMPP en el cliente Lync

