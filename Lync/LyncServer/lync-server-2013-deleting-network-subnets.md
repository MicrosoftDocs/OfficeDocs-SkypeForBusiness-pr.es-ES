---
title: Eliminación de subredes de red
TOCTitle: Eliminación de subredes de red
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49889664
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de subredes de red

 

_**Última modificación del tema:** 2013-02-21_

Puede usar el procedimiento siguiente para eliminar una subred. Desde Panel de control de Lync Server puede crear, modificar o eliminar una subred de red. Para más información sobre cómo crear o modificar subredes de redes, consulte [Crear o modificar subredes de red](lync-server-2013-create-or-modify-network-subnets.md).

En la mayoría de las implementaciones de Microsoft Lync Server 2013 en que el servicio de control de admisión de llamadas (CAC) está implementado, normalmente hay una gran cantidad de subredes. Debido a ello, es mejor configurar subredes desde Shell de administración de Lync Server. Desde allí, puede llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV** de Windows PowerShell. Con todos estos cmdlets puede leer configuraciones de subred desde un archivo .csv y crear varias subredes al mismo tiempo. Para ver ejemplos de cómo crear subredes desde un archivo .csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet).

## Para eliminar una subred de red:

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y en **Subred**.

4.  En la página **Subred**, haga clic en la subred que desea eliminar.
    

    > [!NOTE]
    > Puede eliminar simultáneamente varias subredes. Para ello, mantenga presionada la tecla Ctrl y seleccione varias subredes. O bien, para seleccionar todas las subredes, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.



5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.

## Vea también

#### Tareas

[Crear o modificar subredes de red](lync-server-2013-create-or-modify-network-subnets.md)

