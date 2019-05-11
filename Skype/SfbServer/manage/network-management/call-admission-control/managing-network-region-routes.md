---
title: Administración de rutas de región de red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Una ruta de región de red define la ruta entre un par de regiones de red. Cada par de regiones de red en su implementación de control de admisión de llamadas requiere una ruta de región de red.
ms.openlocfilehash: 53b6383e08196fb22784f3fcd1e8d797c9b138de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888852"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Administrar rutas de regiones de red en Skype Empresarial Server

Una *ruta de región de red* define la ruta entre un par de regiones de red. Cada par de regiones de red en su implementación de control de admisión de llamadas requiere una ruta de región de red. Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región. Utilice los procedimientos descritos en este artículo para ver, crear, modificar o eliminar rutas de región de red.

## <a name="view-network-region-route-information"></a>Ver información de ruta de región de red 

Cada región dentro de una configuración de (CAC) del control de admisión de llamadas debe tener alguna manera de obtener acceso a todas las regiones. Mientras vínculos de región de establecer limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, una ruta determina qué ruta de acceso vinculada que atravesará la conexión de una región a otra. Use los procedimientos siguientes para ver rutas de región de red existentes en Skype para el Panel de Control de servidor empresarial o Skype para Shell de administración de servidor empresarial. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Para ver información de ruta de región de red en Skype para el Panel de Control de servidor empresarial

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Ruta de región**.

4.  En la página **Ruta regional** , haga clic en la ruta de región que desea ver.


    > [!NOTE]  
    > Sólo puede ver una ruta de región a la vez.


5.  En el menú **Editar**, haga clic en **Mostrar detalles**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de ruta de región de red mediante el uso de Cmdlets de Windows PowerShell

Información de ruta de región de red puede verse mediante el uso de Windows PowerShell y el cmdlet Get-CsNetworkInterRegionRoute. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>Para ver la información de ruta de región de red

  - Para ver información acerca de todas las rutas de región de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
    
        Get-CsNetworkInterRegionRoute
    
    Devolverá información similar a la siguiente:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .


## <a name="create-or-modify-network-region-routes"></a>Creación o modificación de rutas de región de red

Cada región dentro de una configuración de (CAC) del control de admisión de llamadas debe tener alguna manera de obtener acceso a todas las regiones. Mientras vínculos de región de establecer limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, una ruta determina qué ruta de acceso vinculada que atravesará la conexión de una región a otra. Puede usar el Skype para el Panel de Control de servidor empresarial para configurar rutas de región de red. De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una ruta de región de red. Utilice este tema para crear o modificar una ruta de región de red. 

### <a name="to-create-a-network-region-route"></a>Para crear una ruta de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Ruta de región**.

4.  En la página **Ruta regional** , haga clic en **nuevo**.

5.  En la **nueva ruta regional**, escriba un valor en el campo **nombre** .
   
    > [!NOTE]  
    > Este valor debe ser único dentro de su Skype para la implementación de Business Server.

6.  Desde el **región de red \#1** lista desplegable, seleccione una de las dos regiones que se conectan mediante esta ruta.

7.  Desde el **región de red \#2** lista desplegable, seleccione la región otra para esta ruta. Esta región debe ser diferente de la región seleccionada para la región de red \#1.

8.  Use el cuadro de lista de **vínculos de región de red** para agregar vínculos de región a la ruta. Haga clic en el botón **Agregar** para mostrar la página **Vínculo de región** . Haga clic en un vínculo de región para agregar a esta ruta y, a continuación, haga clic en **Aceptar**.
    
    > [!NOTE]  
    > Siga haciendo clic en el botón **Agregar** para agregar más vínculos, o seleccione un vínculo y haga clic en **Quitar** para quitar un vínculo.

9.  Haga clic en **Confirmar**.


### <a name="to-modify-a-network-region-route"></a>Para modificar una ruta de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Ruta de región**.

4.  En la página **Ruta regional** , haga clic en la ruta de región que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En **Editar ruta regional**, puede modificar las regiones agregadas a esta ruta y los vínculos de región asociados con la ruta.

7.  Haga clic en **Confirmar**.


## <a name="delete-existing-network-region-routes"></a>Eliminar rutas de región de red existentes

Cada región dentro de una configuración de (CAC) del control de admisión de llamadas debe tener alguna manera de obtener acceso a todas las regiones. Mientras vínculos de región de establecer limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, una ruta determina qué ruta de acceso vinculada que atravesará la conexión de una región a otra. Puede usar el Skype para el Panel de Control de servidor empresarial para configurar rutas de región de red. De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una ruta de región de red. Use este tema para eliminar las rutas de región de red existente. 

### <a name="to-delete-a-network-region-route"></a>Para eliminar una ruta de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Ruta de región**.

4.  En la página **Ruta regional** , haga clic en la ruta de región que desea eliminar.

    > [!NOTE]  
    > Puede eliminar más de una ruta de región a la vez. Para ello, presione la tecla CTRL y seleccione varias rutas de región mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todas las rutas de región, haga clic en **Seleccionar todo** en el menú **Edición** .

5.  En el menú **Edición** , haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.



## <a name="see-also"></a>Vea también

[Administrar regiones de red en Skype Empresarial Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
