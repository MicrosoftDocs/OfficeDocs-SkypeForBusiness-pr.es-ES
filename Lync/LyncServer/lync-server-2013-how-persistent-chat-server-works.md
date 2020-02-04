---
title: 'Lync Server 2013: Cómo funciona el servidor de chat persistente'
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
ms.openlocfilehash: 692f9a40bc2c0fd885fc251a4a792d480a69c57d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>Cómo funciona el servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-21_

Lync Server 2013, el servidor de chat persistente le permite participar en conversaciones con varias partes y basadas en temas que se conservan a lo largo del tiempo. El servidor de chat persistente puede ayudar a su organización a hacer lo siguiente:

  - Mejorar la comunicación entre equipos geográficamente dispersos y con varias funciones

  - Ampliar el conocimiento y la participación de la información

  - Mejorar la comunicación con su organización extendida

  - Reducir sobrecarga de información

  - Mejorar el conocimiento de la información

  - Aumentar la dispersión de información y conocimientos importantes

Puede implementar el servidor de chat persistente como un rol opcional con Lync Server 2013. Los servicios de chat persistente se ejecutan en un grupo dedicado y un grupo de servidores de chat persistente depende de un grupo de Lync Server para enrutar mensajes a él. Los clientes usan la comunicación de chats extensibles a través de SIP (XCCOS). Los servidores front-end de Lync Server están configurados para enrutar el tráfico a un grupo de servidores de chat persistente.

<div>

## <a name="high-level-architecture"></a>Arquitectura de alto nivel

Los siguientes diagramas proporcionan perspectivas de alto nivel de los servicios y la arquitectura del servidor de chat persistente.

**Arquitectura de alto nivel del servidor de chat persistente**

![Arquitectura del servidor de chat persistente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Arquitectura del servidor de chat persistente.")

**Servicios de alto nivel del servidor de chat persistente**

![Componentes del servidor de chat persistente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componentes del servidor de chat persistente.")

Se ejecutan dos servicios en los servidores front-end del servidor de chat persistente:

  - Chat persistente (canal)

  - Respeto

<div>

## <a name="persistent-chat-channel-service"></a>Servicio de chat persistente (canal)

El servicio de chat persistente (canal) es el servicio principal responsable del servidor de chat persistente. Este servicio ofrece las siguientes funciones:

  - Acepta mensajes entrantes

  - Registra y enumera los participantes en línea dentro de un salón de chat persistente

  - Retransmite mensajes a los suscriptores de otros canales

  - Implementa lógica para la administración de canales, la invitación a un salón de chat, una búsqueda y nuevas notificaciones de contenido

El servicio de chat persistente (canal) almacena y accede al contenido del salón de chat y otros metadatos del sistema (reglas de autorización, etc.) mediante el almacén de chats persistentes. Este servicio almacena los archivos cargados en salones de chat en el almacén de archivos de chat persistente.

</div>

<div>

## <a name="compliance-service"></a>Servicio de cumplimiento

El servicio de cumplimiento normativo es un componente opcional de un servidor de chat persistente y es el responsable de archivar el contenido y los eventos de chat en el almacén de cumplimiento persistente de la conversación. Si la organización cuenta con normas que precisan que se archive la actividad del chat persistente, puede implementar el servicio de cumplimiento opcional del chat persistente. El servicio de cumplimiento está instalado en cada servidor de chat persistente en un grupo de chats persistentes. Una vez configurado, el cumplimiento del servidor de chat persistente registra la actividad de los usuarios, como unirse a salas y abandonarlos, y publicar y leer los mensajes. El servicio de cumplimiento almacena los archivos que necesitan archivarse en el almacén de archivos de cumplimiento de chat persistente.

</div>

<div>

## <a name="persistent-chat-web-services"></a>Servicios Web de chat persistente

En los servidores front-end de Lync Server, se ejecutan dos servicios que dependen de Internet Information Services (IIS) y se implementan como componentes Web:

  - **Servicios Web de chat persistente para carga y descarga de archivos** Responsable de publicar y recuperar archivos de salones de chat.

  - **Servicios Web de chat persistente para la administración de salones de chat** Responsable de proporcionar a los usuarios la capacidad de administrar sus salones de chat y de crear nuevos salones de chat.

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>¿Cómo empiezo a usar el servidor de chat persistente?

El servidor de chat persistente es un rol de servidor opcional dentro de la infraestructura de Lync Server 2013. Si instala el rol de servidor de chat persistente, los usuarios que hayan habilitado la Directiva mediante un administrador pueden usar la conversación persistente con el cliente de Lync 2013.

Para obtener más información sobre cómo implementar el servidor de chat persistente y permitir que los usuarios aprovechen las funciones por directiva, consulte [implementar un servidor de chat persistente en Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Para obtener más información sobre cómo configurar las opciones de la implementación del servidor de chat persistente, consulte [implementar un servidor de chat persistente en Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) y [administrar Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md).

Para obtener detalles sobre cómo habilitar a los usuarios mediante directivas de modo que puedan aprovechar la funcionalidad de chat persistente en el cliente de Lync 2013, consulte [implementar el servidor de chat persistente en Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) y [administrar Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md).

Si ha implementado el cumplimiento persistente de la conversación, consulte [administrar Lync server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md) para obtener información sobre cómo configurar las opciones de cumplimiento.

</div>

<div>

## <a name="persistent-chat-call-flows"></a>Flujos de llamadas de chat persistentes

El cliente de chat persistente se comunica con el servicio de chat persistente usando XCCOS. Las siguientes secuencias describen el proceso de inicio de sesión y un escenario típico de suscripción a salas y mensajes.

<div>

## <a name="sign-in"></a>Inicio de sesión

El siguiente diagrama de flujo de llamadas y los pasos describen el proceso de inicio de sesión.

**Flujo de llamadas de inicio de sesión de clientes de chat persistente**

![Diagrama de flujo de llamadas del servidor de chat persistente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagrama de flujo de llamadas del servidor de chat persistente.")

1.  El cliente de chat persistente envía primero un SIP SUBSCRIBE para recuperar el documento de aprovisionamiento en banda del servidor. Este documento indica si el chat persistente está habilitado o deshabilitado para el usuario y la lista de URI de SIP para el grupo de servidores de chat persistente.

2.  El cliente de chat persistente envía un mensaje SIP INVITE al URI SIP del servidor de chat persistente que obtuvo en el paso anterior. La secuencia de invitación viene seguida de 200 aceptar y ACK, y el cliente de chat persistente ha abierto una sesión SIP con un extremo del servidor de chat persistente. Por lo tanto, el cliente de chat persistente se comunica con el servidor de chat persistente enviando mensajes de información SIP que contienen mensajes de chat o comandos que solicitan que el servidor realice una acción. Todos estos mensajes se confirman con el servicio 200 aceptar o 503, ya sea no disponible (es decir, en el caso de una carga pesada del servidor). Si el cliente recibe una respuesta de 503, se volverá a intentar el mensaje. (Este ejemplo no incluye una respuesta 503). Si el servidor acepta el mensaje o el comando y envía 200 aceptar, proporciona una respuesta al cliente en forma de mensaje de información SIP independiente. Esta respuesta incluye una referencia al comando de origen.

3.  El cliente de chat persistente envía un mensaje de información SIP que contiene el comando XCCOS **getServerInfo** . El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene información sobre la configuración del servicio de chat persistente.

4.  El cliente de chat persistente envía un mensaje de información SIP que contiene el comando XCCOS **getassociations** . El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene la lista de salas de las que es miembro el usuario. El cliente de chat persistente repite el comando para recuperar la lista de salas de las que el usuario es administrador.

5.  El cliente de chat persistente obtiene la lista de salones seguidos del documento "de presencia", en el que cada sala seguida está representada por una categoría "roomSetting". Todas las salas seguidas se unen mediante un solo mensaje SIP que contiene el XCCOS **búnete** que contiene la lista de URI de la sala. Dado que la lista de salas seguidas se guarda en el servidor, cualquier cliente en cualquier equipo tiene la misma lista de salones seguidos para el URI de usuario especificado. El cliente de chat persistente también mantiene la lista de salas abiertas (si el usuario ha habilitado esta opción) en el registro del equipo local y se une a cada una de estas salas al enviar un mensaje de información SIP que contiene el comando XCCOS **join** para cada sala abierta. Como esta lista se guarda en el registro, puede ser diferente en dos clientes de chat persistentes que se ejecutan en equipos diferentes.

6.  Para cada habitación Unido, el cliente de chat persistente envía un mensaje SIP INFO que contiene el comando XCCOS **bccontext** . El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene el mensaje de chat más reciente en el salón.

7.  El cliente de la conversación persistente envía un mensaje de información SIP que contiene un XCCOS **getinv** (es decir, obtener invitación) para solicitar nuevas invitaciones Room que el cliente aún no ha visto. En un mensaje de información SIP independiente, el servidor de chat persistente devuelve una lista de esas salas.

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>Suscribirse a una sala y publicar un mensaje

El siguiente diagrama de flujo de llamadas y los pasos describen un escenario típico de suscripción a un salón y mensaje.

**Suscripción al salón del cliente de chat persistente y flujo de llamadas de publicación de mensajes**

![Suscripción al salón y mensaje postescenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Suscripción al salón y mensaje postescenario.")

1.  Desde el cliente de chat persistente, usuario1 hace clic en **unirse a un salón de chat**, hace clic en **Buscar**y, a continuación, escribe algunos criterios de búsqueda. El cliente de chat persistente envía un mensaje SIP INFO que contiene el comando XCCOS **chansrch** (búsqueda de la sala) junto con los criterios de búsqueda. El servidor de chat persistente consulta la base de datos back-end y responde en un mensaje de información SIP nueva que contiene una lista de las salas disponibles que cumplen los criterios de búsqueda.

2.  Usuario1 selecciona el salón de chat al que desea unirse y, a continuación, hace clic en **seguir este salón**. El cliente de la conversación persistente envía un mensaje SIP INFO que contiene el comando XCCOS **join** y el identificador Room del salón de chat que seleccionó el usuario. El servidor de chat persistente responde con un mensaje de información SIP que contiene los datos de aprovisionamiento.

3.  El cliente de la conversación persistente envía un mensaje de información SIP que contiene el XCCOS **bccontext** (contexto de chat). El servidor de chat persistente recupera el historial de chats y lo devuelve al cliente de chat persistente en un mensaje SIP independiente. En este punto, el usuario entra en el salón de chat y está listo para participar.

4.  Usuario1 escribe un nuevo mensaje y, a continuación, hace clic en **Enviar**. El cliente de chat persistente publica el mensaje en el salón de chat en un comando SIP INFO XCCOS **grpchat** . El servidor de chat persistente almacena una copia de este mensaje nuevo en la base de datos back-end de chat persistente.

5.  El servidor de chat persistente envía una copia separada del mensaje SIP INFO XCCOS **grpchat** a user2, que ya ha entrado en el salón de chat.

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>Flujos de llamada de cumplimiento de chat persistente

El servidor de chat persistente usa Message Queue Server (también conocido como MSMQ) y una base de datos de cumplimiento adicional (mgccomp) para procesar los datos de cumplimiento. Como ejemplo de cómo se procesan los eventos de conformidad, la siguiente secuencia de eventos describe cómo se procesa un evento de exposición de mensajes.

1.  Un usuario publica un mensaje en un salón.

2.  El servidor de chat persistente coloca información relacionada con el evento en una cola privada de Message Queue Server.

3.  El servidor de cumplimiento de chat persistente Lee este evento en la cola y lo coloca en la base de datos mgccomp para su procesamiento posterior.

4.  Periódicamente, el servidor de cumplimiento de chat persistente procesa un conjunto de eventos en la base de datos y los envía al adaptador de cumplimiento de chat persistente para su procesamiento.

5.  Si el adaptador procesa correctamente los datos, el servidor de cumplimiento de chat persistente elimina los eventos de la base de datos de mgccomp.

</div>

</div>

<span> </span>

</div>

</div>

</div>

