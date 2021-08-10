---
title: Vincular regiones de red
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
description: 'Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas. '
ms.openlocfilehash: 449901d771a1ac473a4e183b44edd270cad4542473abf7ad06b1bb9a9ebad1f8
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2021
ms.locfileid: "54591094"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Vincular regiones de red en Skype Empresarial Server

Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas. Use las secciones de este artículo para ver información de vínculos de región newtwork o configurar o eliminar vínculos de región netwrok. 

## <a name="view-network-region-link-information"></a>Ver información de vínculos de región de red 

Puede ver enlaces entre dos regiones de red como parte de un servicio de control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN). Puede usar el Panel de control Skype Empresarial Server para ver un vínculo existente entre dos regiones de red. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Para ver un vínculo de región de red en Skype Empresarial Server Panel de control

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Vínculo **de región.**

4.  En la página **Vínculo de región**, haga clic en el vínculo de región que desea ver.
    
    > [!NOTE]
    > Solo puede ver información acerca de un vínculo de región a la vez.

5.  En el menú **Editar**, seleccione **Mostrar detalles**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Ver información de vínculos de región de red mediante Windows PowerShell cmdlets

Puede ver vínculos de región de red mediante Windows PowerShell y el cmdlet **Get-CsNetworkRegionLink.** Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Para ver la información de un vínculo de región de red

  - Para ver información sobre todos los vínculos de región de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
    **Get-CsNetworkRegionLink**
    
    Este comando devolverá información similar a la siguiente:
    
       Identidad : NorthwestToCalifornia BWPolicyProfileID : NetworkRegionLinkID : NorthwestToCalifornia NetworkRegionID1 : Pacific Northwest NetworkRegionID2 : California


Para obtener información detallada, vea [Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurar vínculos de región de red 

Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas. Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN). Puede usar el Panel de control Skype Empresarial Server para definir un vínculo entre dos regiones de red y establecer las limitaciones de ancho de banda en las conexiones de audio y vídeo entre estas regiones.

### <a name="to-create-a-network-region-link"></a>Para crear un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Vínculo **de región.**

4.  En la página **Vínculo regional**, haga clic en **Nuevo**.

5.  En **Vínculo regional nuevo**, escriba un valor en el campo **Nombre**.
 
    > [!NOTE]  
    > Este valor debe ser único dentro de la Skype Empresarial Server implementación.

6.  En la lista desplegable Región de red **\# 1,** seleccione una de las dos regiones que desea vincular.

7.  En la lista desplegable Región de red **\# 2,** seleccione la otra región que se va a vincular. Esta región debe ser diferente de la región seleccionada para la región \# de red 1.

8.  (Opcional) Si desea establecer limitaciones de ancho de banda en llamadas de audio o vídeo entre estas regiones, seleccione un perfil de directiva de ancho de banda en la lista desplegable **Directiva de ancho de banda**.

9.  Haga clic en **Confirmar**.

### <a name="to-modify-a-network-region-link"></a>Para modificar un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Vínculo **de región.**

4.  En la página **Vínculo regional**, haga clic en el vínculo regional que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En **Editar vínculo regional** puede modificar las regiones que están vinculadas o el perfil de directiva de ancho de banda para este vínculo.

7.  Haga clic en **Confirmar**.


## <a name="delete-network-region-links"></a>Eliminar vínculos de región de red

Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas. Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN). Puede usar el Panel de control Skype Empresarial Server para eliminar un vínculo existente entre dos regiones de red. 

### <a name="to-delete-a-network-region-link"></a>Para eliminar un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Vínculo **de región.**

4.  En la página **Vínculo de región**, haga clic en el vínculo de región que desea eliminar.
 
    > [!NOTE]  
    > Se pueden eliminar varios vínculos de región a la vez. Para hacerlo, presione CTRL y seleccione varios vínculos de regiones mientras mantiene presionada la tecla CTRL. O, para seleccionar todos los vínculos de región, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.

5.  En el menú **Editar** seleccione **Eliminar**.

6.  Haga clic en **Aceptar**.


## <a name="see-also"></a>Consulte también

[New-CsNetworkRegionLink](/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink)