---
title: Administrar perfiles de directiva de ancho de banda de red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Use los procedimientos de este artículo para ver, crear, modificar o eliminar perfiles de directiva de ancho de banda de red.
ms.openlocfilehash: a9203c0935673e0dfd12d052876f06583c7c92c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817509"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Administrar perfiles de directivas de ancho de banda de red en Skype Empresarial Server

Use los procedimientos de este artículo para ver, crear, modificar o eliminar perfiles de directiva de ancho de banda de red.

## <a name="view-network-bandwidth-policy-profile-information"></a>Ver la información de Perfil de la Directiva de ancho de banda

Como parte de control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir limitaciones de ancho de banda para determinadas modalidades. En Skype empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer limitaciones generales de ancho de banda y limitaciones de sesión. Puede usar el panel de control de Skype empresarial Server para crear, modificar o eliminar un perfil de contenedor para estas directivas. Cada perfil de directiva de ancho de banda se puede asociar a uno o varios sitios de red. Use los procedimientos siguientes para ver un perfil de directiva de ancho de banda. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Para ver un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en Directiva de **ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea ver.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Ver la información de Perfil de la Directiva de ancho de banda mediante cmdlets de Windows PowerShell

Los perfiles de ancho de banda de red se pueden ver con Windows PowerShell y el cmdlet Get-CsNetworkBandwidthPolicyProfile. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Para ver la información de Perfil de la Directiva de ancho de banda

  - Para ver información sobre todos los perfiles de la Directiva de ancho de banda de la red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Devolverá información similar a la siguiente:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Crear o modificar perfiles de directiva de ancho de banda

Como parte de control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir limitaciones de ancho de banda para determinadas modalidades. En Skype empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer limitaciones generales de ancho de banda y limitaciones de sesión. Puede usar el panel de control de Skype empresarial Server para crear, modificar o eliminar un perfil de contenedor para estas directivas. Cada perfil de directiva de ancho de banda se puede asociar a uno o varios sitios de red. Use los procedimientos siguientes para crear o modificar un perfil de directiva de ancho de banda. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Para crear un nuevo perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en Directiva de **ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en **nuevo**.

5.  En **nuevo perfil de directiva de ancho de banda**, escriba un nombre en el campo **nombre** . Este nombre debe ser único entre todos los perfiles de directiva de ancho de banda.

6.  En el campo **límite de audio** , escriba un valor numérico. Este valor es la cantidad máxima de ancho de banda que se asignará a todas las conexiones de audio, expresadas en kbps.

7.  Escriba un valor numérico en el campo límite de la **sesión de audio** . Este valor es la cantidad máxima de ancho de banda que se asignará a una conexión de audio individual, expresada en kbps. Este valor debe ser 40 o superior.

8.  Escriba un valor numérico en el campo **límite de video** . Este valor es la cantidad máxima de ancho de banda que se asignará a todas las conexiones de vídeo, expresadas en kbps.

9.  Escriba un valor numérico en el campo límite de la **sesión de vídeo** . Este valor es la cantidad máxima de ancho de banda que se asignará a una conexión de video individual, expresada en kbps. Este valor debe ser 100 o superior.

10. Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre este perfil de directiva de ancho de banda que no se puede expresar solo con el nombre.

11. Haga clic en **Confirmar**.

    > [!NOTE]  
    > La creación de un nuevo perfil de directiva de ancho de banda no aplica automáticamente restricciones de ancho de banda. Primero debe asociar el perfil de directiva con un sitio. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Para modificar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en Directiva de **ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar perfil** de la Directiva de ancho de banda, modifique los campos según sea necesario (para obtener información detallada, consulte [para crear un nuevo perfil de directiva de ancho de banda](#to-create-a-new-bandwidth-policy-profile)).

7.  Haga clic en **Confirmar**.

    > [!NOTE]  
    > Al modificar el perfil de directiva de ancho de banda, se actualizarán inmediatamente las limitaciones de ancho de banda de todos los sitios de red asociados a este perfil de directiva de ancho de banda.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Eliminar perfiles de directiva de ancho de banda de red

Como parte de control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir limitaciones de ancho de banda para determinadas modalidades. En Skype empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer limitaciones generales de ancho de banda y limitaciones de sesión. Puede usar el panel de control de Skype empresarial Server para crear, modificar o eliminar un perfil de contenedor para estas directivas. Use los procedimientos siguientes para eliminar los perfiles de la Directiva de ancho de banda de red. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Para eliminar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en Directiva de **ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea eliminar.

    > [!NOTE]  
    > Puede eliminar más de un perfil a la vez. Para ello, presione CTRL y seleccione varios perfiles manteniendo presionada la tecla CTRL. O bien, para seleccionar todos los perfiles, haga clic en **seleccionar todo** en el menú **edición** .

5.  En el menú **Editar** , haga clic en **eliminar**.
   

    > [!WARNING]  
    > No se puede eliminar un perfil de directiva de ancho de banda asociado a un sitio de red. Primero debe quitar la asociación con el sitio de red para poder eliminar el perfil. 


## <a name="see-also"></a>Vea también

[Administrar el control de admisión de llamadas para sitios](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

