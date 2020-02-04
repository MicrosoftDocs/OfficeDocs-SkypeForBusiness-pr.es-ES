---
title: 'Lync Server 2013: configurar una aplicación SNMP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e11d79278318c99e1c6a1db3c4609e19553ba4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Configurar una aplicación SNMP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Lync Server 2013 incluye una interfaz de servicio web estándar que puede usar para conectar el servicio de información de ubicación con aplicaciones de Protocolo simple de administración de redes (SNMP) que coinciden con direcciones MAC con información de puertos y conmutadores.

Si se instala una aplicación SNMP y el servicio de información de ubicación no puede encontrar una coincidencia en la base de datos de ubicación, el servicio de información de ubicación consulta automáticamente la aplicación mediante la dirección MAC proporcionada por el cliente. El servicio de información de ubicación usa la información de puerto y de cambio devuelta por la aplicación SNMP para consultar de nuevo la base de datos de ubicación.

Para obtener más información, consulte [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).

<div>


> [!NOTE]  
> Las direcciones MAC no están disponibles en equipos que ejecutan Windows 8.



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>Para configurar la dirección URL de la aplicación SNMP:

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet siguiente para configurar la dirección URL para la aplicación SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

