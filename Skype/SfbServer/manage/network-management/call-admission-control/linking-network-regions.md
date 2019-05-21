---
title: Vincular regiones de red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Puede configurar vínculos entre dos regiones de red como parte de control de admisión de llamadas (CAC). '
ms.openlocfilehash: b9ffa45c8a0a09ba4a7f9f0ebf6402b87116f01f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279560"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Vincular regiones de red en Skype Empresarial Server

Puede configurar vínculos entre dos regiones de red como parte de control de admisión de llamadas (CAC). Use las secciones de este artículo para ver información de vínculos de la región de newtwork o configurar o eliminar vínculos de región de Netwrok. 

## <a name="view-network-region-link-information"></a>Ver información de vínculos de la región de red 

Puede ver los vínculos entre dos regiones de red como parte de control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas a través de la conectividad de red de área extensa (WAN). Puede usar el panel de control de Skype empresarial Server para ver un vínculo existente entre dos regiones de red. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Para ver un vínculo de región de red en el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **vínculo de región**.

4.  En la página vínculo de la **región** , haga clic en el vínculo de la región que desea ver.
    
    > [!NOTE]  
    > Solo puedes ver información sobre un vínculo de región a la vez.

5.  En el menú **Editar** , seleccione **Mostrar detalles**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Ver información de vínculos de la región de red con cmdlets de Windows PowerShell

Puede ver los vínculos de la región de red con Windows PowerShell y el cmdlet **Get-CsNetworkRegionLink** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Para ver información de vínculos de la región de red

  - Para ver información sobre todos los vínculos de la región de red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkRegionLink
    
    Este comando devolverá información similar a la siguiente:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Para obtener más información, vea [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurar vínculos de región de red 

Puede configurar vínculos entre dos regiones de red como parte de control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas a través de la conectividad de red de área extensa (WAN). Puede usar el panel de control de Skype empresarial Server para definir un vínculo entre dos regiones de red y establecer las limitaciones de ancho de banda en las conexiones de audio y vídeo entre estas regiones.

### <a name="to-create-a-network-region-link"></a>Para crear un vínculo a región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **vínculo de región**.

4.  En la página vínculo de la **región** , haga clic en **nuevo**.

5.  En el **vínculo nueva región**, escriba un valor en el campo **nombre** .
 
    > [!NOTE]  
    > Este valor debe ser único dentro de la implementación de Skype empresarial Server.

6.  En la lista desplegable ** \#región de red 1** , seleccione una de las dos regiones para vincular.

7.  En la lista desplegable ** \#región de red 2** , seleccione la otra región que desea vincular. Esta región debe ser diferente de la región seleccionada para la región \#de red 1.

8.  Faculta Si desea colocar limitaciones de ancho de banda en las llamadas de audio o vídeo entre estas regiones, seleccione un perfil de directiva de ancho de banda en la lista desplegable **Directiva de ancho de banda** .

9.  Haga clic en **Confirmar**.

### <a name="to-modify-a-network-region-link"></a>Para modificar un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **vínculo de región**.

4.  En la página vínculo de la **región** , haga clic en el vínculo de la región que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En el **vínculo editar región**, puede modificar las regiones vinculadas o el perfil de directiva de ancho de banda para este vínculo.

7.  Haga clic en **Confirmar**.


## <a name="delete-network-region-links"></a>Eliminar vínculos de la región de red

Puede configurar vínculos entre dos regiones de red como parte de control de admisión de llamadas (CAC). Las regiones dentro de una red están vinculadas a través de la conectividad de red de área extensa (WAN). Puede usar el panel de control de Skype empresarial Server para eliminar un vínculo existente entre dos regiones de red. 

### <a name="to-delete-a-network-region-link"></a>Para eliminar un vínculo a una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **vínculo de región**.

4.  En la página vínculo de la **región** , haga clic en el vínculo de la región que desea eliminar.
 
    > [!NOTE]  
    > Puedes eliminar más de un vínculo de región a la vez. Para ello, presione CTRL y seleccione varios vínculos de región mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todos los vínculos de la región, haga clic en <STRONG>seleccionar todo</STRONG> en el menú <STRONG>edición</STRONG> .

5.  En el menú **Editar** , seleccione **eliminar**.

6.  Haga clic en **Aceptar**.


## <a name="see-also"></a>Vea también

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
