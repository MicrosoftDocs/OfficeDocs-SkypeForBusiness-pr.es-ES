---
title: 'Lync Server 2013: Uso de cmdlets para revertir la preparación del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b03ab3218a1568613731efe60eaa95b05a91ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Uso de cmdlets para revertir la preparación del dominio para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Use el cmdlet **Disable-CsAdDomain** para invertir el paso de preparación del dominio.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>Para usar los cmdlets para invertir la preparación del dominio

1.  Inicie sesión en cualquier servidor del dominio como miembro del grupo administradores de dominio.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Por ejemplo:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Si el parámetro Force está presente, la preparación de dominio se revierte, incluso si se activan uno o varios servidores front-end o servidores de conferencia A/V en el dominio. Si el parámetro Force no está presente, la reversión de la preparación de dominios se finaliza si se activan los servidores front-end o los servidores de conferencia A/V del dominio.
    
    <div>
    

    > [!NOTE]  
    > El parámetro GlobalSettingsDomainController le permite indicar dónde se almacena la configuración global. Si la configuración se almacena en el contenedor del sistema (que es habitual en las implementaciones de actualización en las que no se ha migrado la configuración global al contenedor de configuración), se define un controlador de dominio en la raíz del bosque de Active Directory. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), necesitará definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet supone que la configuración se almacena en el contenedor de configuración y se refiere a cualquier controlador de dominio&nbsp;de AD DS.

    
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

