---
title: 'Lync Server 2013: ver la configuración del servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972a5861af803dbaf66843883595c446345ac29a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>Ver la configuración del servidor perimetral en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-20_

Las configuraciones de servidor de borde general se deben revisar según los datos de la base de datos de administración de la configuración, para ayudar a garantizar que todos los cambios se documentaron según los procedimientos de control de cambios definidos.

Las comprobaciones adicionales podrían incluir las que se describen en las siguientes secciones:

<div>

## <a name="verify-the-allow-and-block-lists"></a>Comprobar las listas permitir o bloquear

Comprobar el URI del SIP las listas "permitir" y "bloquear" de los dominios federados, para determinar si los espacios de nombres en la lista siguen siendo válidos.

Puede usar Windows PowerShell para ver las listas permitidas y bloqueadas. Para revisar los dominios en la lista dominios permitidos, ejecute el siguiente comando de Windows PowerShell:

`Get-CsAllowedDomain`

Ese comando devuelve información similar a la siguiente para los dominios de la lista de dominios permitidos:

Identidad: contoso.com

Dominio: contoso.com

ProxyFqdn :

Lín

MarkForMonitoring: falso

Lín

Para revisar los dominios de la lista de dominios bloqueados, use este comando:

`Get-CsBlockedDomain`

A su vez, recibirá información como esta para cada dominio bloqueado:

Identidad: tailspintoys.com

Dominio: tailspintoys.com

Windows PowerShell también le permite comprobar si puede conectarse a los dominios de su lista de dominios permitidos. Por ejemplo, este comando comprueba la conexión entre el servidor perimetral (el TargetFqdn) y el dominio federado contoso.com:

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

Y este comando comprueba la conexión entre el servidor perimetral y todos los dominios que se encuentran en la lista de dominios permitidos:

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>Comprobar si hay varios servidores perimetrales idénticos

Si se implementan varios servidores perimetrales en una matriz de equilibrio de carga, le recomendamos verificar que todos los servidores perimetrales de la matriz estén configurados de la misma manera.

Puede ver la configuración de los servidores perimetrales en el panel de detalles de la extensión 2013 de Lync Server para el complemento Administración de equipos.

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

