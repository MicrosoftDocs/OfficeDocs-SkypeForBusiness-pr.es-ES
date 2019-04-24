---
title: Administración de subredes de red
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En la mayoría de las implementaciones de Skype para Business Server donde se implementa el control de admisión de llamadas (CAC), habrá normalmente un gran número de subredes. Por este motivo, a menudo es mejor configurar subredes desde el Skype para Shell de administración de servidor empresarial.
ms.openlocfilehash: 3b61ad1b4e1eb7f11d61b32c15e337bcd4ff77c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198911"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Administrar subredes de red en Skype Empresarial Server

Puede usar cualquiera el Skype para Panel de Control de servidor empresarial o el Skype para Shell de administración de servidor empresarial para administrar subredes de red. En la mayoría de las implementaciones de Skype para Business Server donde se implementa el control de admisión de llamadas (CAC), habrá normalmente un gran número de subredes. Por este motivo, a menudo es mejor configurar subredes desde el Skype para Shell de administración de servidor empresarial.

Use las secciones de este artículo para ver la información de la subred de red o crear, modificar o eliminar las subredes de la red. 

## <a name="view-network-subnet-information"></a>Ver información de subred de red 

Puede usar el siguiente procedimiento para ver una subred de red. De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una subred de red. 

### <a name="to-view-a-network-subnet"></a>Para ver una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **subred**.

4.  En la página **subred** , haga clic en la subred que desea ver.
 
    > [!NOTE]  
    > Sólo se puede ver una subred a la vez.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Ver la información de configuración de subred de red mediante cmdlets de uso de Windows PowerShell

Información de subred de red puede verse mediante el uso de Windows PowerShell y el cmdlet Get-CsNetworkSubnet. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Para ver la información de la subred de red

  - Para ver información acerca de todas las subredes de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
    
        Get-CsNetworkSubnet
    
    Devolverá información similar a la siguiente:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .


## <a name="create-or-modify-network-subnets"></a>Crear o modificar subredes de red 

Una subred de red debe asociarse con un sitio de red con el fin de determinar la ubicación geográfica del host que pertenecen a esta subred. Puede usar el Skype para el Panel de Control de servidor empresarial para configurar subredes. De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una subred de red. 

En la mayoría de las implementaciones de Skype para Business Server donde se implementa el control de admisión de llamadas (CAC), habrá normalmente un gran número de subredes. Por este motivo, a menudo es mejor configurar subredes desde el Skype para Shell de administración de servidor empresarial. Desde allí puede llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell. Mediante el uso de estos cmdlets juntos, puede leer en configuración de subred desde un archivo de valores separados por comas (.csv) y crear varias subredes al mismo tiempo. Para obtener ejemplos de cómo crear subredes desde un archivo .csv, vea [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Para crear una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **subred**.

4.  En la página **subred** , haga clic en **nuevo**.

5.  En la **Nueva subred**, escriba un valor en el campo **ID de subred** . Esto debe ser una dirección IP (por ejemplo, 174.11.12.0), y debe ser la primera dirección en el intervalo de direcciones IP definido por la subred.

6.  En el campo **máscara** , escriba un valor numérico comprendido entre 1 y 32.

    > [!NOTE]  
    > Este valor es la máscara de bits que se va a aplicar a la subred que se está creando.

7.  En el **identificador de sitio de red**, seleccione el sitio al que pertenece esta subred.

8.  (Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de esta subred que se pueda deducir de su nombre.

9.  Haga clic en **Confirmar**.


### <a name="to-modify-a-network-subnet"></a>Para modificar una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **subred**.

4.  En la página **subred** , haga clic en la subred que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar subred** , puede modificar la máscara de bits, el sitio de red asociados o la descripción. Si modifica la máscara de bits, tenga en cuenta que el ID de subred aún debe ser la primera dirección en el intervalo de direcciones IP definido por la subred.

7.  Haga clic en **Confirmar**.

## <a name="delete-network-subnets"></a>Eliminación de subredes de red

Puede usar el siguiente procedimiento para eliminar una subred. De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una subred de red. 

En la mayoría de las implementaciones de Skype para Business Server donde se implementa el control de admisión de llamadas (CAC), habrá normalmente un gran número de subredes. Por este motivo, a menudo es mejor configurar subredes desde el Skype para Shell de administración de servidor empresarial. Desde allí puede llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell. Mediante el uso de estos cmdlets juntos, puede leer en configuración de subred desde un archivo de valores separados por comas (.csv) y crear varias subredes al mismo tiempo. Para obtener ejemplos de cómo crear subredes desde un archivo .csv, vea [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>Para eliminar una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **subred**.

4.  En la página **subred** , haga clic en la subred que desea eliminar.
 
    > [!NOTE]  
    > Puede eliminar más de una subred a la vez. Para ello, presione la tecla CTRL y seleccione varias subredes mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todas las subredes, haga clic en **Seleccionar todo** en el menú **Edición** .

5.  En el menú **Edición** , haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.


## <a name="see-also"></a>Consulte también

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
