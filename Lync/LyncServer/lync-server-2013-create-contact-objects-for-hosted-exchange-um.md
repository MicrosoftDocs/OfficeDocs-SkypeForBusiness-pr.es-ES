---
title: 'Lync Server 2013: crear objetos de contacto para la mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07b363c3f52abe2e62955d456f9d708393e4574b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Crear objetos de contacto para la mensajería unificada de Exchange hospedada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

El siguiente procedimiento explica cómo crear objetos de contacto de operador automático (AA) o de acceso de suscriptor (SA) para mensajería unificada (UM) hospedada de Exchange.

Para obtener más información, consulte [Hosted Exchange Contact Object Management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) en la documentación referente a la planeación.

Para obtener más información acerca de la configuración de objetos de contacto, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Antes de que Lync Server 2013 los objetos de contacto se puedan habilitar para la mensajería unificada de Exchange hospedada, debe implementarse una directiva de correo de voz hospedada que se les aplique. Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>Para crear objetos de contacto AA o SA para la mensajería unificada de Exchange hospedada

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsExUmContact para crear cualquier objeto de contacto necesario para la implementación. Por ejemplo, ejecute lo siguiente para crear un objeto de contacto de la AA y de la Asociación:
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    En estos ejemplos se establecen los siguientes parámetros:
    
      - **SipAddress** especifica la dirección SIP del objeto de contacto. Debe tratarse de una dirección que aún no se haya usado para configurar un objeto de contacto o de usuario en servicios de dominio de Active Directory. Este valor debe tener el formato "SIP:\<*Dirección*\>SIP", tal como se muestra en los ejemplos anteriores.
    
      - **RegistrarPool** especifica el nombre de dominio completo (FQDN) del grupo en el que se está ejecutando el servicio de registrador.
        
        <div class=" ">
        

        > [!NOTE]  
        > Los objetos de contacto de mensajería unificada de Exchange no se pueden mover a los grupos que forman parte de implementaciones de Lync Server 2013 anteriores a Lync Server 2013.

        
        </div>
    
      - **Ou** especifica la unidad organizativa de Active Directory donde se ubicará este objeto de contacto.
    
      - **DisplayNumber** especifica el número de teléfono del objeto de contacto. El número de teléfono de cada objeto de contacto debe ser único.
    
      - **Autoattendant** especifica si el objeto de contacto es un operador automático. Operador automático proporciona un conjunto de mensajes de voz que permiten a los autores de llamadas navegar por el sistema telefónico y llegar a la parte de la que quieren contactar. Un valor de **false** (valor predeterminado) para este parámetro indica un objeto de contacto de acceso de suscriptor.

</div>

</div>

<span> </span>

</div>

</div>

</div>

