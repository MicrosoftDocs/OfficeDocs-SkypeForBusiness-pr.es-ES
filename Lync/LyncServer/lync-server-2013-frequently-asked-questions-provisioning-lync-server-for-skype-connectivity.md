---
title: 'Preguntas frecuentes: Aprovisionamiento de conectividad de Lync Server para Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7204119aca18bfeb2539b0ee5eae5bb53f38efd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>Preguntas frecuentes: Aprovisionamiento de conectividad de Lync Server 2013 para Skype

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2019-03-22_

A partir del 2019 de abril, detendremos la recopilación y la retención de la información de contacto de los clientes que estén aprovisionados para la Federación de Skype a través del sitio web de pic.lync.com. Este cambio se está efectuando para garantizar que el sistema de provisioning de pic.lync.com cumpla con las directivas de privacidad de Microsoft. 
 
Una vez que este cambio se produzca en vivo, ya no podremos proporcionar actualizaciones de correo electrónico en los cambios pendientes de aprovisionamiento. Los cambios de aprovisionamiento PIC suelen completarse en 24-48 horas después de haberlos introducido. Si sigue experimentando problemas de Federación de Skype 48 horas después de enviar una solicitud de aprovisionamiento, comuníquese con el servicio de soporte técnico de Microsoft para investigar más.

> [!IMPORTANT]
> Como parte de este cambio, toda la información de contacto introducida previamente se purgará de nuestro sistema antes de que finalice el abril de 2019.


**P: ¿Qué características se admiten entre Microsoft Lync y Skype?**

**A:** Con Skype ahora es parte de la familia de Microsoft, se abren nuevas posibilidades para ampliar los escenarios de comunicación unificada a los cientos de millones de personas que usan Skype. Esta combinación permitirá a los clientes de Lync conectarse y colaborar con proveedores, clientes y socios, confiando en la riqueza de Lync y en el alcance de Skype.

  - Mensajes instantáneos y llamadas de audio y vídeo: videollamadas federadas y mensajería instantánea entre usuarios de Lync y Skype

  - Uso compartido de presencia: información de presencia de Exchange entre contactos federados

  - Administración simple: configuración y controles para configurar las comunicaciones federadas de acuerdo con las políticas y estándares de la organización

**P: ¿Cómo puedo calificar para conectar mi implementación de Lync con Skype?**

**A:** Usted tiene licencia para conectividad de Skype si tiene alguna de las siguientes opciones:

  - Lync Server (2010 o 2013) más licencias de acceso de cliente de Lync Server Standard ("cal"; 2010 o 2013) para los usuarios y/o dispositivos de su organización que se conectarán a Skype. 

  - Lync Online (como licencias independientes o como parte de un conjunto de programas de Office 365).Sin embargo, este servicio (pic.lync.com) solo es para aprovisionar Lync Server y las implementaciones híbridas de Lync Server y Lync Online.El aprovisionamiento de PIC en Lync Online se realiza en el panel de control de Lync Online (LOCP).

**P: ¿qué deben hacer los usuarios finales de Lync para conectarse a los contactos de Skype?**

**A:** Una vez que un dominio está activado y las características están habilitadas por el administrador de Lync de una organización, los usuarios de Lync pueden agregar contactos de Skype a sus listas de contactos en el cliente de Lync.

**P: ¿qué deben hacer los usuarios finales de Skype para conectarse a los contactos de Lync?**

**A:** Todos los usuarios de Skype que deseen conectarse con un usuario de Lync deben tener una cuenta de Microsoft asociada a sus identificadores de Skype e iniciar sesión con la cuenta de Microsoft.Esto se puede habilitar en el cliente de Skype.

**P: ¿aún está disponible la Federación con Windows Live?**

**A:** A partir de octubre de 2012, Microsoft empezó a ayudar a que los usuarios de Windows Live Messenger (Skype) pasen a Skype, en ruta para retirarlo en cualquier momento.Lync seguirá admitiendo la Federación con Skype siempre que Skype esté en el mercado, pero no se permitirán activaciones adicionales de dominios de Windows Live.El movimiento de los usuarios de Skype está habilitado por Skype 6,0 para Mac y Windows (publicada el 25 de octubre de 2012) que permite iniciar sesión con una cuenta de Microsoft (es decir, las mismas credenciales que Skype). Después de iniciar sesión en Skype, las listas de Skype conocidos se rellenan automáticamente en Skype y los usuarios pueden aprovechar las capacidades de comunicación ampliada de Skype, como llamar a teléfonos fijos y móviles, pantalla compartida, videollamadas grupales y asistencia para una amplia variedad de dispositivos.Además, los contactos federados de Lync de Skype de los usuarios siguen la transición a Skype con el resto de sus listas de amigos y la mensajería instantánea entre Skype y Lync para estos contactos estará disponible inmediatamente. Los clientes de Lync no tienen que hacer nada para habilitar esta continuidad de servicio.

**P: ¿está disponible la\! Federación con Yahoo o AOL?**

**A:** No. Federación con Yahoo\! y AOL estaban supeditados al soporte técnico de Yahoo\! y AOL.Para ambos Yahoo\! y AOL, el servicio finalizó el 30 de junio de 2014. 

**P: ¿puedo probar la conectividad de Skype antes de comprar Lync?**

**A:** La conectividad de Skype no se ofrece en forma de prueba. En lugar de una prueba, se recomienda a los clientes de Lync con licencias aptas que simplemente se suscriban al servicio que se va a probar.

**P: ¿Qué información se necesita para el aprovisionamiento?**

**A:** Para enviar una solicitud de aprovisionamiento bajo una licencia calificada, necesita lo siguiente:

  - Número de contrato de Microsoft:
    
      - Soporte de licencias por volumen de Microsoft: número del contrato de licencias por volumen de Microsoft
    
      - Microsoft Partner Network: identificador de socio de la sede
    
      - Contrato de licencia del proveedor de servicios: número inicial de inscripción
    
      - Servicios de gran volumen: número de inscripción de producto

  - Nombres de dominio completos (FQDN) para el servicio perimetral de acceso.
    
      - Se requiere un FQDN para al menos un servicio perimetral de acceso.
    
      - Si su organización tiene más de un servidor que ejecuta el servicio perimetral de acceso, especifique los FQDN de cada servicio perimetral de acceso adicional. Importante: si previamente especificó un FQDN para el servicio perimetral de acceso y quiere cambiarlo, el aprovisionamiento del cambio puede tardar varios días en completarse y puede dar lugar a interrupciones en el servicio. Para evitar interrupciones en el servicio, le recomendamos que mantenga el FQDN especificado previamente del servicio perimetral de acceso.

  - Dominio (s) de protocolo de inicio de sesión (SIP). Este es el sufijo de dominio del URI del SIP que los usuarios usan actualmente para la mensajería instantánea. Si su organización tiene más de un dominio SIP, especifique el sufijo de dominio de cada dominio usado para la mensajería instantánea. Por ejemplo, para user1@contoso.com, especifique contoso.com para el dominio SIP; para user1@example.fabrikam.com, especifique example.fabrikam.com como el dominio SIP.
    
    <div>
    

    > [!NOTE]
    > Especifique solo el sufijo de dominio para el dominio SIP. No especifique FQDN, incluido el FQDN del servicio perimetral de acceso, para el dominio SIP.

    
    </div>

  - Información de contacto. Especifique una dirección de correo electrónico para el administrador de cada dominio SIP que especifique.

**P: ¿Cómo habilito la conectividad entre Lync y Skype en un escenario de dominios divididos?**

**A:** Si tiene un escenario de dominio dividido local de Lync Online 2013 y Lync Server (con usuarios en línea y locales mediante el mismo dominio SIP), habilite la conectividad entre Lync y Skype siguiendo estos dos pasos en el siguiente orden:

1.  Configure la conectividad de Skype en Lync local, como se explica en la guía de aprovisionamiento de PIC.

2.  Espere hasta que vea confirmación de que Microsoft ha aprovisionado su dominio.

3.  Después de ver la confirmación, use el centro de administración de Lync para activar las comunicaciones externas. Para obtener más información, consulte[http://office.microsoft.com/en-us/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/en-us/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

Este pedido es importante.Debe configurar la conectividad local antes de habilitar las comunicaciones en Lync Online. Si el pedido se revierte, la información introducida en el local de <https://pic.lync.com> no se enviará. Si ya ha configurado Lync Online para las comunicaciones externas con este dominio, debe desactivarlo, esperar 24 horas y volver a empezar, primero escribiendo su información local en <https://pic.lync.com> y, a continuación, activando las comunicaciones externas para Lync Online.

**P: ¿puedo aprovisionar FQDN de servicio perimetral de acceso múltiple para conectividad de Skype?**

**A:** Solo puede aprovisionar un FQDN de extremo de Access para uno o más dominios. Puede aprovisionar FQDN de borde de acceso múltiple, hasta 10 por solicitud, si tienen dominios distintos.

**P: ¿puedo obtener la lista de direcciones de correo electrónico de la cuenta de Microsoft que encuentre para la organización que solicita el aprovisionamiento?**

**A:** No. Estas direcciones se consideran información de identificación personal y no se comparten.

**P: ¿Cómo agrego un contacto de Windows Live Messenger que tiene un identificador que contiene un dominio que no es compatible con Windows Live?**

**A:** Si va a agregar un usuario de Windows Live Messenger con una cuenta o un identificador con un dominio que no sea de Windows Live, escriba la dirección en \<el siguiente\>formato\<: nombre\>de usuario (nombre de dominio \<) @msn\> . com, donde nombre de dominio es el nombre de dominio de la dirección de correo electrónico del usuario. Por ejemplo, si deseara agregar ted@contoso.com, usaría el siguiente formato: Ted (contoso. com) @msn. com. Para obtener una lista de los dominios administrados por Windows Live, consulte la sección dominios admitidos en "problemas conocidos que se producen con mensajería instantánea pública después de instalar el Service Pack 1 de http://support.microsoft.com/?kbid=897567Live Communications Server" en.

**P: ¿Cuánto tiempo tarda el proceso de aprovisionamiento?**

**A:** El aprovisionamiento puede demorar hasta 30 días.

**P: ¿Cómo sé cuándo se completa el aprovisionamiento?**

**A:** Microsoft enviará una notificación por correo electrónico cuando se complete el aprovisionamiento.

**P: ¿Cómo puedo actualizar la configuración o los detalles de contacto que envío?**

**A:** Puede actualizar la información en el mismo sitio web que usó para solicitar el aprovisionamiento, después de que se complete el aprovisionamiento. Escriba el número de su contrato y, a continuación, haga clic en actualizar servicio.

</div>

<span> </span>

</div>

</div>

</div>

