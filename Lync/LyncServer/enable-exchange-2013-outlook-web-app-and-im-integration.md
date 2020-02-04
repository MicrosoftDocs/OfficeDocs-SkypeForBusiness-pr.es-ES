---
title: Habilitar Exchange 2013 Outlook Web App y la integración con mensajería instantánea
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
ms.openlocfilehash: 0bd9fb94dd0f068547819aa884b608ac6ddf7e39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Habilitar Exchange 2013 Outlook Web App y la integración con mensajería instantánea

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Para habilitar la integración de Exchange 2013 Outlook Web Access (OWA) y la mensajería instantánea (mi) con Lync Server 2013, debe agregar el servidor de servidor de acceso de cliente (CA) de Exchange 2013 a la topología de Lync Server 2013 como servidor de aplicaciones de confianza.

<div>

## <a name="to-create-a-trusted-application-pool"></a>Para crear un grupo de aplicaciones de confianza

1.  Inicie el shell de administración de Lync Server 2013.

2.  Ejecute el siguiente cmdlet:
    
        Get-CsSite
    
    Esto devuelve el siteID del siteName en el que está creando el grupo. Para obtener más información, vea [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) en la documentación del shell de administración de Lync Server 2013.

3.  Ejecute el siguiente cmdlet:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Para obtener más información, vea [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) en la documentación del shell de administración de Lync Server 2013.
    
    El FQDN del servidor de Exchange debe configurarse como el nombre de sujeto del certificado OWA de Exchange (SN) o el nombre alternativo de asunto (SAN).
    
    En Exchange OWA, compruebe que el FQDN del grupo también es de confianza.
    
    <div>
    

    > [!IMPORTANT]  
    > Si el servidor CAS <EM>no</EM> se encuentra en el mismo servidor que ejecuta la mensajería unificada (UM) de Exchange 2013, omita los pasos restantes de este procedimiento y realice el procedimiento "crear una aplicación de confianza para el servidor de Exchange 2013" más adelante en este tema. Si el servidor CAS se encuentra en el mismo servidor que ejecuta la mensajería unificada (UM) de Exchange 2013, realice los pasos de este procedimiento y no realice el procedimiento "crear una aplicación de confianza para el servidor CAS de Exchange 2013" más adelante en este tema.

    
    </div>

4.  Ejecute **enable-CsTopology**.

5.  Abra el generador de topologías y descargue la topología existente.

6.  En el panel izquierdo, expanda el árbol hasta llegar a **los servidores de aplicaciones de confianza**.

7.  Expanda el nodo **servidores de aplicaciones de confianza** .

8.  Ahora debería ver el servidor CAS de Exchange 2013, que aparece como servidor de aplicaciones de confianza.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Para crear una aplicación de confianza para el servidor CAS de Exchange 2013

1.  Inicie el shell de administración de Lync Server 2013.

2.  Si el servidor CAS *no* se encuentra en el mismo servidor que ejecuta la mensajería unificada (UM) de Exchange 2013, ejecute el siguiente cmdlet:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Para obtener más información, consulte el tema [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) en la documentación del shell de administración de Lync Server 2013.

3.  Ejecute **enable-CsTopology**.

4.  Desde el generador de topologías, en el panel izquierdo, expanda el árbol hasta llegar a **los servidores de aplicaciones de confianza**.

5.  Expanda el nodo **servidores de aplicaciones de confianza** .

6.  Ahora debería ver el servidor CAS de Exchange 2013, que aparece como servidor de aplicaciones de confianza.

</div>

</div>

<span> </span>

</div>

</div>

</div>

