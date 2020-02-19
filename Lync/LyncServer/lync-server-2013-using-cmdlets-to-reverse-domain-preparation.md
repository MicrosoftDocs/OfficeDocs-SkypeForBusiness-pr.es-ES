---
title: 'Lync Server 2013: usar cmdlets para invertir la preparación del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1d1f2bd6d285e57c1db9bdac756685d3c24bd1b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Uso de cmdlets para invertir la preparación del dominio para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Use el cmdlet **Disable-CsAdDomain** para revertir el paso de preparación del dominio.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>Usar cmdlets para revertir la preparación del dominio

1.  Inicie sesión en cualquier servidor del dominio como miembro del grupo Admins. del dominio.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Realizar
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Por ejemplo:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Si el parámetro Force está presente, la preparación del dominio se revierte, incluso si se activan uno o más servidores front-end o servidores de conferencia A/V en el dominio. Si el parámetro Force no está presente, la reversión de la preparación del dominio finaliza si se activan los servidores front-end o los servidores de conferencia A/V del dominio.
    
    <div>
    

    > [!NOTE]  
    > El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global. Si la configuración se guarda en el contenedor del sistema (habitual en implementaciones de actualización cuya configuración global no se ha migrado al contenedor de configuración), deberá definir un controlador de dominio en la raíz del bosque de Active Directory. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), deberá definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet presupone que la configuración se almacena en el contenedor de configuración y hace referencia a cualquier controlador de dominio de&nbsp;AD DS.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Ejecutar la preparación del dominio para Lync Server 2013](lync-server-2013-running-domain-preparation.md)  


[Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

