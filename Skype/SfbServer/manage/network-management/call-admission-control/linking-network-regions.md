---
title: Vinculación de regiones de red
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas (CAC). '
ms.openlocfilehash: f2f3e170b11677663739f4e06ea7c6768f0a9c11
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223020"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Vinculación de regiones de red en Skype para Business Server

Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas (CAC). Use las secciones de este artículo para ver la información del vínculo de región newtwork o configurar o eliminar vínculos de región de red. 

## <a name="view-network-region-link-information"></a>Ver información de vínculo de región de red 

Puede ver los vínculos entre dos regiones de red como parte del control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas a través de la conectividad de área extensa (WAN) de la red. Puede usar el Skype para el Panel de Control de servidor empresarial para ver un vínculo existente entre dos regiones de red. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Para ver un vínculo de región de red en Skype para el Panel de Control de servidor empresarial

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en el **Vínculo de región**.

4.  En la página **Vínculo de región** , haga clic en el vínculo de región que desea ver.
    
    > [!NOTE]  
    > Sólo se puede ver información acerca de un vínculo de región a la vez.

5.  En el menú **Editar** , seleccione **Mostrar detalles**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Ver la información de vínculo de región de red mediante el uso de cmdlets de Windows PowerShell

Puede ver los vínculos de región de red mediante el uso de Windows PowerShell y el cmdlet **Get-CsNetworkRegionLink** . Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Para ver la información del vínculo de región de red

  - Para ver información acerca de todos los vínculos de región de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
    
        Get-CsNetworkRegionLink
    
    Este comando devolverá información similar a la siguiente:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Para obtener información detallada, vea [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurar vínculos de región de red 

Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas a través de la conectividad de área extensa (WAN) de la red. Puede usar el Skype para el Panel de Control de servidor empresarial para definir un vínculo entre dos regiones de red y establecer las limitaciones de ancho de banda en las conexiones de audio y vídeos entre estas regiones.

### <a name="to-create-a-network-region-link"></a>Para crear un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en el **Vínculo de región**.

4.  En la página **Vínculo de región** , haga clic en **nuevo**.

5.  En el **Vínculo de región de nuevo**, escriba un valor en el campo **nombre** .
 
    > [!NOTE]  
    > Este valor debe ser único dentro de su Skype para la implementación de Business Server.

6.  Desde el **región de red \#1** lista desplegable, seleccione una de las dos regiones que se vincularán.

7.  Desde el **región de red \#2** lista desplegable, seleccione la región de otra que se vincularán. Esta región debe ser diferente de la región seleccionada para la región de red \#1.

8.  (Opcional) Si desea poner limitaciones de ancho de banda en llamadas de audio o vídeos entre estas regiones, seleccione un perfil de directiva de ancho de banda de la lista desplegable **Directiva de ancho de banda** .

9.  Haga clic en **Confirmar**.

### <a name="to-modify-a-network-region-link"></a>Para modificar un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en el **Vínculo de región**.

4.  En la página **Vínculo de región** , haga clic en el vínculo de región que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En **Editar vínculo de región**, puede modificar las regiones que están vinculadas o el perfil de directiva de ancho de banda para este vínculo.

7.  Haga clic en **Confirmar**.


## <a name="delete-network-region-links"></a>Eliminar vínculos de región de red

Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas a través de la conectividad de área extensa (WAN) de la red. Puede usar el Skype para el Panel de Control de servidor empresarial para eliminar un vínculo entre dos regiones de red existente. 

### <a name="to-delete-a-network-region-link"></a>Para eliminar un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en el **Vínculo de región**.

4.  En la página **Vínculo de región** , haga clic en el vínculo de región que desea eliminar.
 
    > [!NOTE]  
    > Puede eliminar más de un vínculo de región a la vez. Para ello, presione la tecla CTRL y seleccione varios vínculos de región mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todos los vínculos de región, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Edición</STRONG> .

5.  En el menú **Editar** , seleccione **Eliminar**.

6.  Haga clic en **Aceptar**.


## <a name="see-also"></a>Consulte también

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  