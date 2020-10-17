---
title: 'Lync Server 2013: crear o modificar subredes de red'
description: 'Lync Server 2013: crear o modificar subredes de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37695707bf39b10c351a4990b132c9799406f9c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546926"
---
# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Crear o modificar subredes de red en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Cada subred de red debe asociarse a un sitio de red para poder determinar la ubicación geográfica del host que pertenece a esta subred. Puede usar el panel de control de Lync Server para configurar subredes. Desde el panel de control de Lync Server, puede crear, modificar o eliminar una subred de red. Para obtener más información sobre cómo eliminar subredes de red, consulte [eliminar subredes de red en Lync Server 2013](lync-server-2013-deleting-network-subnets.md).

En la mayoría de las implementaciones de Microsoft Lync Server 2013 donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes. Por ello, suele ser mejor configurar subredes desde el shell de administración de Lync Server. Desde allí puede llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell. Con todos estos cmdlets puede leer configuraciones de subred desde un archivo .csv y crear varias subredes al mismo tiempo. Para consultar ejemplos sobre cómo crear subredes a partir de un archivo .csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-create-a-network-subnet"></a>Para crear una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Subred**.

4.  En la página **Subred**, haga clic en **Nueva**.

5.  En **Nueva subred**, especifique un valor en el campo **ID de subred**. Debe ser una dirección IP (por ejemplo, 174.11.12.0) y debe estar ubicada en primer lugar en el intervalo de direcciones IP definido por la subred.

6.  En el campo **Máscara**, especifique un valor numérico del 1 al 32.
    
    <div>
    

    > [!NOTE]  
    > Este valor es la máscara de bits que se aplicará a la subred que se está creando.

    
    </div>

7.  En **Id. del sitio de red**, seleccione el sitio al que pertenece la subred.

8.  (Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre esta subred más allá de lo que se pueda deducir de su nombre.

9.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>Para modificar una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y luego en **Subred**.

4.  En la página **Subred**, haga clic en la subred que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar subred**, puede modificar la máscara de bits, el sitio de red asociado o la descripción. Si modifica la máscara de bits, recuerde que el ID de subred debe seguir siendo la primera dirección del intervalo de dirección IP definido en la subred.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Eliminación de subredes de red en Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  


[Acerca de las regiones de red, sitios y subredes en Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

