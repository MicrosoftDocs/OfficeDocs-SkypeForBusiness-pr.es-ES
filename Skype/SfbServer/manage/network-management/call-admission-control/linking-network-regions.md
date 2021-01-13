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
ms.openlocfilehash: 0a4f5c63b4470fbfe6d2677f0e9e6f52841f7ebb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816470"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Vincular regiones de red en Skype Empresarial Server

Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas. Use las secciones de este artículo para ver información de vínculos de región de trabajo nuevo o configurar o eliminar vínculos de región netwrok. 

## <a name="view-network-region-link-information"></a>Ver información de vínculos de región de red 

Puede ver enlaces entre dos regiones de red como parte de un servicio de control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN). Puede usar el Panel de control de Skype Empresarial Server para ver un vínculo existente entre dos regiones de red. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Para ver un vínculo de región de red en el Panel de control de Skype Empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Vínculo **de región.**

4.  En la página **Vínculo de región**, haga clic en el vínculo de región que desea ver.
    
    > [!NOTE]  
    > Solo puede ver información acerca de un vínculo de región a la vez.

5.  En el menú **Editar**, seleccione **Mostrar detalles**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Ver información de vínculos de región de red mediante cmdlets Windows PowerShell de red

Puede ver vínculos de región de red mediante Windows PowerShell y el cmdlet **Get-CsNetworkRegionLink.** Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Para ver la información de un vínculo de región de red

  - Para ver información sobre todos los vínculos de región de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkRegionLink
    
    Este comando devolverá información similar a la siguiente:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Para obtener información detallada, vea [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurar vínculos de región de red 

Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas. Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN). Puede usar el Panel de control de Skype Empresarial Server para definir un vínculo entre dos regiones de red y establecer las limitaciones de ancho de banda en las conexiones de audio y vídeo entre estas regiones.

### <a name="to-create-a-network-region-link"></a>Para crear un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Vínculo **de región.**

4.  En la página **Vínculo regional**, haga clic en **Nuevo**.

5.  En **Vínculo regional nuevo**, escriba un valor en el campo **Nombre**.
 
    > [!NOTE]  
    > Este valor debe ser único en la implementación de Skype Empresarial Server.

6.  En la lista desplegable Región de red **\# 1,** seleccione una de las dos regiones que desea vincular.

7.  En la lista desplegable Región de red **\# 2,** seleccione la otra región que desea vincular. Esta región debe ser diferente de la región seleccionada para la región de red \# 1.

8.  (Opcional) Si desea establecer limitaciones de ancho de banda en llamadas de audio o vídeo entre estas regiones, seleccione un perfil de directiva de ancho de banda en la lista desplegable **Directiva de ancho de banda**.

9.  Haga clic en **Confirmar**.

### <a name="to-modify-a-network-region-link"></a>Para modificar un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Vínculo **de región.**

4.  En la página **Vínculo regional**, haga clic en el vínculo regional que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En **Editar vínculo regional** puede modificar las regiones que están vinculadas o el perfil de directiva de ancho de banda para este vínculo.

7.  Haga clic en **Confirmar**.


## <a name="delete-network-region-links"></a>Eliminar vínculos de región de red

Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas. Las regiones dentro de una red están vinculadas con una conectividad física de red de área extensa (WAN). Puede usar el Panel de control de Skype Empresarial Server para eliminar un vínculo existente entre dos regiones de red. 

### <a name="to-delete-a-network-region-link"></a>Para eliminar un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Vínculo **de región.**

4.  En la página **Vínculo de región**, haga clic en el vínculo de región que desea eliminar.
 
    > [!NOTE]  
    > Se pueden eliminar varios vínculos de región a la vez. Para hacerlo, presione CTRL y seleccione varios vínculos de regiones mientras mantiene presionada la tecla CTRL. O, para seleccionar todos los vínculos de región, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.

5.  En el menú **Editar** seleccione **Eliminar**.

6.  Haga clic en **Aceptar**.


## <a name="see-also"></a>Consulte también

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
