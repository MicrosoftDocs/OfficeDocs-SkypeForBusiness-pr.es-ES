---
title: Configurar opciones de archivado a nivel global
TOCTitle: Configurar opciones de archivado a nivel global
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48276540
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar opciones de archivado a nivel global

 

_**Última modificación del tema:** 2012-10-10_

Si agrega el archivado a su topología y publica esta, Lync Server crea una configuración global para el archivado. De forma predeterminada, no se habilita ninguna opción de archivado en la configuración global. La configuración global controla qué opciones se habilitan para su completa implementación, a menos que realice configuraciones de sitio o grupo de servidores, que omiten la configuración global.

Para obtener información acerca de cómo funcionan las configuraciones de archivado, incluida la jerarquía para configuraciones globales, de sitio y de grupo de servidores, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre planificación, sobre implementación o sobre operaciones.


> [!NOTE]
> Debe especificar todas las opciones adecuadas en las configuraciones de archivado antes de habilitar el archivado.



## Procedimiento para configurar las opciones de archivado en el nivel global

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del navegador y escriba la dirección URL de administración para abrir el Panel de control de Lync Server 2013. Para obtener información acerca de los diferentes métodos que puede usar para iniciar Panel de control de Lync Server 2013, consulte[Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  En la página **Configuración de archivado**, haga clic en **Global**, **Editar** y **Mostrar detalles**.

5.  En **Editar configuración de archivado: global**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones de archivado:
    
      - **Deshabilitar archivado**
    
      - **Archivar sesiones de mensajería instantánea**
    
      - **Archivar mensajería instantánea y sesiones de conferencias web**

6.  Además, en la página **Editar configuración de archivado: global**, haga lo siguiente:
    
      - Para bloquear la actividad si el archivado no está disponible, seleccione la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.
    
      - Para usar Microsoft Exchange Server para almacenar los datos de archivado, haga clic en la casilla de integración de **Microsoft Exchange**.
    
      - Para habilitar el purgado de datos, seleccione la casilla **Habilitar purgado de los datos de archivado** y haga una de las siguientes acciones:
        
          - Para especificar el purgado al cabo de un número determinado de días, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.
        
          - Para limitar el purgado a los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.

7.  Haga clic en **Confirmar**.

