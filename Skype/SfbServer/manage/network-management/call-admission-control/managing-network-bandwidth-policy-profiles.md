---
title: Administración de perfiles de directivas de ancho de banda de red
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Use los procedimientos de este artículo para ver, crear, modificar o eliminar perfiles de directivas de ancho de banda de red.
ms.openlocfilehash: 58a73774a55a64ac6cb81f0bdf887eb0d1493a35
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222943"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Administración de perfiles de directivas de ancho de banda de red en Skype para Business Server

Use los procedimientos de este artículo para ver, crear, modificar o eliminar perfiles de directivas de ancho de banda de red.

## <a name="view-network-bandwidth-policy-profile-information"></a>Ver la información de perfil de directiva de ancho de banda de red

Como parte del control de admisión de llamadas (CAC), una directiva de ancho de banda se usa para definir las limitaciones de ancho de banda para determinadas modalidades. En Skype para Business Server, se pueden asignar a las modalidades de sólo audio y vídeos limitaciones de ancho de banda. Puede establecer limitaciones de ancho de banda general y sesión. Puede usar el Skype para el Panel de Control de servidor empresarial para crear, modificar o eliminar un perfil de contenedor para estas directivas. Cada perfil de directiva de ancho de banda se puede asociar con uno o varios sitios de red. Use los siguientes procedimientos para ver un perfil de directiva de ancho de banda. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Para ver un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, haga clic en **Directiva de ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea ver.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de perfil de directiva de ancho de banda de red mediante el uso de cmdlets de Windows PowerShell

Perfiles de ancho de banda de red pueden verse mediante el uso de Windows PowerShell y el cmdlet Get-CsNetworkBandwidthPolicyProfile. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Para ver la información de perfil de directiva de ancho de banda de red

  - Para ver información acerca de todos los perfiles de directiva de ancho de banda de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Devolverá información similar a la siguiente:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Crear o modificar perfiles de directivas de ancho de banda

Como parte del control de admisión de llamadas (CAC), una directiva de ancho de banda se usa para definir las limitaciones de ancho de banda para determinadas modalidades. En Skype para Business Server, se pueden asignar a las modalidades de sólo audio y vídeos limitaciones de ancho de banda. Puede establecer limitaciones de ancho de banda general y sesión. Puede usar el Skype para el Panel de Control de servidor empresarial para crear, modificar o eliminar un perfil de contenedor para estas directivas. Cada perfil de directiva de ancho de banda se puede asociar con uno o varios sitios de red. Use los procedimientos siguientes para crear o modificar un perfil de directiva de ancho de banda. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Para crear un nuevo perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Directiva de ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en **nuevo**.

5.  En el **Nuevo perfil de directiva de ancho de banda**, escriba un nombre en el campo **nombre** . Este nombre debe ser único entre todos los perfiles de directiva de ancho de banda.

6.  En el campo **límite de Audio** , escriba un valor numérico. Este valor es la cantidad máxima de ancho de banda para asignar para todas las conexiones de audioconferencias, expresadas en kbps.

7.  Escriba un valor numérico en el campo **límite de sesión de Audio** . Este valor es la cantidad máxima de ancho de banda para asignar para una conexión de audio individual, expresada en kbps. Este valor debe ser 40 o superior.

8.  Escriba un valor numérico en el campo **límite de vídeo** . Este valor es la cantidad máxima de ancho de banda para asignar para todas las conexiones de vídeo, expresadas en kbps.

9.  Escriba un valor numérico en el campo **límite de sesión de vídeo** . Este valor es la cantidad máxima de ancho de banda para asignar para una conexión de vídeo individual, expresada en kbps. Este valor debe ser 100 o superior.

10. (Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de este perfil de directiva de ancho de banda que se pueda deducir de su nombre.

11. Haga clic en **Confirmar**.

    > [!NOTE]  
    > Creación de un nuevo perfil de directiva de ancho de banda no aplica automáticamente las restricciones de ancho de banda. En primer lugar debe asociar el perfil de directiva a un sitio. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Para modificar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Directiva de ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar perfil de directiva de ancho de banda** , modifique los campos según sea necesario (para obtener más información, vea [para crear un nuevo perfil de directiva de ancho de banda](#to-create-a-new-bandwidth-policy-profile)).

7.  Haga clic en **Confirmar**.

    > [!NOTE]  
    > Modificar el perfil de directiva de ancho de banda, se actualizarán inmediatamente las limitaciones de ancho de banda de todos los sitios de red asociados a este perfil de directiva de ancho de banda.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Eliminar perfiles de directivas de ancho de banda de red

Como parte del control de admisión de llamadas (CAC), una directiva de ancho de banda se usa para definir las limitaciones de ancho de banda para determinadas modalidades. En Skype para Business Server, se pueden asignar a las modalidades de sólo audio y vídeos limitaciones de ancho de banda. Puede establecer limitaciones de ancho de banda general y sesión. Puede usar el Skype para el Panel de Control de servidor empresarial para crear, modificar o eliminar un perfil de contenedor para estas directivas. Use los procedimientos siguientes para eliminar un perfiles de directivas de ancho de banda de red. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Para eliminar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Directiva de ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea eliminar.

    > [!NOTE]  
    > Puede eliminar más de un perfil a la vez. Para ello, presione la tecla CTRL y seleccione varios perfiles mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todos los perfiles, haga clic en **Seleccionar todo** en el menú **Edición** .

5.  En el menú **Edición** , haga clic en **Eliminar**.
   

    > [!WARNING]  
    > No se puede eliminar un perfil de directiva de ancho de banda que está asociado con un sitio de red. En primer lugar debe quitar la asociación con el sitio de red antes de eliminar el perfil. 


## <a name="see-also"></a>Consulte también

[Administración de control de admisión de llamadas para sitios](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

