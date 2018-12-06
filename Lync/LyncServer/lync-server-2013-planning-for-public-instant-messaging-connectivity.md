---
title: Planear la conectividad de mensajería instantánea pública en Lync Server 2013
TOCTitle: Planear la conectividad de mensajería instantánea pública en Lync Server 2013
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48277022
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planear la conectividad de mensajería instantánea pública en Lync Server 2013

 

_**Última modificación del tema:** 2017-03-09_

La conectividad de mensajería instantánea pública es una clase especial de federación y está configurada para que los usuarios internos y externos de Lync Server 2013 puedan agregar contactos desde cualquiera de las siguientes aplicaciones:

  - Contactos de Messenger

  - Contactos de Yahoo\!

  - Contactos de America Online (AOL)

> [!IMPORTANT]  
> <ul>
> <li><p>Desde el 1 de septiembre de 2012 no se pueden comprar ni renovar acuerdos de licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (“PIC USL”). Los clientes que dispongan de licencias activas podrán mantener su federación con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha de cierre anunciada para AOL y Yahoo! se sitúa en junio de 2014. Para más información, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
> <li><p>La PIC USL es una licencia de suscripción por usuario y mes necesaria para que Lync Server o el servidor Office Communications Server puedan federarse con Yahoo! Messenger. La capacidad de Microsoft para prestar este servicio ha dependido siempre del soporte ofrecido por Yahoo!, cuyo acuerdo subyacente no se va a renovar.</p></li>
> <li><p>Lync es ahora más que nunca una poderosa herramienta de conexión entre empresas y con individuos de todo el mundo. La federación con Windows Live Messenger no precisa de ninguna licencia de usuario/dispositivo extra, aparte de la licencia CAL de Lync Standard. Esta lista incluirá también la federación con Skype, lo que permitirá a los usuarios de Lync llegar a cientos de millones de personas mediante voz y mensajería instantánea.</p></li>
> </ul>


Esta clase de federación requiere las siguientes consideraciones de planificación:

  - Los usuarios de Windows Live Messenger pueden tener una comunicación audiovisual punto a punto con usuarios de Lync Server 2013 además de la mensajería instantánea. Sus Servidores perimetrales deben cumplir unos determinados requisitos de puerto y protocolo. Para más información, consulte [Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - La mensajería instantánea de Yahoo no tiene ningún requisito único aparte de los que se suelen usar en la planificación e implementación del Servidor perimetral típico que proporciona federación.

  - America Online requiere una configuración de certificado única. Además del uso de clave mejorada del servidor normal (EKU), America Online requiere el certificado o los certificados (en el caso de un grupo de servidores de Servidor perimetral) para contener también el EKU del cliente.

## En esta sección

  - [Resumen de certificado - Conectividad de mensajería instantánea pública](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Resumen de puertos - Conectividad de mensajería instantánea pública](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [Resumen de DNS - Conectividad de mensajería instantánea pública](https://technet.microsoft.com/es-es/library/jj618375\(v=ocs.15\))

