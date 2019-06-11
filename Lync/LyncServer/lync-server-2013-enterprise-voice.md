---
title: 'Lync Server 2013: Telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7c8131c2f52dfc7ab061d8dec46ee34b62f89e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-04-08_

Con la telefonía IP empresarial, Lync Server ofrece una oferta independiente de protocolo de voz a través de Internet (VoIP) para mejorar o reemplazar sistemas de central de conmutación (PBX) tradicionales. Los usuarios de la telefonía IP empresarial pueden llamar a colegas de la red de VoIP o PBX de su organización, y pueden llamar a números de teléfono tradicionales fuera de su organización. La solución de voz para empresas incluye características comunes de llamadas, como responder, desviar, transferir, suspender, desviar, soltar y detener, y las llamadas de 9-1-1 (E9-1-1) (E9-1-1 solo está disponible en los Estados Unidos). Enterprise Voice también admite una amplia variedad de dispositivos IP y USB actuales y anteriores.

<div>

## <a name="placing-and-receiving-calls"></a>Realizar y recibir llamadas

Con Lync, los usuarios pueden realizar llamadas escribiendo un nombre o número de teléfono en el teclado o usando un teclado de marcado que se muestra en la pantalla. Los usuarios también pueden iniciar llamadas directamente desde su lista de contactos. También puede implementar dispositivos de Lync Phone Edition, que son dispositivos telefónicos de telefonía IP independientes proporcionados por socios de Microsoft.

Los usuarios pueden tener varios dispositivos de telefonía registrados en Lync Server y cambiar de uno a otro.

Los usuarios reciben alertas de llamadas entrantes en todos sus dispositivos de forma simultánea, con tonos de timbre personalizables en dispositivos telefónicos IP y una notificación similar a la de un mensaje instantáneo en su equipo informático.

Los usuarios también pueden establecer un único número de teléfono que se conecte a su teléfono de escritorio, equipo informático y teléfono móvil, de modo que se pueda llegar sin importar dónde estén.

</div>

<div>

## <a name="basic-call-features"></a>Características de llamadas básicas

Mientras se encuentra en una llamada, un usuario puede contestar llamadas entrantes adicionales o iniciar llamadas salientes, y la llamada activa existente se coloca automáticamente en espera. Las llamadas se pueden transferir de un usuario a otro, ya sea directamente o después de que el primer usuario hable en privado con el segundo usuario. Los usuarios también pueden transferir llamadas a otro dispositivo. por ejemplo, pueden transferir una llamada activa a su teléfono móvil mientras salen de la puerta de su oficina.

</div>

<div>

## <a name="richer-communications"></a>Comunicaciones más ricas

Al hablar con otro usuario con Lync, los usuarios pueden agregar fácilmente texto, vídeo o uso compartido de escritorio a la llamada. La característica do-not-molestar se integra con la configuración de presencia en Lync.

Con mensajería unificada (UM) de Exchange, Lync y Lync Server se integran con Microsoft Exchange Server 2013 y Microsoft Outlook 2013. Los usuarios pueden ver si tienen el correo de voz nuevo tanto en la ventana de Lync como en el correo electrónico. En el correo electrónico, pueden hacer clic en para reproducir el audio del correo de voz en un mensaje de correo electrónico o ver una transcripción del mensaje de correo de voz.

</div>

<div>

## <a name="advanced-calling-features"></a>Características avanzadas de llamadas

La telefonía IP empresarial también incluye varias características de llamadas avanzadas, como la delegación de llamadas de Lync, las llamadas de equipo, la recogida de llamadas grupales y los grupos de respuesta.

La delegación de llamadas de Lync permite a los usuarios delegar el control de llamadas en uno o varios asistentes, yendo a **herramientas** \> **Opciones** \> de **desvío de llamadas**. El delegado puede realizar varias tareas de llamada en nombre del usuario, entre las que se incluyen las llamadas de filtrado, la realización de llamadas y la apertura de conferencias.

<div>


> [!IMPORTANT]  
> Es posible que esté buscando otra característica con un nombre similar, Delegación de calendarios de Lync. No requiere la característica de telefonía IP empresarial y permite a los usuarios programar reuniones de Lync en línea desde Outlook. Si ha llegado para esa información, le recomendamos que consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-ClientPolicy</A> para obtener información sobre cómo habilitar la sincronización de delegados de Exchange.



</div>

Las llamadas de equipo permiten a un usuario hacer llamadas entrantes simultáneamente en los teléfonos de los compañeros de equipo para que cualquier persona del equipo pueda responder a la llamada.

Recogida de la llamada grupal, una nueva característica de las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero, permite a los usuarios contestar las llamadas entrantes a sus colegas desde sus propios teléfonos. La recogida de llamadas grupales difiere de las llamadas de equipo principalmente en que las llamadas entrantes solo suenan en el teléfono del destinatario deseado, pero cualquier otro usuario puede contestarla marcando un número de grupo de recogida de llamadas.

Los grupos de respuesta se pueden configurar para la cola y enrutar de forma inteligente las llamadas a agentes designados. Los usos más comunes incluyen el servicio de asistencia al usuario de ti, las líneas directas de recursos humanos y otros centros internos de contacto.

</div>

<div>

## <a name="enterprise-voice-administration"></a>Administración de telefonía IP empresarial

Lync Server usa estándares e interfaces publicadas para interoperar con la infraestructura existente. Es compatible con las opciones de puerta de enlace y de SIP (como la Troncalización SIP) para la interconexión con sistemas PBX IP y las redes RTC, de modo que pueda migrar los usuarios a Enterprise Voice a través del tiempo, a la vez que minimiza las interrupciones. Lync Server admite los códecs tradicionales, como G. 711, G. 722 y G. 723.1 para la interoperabilidad con las soluciones de VoIP tradicionales.

Con control de admisión de llamadas (CAC), los administradores pueden establecer límites en la cantidad de tráfico de voz y vídeo de Lync Server que se transporta en los vínculos de red restringidos y especificar la acción que se debe realizar si una nueva llamada supera el límite. Las acciones pueden incluir el enrutamiento mediante una ruta de acceso alternativa o la negación de la llamada.

Lync Server funciona con equipos de sucursales de terceros que permiten ofrecer servicios de llamadas locales y una conexión a PSTN en sucursales, en caso de que se produzcan errores de WAN en el sitio central.

</div>

</div>

<span> </span>

</div>

</div>

</div>

