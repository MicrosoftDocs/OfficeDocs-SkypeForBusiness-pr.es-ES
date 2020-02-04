---
title: 'Lync Server 2013: habilitar o deshabilitar la entrada de lápiz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c56d7ae13be9afa3af7e4732242a86f4be4c458
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Habilitar o deshabilitar la entrada manuscrita en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Puedes configurar teléfonos de área común como *teléfonos de escritorio*. Con los teléfonos de escritorio activo, los usuarios pueden iniciar sesión en su propia cuenta de usuario y, una vez que hayan iniciado sesión, usar las características de Lync Server y su propia configuración de Perfil de usuario. La entrada de lápiz en caliente se administra mediante directivas de cliente: para habilitar o deshabilitar la entrada manuscrita activa, debe modificar las directivas de cliente que usan sus teléfonos de área común. Para obtener más información sobre cómo determinar las directivas de conferencia que se han asignado a los teléfonos de área común, vea [ver información de los teléfonos de áreas comunes en Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

Use el parámetro EnableHotdesking del cmdlet **New-ClientPolicy** o el cmdlet **set-ClientPolicy** para habilitar o deshabilitar la entrada de lápiz caliente en un teléfono, como se indica a continuación. Ejecute estos cmdlets desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>


<div>

## <a name="enabling-hot-desking"></a>Cómo habilitar las entradas de lápiz en caliente

  - Para habilitar la entrada de lápiz para un teléfono de área común, debe modificar la Directiva de cliente que se ha asignado a ese teléfono (o colección de teléfonos).
    
    Una vez identificada la Directiva que debe modificarse, el siguiente paso consiste en usar el cmdlet **set-ClientPolicy** para establecer el parámetro EnableHotdesking en true. Por ejemplo:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - También puede usar el cmdlet **New-ClientPolicy** para crear una nueva Directiva de cliente que permita la entrada de lápiz. Por ejemplo:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> Después de crear esta Directiva, debe asignarla a los teléfonos de área común que corresponda. Para obtener más información, vea <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">asignar directivas en Lync Server 2013 a un teléfono de área común</A>.



</div>

<div>

## <a name="disabling-hot-desking"></a>Deshabilitar la entrada de lápiz

  - Para deshabilitar la entrada de lápiz para un teléfono de área común, restablezca el parámetro EnableHotdesking del cmdlet **set-ClientPolicy** al valor predeterminado de falso. Por ejemplo:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Para obtener más información, consulte los temas de ayuda para el cmdlet [New-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) y el cmdlet [set-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

