---
title: Eliminación de vínculos de región de red
TOCTitle: Eliminación de vínculos de región de red
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49889355
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de vínculos de región de red

 

_**Última modificación del tema:** 2012-11-01_

Puede configurar vínculos entre dos regiones de red como parte del servicio de control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN). Puede usar el Panel de control de Lync Server para eliminar un vínculo existente entre dos regiones de red. Para obtener detalles acerca de la creación o modificación de un vínculo de región de red, vea [Configuración de vínculos de regiones de red](lync-server-2013-configuring-network-region-links.md).

## Para eliminar un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y luego en **Vínculo de región**.

4.  En la página **Vínculo de región**, haga clic en el vínculo de región que desea eliminar.
    

    > [!NOTE]
    > Se pueden eliminar varios vínculos de región a la vez. Para hacerlo, presione CTRL y seleccione varios vínculos de regiones mientras mantiene presionada la tecla CTRL. O, para seleccionar todos los vínculos de región, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.



5.  En el menú **Editar** seleccione **Eliminar**.

6.  Haga clic en **Aceptar**.

## Vea también

#### Tareas

[Configuración de vínculos de regiones de red](lync-server-2013-configuring-network-region-links.md)

