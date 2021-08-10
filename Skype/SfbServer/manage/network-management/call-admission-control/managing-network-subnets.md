---
title: Administración de subredes de red
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
description: En la mayoría de las implementaciones Skype Empresarial Server donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes. Debido a esto, a menudo es mejor configurar subredes desde el Shell Skype Empresarial Server administración.
ms.openlocfilehash: c42d0cf4a3970a354183de3bb39878f7955b8678aae93c4f0703257a1ae1f901
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2021
ms.locfileid: "54591104"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Administrar subredes de red en Skype Empresarial Server

Puede usar el Panel de control Skype Empresarial Server o el Shell de administración de Skype Empresarial Server para administrar subredes de red. En la mayoría de las implementaciones Skype Empresarial Server donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes. Debido a esto, a menudo es mejor configurar subredes desde el Shell Skype Empresarial Server administración.

Use las secciones de este artículo para ver información de subred de red o crear, modificar o eliminar subredes de red. 

## <a name="view-network-subnet-information"></a>Ver información de subred de red 

Puede usar el siguiente procedimiento para ver una subred de la red. Desde el panel Skype Empresarial Server control, puede crear, modificar o eliminar una subred de red. 

### <a name="to-view-a-network-subnet"></a>Para ver una subred de la red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Subred**.

4.  En la página **Subred**, haga clic en la subred que desea ver.
 
    > [!NOTE]
    > Solo puede ver una subred de cada vez.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Ver la información de configuración de subred de red mediante Windows PowerShell cmdlets

La información de subred de red se puede ver mediante Windows PowerShell y el cmdlet Get-CsNetworkSubnet red. Este cmdlet se puede ejecutar desde el Shell Skype Empresarial Server administración o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Para ver información de subred de red

  - Para ver información sobre todas las subredes de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
    **Get-CsNetworkSubnet**
    
    Devolverá información similar a la siguiente:
    
    Identidad : 172.11.15.0<br/>
    MaskBits : 28<br/>
    Descripción :<br/>
    NetworkSiteID : Redmond<br/>
    SubnetID : 172.11.15.0<br/>


Para más información, vea el tema de ayuda del cmdlet [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet).


## <a name="create-or-modify-network-subnets"></a>Crear o modificar subredes de red 

Cada subred de red debe asociarse a un sitio de red para poder determinar la ubicación geográfica del host que pertenece a esta subred. Puede usar el Panel de control Skype Empresarial Server para configurar subredes. Desde el panel Skype Empresarial Server control, puede crear, modificar o eliminar una subred de red. 

En la mayoría de las implementaciones Skype Empresarial Server donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes. Debido a esto, a menudo es mejor configurar subredes desde el Shell Skype Empresarial Server administración. Desde allí puede llamar a **New-CsNetworkSubnet** junto con el cmdlet **Windows PowerShell import-CSV**. Con todos estos cmdlets puede leer configuraciones de subred desde un archivo .csv y crear varias subredes al mismo tiempo. Para consultar ejemplos sobre cómo crear subredes a partir de un archivo .csv, consulte [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Para crear una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Subred**.

4.  En la página **Subred**, haga clic en **Nueva**.

5.  En **Nueva subred**, especifique un valor en el campo **ID de subred**. Debe ser una dirección IP (por ejemplo, 174.11.12.0) y debe estar ubicada en primer lugar en el intervalo de direcciones IP definido por la subred.

6.  En el campo **Máscara**, especifique un valor numérico del 1 al 32.

    > [!NOTE]  
    > Este valor es la máscara de bits que se aplicará a la subred que se está creando.

7.  En **Id. del sitio de red**, seleccione el sitio al que pertenece la subred.

8.  (Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre esta subred más allá de lo que se pueda deducir de su nombre.

9.  Haga clic en **Confirmar**.


### <a name="to-modify-a-network-subnet"></a>Para modificar una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Subred**.

4.  En la página **Subred**, haga clic en la subred que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar subred**, puede modificar la máscara de bits, el sitio de red asociado o la descripción. Si modifica la máscara de bits, recuerde que el ID de subred debe seguir siendo la primera dirección del intervalo de dirección IP definido en la subred.

7.  Haga clic en **Confirmar**.

## <a name="delete-network-subnets"></a>Eliminar subredes de red

Puede usar el procedimiento siguiente para eliminar una subred. Desde el panel Skype Empresarial Server control, puede crear, modificar o eliminar una subred de red. 

En la mayoría de las implementaciones Skype Empresarial Server donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes. Debido a esto, a menudo es mejor configurar subredes desde el Shell Skype Empresarial Server administración. Desde allí puede llamar a **New-CsNetworkSubnet** junto con el cmdlet **Windows PowerShell import-CSV**. Con todos estos cmdlets puede leer configuraciones de subred desde un archivo .csv y crear varias subredes al mismo tiempo. Para ver ejemplos de cómo crear subredes desde un archivo .csv, consulte [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>Para eliminar una subred de red:

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Subred**.

4.  En la página **Subred**, haga clic en la subred que desea eliminar.
 
    > [!NOTE]  
    > Puede eliminar simultáneamente varias subredes. Para ello, mantenga presionada la tecla Ctrl y seleccione varias subredes. O bien, para seleccionar todas las subredes, haga clic en **Seleccionar todo** en el menú **Editar**.

5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.


## <a name="see-also"></a>Consulte también

[New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet)