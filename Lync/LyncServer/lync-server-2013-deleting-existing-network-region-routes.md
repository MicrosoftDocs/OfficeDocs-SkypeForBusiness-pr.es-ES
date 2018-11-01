---
title: Eliminación de rutas de región de red existentes
TOCTitle: Eliminación de rutas de región de red existentes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49889205
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de rutas de región de red existentes

 

_**Última modificación del tema:** 2012-11-01_

Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma al resto de regiones. Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y, asimismo, representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra. Puede usar el Panel de control de Lync Server para configurar rutas regionales de red. En el Panel de control de Lync Server puede crear, modificar o eliminar una ruta regional de red. Use este tema para eliminar las rutas de región de red existentes. Para obtener información detallada sobre cómo crear o modificar rutas de región de red, consulte [Creación o modificación de rutas de regiones de red](lync-server-2013-creating-or-modifying-network-region-routes.md).

## Para eliminar una ruta regional de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Ruta regional**.

4.  En la página **Ruta regional**, haga clic en la ruta regional que quiera eliminar.
    

    > [!NOTE]
    > Puede eliminar más de una ruta regional en la misma operación. Para hacerlo, presione la tecla CTRL y seleccione varias rutas regionales sin dejar de presionar CTRL. También puede seleccionar todas las rutas regionales haciendo clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.



5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.

## Vea también

#### Tareas

[Creación o modificación de rutas de regiones de red](lync-server-2013-creating-or-modifying-network-region-routes.md)  

#### Conceptos

[Configurar una ruta de región de red](https://technet.microsoft.com/es-es/library/gg133706\(v=ocs.15\))  

#### Otros recursos

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute)

