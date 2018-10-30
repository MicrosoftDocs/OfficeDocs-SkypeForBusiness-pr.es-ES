---
title: Migrar servidor de mediación
TOCTitle: Migrar servidor de mediación
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48276377
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar servidor de mediación

 

_**Última modificación del tema:** 2012-09-28_

El servidor de mediación se combina con la topología piloto de Lync Server 2013 cuando se ejecuta el Asistente para combinaciones. No obstante, el servidor de mediación de Lync Server 2013 se configura después de que todos los usuarios se migraron porque un grupo de servidores Office Communications Server 2007 R2 no se puede comunicar con un servidor de mediación de Lync Server 2013. Durante la migración en paralelo, el grupo de servidores de Lync Server 2013 se comunica con el servidor de mediación de Office Communications Server 2007 R2.

Al configurar el servidor de mediación de Lync Server 2013, también debe actualizar o reemplazar las puertas de enlace de Office Communications Server 2007 R2. Las puertas de enlace de Office Communications Server 2007 R2 no son compatibles con el servidor de mediación de Lync Server 2013. Debe implementar puertas de enlace certificadas para Lync Server 2013 y asociarlas con el servidor de mediación de Lync Server 2013. Este paso es obligatorio antes de poder retirar completamente la implementación de Office Communications Server 2007 R2.

Los temas de esta sección describen las tareas de configuración que debe realizar una vez completada la migración del servidor de mediación de Lync Server 2013. La transición del servidor de mediación combinado a un servidor de mediación independiente es una tarea opcional.

  - [Configurar servidor de mediación](configure-mediation-server.md)

  - [Cambiar rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Transición de un servidor de mediación combinado a un servidor de mediación independiente (opcional)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

