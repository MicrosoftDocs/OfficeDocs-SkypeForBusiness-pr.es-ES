---
title: 'Lync Server 2013: Nuevas funciones de las aplicaciones de grupo de respuesta'
TOCTitle: Nuevas funciones de las aplicaciones de grupo de respuesta
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48275294
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nuevas funciones de las aplicaciones de grupo de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-29_

La aplicación de grupo de respuesta permite enrutar y poner en cola llamadas entrantes para personas designadas para fines especiales, como el servicio al cliente, un servicio de asistencia interno o un teléfono general de asistencia para un departamento.

Las siguientes características de la aplicación de grupo de respuesta son nuevas en Lync Server 2013:

  - **Rol de administrador**
    
    Lync Server 2013 presenta un nuevo rol de administrador de Grupo de respuesta. Ahora hay dos funciones de administración de grupos de respuesta: director de Grupo de respuesta y administrador de Grupo de respuesta. Mientras que los administradores de Grupo de respuesta todavía pueden configurar cualquier elemento de cualquier grupo de respuesta, los directores pueden configurar solo ciertos elementos, solo de los grupos de respuesta de los que son propietarios.
    
    Esta mejora en el modelo de administración beneficia la escalabilidad del grupo de respuesta, especialmente en los escenarios de grandes implementaciones.

  - **Alta disponibilidad**
    
    Se admite la alta disponibilidad en Aplicación de grupo de respuesta, en forma de reflejo de SQL Server, está habilitada como parte de la configuración general de la implementación de alta disponibilidad de Lync Server 2013. Si configura para alta disponibilidad y pierde la conectividad con el servidor back-end principal, el aprovechamiento del servidor reflejado no afecta a las funciones del grupo de respuesta.
    
    La compatibilidad de la creación de reflejos de SQL Server en el Aplicación de grupo de respuesta no se puede habilitar o configurar de manera individual fuera de la configuración general de alta disponibilidad de Lync Server 2013.

  - **Recuperación ante desastres**
    
    La compatibilidad de recuperación ante desastres para la Aplicación de grupo de respuesta está habilitada como parte de la configuración e implementación de los pares de Grupos de servidores front-end, que forman parte de la configuración de recuperación ante desastres de Lync Server 2013 general. Además, los cmdlets de importación y exportación de grupos de respuesta admiten el proceso de conmutación por error al grupo de copia de seguridad y el proceso de conmutación por recuperación al grupo principal o a un nuevo grupo. Si se produce una interrupción en el grupo principal, los grupos de respuesta pueden conmutarse por error al grupo de copia de seguridad y luego conmutarse por recuperación al grupo principal o a un nuevo grupo cuando finalice la interrupción.

## Vea también

#### Otros recursos

[Planificar para grupos de respuesta en Lync Server 2013](lync-server-2013-planning-for-response-groups.md)

