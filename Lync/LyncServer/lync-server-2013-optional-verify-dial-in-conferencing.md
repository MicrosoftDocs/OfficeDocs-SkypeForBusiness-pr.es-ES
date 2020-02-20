---
title: 'Lync Server 2013: (opcional) comprobar la Conferencia de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5fbe9298a3a4157dfc62a31d7a429079ac1853
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a>Opcional Comprobar la Conferencia de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2011-01-21_

Para comprobar que la página web Configuración de la conferencia de acceso telefónico local y los números de acceso telefónico local funcionan correctamente, debe realizar las siguientes acciones:

  - Pruebe la página web Configuración de la conferencia de acceso telefónico local iniciando sesión en la dirección URL sencilla.

  - Pruebe que los números de acceso telefónico local funcionan correctamente para un grupo de servidores específico ejecutando el script que se ofrece más adelante en este tema. Este script simula llamadas a números de acceso. Para usar este script necesita la dirección SIP y las credenciales de un cliente de comunicaciones unificadas (UC) que se hospede en el grupo de servidores específico.

Este paso es opcional.

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a>Para probar números de acceso para un grupo de servidores específico

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    El informe resultante indica si hay errores, junto con la información de diagnóstico específica. La marca –Verbose proporciona más información sobre la cantidad de números de acceso que se encontraron y detalles sobre ellos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

