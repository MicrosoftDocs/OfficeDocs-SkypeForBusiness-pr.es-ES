---
title: 'Lync Server 2013: Clientes compatibles con el grupo de respuesta'
TOCTitle: Clientes compatibles con el grupo de respuesta
ms:assetid: 84911025-e754-41a8-ba48-e31c058fc557
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398674(v=OCS.15)
ms:contentKeyID: 48275889
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Clientes compatibles con el grupo de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2014-03-28_

Aplicación de grupo de respuesta admite los siguientes clientes:

  - Cliente de escritorio de Lync 2013

  - Cliente de escritorio de Lync 2010

  - Operador de Lync 2010

  - Office Communications Server 2007 R2 Attendant

  - Lync Phone Edition


> [!NOTE]
> Aplicación de grupo de respuesta no es compatible con los clientes móviles de Lync.



Para obtener información sobre las características nuevas, consulte [Nuevas funciones de las aplicaciones de grupo de respuesta en Lync Server 2013](lync-server-2013-new-response-group-application-features.md) en la documentación de introducción.

El cliente concreto que puede usar depende del tipo de usuario de Grupo de respuesta que sea:

  - Los **autores de llamadas** pueden llamar a un grupo de respuesta mediante cualquiera de los clientes de la lista anterior y a través de un teléfono normal por la red telefónica conmutada (RTC).

  - Los **agentes informales** (agentes que no inician ni cierran sesión en sus grupos para aceptar llamadas) pueden aceptar llamadas mediante Operador, Lync o Lync Phone Edition. Los agentes informales inician sesión automáticamente en sus grupos al iniciar sesión en Lync Server 2013 mediante uno de estos clientes.

  - Los **agentes formales** (agentes que deben iniciar y cerrar sesión en sus grupos para poder aceptar llamadas) pueden aceptar llamadas usando Lync 2013 y accediendo a la consola del agente desde el elemento de menú o usando Operador y accediendo a la consola del agente directamente desde Internet Explorer.

