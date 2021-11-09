---
title: Administración de perfiles de directiva de ancho de banda de red
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Use los procedimientos de este artículo para ver, crear, modificar o eliminar perfiles de directiva de ancho de banda de red.
ms.openlocfilehash: fee0d4f57847747b0e25c98bc99183daa22a9996
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851003"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Administrar perfiles de directivas de ancho de banda de red en Skype Empresarial Server

Use los procedimientos de este artículo para ver, crear, modificar o eliminar perfiles de directiva de ancho de banda de red.

## <a name="view-network-bandwidth-policy-profile-information"></a>Ver información de perfil de directiva de ancho de banda de red

Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades. En Skype Empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer limitaciones generales de ancho de banda y sesión. Puede usar el Panel Skype Empresarial Server control para crear, modificar o eliminar un perfil de contenedor para estas directivas. Cada perfil de directiva de ancho de banda se puede asociar a uno o más sitios de red. Utilice los siguientes procedimientos para ver un perfil de directiva de ancho de banda. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Para ver un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.

4.  En la página **Directiva de ancho de** banda, haga clic en el perfil de directiva de ancho de banda que desea ver.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de perfil de directiva de ancho de banda de red mediante Windows PowerShell cmdlets

Los perfiles de ancho de banda de red se pueden ver mediante Windows PowerShell y el cmdlet Get-CsNetworkBandwidthPolicyProfile red. Este cmdlet se puede ejecutar desde el Shell Skype Empresarial Server administración o desde una sesión remota de Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Para ver la información del perfil de directiva de ancho de banda de red

  - Para ver información sobre todos los perfiles de directiva de ancho de banda de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
    **Get-CsNetworkBandwidthPolicyProfile**
    
    Devolverá información similar a la siguiente:
    
    Identity : RedmondBandwidthPolicy<br/>
    BWPolicy : {BWLimit=200; BWSessionLimit=200;<br/>
                        BWPolicyModality=Audio, <br/>
                        BWLimit=1400; BWSessionLimit=500;<br/>
                        BWPolicyModality=Video}<br/>
    BWPolicyProfileID : RedmondBandwidthPolicy<br/>
    Descripción :

Si desea más información, consulte el tema de ayuda relativo al cmdlet [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Crear o modificar perfiles de directiva de ancho de banda

Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades. En Skype Empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer limitaciones generales de ancho de banda y sesión. Puede usar el Panel Skype Empresarial Server control para crear, modificar o eliminar un perfil de contenedor para estas directivas. Cada perfil de directiva de ancho de banda se puede asociar a uno o más sitios de red. Use los siguientes procedimientos para crear o modificar un perfil de directiva de ancho de banda. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Para crear un nuevo perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Directiva de ancho **de banda.**

4.  En la página **Directiva de ancho de banda**, haga clic en **Nuevo**.

5.  En **Nuevo perfil de directiva de ancho de banda**, escriba un nombre en el campo **Nombre**. Este nombre debe ser diferente al resto de perfiles de directiva de ancho de banda.

6.  En el campo **Límite de audio**, escriba un valor numérico. Este valor es la cantidad máxima de ancho de banda que se puede asignar a todas las conexiones de audio, expresado en kbps.

7.  Especifique un valor numérico en el campo **Límite de sesión de audio**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a una conexión de audio individual, expresado en kbps. El valor debe ser mayor o igual que 40.

8.  Especifique un valor numérico en el campo **Límite de vídeo**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a todas las conexiones de vídeo, expresado en kbps.

9.  Especifique un valor numérico en el campo **Límite de sesión de vídeo**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a una conexión de vídeo individual, expresado en kbps. El valor debe ser mayor o igual que 100.

10. (Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre este perfil de directiva de ancho de banda más allá de lo que se pueda deducir de su nombre.

11. Haga clic en **Confirmar**.

    > [!NOTE]  
    > Crear un nuevo perfil de directiva de ancho de banda no supone la aplicación automática de las restricciones de ancho de banda. Primero debe asociar el perfil de directiva a un sitio. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Para modificar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Directiva de ancho **de banda.**

4.  En la página **Directiva de ancho de banda**, haga clic en el perfil de directiva de ancho de banda que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la **página Editar perfil de** directiva de ancho de banda, modifique los campos según sea necesario (para obtener más información, vea Para crear un nuevo perfil de directiva de ancho de [banda).](#to-create-a-new-bandwidth-policy-profile)

7.  Haga clic en **Confirmar**.

    > [!NOTE]  
    > Cuando modifique el perfil de directiva de ancho de banda, se actualizarán inmediatamente las limitaciones de ancho de banda de todos los sitios de red asociados a este perfil de directiva de ancho de banda.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Eliminar perfiles de directiva de ancho de banda de red

Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades. En Skype Empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer limitaciones generales de ancho de banda y sesión. Puede usar el Panel Skype Empresarial Server control para crear, modificar o eliminar un perfil de contenedor para estas directivas. Use los siguientes procedimientos para eliminar perfiles de directiva de ancho de banda de red. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Para eliminar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Directiva de ancho **de banda.**

4.  En la página **Directiva de ancho de banda**, haga clic en el perfil de directiva de ancho de banda que desea eliminar.

    > [!NOTE]  
    > Puede eliminar más de un perfil en la misma operación. Para hacerlo, pulse CTRL y seleccione varios perfiles manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los perfiles, haga clic en **Seleccionar todo** en el menú **Editar**.

5.  En el menú **Editar**, haga clic en **Eliminar**.
   

    > [!WARNING]  
    > No puede eliminar un perfil de directiva de ancho de banda que esté asociado a un sitio de red. Primero debe eliminar la asociación establecida con el sitio de red para poder eliminar el perfil. 


## <a name="see-also"></a>Consulte también

[Administración del control de admisión de llamadas para sitios](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
