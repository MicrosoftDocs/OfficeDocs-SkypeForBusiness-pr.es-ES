---
title: 'Lync Server 2013: Recuperación ante desastres del servidor perimetral'
TOCTitle: Recuperación ante desastres del servidor perimetral
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49888795
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Recuperación ante desastres del servidor perimetral en Lync Server 2013

 

_**Última modificación del tema:** 2014-03-12_

Como con otros roles de servidor, la mejor manera que tiene de proporcionar alta disponibilidad para sus servidores perimetrales es implementar varios servidores perimetrales en grupos de servidores en cada sitio. Si un servidor perimetral deja de funcionar, los demás servidores del grupo de servidores continuarán proporcionando servicios perimetrales.

Para habilitar los procedimientos de recuperación ante desastres, debe tener grupos de servidores perimetrales implementados en sitios independientes. No tiene que emparejar explícitamente grupos de servidores perimetrales como hace con grupos de servidores front-end, pero tener varios grupos de servidores perimetrales ofrece todavía la disponibilidad de continuar si un grupo de servidores perimetrales completo dejar de funcionar. Las secciones siguientes proporcionan detalles sobre la recuperación ante desastres para las distintas funciones de los servidores perimetrales.

## Acceso remoto

Si tiene varios sitios, cada uno de ellos con un grupo de servidores perimetrales, y se produce un error de un grupo de servidores perimetrales completo, los servicios de acceso remoto continuarán funcionando sin necesitar acciones de administrador. Cuando se crean grupos de servidores perimetrales en diferentes sitios, no se puede usar el mismo FQDN, sino que cada grupo de servidores perimetrales debe tener un FQDN único (en el ámbito interno y externo). Los servidores de grupos perimetrales no utilizan reglas de publicación de proxy inverso para comunicarse con los servidores de Front End. Cuando el cliente repite la solicitud de registros de servicio de DNS de acceso remoto se produce la conmutación por error y se enruta a los usuarios remotos a los servidores perimetrales de otro sitio. El cliente prueba con cada FQDN perimetral externo conforme con la prioridad de los registros SRV de DNS.


> [!NOTE]
> Para que la conmutación por error se realice de forma imperceptible, compruebe que el firewall permite a los servidores front-end de todos los grupos de servidores comunicarse con todos los servidores perimetrales.



## Federación

Para relaciones de federación con otras organizaciones que ejecutan Lync Server, las solicitudes de federación entrantes seguirán funcionando, siempre y cuando haya configurado cada grupo de servidores perimetrales de manera que tengan una prioridad diferente en sus registros SRV. Cualquier solicitud de federación que vaya a un grupo de servidores perimetrales que ha dejado de funcionar devolverá un error y, a continuación, se conectará a un grupo de servidores perimetrales que se esté ejecutando.

La federación saliente siempre se configura a través de un grupo de servidores perimetrales publicado o un servidor perimetral de la organización. Si este grupo de servidores perimetrales ha quedado inactivo, debe usar el Generador de topologías para cambiar la ruta de federación saliente para que use un grupo de servidores perimetrales que se está ejecutando todavía. Para obtener detalles, vea [Conmutación por error para el grupo de servidores perimetrales usado para la federación Lync Server en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

## Federación XMPP

Para la federación XMPP, se producirá un error tanto en el tráfico entrante como en el saliente si el grupo de servidores perimetrales que está designado como la puerta de enlace de federación XMPP deja de funcionar. Para que la federación XMPP vuelva a funcionar, debe cambiar la federación de XMPP para que use un grupo de servidores perimetrales diferente. Para obtener detalles, vea [Conmutación por error para el grupo de servidores perimetrales para la federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

## Se produce un error en el grupo de servidores perimetrales pero el grupo de servidores front-end todavía se está ejecutando

Si se produce un error en un grupo de servidores perimetrales en un sitio, pero el grupo de servidores front-end de ese sitio todavía se está ejecutando, tendrá que cambiar el grupo de servidores front-end para que use un grupo de servidores perimetrales diferente en un sitio diferente mientras que el primer grupo de servidores perimetrales ha dejado de funcionar. Para obtener más información, vea [Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

