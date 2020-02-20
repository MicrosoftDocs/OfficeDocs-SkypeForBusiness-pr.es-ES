---
title: 'Lync Server 2013: eliminación de subredes de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f371dde69c95920def1785b3565573b2dc24f93c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>Eliminación de subredes de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Puede usar el procedimiento siguiente para eliminar una subred. Desde el panel de control de Lync Server, puede crear, modificar o eliminar una subred de red. Para obtener más información sobre cómo crear o modificar subredes de red, vea [crear o modificar subredes de red en Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

En la mayoría de las implementaciones de Microsoft Lync Server 2013 donde se implementa el control de admisión de llamadas (CAC), normalmente habrá un gran número de subredes. Por ello, suele ser mejor configurar subredes desde el shell de administración de Lync Server. Desde allí puede llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV**de Windows PowerShell. Con todos estos cmdlets puede leer configuraciones de subred desde un archivo .csv y crear varias subredes al mismo tiempo. Para ver ejemplos de cómo crear subredes desde un archivo .csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-delete-a-network-subnet"></a>Para eliminar una subred de red:

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y en **Subred**.

4.  En la página **Subred**, haga clic en la subred que desea eliminar.
    
    <div>
    

    > [!NOTE]  
    > Puede eliminar simultáneamente varias subredes. Para ello, mantenga presionada la tecla Ctrl y seleccione varias subredes. O bien, para seleccionar todas las subredes, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.

    
    </div>

5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar subredes de red en Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

