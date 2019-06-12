---
title: Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2a8aea4b412d2d744c42d659d2414a93c8435e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL) de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-09-26_

Una aplicación de servidor de Microsoft SIP Processing language (MSPL) es una aplicación de solo secuencias de comandos que usa un lenguaje de scripting en lugar de la API 2010 de Microsoft Lync. MSPL proporciona un control más granular sobre el filtrado y los comportamientos de proxy, además de una facilidad para enviar mensajes específicos a aplicaciones SIP basadas en transacciones. MSPL se usa específicamente para filtrar y enrutar mensajes SIP. Las aplicaciones MSPL se ejecutan en el mismo proceso que el módulo UserServices, mientras que un programa basado en la API de Lync 2010 se ejecuta en un proceso independiente.

Puede usar la página de **aplicación de servidor** del grupo **topología** del panel de control de Lync Server para ver una lista de aplicaciones de servidor MSPL que se ejecutan en servidores front-end en su entorno de Lync Server 2013. La lista muestra las secuencias de comandos disponibles para cada grupo, así como si están habilitadas o críticas. Las secuencias de comandos se ejecutan en el orden en que aparecen.

Estas secuencias de comandos incluyen lo siguiente:

  - ClientVersionFilter proporciona al administrador una manera de especificar la versión de los clientes compatibles con un grupo. El filtro de versión del cliente comprueba la versión del cliente y puede impedir que el cliente inicie sesión o presente al usuario con un mensaje que indica que está usando un cliente que no es compatible. El filtro de versión del cliente también se puede configurar para mostrar un mensaje al usuario que contiene la dirección URL de la última versión descargable del cliente.

  - TranslationService traduce un número que un usuario marca a un número E. 164 según las reglas de normalización definidas por el administrador. Para obtener más información, vea [reglas de traducción en Lync Server 2013](lync-server-2013-translation-rules.md).

  - IncomingFederation exige la validación de la Federación de nivel de inquilino para los mensajes entre inquilinos y los mensajes entrantes de implementaciones externas.

  - UserServices es el componente de las conferencias, la presencia y el registrador SIP de un servidor front-end. Ofrece características de conferencia, presencia y mensajería instantánea estrechamente integradas que se basan en la parte superior del proxy SIP.

  - InterClusterRouting es responsable de dirigir las llamadas al grupo de registrador principal de la persona que llama. Para obtener más información, consulte [componentes de VoIP del servidor front-end para Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).

  - IIMFilter (filtro inteligente de mensajes instantáneos) bloquea los mensajes que contienen direcciones URL en las que se puede hacer clic o que intentan iniciar transferencias de archivos. IIMFilter también comprueba la versión del cliente en nombre del servidor. IIMFilter afecta a las transferencias de archivos que se inician mediante Lync Server o Communicator. De forma predeterminada, los vínculos seleccionables se desactivan agregando un carácter de subrayado antes del primer carácter del vínculo. Un administrador puede cambiar este comportamiento para que el vínculo esté bloqueado, en cuyo caso los mensajes que contengan direcciones URL en las que se puede hacer clic o que intenten iniciar una transferencia de archivos están bloqueados por el servidor para que no llegue a sus destinos previstos. IIMFilter se instala en todos los servidores que ejecutan Lync Server, excepto los servidores proxy y los servidores de archivado.

  - UserPinService se usa para comprobar los números de identificación personal (PIN) para las conferencias de acceso telefónico local.

  - DefaultRouting es la aplicación de enrutamiento predeterminada para servidores que ejecutan Lync Server. Está habilitado de forma predeterminada. La aplicación de enrutamiento se instala en todos los servidores Standard Edition y Enterprise Edition.

  - ExumRouting enruta las llamadas a la mensajería unificada de Exchange Server (UM). ExumRouting determina el servidor de mensajería unificada de Exchange adecuado para enrutar la llamada a cuando haya un nuevo mensaje de correo de voz para depositar. ExumRouting también controla otros aspectos de la integración de mensajería unificada de Exchange, incluido el enrutamiento al operador automático y al acceso de suscriptor.

  - OutboundRouting determina la puerta de enlace que dirige una llamada a un número de teléfono según el número marcado y la autorización de marcado del usuario. OutboundRouting también controla el redireccionamiento de llamadas si una puerta de enlace no puede procesar una llamada.

  - QoEAgent recibe informes de datos de la calidad de la experiencia (QoE) a partir de puntos de conexión a través de solicitudes de servicio SIP y envía los datos a la cola de destino en el servidor de supervisión o a consumidores de terceros mediante HTTP POST. Para obtener más información, consulte [implementación de la supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md).

  - OutgoingFederation exige la validación de la Federación en el nivel de inquilino para los mensajes dirigidos a una implementación externa de destino.

  - AcpRoutinglos servidores proxy INVITAn a las solicitudes dirigidas al proveedor de servicios de audioconferencia a la puerta de enlace del proveedor de audioconferencia.

Entre los scripts que se ejecutan en servidores perimetrales se incluyen los siguientes:

  - IIMFilter

  - OptionsHandler responde a las solicitudes de opciones entrantes con **200 aceptar** si la solicitud se destina al servidor actual. Se usa para la validación de topología.

<div>

## <a name="see-also"></a>Vea también


[Habilitar o deshabilitar una aplicación de servidor de Microsoft SIP Processing language (MSPL) en Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Marcar una aplicación de Microsoft SIP Processing language (MSPL) como crítica o incrítica en Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

