---
title: 'Lync Server 2013: visualización de la información de subred de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a157746e40de8f4793fab24e7e91121779d7602e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-subnet-information-in-lync-server-2013"></a>Ver la información de subred de la red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede usar el procedimiento siguiente para ver una subred de red. En el panel de control de Lync Server, puede crear, modificar o eliminar una subred de red. Para obtener detalles acerca de la creación o modificación de subredes de red, consulte [crear o modificar subredes de red en Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

<div>

## <a name="to-view-a-network-subnet"></a>Para ver una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **subred**.

4.  En la página **subred** , haga clic en la subred que desea ver.
    
    <div>
    

    > [!NOTE]  
    > Solo puedes ver una subred a la vez.

    
    </div>

5.  En el menú **Editar** , haga clic en **Mostrar detalles...**.

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualización de la información de configuración de subred de red con cmdlets de Windows PowerShell

La información de subred de red se puede ver con Windows PowerShell y el cmdlet Get-CsNetworkSubnet. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-view-network-subnet-information"></a>Para ver la información de subred

  - Para ver la información de todas las subredes de la red, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkSubnet
    
    Devolverá información similar a la siguiente:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar subredes de red en Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
[Eliminar subredes de la red en Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

