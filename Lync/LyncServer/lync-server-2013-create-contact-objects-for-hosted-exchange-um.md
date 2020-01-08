---
title: 'Lync Server 2013: Crear objetos de contacto para la mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53d5bdfe3b341f534a3e8066fe85be5e93b0a7f7
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Crear objetos de contacto para la mensajería unificada de Exchange hospedada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

El procedimiento siguiente explica cómo crear objetos de contacto de acceso de suscriptor automático (AA) o de acceso de suscriptor (SA) para mensajería unificada de Exchange hospedado (UM).

Para obtener más información, consulte [Administración de objetos de contactos hospedados de Exchange en Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) en la documentación de planeación.

Para obtener detalles sobre la configuración de objetos de contacto, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Antes de que los objetos de contacto de Lync Server 2013 se puedan habilitar para la mensajería unificada de Exchange hospedada, se debe implementar una directiva de correo de voz hospedada que se aplica. Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>Para crear objetos de contacto AA o SA para una mensajería unificada de Exchange hospedado

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsExUmContact para crear cualquier objeto de contacto necesario para su implementación. Por ejemplo, ejecute lo siguiente para crear un objeto de contacto de AA y de SA:
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    Estos ejemplos establecen los siguientes parámetros:
    
      - **SipAddress** especifica la dirección SIP del objeto de contacto. Debe ser una dirección que aún no se haya usado para configurar un objeto de usuario o contacto en los servicios de dominio de Active Directory. Este valor debe tener el formato "SIP:\<*Dirección*\>SIP", tal y como se muestra en los ejemplos anteriores.
    
      - **RegistrarPool** especifica el nombre de dominio completo (FQDN) del grupo en el que se está ejecutando el servicio de registro.
        
        <div class=" ">
        

        > [!NOTE]  
        > Los objetos de contacto de mensajería unificada de Exchange no se pueden mover a los grupos que forman parte de implementaciones de Lync Server 2013 anteriores a Lync Server 2013.

        
        </div>
    
      - **Ou** especifica la unidad organizativa de Active Directory donde se ubicará este objeto de contacto.
    
      - **DisplayNumber** especifica el número de teléfono del objeto de contacto. El número de teléfono de cada objeto de contacto debe ser único.
    
      - **Autoattendant** especifica si el objeto Contact es un operador automático. El operador automático proporciona un conjunto de mensajes de voz que permiten que las personas que llaman puedan navegar por el sistema telefónico y llegar a la persona con quien desean ponerse en contacto. Un valor de **falso** (el valor predeterminado) de este parámetro indica un objeto de contacto de acceso de suscriptor.

</div>

</div>

<span> </span>

</div>

</div>

</div>

