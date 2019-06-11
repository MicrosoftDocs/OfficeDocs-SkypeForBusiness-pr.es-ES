---
title: 'Lync Server 2013: crear o modificar subredes de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f27088b59745bac580990b3e898f485d34dcad57
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Crear o modificar subredes de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Una subred de red debe estar asociada a un sitio de red para determinar la ubicación geográfica del host que pertenece a esta subred. Puede usar el panel de control de Lync Server para configurar subredes. En el panel de control de Lync Server, puede crear, modificar o eliminar una subred de red. Para más información sobre cómo eliminar subredes de red, vea [eliminar subredes de red en Lync Server 2013](lync-server-2013-deleting-network-subnets.md).

En la mayoría de las implementaciones de Microsoft Lync Server 2013 donde se implementa control de admisión de llamadas (CAC), generalmente habrá un gran número de subredes. Por ello, suele ser mejor configurar las subredes desde el shell de administración de Lync Server. Desde allí puedes llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell. Al usar estos cmdlets juntos, puede leer la configuración de la subred de un archivo de valores separados por comas (. csv) y crear varias subredes al mismo tiempo. Para obtener ejemplos de cómo crear subredes a partir de un archivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-create-a-network-subnet"></a>Para crear una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **subred**.

4.  En la página **subred** , haga clic en **nueva**.

5.  En **nueva subred**, escriba un valor en el campo **ID de subred** . Debe ser una dirección IP (por ejemplo, 174.11.12.0) y debe ser la primera dirección del intervalo de direcciones IP definido por la subred.

6.  En el campo **máscara** , escriba un valor numérico comprendido entre 1 y 32.
    
    <div>
    

    > [!NOTE]  
    > Este valor es la máscara de red que se aplicará a la subred que se va a crear.

    
    </div>

7.  En **identificador de sitio de red**, seleccione el sitio al que pertenece esta subred.

8.  Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre esta subred que no puede expresarse solo por el nombre.

9.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>Para modificar una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **subred**.

4.  En la página **subred** , haga clic en la subred que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar subred** , puede modificar la máscara de máscara, el sitio de red asociado o la descripción. Si modifica la máscara de subred, tenga en cuenta que el identificador de subred debe ser la primera dirección del intervalo de direcciones IP definido por la subred.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar subredes de la red en Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  


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

