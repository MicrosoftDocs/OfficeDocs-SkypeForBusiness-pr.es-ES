---
title: Administración de control de admisión de llamadas para sitios
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sitios de red son las oficinas o ubicaciones dentro de cada región de red de llamadas (CAC) el control de admisión, E9-1-1 y las implementaciones de desvío de medios.
ms.openlocfilehash: ecf23a8a052afbd21b02f8ff5507c248d42b7118
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223174"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Administración de control de admisión de llamadas para sitios de Skype para Business Server

Sitios de red son las oficinas o ubicaciones dentro de cada región de red de llamadas (CAC) el control de admisión, E9-1-1 y las implementaciones de desvío de medios. Use los procedimientos de este artículo para configurar el control de admisión de llamadas para sitios de red.

## <a name="configure-network-site-links"></a>Configuración de vínculos de sitio de red

Dentro de una configuración de (CAC) del control de admisión de llamadas, puede crear directivas entre sitios que definen las limitaciones de ancho de banda entre sitios que están vinculados directamente de red. Cuando los sitios de red compartirán un vínculo directo, se pueden definir las limitaciones de ancho de banda para las conexiones de audio y vídeos entre los dos sitios. No se puede usar el Skype para el Panel de Control de servidor empresarial para configurar las directivas de sitio de red, esto puede realizarse sólo mediante el uso de cmdlets desde el Skype de consola de administración de servidor empresarial. Puede crear, modificar y quitar un vínculo de sitio de red (también conocido como una directiva entre sitios de red) de la Skype para Shell de administración de servidor empresarial.

### <a name="to-create-a-network-site-link"></a>Para crear un vínculo de sitio de red

1.  Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.

2.  Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.

3.  En el símbolo del sistema, escriba el siguiente comando, sustituyendo los valores que son válidos para su configuración:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    En este ejemplo se crea un nuevo vínculo de sitio de red denominado Reno\_Portland que establece las limitaciones de ancho de banda entre los sitios de red Reno y Portland. Los sitios de red y el perfil de directiva de ancho de banda ya deben existir antes de ejecutar este comando.

Para obtener descripciones de parámetros detalladas, vea [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy). Para recuperar una lista de perfiles de directivas de ancho de banda que se puede aplicar el vínculo de sitio de red, llamar al cmdlet **Get-CsNetworkBandwidthPolicyProfile** . Para obtener información detallada, vea [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>Para modificar un vínculo de sitio de red

1.  Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.

2.  Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.

3.  Use el cmdlet **Set-CsNetworkInterSitePolicy** para modificar las propiedades de un vínculo de sitio de red determinado. Puede modificar una (o ambas) o los sitios conectados y se puede modificar el perfil de directiva de ancho de banda asociado con el vínculo. Este es un ejemplo de cómo modificar el perfil de directiva de ancho de banda de un vínculo de sitio denominado Reno\_Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Para obtener descripciones de parámetros detalladas, consulte [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>Para eliminar un vínculo de sitio de red

1.  Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.

2.  Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.

3.  Use el cmdlet **Remove-CsNetworkInterSitePolicy** para quitar un vínculo de sitio de red. En el ejemplo siguiente se elimina el Reno\_vínculo de sitio de red de Portland:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Para obtener descripciones de parámetros detalladas, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Ver información de sitios de red

Sitios de red son las oficinas o las ubicaciones configuradas dentro de cada región de un control de admisión de llamadas (CAC) o la implementación de Enhanced 9-1-1. Puede ver información de sitio de red en puede ser la Skype para el Panel de Control de servidor empresarial o el Skype para Shell de administración de servidor empresarial. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Para ver la información de sitio de red en Skype para el Panel de Control de servidor empresarial

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **sitio**.

4.  En la página del **sitio** , haga clic en el sitio que desea ver.
 
    > [!NOTE]  
    > Sólo se puede ver información para un sitio a la vez.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de sitio de red mediante el uso de cmdlets de Windows PowerShell

Puede ver información de sitio de red mediante el uso de Windows PowerShell y el cmdlet Get-CsNetworkSite. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-site-information"></a>Para ver la información de sitio de red

  - Para ver información acerca de todos los sitios de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
    
        Get-CsNetworkSite
    
    Devolverá información similar a la siguiente:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .


## <a name="create-or-modify-network-sites"></a>Crear o modificar sitios de red 

Sitios de red son las oficinas o las ubicaciones configuradas dentro de cada región de un control de admisión de llamadas (CAC) o la implementación de Enhanced 9-1-1. Puede usar el Skype para el Panel de Control de servidor empresarial para configurar sitios y asociarlos a regiones. Por ejemplo, una región de red para Norteamérica podría ser asociada a los sitios de redes como Chicago, Redmond y Vancouver. Debe crearse un sitio de red CAC para cada sitio dentro de una organización, incluso si ese sitio tiene no hay limitaciones de ancho de banda. Desde el Skype para el Panel de Control de servidor empresarial puede crear, modificar y eliminar sitios de red. Use los procedimientos siguientes para crear o modificar un sitio de red. 

### <a name="to-create-a-network-site"></a>Para crear un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **sitio**.

4.  En la página del **sitio** , haga clic en **nuevo**.

5.  En el **Nuevo sitio**, escriba un nombre para este sitio en el campo **nombre** .

    > [!NOTE]  
    > Los nombres de sitios deben ser únicos dentro de la Skype para la implementación de Business Server.

6.  En la lista desplegable **región** , seleccione una región de red para asociar con este sitio.

7.  (Opcional) Si desea poner limitaciones de ancho de banda en llamadas de audio o vídeos a este sitio, seleccione el perfil de directiva de ancho de banda con la configuración correspondiente de la lista desplegable **Directiva de ancho de banda** .
 
    > [!NOTE]  
    > Puede ver los detalles de los perfiles de directiva de ancho de banda disponible, o crear un nuevo perfil de directiva de ancho de banda, en la página **Perfiles de directiva de** grupo de la **Configuración de red** . Para obtener información detallada, vea [perfiles de directivas de ancho de banda de red de administración](managing-network-bandwidth-policy-profiles.md).

8.  (Opcional) Si desea proporcionar parámetros de ubicación para este sitio, seleccione una directiva de ubicación de la lista desplegable **Directiva de ubicación** .

    > [!NOTE]  
    > La directiva de ubicación asigna específico Enhanced 9-1-1 (E9-1-1) y el cliente de configuración de ubicación al sitio. Puede ver los detalles de las directivas de ubicación disponibles, o crear una nueva directiva de ubicación, desde la página **Directiva de ubicación** del grupo de **Configuración de red** . 

9.  (Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de este sitio que se pueda deducir de su nombre.

10. Haga clic en **Confirmar**.

    > [!NOTE]  
    > No use la tabla de **Subredes asociadas** al crear un nuevo sitio de red. Asociar una subred a un sitio al crear o modificar la subred. Para obtener información detallada, vea [Managing subredes de la red](managing-network-subnets.md).

### <a name="to-modify-a-network-site"></a>Para modificar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **sitio**.

4.  En la página del **sitio** , haga clic en el sitio que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Modificar sitio** , puede modificar la descripción, región, perfil de directiva de ancho de banda y directiva de ubicación asociada con el sitio. Para obtener más información, vea [para crear un sitio de red](#to-create-a-network-site) anterior.

7.  Haga clic en **Confirmar**.

No se puede modificar la tabla de **Subredes asociadas** en esta página. La lista de subredes asociadas se proporciona como referencia para que tener en cuenta qué subredes se verán afectadas cuando se modifica la configuración del sitio.


## <a name="delete-an-existing-network-site"></a>Eliminación de un sitio de red existente

Sitios de red son las oficinas o las ubicaciones configuradas dentro de cada región de un control de admisión de llamadas (CAC) o la implementación de Enhanced 9-1-1. Puede usar el Skype para el Panel de Control de servidor empresarial para configurar sitios y asociarlos a regiones. Por ejemplo, una región de red para Norteamérica podría ser asociada a los sitios de redes como Chicago, Redmond y Vancouver. Debe crearse un sitio de red CAC para cada sitio dentro de una organización, incluso si ese sitio tiene no hay limitaciones de ancho de banda. Desde el Skype para el Panel de Control de servidor empresarial puede crear, modificar y eliminar sitios de red. Use el procedimiento siguiente para eliminar un sitio de red existente. Para obtener información detallada acerca de la creación o modificación de sitios de red, consulte [Managing control de admisión de llamadas para los sitios](managing-call-admission-control-for-sites.md).


### <a name="to-delete-a-network-site"></a>Para eliminar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **sitio**.

4.  En la página del **sitio** , haga clic en el sitio que desea eliminar.

    > [!NOTE]  
    > Puede eliminar más de un sitio a la vez. Para ello, presione la tecla CTRL y seleccione varios sitios mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todos los sitios, haga clic en **Seleccionar todo** en el menú **Edición** .

5.  En el menú **Edición** , haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.
    

    > [!WARNING]  
    > No se puede quitar un sitio de red si está asociada con una subred de red. Si se intenta eliminar un sitio asociado con una subred recibirá un mensaje de error. Para ver si un sitio está asociado a las subredes, haga clic en el sitio y, a continuación, haga clic en **Mostrar detalles** en el menú **Edición** .


## <a name="see-also"></a>Consulte también


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  