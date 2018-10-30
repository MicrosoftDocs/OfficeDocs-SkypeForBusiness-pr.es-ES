---
title: Configurar opciones de archivado para un sitio
TOCTitle: Configurar opciones de archivado para un sitio
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48275366
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar opciones de archivado para un sitio

 

_**Última modificación del tema:** 2012-10-09_

Puede especificar las opciones de archivado que se aplican a los sitios específicos mediante la creación y configuración de opciones en una configuración de archivado para cada uno de esos sitios. Una configuración de sitio reemplaza la configuración global, pero solo para el sitio especificado en la configuración del sitio. Las configuraciones de grupo anulan las configuraciones de sitio

Para obtener información detallada acerca de cómo funciona la configuración de archivado incluida la jerarquía para configuraciones globales, de sitio y grupos de servidores, vea [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación referente a la planificación, la implementación y las operaciones.


> [!NOTE]
> Debe especificar todas las opciones pertinentes en las configuraciones de archivado antes de habilitar el archivado.



> [!IMPORTANT]  
> Para habilitar el archivado, es necesario especificar directivas de archivado para controlar el archivado de comunicaciones internas y externas en el nivel global y, si es adecuado, en los niveles de sitio y usuario. Si configura directivas de nivel de usuario, también deberá asignar directivas a usuarios específicos. Para más información sobre la creación y configuración de directivas de archivado, vea <a href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Administrar el archivado de las comunicaciones internas y externas en Lync Server 2013</a> en la documentación de operaciones.



## Para configurar las opciones de archivado en el nivel de sitio

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el Panel de control de Lync Server 2013. Para información detallada sobre los diferentes métodos que puede usar para abrir Panel de control de Lync Server 2013, vea [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  En la página **Configuración de archivado**, haga clic en **Nueva** y luego en **Configuración de sitio**.

5.  En **Seleccionar un sitio**, seleccione el sitio que debe configurarse para el archivado.

6.  En **Nueva configuración de archivado**, en el cuadro de lista desplegable **Configuración de archivado**, realice una de las siguientes acciones:
    
      - Para habilitar el archivado solamente para las sesiones de mensajería instantánea, haga clic en **Archivar sesiones de mensajería instantánea** .
    
      - Para habilitar el archivado tanto para las sesiones de mensajería instantánea como de conferencias, haga clic en **Archivar mensajería instantánea y sesiones de conferencias web**.
    
      - Para deshabilitar el archivado correspondiente a la directiva, haga clic en **Deshabilitar archivado**.

7.  También en **Nueva configuración de archivado**, haga lo siguiente:
    
      - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.
    
      - Para usar Microsoft Exchange Server y almacenar datos de archivado, haga clic en la casilla **Integración de Microsoft Exchange**.
    
      - Para habilitar la depuración de datos, active la casilla **Habilitar depuración de datos archivados** y siga uno de estos procedimientos:
        
          - Para especificar la depuración después de un número concreto de días, haga clic en **Depurar datos archivados exportados y datos archivados almacenados tras una duración máxima (días)** y, a continuación, especifique el número de días.
        
          - Para limitar la depuración de datos archivados que se han exportado, haga clic en **Depurar solo datos archivados exportados**.

8.  Haga clic en **Confirmar**.

