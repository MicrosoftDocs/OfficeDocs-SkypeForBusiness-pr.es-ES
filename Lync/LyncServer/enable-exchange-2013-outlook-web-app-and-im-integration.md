---
title: Habilitar la integración de Exchange 2013 Outlook Web App y mensajería instantánea
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da4289f663d62d1638c0f669e17a5e318e0788d3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Habilitar la integración de Exchange 2013 Outlook Web App y mensajería instantánea

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Para habilitar la integración de Exchange 2013 Outlook Web Access (OWA) y la mensajería instantánea (mi) con Lync Server 2013, debe agregar el servidor de servidor de acceso de cliente (CAS) de Exchange 2013 a la topología de Lync Server 2013 como un servidor de aplicaciones de confianza.

<div>

## <a name="to-create-a-trusted-application-pool"></a>Para crear un grupo de aplicaciones de confianza

1.  Inicie el shell de administración de Lync Server 2013.

2.  Ejecute el siguiente cmdlet:
    
        Get-CsSite
    
    Esto devuelve el siteID para el siteName en el que está creando el grupo. Para obtener más información, consulte [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) en la documentación del shell de administración de Lync Server 2013.

3.  Ejecute el siguiente cmdlet:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Para obtener más información, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) en la documentación del shell de administración de Lync Server 2013.
    
    El FQDN de Exchange Server debe configurarse como el nombre alternativo del sujeto (SAN) o el nombre de sujeto (SN) del certificado de Exchange OWA.
    
    En Exchange OWA, compruebe que el FQDN del grupo también es de confianza.
    
    <div>
    

    > [!IMPORTANT]  
    > Si el servidor CAS <EM>no</EM> se encuentra en el mismo servidor que ejecuta la mensajería unificada (MU) de Exchange 2013, omita los pasos restantes de este procedimiento y realice el procedimiento "crear una aplicación de confianza para el servidor Exchange 2013 CAS" más adelante en este tema. Si el servidor CAS está combinado en el mismo servidor que ejecuta la mensajería unificada (MU) de Exchange 2013, complete los pasos de este procedimiento y no realice el procedimiento "crear una aplicación de confianza para el servidor de Exchange 2013 CAS" más adelante en este tema.

    
    </div>

4.  Ejecute **Enable-CsTopology  **.

5.  Abra el Generador de topologías y descargue la topología existente.

6.  En el panel izquierdo, expanda el árbol hasta llegar a **Servidores de aplicaciones de confianza**.

7.  Expanda el nodo **Servidores de aplicaciones de confianza **.

8.  Ahora debería ver el servidor CAS de Exchange 2013 como un servidor de aplicaciones de confianza.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Para crear una aplicación de confianza para el servidor CAS de Exchange 2013

1.  Inicie el shell de administración de Lync Server 2013.

2.  Si el servidor CAS *no* se encuentra en el mismo servidor que ejecuta la mensajería unificada (UM) de Exchange 2013, ejecute el siguiente cmdlet:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Para obtener más información, consulte el tema [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) en la documentación del shell de administración de Lync Server 2013.

3.  Ejecute **Enable-CsTopology**.

4.  En el panel izquierdo del Generador de topologías, expanda el árbol hasta llegar a **Servidores de aplicaciones de confianza**.

5.  Expanda el nodo **Servidores de aplicaciones de confianza**.

6.  Ahora debería ver el servidor CAS de Exchange 2013 como un servidor de aplicaciones de confianza.

</div>

</div>

<span> </span>

</div>

</div>

</div>

