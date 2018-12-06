---
title: Consideraciones sobre la coexistencia
TOCTitle: Consideraciones sobre la coexistencia
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48276145
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Consideraciones sobre la coexistencia

 

_**Última modificación del tema:** 2012-10-06_

Tras la migración, solo existirá un Lync Server 2013, Grupo de servidores de chat persistente, y podrá retirar su implementación heredada.

Antes de completar la migración y de haber retirado del todo su implementación actual de Servidor de chat en grupo, es posible que tenga alguna de las siguientes implementaciones:

  - Lync Server 2013, Grupo de servidores de chat persistente, que debe estar alojado en un grupo de servidores de Lync Server 2013.

  - Grupo de servidores de Lync Server 2010, chat en grupo, que debe estar alojado en un grupo de servidores de Lync Server 2010.

  - Grupo de servidores de Office Communications Server 2007 R2Chat en grupo, que debe estar alojado en un grupo de servidores de Office Communications Server 2007 R2.

Estas implementaciones pueden existir simultáneamente. Ahora bien, las categorías, salones y complementos de una implementación no interactúan con las de la implementación que la acompaña.

Si se usa la configuración manual, un cliente heredado (cliente de Chat en grupo) puede establecer contacto con un grupo de servidores al mismo tiempo para Office Communications Server 2007 R2, Lync Server 2010, chat en grupo o Lync Server 2013.

El Lync 2013 (cliente) solo puede interactuar con el Lync Server 2013, Grupo de servidores de chat persistente, no con grupos de servidores de Servidor de chat en grupo heredados. Para usar Chat persistente en un Lync 2013 (cliente), el usuario debe estar alojado en Lync 2013 y habilitado por directiva.

