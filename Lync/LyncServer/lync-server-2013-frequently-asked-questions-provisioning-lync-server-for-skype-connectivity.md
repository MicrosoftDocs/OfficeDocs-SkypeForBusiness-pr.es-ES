---
title: 'Preguntas más frecuentes: aprovisionamiento de Lync Server para conectividad de Skype'
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
ms.openlocfilehash: 690eb5631b57a88d207816a01c887c1f94c0eeb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>Preguntas más frecuentes: aprovisionamiento de Lync Server 2013 para conectividad de Skype

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2019-03-22_

A partir de abril de 2019, detendremos la recopilación y la retención de la información de contacto para los clientes aprovisionados para la Federación de Skype mediante el sitio web pic.lync.com. Se está realizando este cambio para asegurarse de que el sistema de aprovisionamiento de pic.lync.com cumple con las directivas de privacidad de Microsoft. 
 
Una vez que este cambio se produzca, ya no podremos proporcionar actualizaciones de correo electrónico en los cambios pendientes de aprovisionamiento. Los cambios de aprovisionamiento de PIC se completan normalmente en un plazo de 24-48 horas tras su entrada. Si sigue experimentando problemas de Federación de Skype de 48 horas después de enviar una solicitud de aprovisionamiento, comuníquese con el soporte técnico de Microsoft para investigar el problema.

> [!IMPORTANT]
> Como parte de este cambio, toda la información de contacto especificada anteriormente se purgará de nuestro sistema a finales de abril de 2019.


**P: ¿Qué características se admiten entre Microsoft Lync y Skype?**

**A:** Con Skype ahora forma parte de la familia de Microsoft, se abren nuevas posibilidades para ampliar los escenarios de comunicaciones unificadas a cientos de millones de personas que usan Skype. Esta combinación permitirá a los clientes de Lync conectarse y colaborar con proveedores, clientes y socios, confiando en la riqueza de Lync y en el alcance de Skype.

  - Mensajes instantáneos y llamadas de audio y vídeo: llamadas de audio y vídeo federadas y mensajería instantánea entre usuarios de Lync y Skype

  - Uso compartido de presencia: información de presencia de Exchange entre contactos federados

  - Administración sencilla: configuración y controles para configurar las comunicaciones federadas de acuerdo con las directivas y los estándares de la organización

**P: ¿Cómo puedo calificar para conectar mi implementación de Lync con Skype?**

**A:** Tiene una licencia para la conectividad de Skype si tiene:

  - Lync Server (2010 o 2013) más licencias de acceso de cliente de Lync Server Standard ("cal"; 2010 o 2013) para los usuarios o dispositivos de su organización que se conectarán a Skype. 

  - Lync Online (como licencias independientes o como parte de un conjunto de aplicaciones de Office 365).Sin embargo, este servicio (pic.lync.com) solo es para aprovisionar Lync Server y las implementaciones híbridas de Lync Server y Lync Online.El aprovisionamiento de PIC en Lync Online se realiza en el panel de control de Lync Online (LOCP).

**P: ¿qué deben hacer los usuarios finales de Lync para conectarse a los contactos de Skype?**

**A:** Una vez que un dominio está activado y las características están habilitadas por el administrador de Lync de una organización, los usuarios de Lync pueden agregar contactos de Skype a sus listas de contactos dentro del cliente de Lync.

**P: ¿qué deben hacer los usuarios finales de Skype para conectarse a los contactos de Lync?**

**A:** Todos los usuarios de Skype que quieran conectarse a un usuario de Lync deben tener una cuenta de Microsoft asociada a sus identificadores de Skype e iniciar sesión con la cuenta de Microsoft.Esto se puede habilitar en el cliente de Skype.

**P: ¿todavía está disponible la Federación con Windows Live?**

**A:** A partir de octubre de 2012, Microsoft empezó a ayudar a que los usuarios de Windows Live Messenger (WLM) pasen a Skype, en camino a retirar de WLM.Lync seguirá admitiendo la Federación con WLM siempre que WLM esté en el mercado, pero no se permitirá ninguna otra activación de dominio de Windows Live.El movimiento de los usuarios de WLM está habilitado por el 6,0 de Skype para Mac y Windows (lanzado el 25 de octubre de 2012) que permite iniciar sesión con una cuenta de Microsoft (es decir, las mismas credenciales que WLM). Después de iniciar sesión en Skype, las listas de WLM Buddy se rellenan automáticamente en Skype y los usuarios pueden aprovechar las capacidades de comunicación ampliada de Skype, como la llamada a teléfonos fijos y móviles, el uso compartido de la pantalla, las llamadas de vídeo en grupo y la compatibilidad con una amplia variedad de dispositivos.Además, los contactos federados de Lync de WLM de los usuarios siguen la transición a Skype con el resto de sus listas de amigos y la mensajería instantánea entre Skype y Lync para estos contactos estará disponible inmediatamente. Los clientes de Lync no necesitan hacer nada para habilitar esta continuidad del servicio.

**P: ¿está disponible la\! Federación con Yahoo o AOL?**

**A:** No. Federación con Yahoo\! y AOL están supeditados al soporte de Yahoo\! y AOL.Para Yahoo\! y AOL, el servicio finalizó el 30 de junio de 2014. 

**P: ¿puedo probar la conectividad de Skype antes de comprar Lync?**

**A:** La conectividad de Skype no se ofrece en un período de prueba. En vez de una versión de prueba, se recomienda a los clientes de Lync con licencias elegibles que simplemente se suscriban al servicio que se va a probar.

**P: ¿Qué información se necesita para el aprovisionamiento?**

**A:** Para enviar una solicitud de aprovisionamiento con una licencia calificada, necesita lo siguiente:

  - Número de contrato de Microsoft:
    
      - Soporte de licencias por volumen de Microsoft: número del contrato de licencias por volumen de Microsoft
    
      - Red de asociados de Microsoft: identificador de asociado de la sede central
    
      - Contrato de licencia del proveedor de servicios: número de inscripción inicial
    
      - Servicios de gran volumen: número de inscripción de producto

  - Nombres de dominio completos (FQDN) para el servicio perimetral de acceso.
    
      - Se requiere un FQDN para al menos un servicio perimetral de acceso.
    
      - Si su organización tiene más de un servidor que ejecuta el servicio perimetral de acceso, especifique los FQDN para cada servicio perimetral de acceso adicional. Importante: si anteriormente especificó un FQDN para el servicio perimetral de acceso y quiere cambiarlo, el aprovisionamiento del cambio puede tardar varios días en completarse y puede dar lugar a una interrupción del servicio. Para evitar la interrupción del servicio, le recomendamos que mantenga el FQDN especificado previamente del servicio perimetral de acceso.

  - Dominio (s) del Protocolo de inicio de sesión (SIP). Este es el sufijo de dominio del URI de SIP que los usuarios usan actualmente para la mensajería instantánea. Si su organización tiene más de un dominio SIP, especifique el sufijo de dominio para cada dominio usado para la mensajería instantánea. Por ejemplo, para user1@contoso.com, especifique contoso.com para el dominio SIP; para user1@example.fabrikam.com, especifique example.fabrikam.com como el dominio SIP.
    
    <div>
    

    > [!NOTE]
    > Especifique solo el sufijo de dominio para el dominio SIP. No especifique ningún FQDN, incluido el FQDN del servicio perimetral de acceso, para el dominio SIP.

    
    </div>

  - Información de contacto. Especifique una dirección de correo electrónico para el administrador de cada dominio SIP que especifique.

**P: ¿Cómo habilito la conectividad de Lync-Skype en un escenario de dominio dividido?**

**A:** Si tiene un escenario de dominio dividido local de Lync Online 2013 y Lync Server (con usuarios en línea y locales que usan el mismo dominio SIP), habilite la conectividad entre Lync y Skype siguiendo estos dos pasos en el siguiente orden:

1.  Configure la conectividad de Lync-Skype local, tal y como se explica en la guía de aprovisionamiento de PIC.

2.  Espere hasta que vea la confirmación de que Microsoft ha aprovisionado su dominio.

3.  Después de ver la confirmación, use el centro de administración de Lync para activar "comunicaciones externas". Para obtener más información, vea[http://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

Este orden es importante.Debe configurar la conectividad local antes de habilitar las comunicaciones en Lync Online. Si se invierte el orden, la información que se especifica para on- <https://pic.lync.com> premise no pasará el paso. Si ya ha configurado Lync Online para las comunicaciones externas con este dominio, debe desactivarlo, esperar 24 horas y volver a empezar, primero especificando la información local en <https://pic.lync.com> y, a continuación, activando las comunicaciones externas para Lync Online.

**P: ¿puedo aprovisionar varios FQDN del servicio perimetral de acceso para conectividad de Skype?**

**A:** Solo se puede aprovisionar un FQDN de servidor perimetral de acceso para uno o más dominios. Puede proporcionar varios FQDN de servidor perimetral de acceso, hasta 10 por solicitud, si tienen dominios distintos.

**P: ¿puedo obtener la lista de direcciones de correo electrónico de la cuenta de Microsoft que encuentra para la organización que solicita el aprovisionamiento?**

**A:** No. Estas direcciones se consideran información de identificación personal y no se comparten.

**P: ¿Cómo agrego un contacto de Windows Live Messenger que tiene un identificador que contiene un dominio que no es compatible con Windows Live?**

**A:** Si va a agregar un usuario de Windows Live Messenger con una cuenta o un identificador con un dominio que no es de Windows Live, escriba la dirección con \<el siguiente\>formato\<: nombre\>de usuario (nombre de dominio \<) @msn\> . com, donde nombre de dominio es el nombre de dominio de la dirección de correo electrónico del usuario. Por ejemplo, si deseara agregar ted@contoso.com, usaría el siguiente formato: Ted (contoso. com) @msn. com. Para obtener una lista de los dominios que se administran mediante Windows Live, consulte la sección dominios admitidos en "problemas conocidos que se producen con la mensajería instantánea pública después de instalar Live Communications http://support.microsoft.com/?kbid=897567Server Service Pack 1" en.

**P: ¿Cuánto tiempo tarda el proceso de aprovisionamiento?**

**A:** El aprovisionamiento puede tardar hasta 30 días.

**P: ¿Cómo sé cuándo se ha completado el aprovisionamiento?**

**A:** Microsoft enviará una notificación por correo electrónico cuando se complete el aprovisionamiento.

**P: ¿Cómo puedo actualizar la configuración o los detalles de contacto que envío?**

**A:** Puede actualizar la información en el mismo sitio web que usó para solicitar el aprovisionamiento, después de que se haya completado el aprovisionamiento. Escriba el número de contrato y, a continuación, haga clic en actualizar servicio.

</div>

<span> </span>

</div>

</div>

</div>

