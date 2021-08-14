---
title: Administración del control de admisión de llamadas para sitios
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
description: Los sitios de red se encuentran oficinas o ubicaciones dentro de cada región de la red de control de admisión de llamadas (CAC), E9-1-1 y las implementaciones de desvío de medios.
ms.openlocfilehash: fd353980e7ac2a367b05c0f0be6ce760b7102fcc
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233675"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Administrar el control de admisión de llamadas para sitios en Skype Empresarial Server

Los sitios de red se encuentran oficinas o ubicaciones dentro de cada región de la red de control de admisión de llamadas (CAC), E9-1-1 y las implementaciones de desvío de medios. Use los procedimientos de este artículo para configurar el control de admisión de llamadas para los sitios de red.

## <a name="configure-network-site-links"></a>Configurar vínculos de sitio de red

Dentro de una configuración de control de admisión de llamadas (CAC), puede crear directivas entre sitios de red que definan limitaciones de ancho de banda entre sitios que están directamente vinculados. Cuando los sitios de red comparten un vínculo directo, es posible definir limitaciones de ancho de banda para las conexiones de audio y vídeo entre ambos sitos. No puede usar el Panel de control Skype Empresarial Server para configurar directivas de sitio de red, esto solo se puede hacer mediante cmdlets del Shell de administración Skype Empresarial Server administración. Puede crear, modificar y quitar un vínculo de sitio de red (también conocido como directiva entre sitios de red) del Shell de administración Skype Empresarial Server red.

### <a name="to-create-a-network-site-link"></a>Para crear un vínculo de sitio de red

1.  Inicie sesión en el equipo donde Skype Empresarial Server Shell de administración está instalado como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.

2.  Inicie el Shell Skype Empresarial Server de administración: haga clic en Inicio **,** en Todos los **programas,** haga clic en **Skype Empresarial Server** y, a continuación, haga clic **en Skype Empresarial Server Shell de administración**.

3.  Desde el símbolo del sistema, escriba el comando siguiente, usando los valores aplicables a su configuración:
    
     **New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits**
    
    En este ejemplo se crea un nuevo vínculo de sitio de red denominado Reno Portland que establece las limitaciones de ancho de banda entre los sitios de red \_ Reno y Portland. El perfil de la directiva de sitios de red y de ancho de banda debe existir antes de ejecutar este comando.

Para obtener descripciones de parámetros detalladas, [vea New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy). Para recuperar una lista de perfiles de directivas de ancho de banda que puedan aplicarse al vínculo de sitio de red, ejecute el cmdlet **Get-CsNetworkBandwidthPolicyProfile**. Para obtener más información, [vea Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>Para modificar un vínculo de sitio de red

1.  Inicie sesión en el equipo donde Skype Empresarial Server Shell de administración está instalado como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.

2.  Inicie el Shell Skype Empresarial Server de administración: haga clic en Inicio **,** en Todos los **programas,** haga clic en **Skype Empresarial Server** y, a continuación, haga clic **en Skype Empresarial Server Shell de administración**.

3.  Use el cmdlet **Set-CsNetworkInterSitePolicy** para modificar las propiedades de un vínculo de sitio de red. Puede modificar uno de los sitios conectados (o ambos), y también puede modificar el perfil de directiva de banda de ancha asociado al vínculo. Este es un ejemplo de modificación del perfil de directiva de ancho de banda de un vínculo de sitio denominado Reno \_ Portland:
    
    **Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits**

Para obtener descripciones detalladas de los parámetros, [vea Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>Para eliminar un vínculo de sitio de red

1.  Inicie sesión en el equipo donde Skype Empresarial Server Shell de administración está instalado como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.

2.  Inicie el Shell Skype Empresarial Server de administración: haga clic en Inicio **,** en Todos los **programas,** haga clic en **Skype Empresarial Server** y, a continuación, haga clic **en Skype Empresarial Server Shell de administración**.

3.  Use el cmdlet **Remove-CsNetworkInterSitePolicy** para quitar un vínculo de sitio de red. En el siguiente ejemplo se elimina el vínculo de sitio de red Reno \_ Portland:
    
    **Remove-CsNetworkInterSitePolicy -Identity Reno_Portland**

Para obtener descripciones de parámetros detalladas, [vea Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Ver información del sitio de red

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC). Puede ver la información del sitio de red en el Panel de control Skype Empresarial Server o en el Shell Skype Empresarial Server administración. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Para ver información del sitio de red en Skype Empresarial Server Panel de control

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Sitio**.

4.  En la página **Sitio**, haga clic en el sitio que desea ver.
 
    > [!NOTE]
    > Solo puede ver información para un sitio cada vez.

5.  En el menú  **Editar**, haga clic en  **Mostrar detalles**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Visualización de información del sitio de red mediante Windows PowerShell cmdlets

Puede ver la información del sitio de red mediante Windows PowerShell y el cmdlet Get-CsNetworkSite de red. Este cmdlet se puede ejecutar desde el Shell Skype Empresarial Server administración o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-site-information"></a>Para ver la información de sitio de red

  - Para ver información sobre todos los sitios de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
    **Get-CsNetworkSite**
    
    Devolverá información similar a la siguiente:
    
    Identity : Redmond<br/>
    NetworkSiteID : Redmond<br/>
    Descripción :<br/>
    NetworkRegionID : Pacific Northwest<br/>
    BypassID : 3b232b84-2c1d-4da2-8181-e9330bafebe9<br/>
    BWPolicyProfileID :<br/>
    LocationPolicy :<br/>

Para obtener más información, vea el tema de la Ayuda para el cmdlet [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite).


## <a name="create-or-modify-network-sites"></a>Crear o modificar sitios de red 

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC). Puede usar el Panel de control Skype Empresarial Server para configurar sitios y asociarlos a regiones. Por ejemplo, una región de red para Norteamérica se podría asociar con sitios de red como Chicago, Redmond y Vancouver. Debe crearse un sitio de red CAC para cada sitio de una organización, incluso aunque no tenga limitaciones de ancho de banda. Desde el panel Skype Empresarial Server control puede crear, modificar y eliminar sitios de red. Utilice los procedimientos siguientes para crear o modificar un sitio de red. 

### <a name="to-create-a-network-site"></a>Para crear un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Sitio**.

4.  En la página **Sitio**, haga clic en **Nuevo**.

5.  En **Sitio nuevo**, escriba un nombre para este sitio en el campo **Nombre**.

    > [!NOTE]  
    > Los nombres de sitio deben ser únicos en la Skype Empresarial Server implementación.

6.  En la lista desplegable **Región**, seleccione una región de red para asociarla con este sitio.

7.  (Opcional) Si desea definir limitaciones de ancho de banda en las llamadas de audio o vídeo para este sitio, seleccione el perfil de directiva de ancho de banda con la configuración adecuada en la lista desplegable **Directiva de ancho de banda**.
 
    > [!NOTE]  
    > Puede ver los detalles de los perfiles de directiva de ancho  de banda disponibles, o crear un nuevo perfil de directiva de ancho de banda, en la página Perfil de directiva del grupo **Configuración de** red. Para obtener más información, vea [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).

8.  (Opcional) Si desea proporcionar parámetros de ubicación para este sitio, seleccione una directiva de ubicación de la lista desplegable **Directiva de ubicación**.

    > [!NOTE]  
    > La directiva de ubicación asigna al sitio un Enhanced 9-1-1 (E9-1-1) específico y parámetros de ubicación de cliente. Puede ver la información detallada de las directivas de ubicación disponibles o crear una nueva desde la página **Directiva de ubicación** del grupo **Configuración de red**. 

9.  (Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de este sitio más allá de lo que se pueda deducir de su nombre.

10. Haga clic en **Confirmar**.

    > [!NOTE]  
    > No use la tabla **Subredes asociadas** al crear un sitio de red nuevo. Al crear o modificar la subred, asocie una subred con un sitio. Para obtener más información, vea [Managing network subnets](managing-network-subnets.md).

### <a name="to-modify-a-network-site"></a>Para modificar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Sitio**.

4.  En la página **Sitio**, haga clic en el sitio que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar sitio**, puede modificar la descripción, la región, el perfil de directiva de ancho de banda y la directiva de ubicación asociados con el sitio. Para obtener más información, vea [Para crear un sitio de red anterior.](#to-create-a-network-site)

7.  Haga clic en **Confirmar**.

No es posible modificar la tabla **Subredes asociadas** de esta página. La lista de subredes asociadas solo es de referencia, por lo que debe conocer qué subredes se verán afectadas cuando modifique la configuración del sitio.


## <a name="delete-an-existing-network-site"></a>Eliminar un sitio de red existente

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC). Puede usar el Panel de control Skype Empresarial Server para configurar sitios y asociarlos a regiones. Por ejemplo, una región de red para Norteamérica se podría asociar con sitios de red como Chicago, Redmond y Vancouver. Debe crearse un sitio de red CAC para cada sitio de una organización, incluso aunque no tenga limitaciones de ancho de banda. Desde el panel Skype Empresarial Server control puede crear, modificar y eliminar sitios de red. Utilice el procedimiento siguiente para eliminar un sitio de red existente. Para obtener más información sobre cómo crear o modificar sitios de red, vea [Managing call admission control for sites](managing-call-admission-control-for-sites.md).


### <a name="to-delete-a-network-site"></a>Para eliminar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Sitio**.

4.  En la página **Sitio**, haga clic en el sitio que desea eliminar.

    > [!NOTE]  
    > Puede eliminar más de un sitio en la misma operación. Para hacerlo, pulse CTRL y seleccione varios sitios manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los sitios, haga clic en **Seleccionar todo** en el menú **Editar**.

5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.
    

    > [!WARNING]  
    > No se puede eliminar un sitio de red si está asociado con la subred de una red. Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error. Para ver si un sitio está asociado con alguna subred, haga clic en el sitio y, a continuación, haga clic en **Mostrar detalles** en el menú **Editar**.


## <a name="see-also"></a>Vea también


[New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite)