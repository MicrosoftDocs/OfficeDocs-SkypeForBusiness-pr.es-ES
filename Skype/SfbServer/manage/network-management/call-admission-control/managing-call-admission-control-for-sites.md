---
title: Administrar el control de admisión de llamadas para sitios
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
description: Los sitios de red son las oficinas o ubicaciones dentro de cada región de la red de control de admisión de llamadas (CAC), E9-1-1 y las implementaciones por omisión de medios.
ms.openlocfilehash: ec2a3dda70bdd4b952169ca663ca271b76f98481
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817519"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Administrar el control de admisión de llamadas para sitios en Skype Empresarial Server

Los sitios de red son las oficinas o ubicaciones dentro de cada región de la red de control de admisión de llamadas (CAC), E9-1-1 y las implementaciones por omisión de medios. Use los procedimientos de este artículo para configurar el control de admisión de llamadas para los sitios de red.

## <a name="configure-network-site-links"></a>Configurar vínculos de sitio de red

Dentro de una configuración de control de admisión de llamadas (CAC), puede crear directivas entre sitios de red que definan limitaciones de ancho de banda entre sitios directamente vinculados. Cuando los sitios de red comparten un vínculo directo, se pueden definir limitaciones de ancho de banda para conexiones de audio y vídeo entre esos dos sitios. No puede usar el panel de control de Skype empresarial Server para configurar directivas de sitio de red, esto solo se puede realizar mediante cmdlets desde el shell de administración de Skype empresarial Server. Puede crear, modificar y quitar un vínculo de sitio de red (también conocido como una directiva entre sitios de red) desde el shell de administración de Skype empresarial Server.

### <a name="to-create-a-network-site-link"></a>Para crear un vínculo de sitio de red

1.  Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.

2.  Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial Server**y, por último, en **consola de administración de Skype empresarial Server**.

3.  En el símbolo del sistema, escriba el siguiente comando y cambie los valores que sean válidos para su configuración:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Este ejemplo crea un nuevo vínculo de sitio de red\_denominado Reno Portland que establece limitaciones de ancho de banda entre los sitios de red de Reno y Portland. Los sitios de red y el perfil de directiva de ancho de banda ya deben existir antes de ejecutar este comando.

Para obtener descripciones detalladas de parámetros, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy). Para recuperar una lista de perfiles de directiva de ancho de banda que se pueden aplicar al vínculo de sitio de red, llame al cmdlet **Get-CsNetworkBandwidthPolicyProfile** . Para obtener más información, vea [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>Para modificar un vínculo de sitio de red

1.  Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.

2.  Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial Server**y, por último, en **consola de administración de Skype empresarial Server**.

3.  Use el cmdlet **set-CsNetworkInterSitePolicy** para modificar las propiedades de un vínculo de sitio de red determinado. Puede modificar uno (o ambos) o los sitios conectados, y puede modificar el perfil de directiva de ancho de banda asociado con el vínculo. Este es un ejemplo de cómo modificar el perfil de directiva de ancho de banda de un\_vínculo a sitios denominado Reno Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Para obtener descripciones detalladas de parámetros, consulte [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>Para eliminar un vínculo de sitio de red

1.  Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.

2.  Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial Server**y, por último, en **consola de administración de Skype empresarial Server**.

3.  Use el cmdlet **Remove-CsNetworkInterSitePolicy** para quitar un vínculo de sitio de red. En el siguiente ejemplo se elimina el\_vínculo de sitio de la red Reno Portland:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Para obtener descripciones detalladas de parámetros, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Ver información del sitio de red

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de control de admisión de llamadas (CAC) o implementación mejorada de 9-1-1. Puede ver la información del sitio de red en el panel de control de Skype empresarial Server o en el shell de administración de Skype empresarial Server. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Para ver la información del sitio de red en el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **sitio**.

4.  En la página del **sitio** , haga clic en el sitio que desea ver.
 
    > [!NOTE]  
    > Solo puede ver la información de un sitio a la vez.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Ver información del sitio de red con cmdlets de Windows PowerShell

Puede ver la información del sitio de red con Windows PowerShell y el cmdlet Get-CsNetworkSite. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-site-information"></a>Para ver la información del sitio de red

  - Para ver información sobre todos los sitios de red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkSite
    
    Devolverá información similar a la siguiente:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .


## <a name="create-or-modify-network-sites"></a>Crear o modificar sitios de red 

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de control de admisión de llamadas (CAC) o implementación mejorada de 9-1-1. Puede usar el panel de control de Skype empresarial Server para configurar sitios y asociarlos con regiones. Por ejemplo, una región de red para Norteamérica puede estar asociada a sitios de redes como Chicago, Redmond y Vancouver. Es necesario crear un sitio de red CAC para cada sitio dentro de una organización, incluso si ese sitio no tiene limitaciones de ancho de banda. Desde el panel de control de Skype empresarial Server puede crear, modificar y eliminar sitios de red. Use los procedimientos siguientes para crear o modificar un sitio de red. 

### <a name="to-create-a-network-site"></a>Para crear un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **sitio**.

4.  En la página **sitio** , haga clic en **nuevo**.

5.  En **nuevo sitio**, escriba un nombre para este sitio en el campo **nombre** .

    > [!NOTE]  
    > Los nombres de los sitios deben ser únicos dentro de la implementación de Skype empresarial Server.

6.  En la lista desplegable **región** , seleccione la región de red que se va a asociar con este sitio.

7.  Faculta Si desea colocar limitaciones de ancho de banda en las llamadas de audio o vídeo a este sitio, seleccione el perfil de directiva de ancho de banda con la configuración adecuada de la lista desplegable **Directiva de ancho de banda** .
 
    > [!NOTE]  
    > Puede ver los detalles de los perfiles de directiva de ancho de banda disponibles o crear un nuevo perfil de directiva de ancho de banda en la página de **Profil de directivas** del grupo **configuración de red** . Para obtener más información, consulte [administrar perfiles de directiva de ancho de banda de red](managing-network-bandwidth-policy-profiles.md).

8.  Faculta Si desea proporcionar la configuración de ubicación para este sitio, seleccione una directiva de ubicación en la lista desplegable **Directiva de ubicación** .

    > [!NOTE]  
    > La Directiva de ubicación asigna una configuración de ubicación de cliente, 9-1-1 (E9-1-1) específica y mejorada al sitio. Puede ver los detalles de las directivas de ubicación disponibles o crear una nueva Directiva de ubicación desde la página de **directivas** de ubicación del grupo **configuración de red** . 

9.  Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre este sitio que no puede expresarse solo por el nombre.

10. Haga clic en **Confirmar**.

    > [!NOTE]  
    > No use la tabla de **subredes asociada** cuando cree un nuevo sitio de red. Al crear o modificar la subred, se asocia una subred con un sitio. Para obtener más información, consulte [Administración de subredes de red](managing-network-subnets.md).

### <a name="to-modify-a-network-site"></a>Para modificar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **sitio**.

4.  En la página del **sitio** , haga clic en el sitio que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar sitio** , puede modificar la descripción, la región, el perfil de la Directiva de ancho de banda y la Directiva de ubicación asociada al sitio. Para obtener más información, consulte [para crear un sitio de red](#to-create-a-network-site) arriba.

7.  Haga clic en **Confirmar**.

No puede modificar la tabla de **subredes asociada** en esta página. La lista de subredes asociadas se proporciona para que sea consciente de las subredes que se verán afectadas al modificar la configuración del sitio.


## <a name="delete-an-existing-network-site"></a>Eliminar un sitio de red existente

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de control de admisión de llamadas (CAC) o implementación mejorada de 9-1-1. Puede usar el panel de control de Skype empresarial Server para configurar sitios y asociarlos con regiones. Por ejemplo, una región de red para Norteamérica puede estar asociada a sitios de redes como Chicago, Redmond y Vancouver. Es necesario crear un sitio de red CAC para cada sitio dentro de una organización, incluso si ese sitio no tiene limitaciones de ancho de banda. Desde el panel de control de Skype empresarial Server puede crear, modificar y eliminar sitios de red. Use el siguiente procedimiento para eliminar un sitio de red existente. Para obtener detalles sobre cómo crear o modificar sitios de red, consulte [administrar el control de admisión de llamadas para sitios](managing-call-admission-control-for-sites.md).


### <a name="to-delete-a-network-site"></a>Para eliminar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **sitio**.

4.  En la página del **sitio** , haga clic en el sitio que desea eliminar.

    > [!NOTE]  
    > Puede eliminar más de un sitio a la vez. Para ello, presione CTRL y seleccione varios sitios mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todos los sitios, haga clic en **seleccionar todo** en el menú **edición** .

5.  En el menú **Editar** , haga clic en **eliminar**.

6.  Haga clic en **Aceptar**.
    

    > [!WARNING]  
    > No puede quitar un sitio de red si está asociado con una subred de red. Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error. Para ver si un sitio está asociado con cualquier subred, haga clic en el sitio y, a continuación, haga clic en **Mostrar detalles** en el menú **edición** .


## <a name="see-also"></a>Vea también


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
