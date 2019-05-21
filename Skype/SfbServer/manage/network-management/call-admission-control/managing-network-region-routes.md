---
title: Administrar rutas de regiones de red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Una ruta de región de red define la ruta entre un par de regiones de red. Cada pareja de regiones de red en la implementación de control de admisión de llamadas requiere una ruta de región de red.
ms.openlocfilehash: 174fdd021655f3e338001582a1409107b266582e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279511"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Administrar rutas de regiones de red en Skype Empresarial Server

Una *ruta de región de red* define la ruta entre un par de regiones de red. Cada pareja de regiones de red en la implementación de control de admisión de llamadas requiere una ruta de región de red. Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región. Use los procedimientos de este artilce para ver, crear, modificar o eliminar rutas de región de red.

## <a name="view-network-region-route-information"></a>Ver información de ruta de la región de red 

Cada región dentro de una configuración de control de admisión de llamadas (CAC) debe tener alguna forma de tener acceso a todas las demás regiones. Aunque los vínculos de región establecen limitaciones de ancho de banda en las conexiones entre las regiones y también representan los vínculos físicos, una ruta determina qué ruta de acceso vinculada pasará la conexión de una región a otra. Use los procedimientos siguientes para ver las rutas de la región de red existente en el panel de control de Skype empresarial Server o en el shell de administración de Skype empresarial. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Para ver la información de ruta de la región de red en el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **ruta de región**.

4.  En la página Ruta de la **región** , haga clic en la ruta de la región que desea ver.


    > [!NOTE]  
    > Solo puedes ver una ruta de región a la vez.


5.  En el menú **Editar**, haga clic en **Mostrar detalles**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Ver la información de ruta de la región de red con cmdlets de Windows PowerShell

La información de ruta de la región de red se puede ver con Windows PowerShell y el cmdlet Get-CsNetworkInterRegionRoute. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>Para ver la información de ruta de la región de red

  - Para ver información sobre todas las rutas de la región de red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkInterRegionRoute
    
    Devolverá información similar a la siguiente:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .


## <a name="create-or-modify-network-region-routes"></a>Crear o modificar rutas de región de red

Cada región dentro de una configuración de control de admisión de llamadas (CAC) debe tener alguna forma de tener acceso a todas las demás regiones. Aunque los vínculos de región establecen limitaciones de ancho de banda en las conexiones entre las regiones y también representan los vínculos físicos, una ruta determina qué ruta de acceso vinculada pasará la conexión de una región a otra. Puede usar el panel de control de Skype empresarial Server para configurar las rutas de la región de red. Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una ruta de región de red. Use este tema para crear o modificar una ruta de región de red. 

### <a name="to-create-a-network-region-route"></a>Para crear una ruta de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **ruta de región**.

4.  En la página Ruta de la **región** , haga clic en **nuevo**.

5.  En **ruta de nueva región**, escriba un valor en el campo **nombre** .
   
    > [!NOTE]  
    > Este valor debe ser único dentro de la implementación de Skype empresarial Server.

6.  En la lista desplegable ** \#región de red 1** , seleccione una de las dos regiones que se van a conectar mediante esta ruta.

7.  En la lista desplegable ** \#región de red 2** , seleccione la otra región de esta ruta. Esta región debe ser diferente de la región seleccionada para la región \#de red 1.

8.  Use el cuadro de lista **vínculos de región de red** para agregar vínculos de región a la ruta. Haga clic en el botón **Agregar** para mostrar la página de vínculos de la **región** . Haga clic en un vínculo de región para agregar a esta ruta y, a continuación, haga clic en **Aceptar**.
    
    > [!NOTE]  
    > Siga haciendo clic en el botón **Agregar** para agregar más vínculos o seleccione un vínculo y haga clic en **quitar** para quitar un vínculo.

9.  Haga clic en **Confirmar**.


### <a name="to-modify-a-network-region-route"></a>Para modificar una ruta de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **ruta de región**.

4.  En la página Ruta de la **región** , haga clic en la ruta de la región que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la **ruta de edición región**, puede modificar las regiones Unidas por esta ruta y los vínculos de región asociados a la ruta.

7.  Haga clic en **Confirmar**.


## <a name="delete-existing-network-region-routes"></a>Eliminar las rutas de la región de red existentes

Cada región dentro de una configuración de control de admisión de llamadas (CAC) debe tener alguna forma de tener acceso a todas las demás regiones. Aunque los vínculos de región establecen limitaciones de ancho de banda en las conexiones entre las regiones y también representan los vínculos físicos, una ruta determina qué ruta de acceso vinculada pasará la conexión de una región a otra. Puede usar el panel de control de Skype empresarial Server para configurar las rutas de la región de red. Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una ruta de región de red. Use este tema para eliminar las rutas de la región de red existentes. 

### <a name="to-delete-a-network-region-route"></a>Para eliminar una ruta de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, después, en **ruta de región**.

4.  En la página Ruta de la **región** , haga clic en la ruta de la región que desea eliminar.

    > [!NOTE]  
    > Puede eliminar más de una ruta de región a la vez. Para ello, presione CTRL y seleccione varias rutas de región mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todas las rutas de la región, haga clic en **seleccionar todo** en el menú **edición** .

5.  En el menú **Editar** , haga clic en **eliminar**.

6.  Haga clic en **Aceptar**.



## <a name="see-also"></a>Vea también

[Administrar regiones de red en Skype Empresarial Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
