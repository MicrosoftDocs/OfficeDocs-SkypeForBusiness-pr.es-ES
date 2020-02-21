---
title: Lync Server 2013 Enterprise Voice
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924e15aae9590b6148864084aa68924e4c080f7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-04-08_

Con la telefonía IP empresarial, Lync Server ofrece una oferta de protocolo de voz sobre IP (VoIP) independiente para mejorar o reemplazar sistemas tradicionales de central de conmutación (PBX). Los usuarios de Telefonía IP empresarial pueden llamar a compañeros de la red de VoIP o PBX de la organización y pueden llamar a números de teléfono convencionales fuera de la organización. La solución de telefonía IP empresarial incluye características de llamada comunes como Answer, Forward, transfer, Hold, desvía, Release and Park y la llamada mejorada de 9-1-1 (E9-1-1) (E9-1-1 solo está disponible en Estados Unidos). La telefonía IP empresarial también admite una amplia gama de dispositivos IP y USB actuales y antiguos.

<div>

## <a name="placing-and-receiving-calls"></a>Enviar y recibir llamadas

Con Lync, los usuarios pueden realizar llamadas escribiendo un nombre o número de teléfono en el teclado o usando un teclado de marcado que se muestra en la pantalla. Asimismo, los usuarios pueden iniciar llamadas directamente desde su lista de contactos. También puede implementar dispositivos de Lync Phone Edition, que son dispositivos de telefonía IP independientes proporcionados por los socios de Microsoft.

Los usuarios pueden tener varios dispositivos telefónicos registrados en Lync Server y cambiar entre ellos fácilmente.

Los usuarios reciben una alerta en todos sus dispositivos de forma simultánea cuando se recibe una llamada, con tonos de llamada personalizables en los dispositivos telefónicos IP y una notificación similar de mensaje instantáneo en sus equipos.

Los usuarios también pueden establecer un único número de teléfono que conecta con su teléfono de escritorio, equipo y teléfono móvil, de forma que pueden responder allí donde estén.

</div>

<div>

## <a name="basic-call-features"></a>Características básicas de llamada

Mientras atiende una llamada, un usuario puede responder a llamadas entrantes adicionales o realizar llamadas y la llamada activa en esos momentos pasa a estar en espera de forma automática. Las llamadas se pueden transferir de un usuario a otro, bien de forma directa o después de que el primer usuario hable en privado con el segundo. Además, los usuarios pueden transferir llamadas a otro dispositivo; por ejemplo, podrían transferir una llamada activa a su teléfono móvil si necesitan salir de la oficina.

</div>

<div>

## <a name="richer-communications"></a>Comunicaciones enriquecidas

Al hablar con otro usuario con Lync, los usuarios pueden agregar fácilmente texto, vídeo o uso compartido de escritorio a la llamada. La característica do-not-molestar se integra con la configuración de presencia en Lync.

Con mensajería unificada (MU) de Exchange, Lync y Lync Server se integran con Microsoft Exchange Server 2013 y Microsoft Outlook 2013. Los usuarios pueden ver si tienen correo de voz nuevo tanto en la ventana de Lync como en el correo electrónico. Si están en el correo electrónico, pueden hacer clic en un mensaje de correo electrónico para reproducir el audio del correo de voz o ver una transcripción del mensaje del correo de voz.

</div>

<div>

## <a name="advanced-calling-features"></a>Características avanzadas de llamada

La telefonía IP empresarial también incluye varias características avanzadas de llamada, como la delegación de llamadas de Lync, las llamadas de equipo, la recogida de llamadas de grupo y los grupos de respuesta.

La delegación de llamadas de Lync permite a los usuarios delegar el control de la llamada a uno o más asistentes; para ello, vaya a **Opciones** \> de **reenvío de llamadas**de **herramientas** \> . El delegado puede llevar a cabo múltiples tareas de llamada en nombre del usuario, lo cual incluye la selección de llamadas, envío de llamadas e inicio de conferencias.

<div>


> [!IMPORTANT]  
> Es posible que quiera buscar otra característica con nombre similar, Delegación de calendarios de Lync. No requiere la característica Enterprise Voice y permite a los usuarios programar reuniones de Lync en línea desde Outlook. Si ha llegado a esta información, le recomendamos que consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-CsClientPolicy</A> para obtener información sobre cómo habilitar la sincronización de delegados de Exchange.



</div>

Las llamadas de equipo permiten que un usuario tenga que llamar simultáneamente a los teléfonos de los compañeros de equipo para que cualquier persona del equipo pueda responder a la llamada.

Recogida de llamadas grupales, una nueva característica de las actualizaciones acumulativas de Lync Server 2013: febrero de 2013, permite a los usuarios responder llamadas entrantes a sus colegas desde sus propios teléfonos. La recogida de llamadas de grupo difiere de las llamadas de equipo principalmente en que una llamada entrante suena solo en el teléfono del destinatario previsto, pero cualquier otro usuario puede contestarla marcando un número de grupo de recogida de llamadas.

Los grupos de respuesta pueden establecer el envío a cola y enrutamiento inteligente de llamadas para agentes designados. Entre los usos habituales se incluyen la asistencia técnica de TI, línea directa a recursos humanos y otros centros de contacto internos.

</div>

<div>

## <a name="enterprise-voice-administration"></a>Administración de la Telefonía IP empresarial

Lync Server usa estándares y interfaces publicadas para interoperar con la infraestructura existente. Admite las opciones de puerta de enlace y SIP (como la conexión basada en troncos SIP) para la interconexión a sistemas PBX IP y las redes RTC, de forma que se pueden migrar usuarios a Telefonía IP empresarial de forma continuada, a la vez que se minimiza el riesgo de interrupción. Lync Server admite códecs tradicionales como G. 711, G. 722 y G. 723.1 para la interoperabilidad con las soluciones VoIP tradicionales.

Con el control de admisión de llamadas (CAC), los administradores pueden establecer límites en la cantidad de tráfico de voz y vídeo de Lync Server que se transporta en vínculos de red restringidos y especificar la acción que se realizará si una nueva llamada superará el límite. Las acciones pueden incluir el enrutamiento hacia una ruta alternativa o rechazar la llamada.

Lync Server funciona con aplicaciones de sucursal con funciones de supervivencia de terceros para proporcionar servicios de llamadas locales y conexiones a RTC en las sucursales, en caso de que se produzca un error de WAN en el sitio central.

</div>

</div>

<span> </span>

</div>

</div>

</div>

