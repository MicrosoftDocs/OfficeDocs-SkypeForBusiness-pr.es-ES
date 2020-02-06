---
title: Administración de subredes de red
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
description: En la mayoría de las implementaciones de Skype empresarial Server donde se implementa el control de admisión de llamadas (CAC), generalmente habrá un gran número de subredes. Por ello, suele ser mejor configurar las subredes desde el shell de administración de Skype empresarial Server.
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817469"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Administrar subredes de red en Skype Empresarial Server

Puede usar el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial Server para administrar subredes de red. En la mayoría de las implementaciones de Skype empresarial Server donde se implementa el control de admisión de llamadas (CAC), generalmente habrá un gran número de subredes. Por ello, suele ser mejor configurar las subredes desde el shell de administración de Skype empresarial Server.

Use las secciones de este artículo para ver información de subred de red o crear, modificar o eliminar subredes de red. 

## <a name="view-network-subnet-information"></a>Ver la información de subred de red 

Puede usar el procedimiento siguiente para ver una subred de red. Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una subred de red. 

### <a name="to-view-a-network-subnet"></a>Para ver una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **subred**.

4.  En la página **subred** , haga clic en la subred que desea ver.
 
    > [!NOTE]  
    > Solo puedes ver una subred a la vez.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Ver la información de configuración de subred de red con cmdlets de Windows PowerShell

La información de subred de red se puede ver con Windows PowerShell y el cmdlet Get-CsNetworkSubnet. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Para ver la información de subred

  - Para ver información sobre todas las subredes de la red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkSubnet
    
    Devolverá información similar a la siguiente:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .


## <a name="create-or-modify-network-subnets"></a>Crear o modificar subredes de red 

Una subred de red debe estar asociada a un sitio de red para determinar la ubicación geográfica del host que pertenece a esta subred. Puede usar el panel de control de Skype empresarial Server para configurar subredes. Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una subred de red. 

En la mayoría de las implementaciones de Skype empresarial Server donde se implementa el control de admisión de llamadas (CAC), generalmente habrá un gran número de subredes. Por ello, suele ser mejor configurar las subredes desde el shell de administración de Skype empresarial Server. Desde allí puedes llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell. Al usar estos cmdlets juntos, puede leer la configuración de la subred de un archivo de valores separados por comas (. csv) y crear varias subredes al mismo tiempo. Para obtener ejemplos de cómo crear subredes a partir de un archivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Para crear una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **subred**.

4.  En la página **subred** , haga clic en **nueva**.

5.  En **nueva subred**, escriba un valor en el campo **ID de subred** . Debe ser una dirección IP (por ejemplo, 174.11.12.0) y debe ser la primera dirección del intervalo de direcciones IP definido por la subred.

6.  En el campo **máscara** , escriba un valor numérico comprendido entre 1 y 32.

    > [!NOTE]  
    > Este valor es la máscara de red que se aplicará a la subred que se va a crear.

7.  En **identificador de sitio de red**, seleccione el sitio al que pertenece esta subred.

8.  Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre esta subred que no puede expresarse solo por el nombre.

9.  Haga clic en **Confirmar**.


### <a name="to-modify-a-network-subnet"></a>Para modificar una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **subred**.

4.  En la página **subred** , haga clic en la subred que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar subred** , puede modificar la máscara de máscara, el sitio de red asociado o la descripción. Si modifica la máscara de subred, tenga en cuenta que el identificador de subred debe ser la primera dirección del intervalo de direcciones IP definido por la subred.

7.  Haga clic en **Confirmar**.

## <a name="delete-network-subnets"></a>Eliminar subredes de red

Puede usar el procedimiento siguiente para eliminar una subred. Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una subred de red. 

En la mayoría de las implementaciones de Skype empresarial Server donde se implementa el control de admisión de llamadas (CAC), generalmente habrá un gran número de subredes. Por ello, suele ser mejor configurar las subredes desde el shell de administración de Skype empresarial Server. Desde allí puedes llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell. Al usar estos cmdlets juntos, puede leer la configuración de la subred de un archivo de valores separados por comas (. csv) y crear varias subredes al mismo tiempo. Para obtener ejemplos de cómo crear subredes a partir de un archivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>Para eliminar una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **subred**.

4.  En la página **subred** , haga clic en la subred que desea eliminar.
 
    > [!NOTE]  
    > Puede eliminar más de una subred a la vez. Para ello, presione CTRL y seleccione varias subredes mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todas las subredes, haga clic en **seleccionar todo** en el menú **edición** .

5.  En el menú **Editar** , haga clic en **eliminar**.

6.  Haga clic en **Aceptar**.


## <a name="see-also"></a>Vea también

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
