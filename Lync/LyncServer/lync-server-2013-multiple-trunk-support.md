---
title: 'Lync Server 2013: Compatibilidad con varios troncos'
TOCTitle: Compatibilidad con varios troncos
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48276244
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad con varios troncos en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

La función Lync Server 2013 admite múltiples asociaciones entre puertas de enlace y Servidores de mediación. Estas asociaciones se realizan definiendo un tronco, que es una asociación lógica entre un Grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), controlador de borde de sesión (SBC) o IP-PBX. Use Generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).

  - Para asignar o quitar un tronco en Lync Server 2013, primero debe definir un tronco en Generador de topologías. Un tronco consta de la siguiente asociación: Servidor de mediación FQDN, el puerto de escucha de Servidor de mediación, el nombre de dominio completo (FQDN) de la puerta de enlace y el puerto de escucha de la puerta de enlace.

  - Para configurar múltiples troncos, puede crear múltiples asociaciones entre la misma puerta de enlace y Servidor de mediación. Esto proporciona una resistencia adicional a la infraestructura de Telefonía IP empresarial, lo cual resulta especialmente útil en escenarios interoperativos de central de conmutación (PBX).

Cuando se define un tronco, debe estar asociado con una ruta. Para asociar un tronco con una ruta, se define un nombre sencillo para el tronco en Generador de topologías. Este nombre sencillo se usa como nombre del tronco en Panel de control de Lync Server, donde los troncos pueden asociarse con rutas. El nombre de tronco sencillo debe usarse como nombre de puerta de enlace desde Shell de administración de Lync Server.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

El administrador debe seleccionar un tronco predeterminado asociado con un Servidor de mediación. Desde Generador de topologías, haga clic con el botón secundario en el Servidor de mediación asociado y, a continuación, haga clic en **Propiedades** . Especifique la puerta de enlace predeterminada para el Servidor de mediación.

En el siguiente diagrama se ilustran los múltiples troncos que se han definido para cada Servidor de mediación y puerta de enlace.

**Enrutamiento de troncos M-N**

![Varias asignaciones de tronco.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Varias asignaciones de tronco.")

