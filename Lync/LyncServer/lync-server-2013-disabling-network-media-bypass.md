---
title: Deshabilitación de la omisión de medios de red
TOCTitle: Deshabilitación de la omisión de medios de red
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49889387
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Deshabilitación de la omisión de medios de red

 

_**Última modificación del tema:** 2012-10-15_

La configuración del desvío de medios se aplica globalmente en una implementación de Microsoft Lync Server 2013. Con el desvío de medios, las llamadas pueden omitir el servidor de mediación. Para obtener más información acerca de cuándo usar el desvío de medios, consulte [Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la sección Planeación. El desvío de medios se puede deshabilitar desde el Panel de control de Lync Server. Para obtener más información sobre cómo habilitar y configurar el desvío de medios, consulte [Habilitación del desvío de medios de red](lync-server-2013-enabling-network-media-bypass.md)

## Para deshabilitar el desvío de medios

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Global** .

4.  En la página **Global**, haga clic en la configuración **Global**. En todos los casos hay solo una configuración y siempre se llama Global.

5.  En el menú **Editar**, haga clic en **Ver detalles**.

6.  En la página **Editar configuración global** , desactive la casilla **Habilitar desvío de medios** .

7.  Haga clic en **Confirmar** para guardar los cambios.

## Vea también

#### Tareas

[Habilitación del desvío de medios de red](lync-server-2013-enabling-network-media-bypass.md)

