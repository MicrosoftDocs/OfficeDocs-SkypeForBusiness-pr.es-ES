---
title: Eliminación de regiones de red existentes
TOCTitle: Eliminación de regiones de red existentes
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49889675
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de regiones de red existentes

 

_**Última modificación del tema:** 2013-02-21_

Una región de red interconecta varias partes de una red a través de varias zonas geográficas. Cada región de red debe asociarse con un sitio central. El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda del servicio de control de admisión de llamadas (CAC). Puede usar Panel de control de Lync Server para configurar las regiones de red, que incluyen valores que determinan si se permiten las rutas de acceso alternativas a través de Internet para las conexiones de audio y vídeo. En Panel de control de Lync Server puede crear, modificar o eliminar una región de red. En este tema se explica cómo eliminar las regiones de red actuales. Para más información sobre cómo crear o modificar regiones de red actuales, consulte [Creación o modificación de regiones de red](lync-server-2013-creating-or-modifying-network-regions.md).

## Para eliminar una región de red:

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y en **Región**.

4.  En la página **Región**, haga clic en la región que desea eliminar.
    

    > [!NOTE]
    > Si lo desea, puede eliminar varias regiones en la misma operación. Para ello, presione Ctrl y seleccione varias regiones mientras mantiene presionada esta tecla. O bien, para seleccionar todas las regiones, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.



5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.
    
    > [!WARNING]  
    > No se puede quitar una región si está asociada a un sitio de red. Si lo intenta, recibirá un mensaje de error. Para ver si una región está asociada a algún sitio, seleccione la región y haga clic en <strong>Mostrar detalles</strong> en el menú <strong>Editar</strong>.
    


## Vea también

#### Tareas

[Creación o modificación de regiones de red](lync-server-2013-creating-or-modifying-network-regions.md)

