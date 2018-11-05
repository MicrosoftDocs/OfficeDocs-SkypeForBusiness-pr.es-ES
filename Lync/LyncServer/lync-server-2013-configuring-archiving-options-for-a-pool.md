---
title: Configurar opciones de archivado para un grupo de servidores
TOCTitle: Configurar opciones de archivado para un grupo de servidores
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48276462
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar opciones de archivado para un grupo de servidores

 

_**Última modificación del tema:** 2012-10-10_

Puede especificar las opciones de archivado que se aplican a grupos de servidores específicos al crear y configurar las opciones en una configuración de archivado para cada uno de estos grupos de servidores. La configuración de un grupo de servidores anula la configuración global y de sitio, pero únicamente para el grupo de servidores especificad en la configuración del grupo de servidores.

Para obtener información detallada acerca de cómo funciona la configuración de archivado incluida la jerarquía para configuraciones globales, de sitio y grupos de servidores, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación referente a la planificación, la implementación y las operaciones.


> [!NOTE]
> Debe especificar las opciones correctas en la configuración del archivado antes de habilitar el archivado de las comunicaciones internas o externas en las directivas de archivado. Para obtener información detallada, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configurar opciones de archivado</A> en la documentación referente a la implementación.



## Para configurar las opciones de archivado en el nivel de grupo

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y escriba la URL del administrador para abrir el Panel de control de Lync Server 2013. Para obtener información detallada sobre los diferentes métodos que puede usar para abrir el Panel de control de Lync Server 2013, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  En la página **Configuración de archivado**, haga clic en **Nuevo** y en **Directiva de grupo**.

5.  En **Seleccione un servicio**, seleccione el grupo de servidores que desea configurar para el archivado.

6.  En **Nueva configuración de archivado**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones:
    
      - **Deshabilitar archivado**
    
      - **Archivar sesiones de MI**
    
      - **Archivar sesiones de MI y conferencias**

7.  Además, en la página **Nueva configuración de archivado**, haga lo siguiente:
    
      - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias si se produce algún error en el archivado** .
    
      - Para almacenar datos de archivado en Microsoft Exchange Server, haga clic en la casilla **Integración de Microsoft Exchange**.
    
      - Para habilitar la depuración de datos, active la casilla **Habilitar depuración de datos archivados** y siga uno de estos procedimientos:
        
          - Para especificar la depuración después de un número concreto de días, haga clic en **Depurar datos archivados exportados y datos archivados almacenados tras una duración máxima (días)** y, a continuación, especifique el número de días.
        
          - Para limitar la depuración a los datos archivados que se han exportado, haga clic en **Depurar solo datos archivados exportados** .

8.  Haga clic en **Confirmar** .

