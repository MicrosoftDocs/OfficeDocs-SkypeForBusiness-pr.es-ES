---
title: Administración de grupos de agente de grupos de respuesta en Lync Server 2013
TOCTitle: Administración de grupos de agente de grupos de respuesta en Lync Server 2013
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48274926
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administración de grupos de agente de grupos de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-01_

Un grupo de agentes consiste en un grupo de personas designado para responder llamadas de un grupo de respuesta. Cuando se crea un grupo de agentes, se seleccionan los agentes que se asignan al grupo y se especifica la configuración de grupo adicional, como el método de enrutamiento y si un agente puede iniciar y cerrar sesión en el grupo.


> [!NOTE]
> Los usuarios deben estar habilitados para Telefonía IP empresarial antes de poder agregarlos a grupos de agentes. Para obtener más información acerca de cómo habilitar a un usuario para Telefonía IP empresarial, vea <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013</A>.




> [!NOTE]
> Solo los usuarios locales pueden ser agentes. Si un agente deja de ser local para estar en línea, las llamadas al grupo de respuesta no se enrutarán a dicho agente.



Un agente que debe iniciar y cerrar sesión en el grupo, que no es lo mismo que iniciar o cerrar sesión en Lync Server, recibe el nombre de *agente formal*. Los agentes formales deben iniciar sesión en el grupo para poder recibir llamadas enrutadas al grupo. Esto puede resultar útil para los agentes que atienden llamadas del grupo a media jornada. Los agentes formales inician y cierran la sesión de sus grupos mediante un clic en un elemento de menú de Lync 2013 para abrir el explorador de Internet Microsoft Internet Explorer y mostrar la consola de una página web.

Un agente que no inicia ni cierra sesión en el grupo recibe el nombre de *agente informal*. Los agentes informales se conectan automáticamente al grupo cuando inician sesión en Lync Server y no pueden cerrar la sesión del grupo.

> [!IMPORTANT]  
> Cuando asigne usuarios como agentes de grupo de respuesta, indíqueles que, si tienen habilitado el modo de privacidad, deberán buscar contactos de &quot;Observador de presencia de RGS&quot; y agregarlos a su lista de contactos. Los agentes que tengan el modo de privacidad habilitado, pero que no tengan &quot;Observador de presencia RGS&quot; en su lista de contactos no podrán recibir llamadas en el grupo de respuesta. Los agentes que no tengan habilitado el modo de privacidad, no se verán afectados.



## En esta sección

  - [Crear o modificar un grupo de agentes en Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Eliminar un grupo de agentes de Lync Server 2013](lync-server-2013-delete-an-agent-group.md)

