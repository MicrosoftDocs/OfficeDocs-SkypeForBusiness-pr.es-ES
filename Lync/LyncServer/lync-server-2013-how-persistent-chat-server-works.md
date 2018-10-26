---
title: Funcionamiento del servidor de chat persistente en Lync Server 2013
TOCTitle: Funcionamiento del servidor de chat persistente en Lync Server 2013
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49889052
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Funcionamiento del servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-21_

Lync Server 2013, Servidor de chat persistente le permite participar en conversaciones basadas en temas con varios participantes que persisten a lo largo del tiempo. Servidor de chat persistente puede ayudar a la organización a hacer lo siguiente:

  - Mejorar la comunicación entre equipos geográficamente dispersos y multifuncionales

  - Ampliar el uso de la información y la participación

  - Mejorar la comunicación con la organización extendida

  - Reducir la sobrecarga de la información

  - Mejorar el uso de la información

  - Aumentar la divulgación de información y conocimientos importantes

Puede implementar Servidor de chat persistente como un rol opcional con Lync Server 2013. Los servicios de Chat persistente se ejecutan en un grupo de servidores dedicados, y un Grupo de servidores de chat persistente depende de que un grupo de servidores Lync Server le enrute mensajes. Los clientes utilizan eXtensible Chat Communication Over SIP (XCCOS). Los Lync ServerServidores front-end se configuran para que enruten el tráfico a un Grupo de servidores de chat persistente.

## Arquitectura de alto nivel

El siguiente diagrama proporciona perspectivas de alto nivel de los servicios y la arquitectura de Servidor de chat persistente.

**Arquitectura de alto nivel del servidor de chat persistente**

![Arquitectura del servidor de chat persistente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Arquitectura del servidor de chat persistente.")

**Servicios de alto nivel del servidor de chat persistente**

![Componentes del servidor de chat persistente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componentes del servidor de chat persistente.")

Dos servicios se ejecutan en el Servidor de chat persistenteServidores front-end:

  - Chat persistente (Canal)

  - Cumplimiento

## Servicio de chat persistente (Canal)

El servicio (Canal) de Chat persistente es el servicio central responsable de Servidor de chat persistente. Este servicio proporciona las siguientes funciones:

  - Acepta mensajes entrantes

  - Registra y enumera los participantes en línea dentro de una sala de Chat persistente

  - Retransmite mensajes a los suscriptores de otros canales

  - Implementa la lógica para la administración del canal, la invitación a una sala de chat, las búsquedas y las notificaciones de nuevo contenido

El servicio (Canal) de Chat persistente almacena el contenido de la sala de chat y otros metadatos del sistema (reglas de autorización, entre otros) y accede a ellos utilizando el Almacén de Chat persistente. Este servicio almacena archivos que se cargan en salas de chat en el Almacén de archivos de Chat persistente.

## Servicio de Cumplimiento

El servicio de Cumplimiento es un componente opcional de Servidor de chat persistente y es responsable de archivar eventos y contenido de chat en el Almacén de Cumplimiento de Chat persistente. Si su organización tiene normativas que requieren que se archive la actividad de Chat persistente, puede implementar el servicio de Cumplimiento Chat persistente opcional. El servicio de Cumplimiento se instala en cada Servidor de chat persistente en un grupo de servidores de Chat persistente. Al configurarse, el cumplimiento de Servidor de chat persistente registra la actividad de usuario como la conexión y desconexión de salas y la publicación y lectura de mensajes. El servicio de Cumplimiento almacena archivos que deben ser archivados en el Almacén de archivos de Cumplimiento de Chat persistente.

## Servicios web de Chat persistente

En los Lync ServerServidores front-end, se ejecutan dos servicios que dependen de Servicios de Internet Information Server (IIS) y se implementan como componentes web:

  - **Chat persistente Servicios web para cargar y descargar archivos** Responsable de publicar archivos y recuperarlos de las salas de chat.

  - **Chat persistente Servicios web para la administración de salas de chat** Responsable de brindar a los usuarios la capacidad de administrar sus salas de chat y de crear nuevas salas de chat.

## ¿Cómo empezar a utilizar Servidor de chat persistente?

Servidor de chat persistente es un rol de servidor opcional dentro de la infraestructura de Lync Server 2013. Si instala el rol Servidor de chat persistente, cualquier usuario que haya sido habilitado por un administrador a través de directivas puede utilizar Chat persistente con el cliente Lync 2013. Para obtener detalles sobre cómo implementar Servidor de chat persistente y permitir a los usuarios aprovechar las capacidades a través de directivas, consulte [Implementar el servidor de chat persistente en Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Para obtener detalles sobre cómo configurar los parámetros en su implementación de Servidor de chat persistente, consulte [Implementar el servidor de chat persistente en Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) y [Administrar el servidor de chat persistente de Lync Server 2013](managing-lync-server-2013-persistent-chat-server.md).

Para obtener detalles sobre cómo habilitar a los usuarios a través de directivas de modo tal que puedan aprovechar las capacidades de Chat persistente en el cliente Lync 2013, consulte [Implementar el servidor de chat persistente en Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) y [Administrar el servidor de chat persistente de Lync Server 2013](managing-lync-server-2013-persistent-chat-server.md).

Si implementó el cumplimiento de Chat persistente, consulte [Administrar el servidor de chat persistente de Lync Server 2013](managing-lync-server-2013-persistent-chat-server.md) para obtener detalles sobre cómo configurar los parámetros para el cumplimiento.

## Flujos de llamadas de Chat persistente

El cliente de Lync se comunica con el servicio de Chat persistente utilizando XCCOS. Las siguientes secuencias describen el proceso de inicio de sesión y un escenario típico de suscripción a la sala y de publicación de mensaje.

## Inicio de sesión

La siguiente secuencia describe el proceso de inicio de sesión.

1.  El cliente Lync primero envía un SIP SUBSCRIBE para recuperar el documento de aprovisionamiento en banda del servidor. Este documento indica si Chat persistente está habilitado o deshabilitado para el usuario y la lista de URI de SIP para el Grupo de servidores de chat persistente.

2.  El cliente Lync envía un mensaje SIP INVITE al URI de SIP del Servidor de chat persistente que obtuvo en el paso anterior. Luego de la secuencia INVITE sigue 200 OK y ACK, y el cliente Lync ha abierto ahora una sesión SIP con un extremo de Servidor de chat persistente. En consecuencia, el cliente se comunica con Servidor de chat persistente enviando mensajes SIP INFO que contienen mensajes de chat o comandos que solicitan al servidor que actúe. Todos estos mensajes son reconocidos con 200 OK o 503 Service Unavailable (es decir, en caso de fuertes carga de servidor). Si el cliente recibe una respuesta 503, volverá a intentar el mensaje. (Este ejemplo no incluye una respuesta 503). Si el servidor acepta el mensaje o comando y envía 200 OK, brinda una respuesta al cliente como mensaje SIP INFO independiente. Esta respuesta incluye una referencia al comando original.

3.  El cliente Lync envía un mensaje SIP INFO que contiene el comando **getserverinfo** de XCCOS. Servidor de chat persistente responde con un nuevo mensaje SIP INFO que contiene información sobre la configuración del servicio de Chat persistente.

4.  El cliente Lync envía un mensaje SIP INFO que contiene el comando **getassociations** de XCCOS. Servidor de chat persistente responde con un nuevo mensaje SIP INFO que contiene la lista de salas de las cuales es miembro el usuario. El cliente Lync repite el comando para recuperar la lista de salas de las cuales es administrador el usuario.

5.  El cliente Lync recibe la lista de salas seguidas del documento de "presencia", donde cada sala seguida se representa con una categoría "roomSetting". Todas las salas seguidas están unidas por un único mensaje SIP INFO que contiene el comando **bjoin** de XCCOS que contiene la lista de URI de las salas. Puesto que la lista de salas seguidas se guarda en el servidor, cualquier cliente desde cualquier equipo tiene la misma lista de salas seguidas para el URI de usuario especificado. El cliente Lync también guarda la lista de salas abiertas (si esta opción está habilitada por el usuario) en el registro del equipo local y se une a cada una de estas salas al iniciar sesión enviando un mensaje SIP INFO que contiene el comando **join** XCCOS para cada sala abierta. Puesto que esta lista se guarda en el registro, puede ser distinta en dos clientes Lync que se ejecuten en diferentes equipos.

6.  Por cada sala a la que se ha unido, el cliente Lync envía un mensaje SIP INFO que contiene el comando **bccontext** de XCCOS. Servidor de chat persistente responde con un nuevo mensaje SIP INFO que contiene el mensaje de chat más reciente de la sala.

7.  El cliente Lync envía un mensaje SIP INFO que contiene un comando **getinv** (es decir, recibir invitación) de XCCOS para solicitar cualquier nueva invitación de salas que el cliente aún no ha visto. En un mensaje SIP INFO independiente, Servidor de chat persistente devuelve una lista de esas salas.

## Suscribirse a una sala y publicar un mensaje

La siguiente secuencia describe un escenario típico de suscripción a una sala y publicación de un mensaje.

1.  Desde el cliente Lync, Usuario1 hace clic en **Conectarse a una sala de chat**, hace clic en **Buscar** y luego introduce algún criterio de búsqueda. El cliente envía un mensaje SIP INFO que contiene el comando **chansrch** (búsqueda de sala) de XCCOS, junto con los criterios de búsqueda. Servidor de chat persistente realiza consultas en la base de datos back-end y responde en un nuevo mensaje SIP INFO que contiene una lista de salas disponibles que cumplen con los criterios de búsqueda.

2.  Usuario1 selecciona la sala de chat a la que desea conectarse y luego hace clic en **Seguir esta sala**. El cliente envía Servidor de chat persistente un mensaje SIP INFO que contiene el comando **join** de XCCOS y el identificador de sala de la sala de chat que seleccionó el usuario. Servidor de chat persistente responde con un mensaje SIP INFO que contiene los datos de aprovisionamiento.

3.  El cliente Lync envía Servidor de chat persistente un mensaje SIP INFO que contiene el comando **bccontext** (contexto de backchat) de XCCOS. Servidor de chat persistente recupera el historial de chat y lo devuelve al cliente en un mensaje SIP INFO independiente. En este momento, el usuario ingresa a la sala de chat y está listo para participar.

4.  Usuario1 introduce un nuevo mensaje y luego hace clic en **Enviar**. El cliente Lync publica el mensaje en la sala de chat en un mensaje SIP INFO con el comando **grpchat** de XCCOS. Servidor de chat persistente almacena una copia de este nuevo mensaje en la base de datos back-end Chat persistente.

5.  Servidor de chat persistente envía una copia independiente del mensaje SIP INFO con el comando **grpchat** de XCCOS al Usuario2, que ya ha ingresado a la sala de chat.

## Flujos de llamadas de Cumplimiento de Chat persistente

Servidor de chat persistente utiliza Message Queuing (también conocido como MSMQ) y una base de datos de cumplimiento adicional (mgccomp) para procesar los datos de cumplimiento. Como ejemplo de cómo se procesan los eventos de cumplimiento, la siguiente secuencia de eventos describe cómo se procesa un evento de publicación de mensaje.

1.  Un usuario publica un mensaje en una sala.

2.  Servidor de chat persistente coloca información relacionada con el evento en una cola privada de Message Queuing.

3.  El servidor de Cumplimiento de Chat persistente lee este evento desde la cola y lo coloca en la base de datos mgccomp para que sea procesado posteriormente.

4.  Periódicamente, el servidor de Cumplimiento de Chat persistente procesa una serie de eventos de la base de datos y los envía al adaptador de Cumplimiento de Chat persistente para que sean procesados.

5.  Si el adaptador procesa los datos correctamente, el servidor de Cumplimiento de Chat persistente elimina los eventos de la base de datos mgccomp.

