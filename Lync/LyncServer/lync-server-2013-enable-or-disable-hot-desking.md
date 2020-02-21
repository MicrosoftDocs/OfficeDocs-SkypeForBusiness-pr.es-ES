---
title: 'Lync Server 2013: habilitar o deshabilitar la entrada manuscrita activa'
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
ms.openlocfilehash: bd0378ee0aead4529b61be5f71aa37a64faf86c5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Habilitar o deshabilitar la entrada manuscrita activa en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Puede configurar teléfonos de área común como *teléfonos de escritorio rápido*. Con los teléfonos de escritorio activo, los usuarios pueden iniciar sesión en su propia cuenta de usuario y, una vez iniciada la sesión, usar las características de Lync Server y su propia configuración de Perfil de usuario. La entrada manuscrita en caliente se administra mediante directivas de cliente: para habilitar o deshabilitar la entrada manuscrita activa, debe modificar las directivas de cliente que usan los teléfonos de área común. Para obtener información detallada sobre cómo determinar las directivas de conferencia que se han asignado a los teléfonos de área común, consulte [ver información de teléfono de área común en Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

Use el parámetro EnableHotdesking del cmdlet **New-CSClientPolicy** o el cmdlet **set-CSClientPolicy** para habilitar o deshabilitar la entrada manuscrita activa en un teléfono, como se indica a continuación. Ejecute estos cmdlets desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>


<div>

## <a name="enabling-hot-desking"></a>Habilitación de la entrada manuscrita activa

  - Para habilitar la entrada manuscrita activa para un teléfono de área común, debe modificar la Directiva de cliente que se ha asignado a ese teléfono (o colección de teléfonos).
    
    Una vez que haya identificado la Directiva que debe modificarse, el siguiente paso consiste en usar el cmdlet **set-CsClientPolicy** para establecer el parámetro EnableHotdesking en true. Por ejemplo:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - Como alternativa, puede usar el cmdlet **New-CsClientPolicy** para crear una nueva Directiva de cliente que permita la entrada manuscrita activa. Por ejemplo:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> Una vez creada esta Directiva, debe asignarla a los teléfonos de área común adecuados. Para obtener más información, consulte <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">asignar directivas en Lync Server 2013 a un teléfono de área común</A>.



</div>

<div>

## <a name="disabling-hot-desking"></a>Deshabilitar la entrada manuscrita activa

  - Para deshabilitar la entrada manuscrita activa para un teléfono de área común, restablezca el parámetro EnableHotdesking del cmdlet **set-CsClientPolicy** en el valor predeterminado de false. Por ejemplo:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Para obtener más información, consulte los temas de ayuda del cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) y el cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

