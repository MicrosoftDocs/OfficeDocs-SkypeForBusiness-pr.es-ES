---
title: 'Lync Server 2013: Crear grupos de agentes de grupos de respuesta'
TOCTitle: Crear grupos de agentes de grupos de respuesta
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48274756
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear grupos de agentes de grupos de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-12_

Cuando se crea un grupo de agentes, se seleccionan los agentes que se asignan al grupo y se especifica la configuración de grupo adicional, como el método de enrutamiento y si un agente puede iniciar y cerrar sesión en el grupo.

Al agente que debe iniciar y cerrar sesión en el grupo (que no es lo mismo que iniciar o cerrar sesión en Lync Server) se le conoce como *agente formal* . Los agentes formales deben iniciar sesión en el grupo para poder recibir llamadas enrutadas al grupo. Esto puede resultar útil para los agentes que atienden llamadas del grupo a media jornada. Los agentes formales inician y cierran la sesión de sus grupos haciendo clic en un elemento de menú de Lync 2013 para abrir el explorador de Internet de Windows Internet Explorer y mostrar la consola de una página web.

Un agente que no inicia ni cierra sesión en el grupo recibe el nombre de *agente informal* . Los agentes informales se conectan automáticamente al grupo cuando inician sesión en Lync Server y no pueden cerrar la sesión del grupo.


> [!NOTE]
> Solo los usuarios locales pueden ser agentes. Si un agente local pasa a estar en línea, las llamadas de la Grupo de respuesta no se enrutarán a dicho agente.



## En esta sección

[Crear o modificar un grupo de agentes en Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

