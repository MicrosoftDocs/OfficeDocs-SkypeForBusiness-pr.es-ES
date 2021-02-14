---
title: Administración de rutas de región de red
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Una ruta de región de red define la ruta entre un par de regiones de red. Cada par de regiones de red en su implementación de control de admisión de llamadas requiere una ruta de región de red.
ms.openlocfilehash: 23dec126511b941ff3e25b22c37cbba0854b13bc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816440"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Administrar rutas de regiones de red en Skype Empresarial Server

Una *ruta de región de red* define la ruta entre un par de regiones de red. Cada par de regiones de red en su implementación de control de admisión de llamadas requiere una ruta de región de red. Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región. Use los procedimientos de esta técnica para ver, crear, modificar o eliminar rutas de región de red.

## <a name="view-network-region-route-information"></a>Ver información de ruta de región de red 

Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones. Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra. Use los siguientes procedimientos para ver las rutas de región de red existentes en el Panel de control de Skype Empresarial Server o en el Shell de administración de Skype Empresarial Server. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Para ver la información de ruta de región de red en el Panel de control de Skype Empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Ruta **de región.**

4.  En la página **Ruta de región**, haga clic en la ruta regional que desea ver.


    > [!NOTE]  
    > Solo puede ver una ruta regional cada vez.


5.  En el menú  **Editar**, haga clic en  **Mostrar detalles**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Visualización de la información de ruta de región de red mediante cmdlets Windows PowerShell región

La información de ruta de región de red se puede ver mediante Windows PowerShell y el cmdlet Get-CsNetworkInterRegionRoute región. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>Para ver la información de ruta de región de red

  - Para ver información sobre todas las rutas de región de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkInterRegionRoute
    
    Devolverá información similar a la siguiente:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Para obtener más información, vea el tema de la Ayuda para el cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).


## <a name="create-or-modify-network-region-routes"></a>Crear o modificar rutas de región de red

Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones. Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra. Puede usar el Panel de control de Skype Empresarial Server para configurar rutas regionales de red. Desde el Panel de control de Skype Empresarial Server, puede crear, modificar o eliminar una ruta regional de red. Consulte este tema para crear o modificar una ruta regional de red. 

### <a name="to-create-a-network-region-route"></a>Para crear una ruta regional de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Ruta **de región.**

4.  En la página **Ruta regional**, haga clic en **Nueva**.

5.  En **Nueva ruta regional**, escriba un valor en el campo **Nombre**.
   
    > [!NOTE]  
    > Este valor debe ser único en la implementación de Skype Empresarial Server.

6.  En la lista desplegable Región de red **\# 1,** seleccione una de las dos regiones que se conectarán mediante esta ruta.

7.  En la lista desplegable Región de red **\# 2,** seleccione la otra región para esta ruta. Esta región debe ser diferente de la región seleccionada para la región de red \# 1.

8.  Use el cuadro de lista **Vínculos de región de red** para agregar vínculos de red a la ruta. Haga clic en el botón **Agregar** para mostrar la página **Vínculo regional**. Haga clic en un vínculo regional para agregarlo a esta ruta y, a continuación, haga clic en **Aceptar**.
    
    > [!NOTE]  
    > Haga clic otra vez en el botón **Agregar** para añadir más vínculos, o seleccione un vínculo y haga clic en **Eliminar** para eliminarlo.

9.  Haga clic en **Confirmar**.


### <a name="to-modify-a-network-region-route"></a>Para modificar una ruta regional de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Ruta **de región.**

4.  En la página **Ruta regional**, haga clic en la ruta regional que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En **Editar ruta regional**, puede modificar las regiones agregadas a esta ruta y los vínculos regionales asociados a la misma.

7.  Haga clic en **Confirmar**.


## <a name="delete-existing-network-region-routes"></a>Eliminar rutas de región de red existentes

Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones. Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra. Puede usar el Panel de control de Skype Empresarial Server para configurar rutas regionales de red. Desde el Panel de control de Skype Empresarial Server, puede crear, modificar o eliminar una ruta regional de red. Use este tema para eliminar las rutas de región de red existentes. 

### <a name="to-delete-a-network-region-route"></a>Para eliminar una ruta regional de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Ruta **de región.**

4.  En la página **Ruta regional**, haga clic en la ruta regional que quiera eliminar.

    > [!NOTE]  
    > Puede eliminar más de una ruta regional en la misma operación. Para hacerlo, presione la tecla CTRL y seleccione varias rutas regionales sin dejar de presionar CTRL. También puede seleccionar todas las rutas regionales haciendo clic en **Seleccionar todo** en el menú **Editar**.

5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.



## <a name="see-also"></a>Vea también

[Administrar regiones de red en Skype Empresarial Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
