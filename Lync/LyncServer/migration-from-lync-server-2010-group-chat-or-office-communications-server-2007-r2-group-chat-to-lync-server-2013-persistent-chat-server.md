---
title: "Migrar chat grupal de Lync Server 2010/Office Comms Server 2007 R2 a chat de LS 2013"
TOCTitle: "Migr. de LS 2010, conv. de gr. ou conv. de gr. OCS 2007 R2 vers LS 2013, serv. de conv. perm."
ms:assetid: 5b4d3db1-6eba-4932-b49c-f60bcf9488f9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615442(v=OCS.15)
ms:contentKeyID: 48275379
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migración del chat de grupo de Lync Server 2010 o el chat de grupo de Office Communications Server 2007 R2 al servidor de chat persistente de Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

Los temas de esta sección sirven de orientación para el proceso de migración de un Lync Server 2010, chat en grupo o de un Chat en grupo de Office Communications Server 2007 R2 a un Servidor de chat persistente de Lync Server 2013. Si su intención es que la implementación de Lync Server 2013, Servidor de chat persistente coexista con una implementación de Lync Server 2010, chat en grupo o de un Chat en grupo de Office Communications Server 2007 R2, esta guía también incluye información esencial para el funcionamiento en este entorno mixto. Esta guía se centra principalmente en la migración de datos del Servidor de chat persistente. Para aquellos usuarios que migran de versiones heredadas de Lync Server a Lync Server 2013, consulte [Migrar Lync Server 2010 a Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) y [Migrar de Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

> [!IMPORTANT]  
> Este tema supone que tiene instalado Lync Server 2013 en coexistencia con Lync Server 2010 o Office Communications Server 2007 R2.



> [!IMPORTANT]  
> En este documento se explican los pasos que se suelen requerir para realizar cada fase de la migración. No se aborda cada topología de implementación heredada posible ni cada escenario de migración posible. Por lo tanto, puede que no tenga que realizar cada paso que se describe o que deba realizar más pasos, en función de la implementación. En este documento también se proporcionan ejemplos de pasos de comprobación que le permitirán comprender lo que debe buscar para asegurarse de que cada fase se complete correctamente a medida que avanza en la migración. Adapte estos pasos de comprobación a su proceso de migración específico.



Esta guía le ofrece información específica para actualizar su implementación existente. No explica cómo cambiar su topología existente. Esta guía no aborda la implementación de nuevas características. Cuando se documenta en otro lugar un procedimiento detallado, esta guía le dirige al documento o sección del documento pertinente.

En este documento se definen los términos siguiendo las especificaciones de la lista siguiente.

  - *migración*  
    Trasladar su implementación de una versión anterior del Servidor de chat persistente (antes denominado Servidor de chat en grupo) al Servidor de chat persistente de Lync Server 2013.

<!-- end list -->

  - *actualizar*  
    Instalar una versión más reciente de software en un servidor o equipo de cliente.

<!-- end list -->

  - *coexistencia*  
    El entorno temporal que tiene lugar durante la migración, cuando parte de una funcionalidad se ha migrado al Servidor de chat persistente de Lync Server 2013, mientras que otra sigue en una versión anterior de Servidor de chat en grupo.

El Servidor de chat persistente es una extensión de la infraestructura de Lync Server 2013. Según cuál sea su topología, puede migrar el Lync Server 2010, chat en grupo o el Chat en grupo de Office Communications Server 2007 R2 al Servidor de chat persistente de Lync Server 2013. Para obtener más información sobre las topologías disponibles y los requisitos técnicos y de software necesarios para migrar el Servidor de chat en grupo, consulte [Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación de planeación.

Si su organización requiere compatibilidad con el cumplimiento, ahora se instala automáticamente con cada Servidor de chat persistente y ya no es necesario disponer de un servidor independiente para el cumplimiento.

> [!IMPORTANT]  
> Servidor de chat persistente debe instalarse en un sistema de archivos NTFS para ayudar a aplicar la seguridad del sistema de archivos. FAT32 no es un sistema de archivos admitido para Servidor de chat persistente.<br />
> Si su organización requiere compatibilidad con el cumplimiento, ahora se instala automáticamente con cada Servidor de chat persistente y ya no es necesario disponer de un servidor independiente para el cumplimiento. Para obtener más información sobre los cambios en el Servidor de chat persistente de Lync Server 2013, consulte <a href="lync-server-2013-new-persistent-chat-server-features.md">Nuevas características del servidor de chat persistente en Lync Server 2013</a>en la documentación de introducción.


## En esta sección

  - [Escenario de migración estándar - Alto nivel](standard-migration-scenario-high-level.md)

  - [Proceso de migración - Detalles](migration-process-details.md)

  - [Consideraciones sobre la coexistencia](coexistence-considerations.md)

