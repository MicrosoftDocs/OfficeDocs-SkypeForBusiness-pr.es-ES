---
title: Implementar clientes de Lync Server 2013
TOCTitle: Implementar clientes de Lync Server 2013
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48275214
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar clientes de Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

Después de migrar los usuarios a Lync Server 2013, haga lo siguiente:

1.  Use el filtro de versión de cliente en el nuevo servidor de Lync Server 2013 para permitir que inicien sesión solo los clientes con las actualizaciones más recientes instaladas.

2.  Si es necesario, configure los valores de la directiva de grupo necesarios para el arranque del cliente. Para más información, vea [Configuración de las directivas de arranque del cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) en la documentación de implementación. La configuración de estos valores solo es necesaria si desea cambiar las directivas de arranque del cliente o si desea establecer las nuevas directivas de arranque de cliente. Si no piensa configurar las directivas de arranque de cliente, o si desea que las directivas de arranque de cliente heredadas permanezcan en vigor, no es necesario realizar ninguna acción.

3.  Configure otras directivas de usuario y cliente para usuarios o grupos de usuarios específicos mediante el uso de Panel de control de Lync Server 2013, Shell de administración de Lync Server 2013 o ambos. Para más información, vea [Nueva configuración y configuración modificada para Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) en la documentación de planificación.

4.  Implemente la versión más reciente de los clientes de Lync Server 2013 junto con las actualizaciones acumulativas más recientes. Para más información, vea [Implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) en la documentación de implementación.

5.  (Opcional) Si su organización requiere el modo de privacidad de presencia mejorada de Lync Server 2013, una vez finalizada la migración, defina una regla de directiva de versión de cliente para evitar que versiones anteriores del cliente inicien sesión. A continuación, habilite el modo de privacidad de presencia mejorada.
    
    > [!IMPORTANT]  
    > No habilite el modo de privacidad de presencia mejorada de Lync 2013 hasta que todos los usuarios en un grupo de servidores determinado tengan las últimas versiones de cliente instaladas.
    

