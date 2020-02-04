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
ms.openlocfilehash: d79354522675daaf221052579b0863899d1176ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Mover objetos de contacto de mensajería unificada de Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Para migrar los objetos de contacto del operador automático (AA) y del acceso de suscriptor (SA) a la nueva implementación de Lync Server 2013, primero debe mover los objetos de la implementación heredada de Office Communications Server 2007 R2 a la nueva implementación de Lync Server 2013 con los cmdlets **Get-CsExUmContact** y **Move-CsExUmContact** . En el servidor de Exchange, ejecute el script de Windows PowerShell **ExchUCUtil** para hacer lo siguiente para el grupo de Lync recién implementado:

  - Agréguelo a las puertas de enlace IP de mensajería unificada.

  - Agréguelo a los grupos de captura de mensajería unificada.

<div>


> [!NOTE]  
> Para poder usar los cmdlets <STRONG>Get-CsExUmContact</STRONG> y <STRONG>Move-CsExUmContact</STRONG> , debe ser miembro del grupo RTCUniversalUserAdmins y tener permisos de unidad organizativa (OU) en la ou donde se almacenan los objetos de contactos. El permiso de uo se puede conceder mediante el cmdlet <STRONG>Grant-OUPermission</STRONG> .



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Para mover objetos de contacto mediante el shell de administración de Lync Server

1.  Abra el shell de administración de Lync Server.

2.  Para cada grupo registrado con Exchange UM (donde pool1.contoso.net es un grupo de la implementación de Office Communications Server 2007 R2 y pool2.contoso.net es el grupo de la implementación de Lync Server 2013) en la línea de comandos, escriba lo siguiente:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Para comprobar que los objetos de contacto se mueven, ejecute el cmdlet **Get-CsExumContact** y confirme que **RegistrarPool** apunta al nuevo grupo.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>Para ejecutar el script de Windows PowerShell ExchUCUtil

1.  Inicie sesión en el servidor de mensajería unificada de Exchange como usuario con privilegios de administrador de la organización de Exchange.

2.  Vaya al script de Windows PowerShell ExchUCUtil.
    
    En Exchange 2007, ExchUCUtil. PS1 se encuentra en: **% archivos de programa\\%\\Microsoft Exchange\\Server\\scripts ExchUCUtil. PS1**
    
    En Exchange 2010, ExchUCUtil. PS1 se encuentra en: **% archivos de programa\\%\\Microsoft Exchange\\Server\\V14\\scripts ExchUCUtil. PS1**

3.  Si Exchange se implementa en un único bosque, escriba:
    
        exchucutil.ps1
    
    O bien, si Exchange se implementa en varios bosques, escriba:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    donde FQDN de bosque especifica el bosque en el que se implementa Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Asegúrese de reiniciar el servicio <STRONG>front-end de Lync Server</STRONG> (RtcSrv. exe) <EM>después</EM> de ejecutar ExchUCUtil. ps1. De lo contrario, Lync Server 2013 no detectará la mensajería unificada en la topología.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

