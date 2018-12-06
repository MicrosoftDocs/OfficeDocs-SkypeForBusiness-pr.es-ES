---
title: Eliminación de un sitio de red existente
TOCTitle: Eliminación de un sitio de red existente
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49889012
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de un sitio de red existente

 

_**Última modificación del tema:** 2012-11-01_

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC). Puede usar Panel de control de Lync Server 2013 para configurar sitios y asociarlos con regiones. Por ejemplo, una región de red para Norteamérica se podría asociar con sitios de red como Chicago, Redmond y Vancouver. Debe crearse un sitio de red CAC para cada sitio de una organización, incluso aunque no tenga limitaciones de ancho de banda. En Panel de control de Lync Server, puede crear, modificar y eliminar sitios de red. Utilice el procedimiento siguiente para eliminar un sitio de red existente. Para obtener más detalles sobre la creación o modificación de sitios de red, vea [Creación o modificación de sitios de red](lync-server-2013-creating-or-modifying-network-sites.md).

## Para eliminar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio** .

4.  En la página **Sitio** , haga clic en el sitio que desea eliminar.
    

    > [!NOTE]
    > Puede eliminar más de un sitio en la misma operación. Para hacerlo, pulse CTRL y seleccione varios sitios manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los sitios, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.



5.  En el menú **Edición**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.
    
    > [!WARNING]  
    > No se puede eliminar un sitio de red si está asociado con la subred de una red. Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error. Para ver si un sitio está asociado con alguna subred, haga clic en el sitio y, a continuación, haga clic en <strong>Mostrar detalles</strong> en el menú <strong>Editar</strong>.
    

