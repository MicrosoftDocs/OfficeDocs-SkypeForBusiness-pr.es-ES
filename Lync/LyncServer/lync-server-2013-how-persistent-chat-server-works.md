---
title: 'Lync Server 2013: funcionamiento del servidor de chat persistente'
description: 'Lync Server 2013: Cómo funciona el servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c65df6a13305f75a8a25b85a39688fadf64e476c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562966"
---
# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>Cómo funciona el servidor de chat persistente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-21_

Lync Server 2013, el servidor de chat persistente permite participar en conversaciones basadas en temas con varios participantes que persisten a lo largo del tiempo. El servidor de chat persistente puede ayudar a su organización a hacer lo siguiente:

  - Mejorar la comunicación entre equipos geográficamente dispersos y multifuncionales

  - Ampliar el uso de la información y la participación

  - Mejorar la comunicación con la organización extendida

  - Reducir la sobrecarga de la información

  - Mejorar el uso de la información

  - Aumentar la divulgación de información y conocimientos importantes

Puede implementar el servidor de chat persistente como un rol opcional con Lync Server 2013. Los servicios de chat persistente se ejecutan en un grupo dedicado y un grupo de servidores de chat persistente depende de un grupo de Lync Server para enrutar mensajes a él. Los clientes utilizan eXtensible Chat Communication Over SIP (XCCOS). Los servidores front-end de Lync Server están configurados para enrutar el tráfico a un grupo de servidores de chat persistente.

<div>

## <a name="high-level-architecture"></a>Arquitectura de alto nivel

En los siguientes diagramas se proporcionan perspectivas de alto nivel de los servicios y la arquitectura del servidor de chat persistente.

**Arquitectura de alto nivel del servidor de chat persistente**

![Arquitectura del servidor de chat persistente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Arquitectura del servidor de chat persistente.")

**Servicios de alto nivel del servidor de chat persistente**

![Componentes del servidor de chat persistente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componentes del servidor de chat persistente.")

Se ejecutan dos servicios en los servidores front-end del servidor de chat persistente:

  - Chat persistente (Canal)

  - Cumplimiento

<div>

## <a name="persistent-chat-channel-service"></a>Servicio de chat persistente (Canal)

El servicio de chat persistente (canal) es el servicio principal responsable del servidor de chat persistente. Este servicio proporciona las siguientes funciones:

  - Acepta mensajes entrantes

  - Registra y enumera los participantes en línea dentro de un salón de chat persistente

  - Retransmite mensajes a los suscriptores de otros canales

  - Implementa la lógica para la administración del canal, la invitación a una sala de chat, las búsquedas y las notificaciones de nuevo contenido

El servicio de chat persistente (canal) almacena y accede al contenido del salón de chat y otros metadatos del sistema (reglas de autorización, etc.) mediante el almacén de chat persistente. Este servicio almacena los archivos que se cargan en salones de chat en el almacén de archivos de chat persistente.

</div>

<div>

## <a name="compliance-service"></a>Servicio de Cumplimiento

El servicio de cumplimiento es un componente opcional del servidor de chat persistente y es responsable de archivar el contenido y los eventos de chat en el almacén de cumplimiento de chat persistente. Si su organización tiene regulaciones que requieran que se Archive la actividad de chat persistente, puede implementar el servicio opcional de cumplimiento de chat persistente. El servicio de cumplimiento se instala en cada servidor de chat persistente en un grupo de chat persistente. Cuando se configura, el cumplimiento del servidor de chat persistente registra la actividad de los usuarios, como unirse y abandonar salas, y publicar y leer los mensajes. El servicio de cumplimiento almacena los archivos que se deben archivar en el almacén de archivos de cumplimiento de chat persistente.

</div>

<div>

## <a name="persistent-chat-web-services"></a>Servicios Web de chat persistente

En los servidores front-end de Lync Server, se ejecutan dos servicios que dependen de Internet Information Services (IIS) y se implementan como componentes Web:

  - **Servicios Web de chat persistente para la carga y descarga de archivos** Responsable de publicar y recuperar archivos de salones de chat.

  - **Servicios Web de chat persistente para la administración de salones de chat** Responsable de ofrecer a los usuarios la capacidad de administrar sus salones de chat y crear nuevos salones de chat.

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>¿Cómo puedo empezar a usar el servidor de chat persistente?

El servidor de chat persistente es un rol de servidor opcional dentro de la infraestructura de Lync Server 2013. Si instala el rol de servidor de chat persistente, todos los usuarios que hayan sido habilitados mediante la Directiva por un administrador pueden usar chat persistente con el cliente de Lync 2013.

Para obtener más información sobre cómo implementar el servidor de chat persistente y permitir a los usuarios aprovechar las funciones por directiva, consulte [Deploying persistent chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Para obtener más información sobre cómo configurar las opciones en la implementación del servidor de chat persistente, consulte [Deploying persistent chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) y [Managing Lync Server 2013, persistent chat Server](managing-lync-server-2013-persistent-chat-server.md).

Para obtener información detallada sobre cómo habilitar a los usuarios mediante directivas de modo que puedan aprovechar la funcionalidad de chat persistente en el cliente de Lync 2013, consulte [Deploying persistent chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) y [Managing Lync Server 2013, persistent chat Server](managing-lync-server-2013-persistent-chat-server.md).

Si ha implementado el cumplimiento de chat persistente, consulte [Managing Lync server 2013, persistent chat Server](managing-lync-server-2013-persistent-chat-server.md) para obtener más información sobre cómo configurar las opciones para el cumplimiento normativo.

</div>

<div>

## <a name="persistent-chat-call-flows"></a>Flujos de llamadas de chat persistente

El cliente de chat persistente se comunica con el servicio de chat persistente mediante XCCOS. Las siguientes secuencias describen el proceso de inicio de sesión y un escenario típico de suscripción a la sala y de publicación de mensaje.

<div>

## <a name="sign-in"></a>Inicio de sesión

El siguiente diagrama de flujo de llamadas y los pasos describen el proceso de inicio de sesión.

**Flujo de llamadas de inicio de sesión de cliente de chat persistente**

![Diagrama de flujo de llamadas del servidor de chat persistente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagrama de flujo de llamadas del servidor de chat persistente.")

1.  El cliente de chat persistente envía primero un SIP SUBSCRIBE para recuperar el documento de aprovisionamiento en banda del servidor. Este documento indica si el chat persistente está habilitado o deshabilitado para el usuario y la lista de URI de SIP para el grupo de servidores de chat persistente.

2.  El cliente de chat persistente envía un mensaje SIP INVITE al URI del SIP del servidor de chat persistente que obtuvo en el paso anterior. La secuencia de invitación va seguida de 200 aceptar y ACK, y el cliente de chat persistente ahora ha abierto una sesión SIP con un extremo del servidor de chat persistente. Por lo tanto, el cliente de chat persistente se comunica con el servidor de chat persistente mediante el envío de mensajes de información SIP que contienen mensajes de chat o comandos que solicitan al servidor que realice una acción. Todos estos mensajes son reconocidos con 200 OK o 503 Service Unavailable (es decir, en caso de fuertes carga de servidor). Si el cliente recibe una respuesta 503, volverá a intentar el mensaje. (En este ejemplo no se incluye una respuesta 503). Si el servidor acepta el mensaje o el comando y envía 200 aceptar, proporciona una respuesta al cliente en forma de un mensaje SIP independiente. Esta respuesta incluye una referencia al comando original.

3.  El cliente de chat persistente envía un mensaje de información SIP que contiene el comando XCCOS **getServerInfo** . El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene información sobre la configuración del servicio de chat persistente.

4.  El cliente de chat persistente envía un mensaje de información SIP que contiene el comando XCCOS **getassociations** . El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene la lista de salas de las que el usuario es miembro. El cliente de chat persistente repite el comando para recuperar la lista de salas de las que el usuario es administrador.

5.  El cliente de chat persistente obtiene la lista de salones seguidos del documento "Presence", donde cada salón seguido está representado por una categoría "roomSetting". Todas las salas seguidas están unidas por un único mensaje SIP INFO que contiene el comando **bjoin** de XCCOS que contiene la lista de URI de las salas. Puesto que la lista de salas seguidas se guarda en el servidor, cualquier cliente desde cualquier equipo tiene la misma lista de salas seguidas para el URI de usuario especificado. El cliente de chat persistente también mantiene la lista de salones abiertos (si el usuario ha habilitado esta opción) en el registro del equipo local y combina cada uno de estos salones en el inicio de sesión mediante el envío de un mensaje de información SIP que contiene el comando XCCOS **join** para cada salón abierto. Como esta lista se guarda en el registro, puede ser diferente en dos clientes de chat persistente que se ejecutan en equipos diferentes.

6.  Para cada habitación que se une, el cliente de chat persistente envía un mensaje de información SIP que contiene el comando XCCOS **bccontext** . El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene el mensaje de chat más reciente en el salón.

7.  El cliente de chat persistente envía un mensaje de información SIP que contiene un comando XCCOS **getinv** (es decir, obtener invitación) para solicitar nuevas invitaciones Room que el cliente todavía no ha visto. En un mensaje de información SIP independiente, el servidor de chat persistente devuelve una lista de estas salas.

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>Suscribirse a una sala y publicar un mensaje

El siguiente diagrama de flujo de llamadas y los pasos describen una suscripción de salón típica y un escenario de exposición de mensajes.

**Suscripción de salón de cliente de chat persistente y flujo de llamada de registro de mensajes**

![Suscripción a salas y escenario de exposición de mensajes.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Suscripción a salas y escenario de exposición de mensajes.")

1.  Desde el cliente de chat persistente, user1 hace clic en **unirse a un salón de chat**, hace clic en **Buscar**y, a continuación, escribe algunos criterios de búsqueda. El cliente de chat persistente envía un mensaje SIP INFO que contiene el comando XCCOS **chansrch** (Search Room), junto con los criterios de búsqueda. El servidor de chat persistente consulta la base de datos back-end y responde en un nuevo mensaje de información SIP que contiene una lista de salones disponibles que cumplen con los criterios de búsqueda.

2.  Usuario1 selecciona la sala de chat a la que desea conectarse y luego hace clic en **Seguir esta sala**. El cliente de chat persistente envía un mensaje SIP información del servidor de chat persistente que contiene el comando XCCOS **join** y el identificador de sala del salón de chat que seleccionó el usuario. El servidor de chat persistente responde con un mensaje de información SIP que contiene los datos de aprovisionamiento.

3.  El cliente de chat persistente envía un mensaje SIP información del servidor de chat persistente que contiene el comando XCCOS **bccontext** (contexto de mi chat). El servidor de chat persistente recupera el historial de chats y lo devuelve al cliente de chat persistente en un mensaje SIP independiente. En este momento, el usuario ingresa a la sala de chat y está listo para participar.

4.  Usuario1 introduce un nuevo mensaje y luego hace clic en **Enviar**. El cliente de chat persistente publica el mensaje en el salón de chat en un comando SIP información XCCOS **grpchat** . El servidor de chat persistente almacena una copia de este nuevo mensaje en la base de datos back-end de chat persistente.

5.  El servidor de chat persistente envía una copia independiente del mensaje SIP información XCCOS **grpchat** a user2, que ya ha entrado en el salón de chat.

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>Flujos de llamadas de cumplimiento de chat persistente

El servidor de chat persistente usa Message Queue Server (también conocido como MSMQ) y una base de datos de cumplimiento adicional (mgccomp) para procesar los datos de cumplimiento. Como ejemplo de cómo se procesan los eventos de cumplimiento, la siguiente secuencia de eventos describe cómo se procesa un evento de publicación de mensaje.

1.  Un usuario publica un mensaje en una sala.

2.  El servidor de chat persistente coloca información relativa al evento en una cola privada de Message Queue Server.

3.  El servidor de cumplimiento de chat persistente Lee este evento de la cola y lo coloca en la base de datos de mgccomp para su procesamiento posterior.

4.  Periódicamente, el servidor de cumplimiento de chat persistente procesa un conjunto de eventos en la base de datos y los envía al adaptador de cumplimiento de chat persistente para su procesamiento.

5.  Si el adaptador procesa los datos correctamente, el servidor de cumplimiento de chat persistente elimina los eventos de la base de datos de mgccomp.

</div>

</div>

<span> </span>

</div>

</div>

</div>

