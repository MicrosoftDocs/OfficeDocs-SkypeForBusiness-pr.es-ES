---
title: 'Lync Server 2013: ver la configuración del servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb3f536a0aadb181b1b740d74c8f61715efed21
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506397"
---
# <a name="view-edge-server-settings-in-lync-server-2013"></a>Ver la configuración del servidor perimetral en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-20_

Las configuraciones de servidor perimetral general deben revisarse en función de los datos de la base de datos de administración de configuración, para ayudar a garantizar que todos los cambios se documentaron según los procedimientos de control de cambios definidos.

Las comprobaciones adicionales podrían incluir las que se describen en las secciones siguientes:

<div>

## <a name="verify-the-allow-and-block-lists"></a>Comprobar las listas de permitidos y bloqueados

Compruebe las listas de URI de SIP "permitir" y "bloquear" para los dominios federados, para determinar si los espacios de nombres enumerados siguen siendo válidos.

Puede usar Windows PowerShell para ver las listas permitidas y bloqueadas. Para revisar los dominios en la lista de dominios permitidos, ejecute el siguiente comando de Windows PowerShell:

`Get-CsAllowedDomain`

Ese comando devuelve información similar a la siguiente para los dominios de la lista de dominios permitidos:

Identidad: contoso.com

Dominio: contoso.com

ProxyFqdn

Sin

MarkForMonitoring: false

Sin

Para revisar los dominios de la lista de dominios bloqueados, use este comando:

`Get-CsBlockedDomain`

A su vez, recibirá información como esta para cada dominio bloqueado:

Identidad: tailspintoys.com

Dominio: tailspintoys.com

Windows PowerShell también le permite comprobar si puede conectarse a los dominios de la lista de dominios permitidos. Por ejemplo, este comando comprueba la conexión entre el servidor perimetral (el TargetFqdn) y el dominio federado contoso.com:

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

Y este comando comprueba la conexión entre el servidor perimetral y todos los dominios que se encuentran en la lista de dominios permitidos:

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>Comprobar que hay varios servidores perimetrales idénticos

Si se implementan varios servidores perimetrales en una matriz con equilibrio de carga, se recomienda comprobar que todos los servidores perimetrales de la matriz se configuran de la misma manera.

Puede ver la configuración de servidores perimetrales en el panel de detalles de la extensión Lync Server 2013 para el complemento Administración de equipos.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Get-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

