---
title: Mover objetos de contacto de mensajería unificada de Exchange
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c9a16251ca49d4d5179ed3ad72e4d0307beb4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Mover objetos de contacto de mensajería unificada de Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Para migrar los objetos de contacto de operador automático (AA) y acceso de suscriptor (SA) a la nueva implementación de Lync Server 2013, primero debe mover los objetos de la implementación heredada de Office Communications Server 2007 R2 a la nueva implementación de Lync Server 2013 con los cmdlets **Get-CsExUmContact** y **Move-CsExUmContact** . En el servidor de Exchange, ejecute el script de Windows PowerShell **script ExchUCUtil** para hacer lo siguiente para el grupo de Lync recién implementado:

  - Agregarlo a las puertas de enlace de IP de mensajería unificada.

  - Agregarlo a los grupos de búsqueda de Mensajería unificada.

<div>


> [!NOTE]  
> Para usar los cmdlets <STRONG>Get-CsExUmContact</STRONG> y <STRONG>Move-CsExUmContact</STRONG>, debe pertenecer al grupo RTCUniversalUserAdmins y tener permiso de unidad organizativa (OU) en la OU en donde se almacenan los objetos de contacto. El permiso de OU se puede conceder con el cmdlet <STRONG>Grant-OUPermission</STRONG>.



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Para mover objetos de contacto mediante el Shell de administración de Lync Server

1.  Abra el Shell de administración de Lync Server.

2.  Para cada grupo registrado con mensajería unificada de Exchange (donde pool1.contoso.net es un grupo de servidores de la implementación de Office Communications Server 2007 R2 y pool2.contoso.net es el grupo de servidores de la implementación de Lync Server 2013) en la línea de comandos, escriba lo siguiente:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Para comprobar que se mueven los objetos de contacto, ejecute el cmdlet **Get-CsExumContact**  y confirme que **RegistrarPool** está señalando ahora al nuevo grupo de servidores.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>Para ejecutar el script ExchUCUtil de Windows PowerShell

1.  Inicie sesión en el servidor de Mensajería unificada de Exchange como usuario con privilegios de administrador de organización de Exchange.

2.  Navegue al script de Windows PowerShell script ExchUCUtil.
    
    En Exchange 2007, script ExchUCUtil. PS1 se encuentra en: **% archivos de programa\\%\\Microsoft Exchange\\Server\\scripts script ExchUCUtil. PS1**
    
    En Exchange 2010, script ExchUCUtil. PS1 se encuentra en: **% archivos de programa\\%\\Microsoft Exchange\\Server\\V14\\scripts script ExchUCUtil. PS1**

3.  Si Exchange se implementa en un solo bosque, escriba:
    
        exchucutil.ps1
    
    Si Exchange se implementa en varios bosques, escriba:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    donde FQDN del bosque especifica el bosque en el que se implementa Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Asegúrese de reiniciar el servicio <STRONG>Front-end de Lync Server</STRONG> (rtcsrv.exe) <EM>después</EM> de ejecutar exchucutil.ps1. De lo contrario, Lync Server 2013 no detectará la mensajería unificada en la topología.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

