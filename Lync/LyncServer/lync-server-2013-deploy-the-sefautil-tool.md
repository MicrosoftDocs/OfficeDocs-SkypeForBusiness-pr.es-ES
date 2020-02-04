---
title: 'Lync Server 2013: implementar la herramienta SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd995a99514fa54a221e17f1ea556565cbebdcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Deploy the SEFAUtil tool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Para implementar y administrar la recopilación de llamadas de grupo, necesita usar la herramienta del kit de recursos de SEFAUtil. La herramienta forma parte de las herramientas del kit de recursos de Lync Server 2013. Para poder instalar SEFAUtil, debe disponer de un grupo de aplicaciones de confianza en su topología, especificar SEFAUtil como una aplicación de confianza y habilitar la topología.

<div>


> [!IMPORTANT]  
> Instale el SDK de la API administrada de comunicaciones unificadas (UCMA) de Microsoft 3.0 Core en los equipos donde planee ejecutar la herramienta SEFAUtil.



</div>

Puede ejecutar el SEFAUtil en cualquier grupo de servidores front-end de su implementación.

<div>


> [!NOTE]  
> Para obtener más información sobre cómo ejecutar SEFAUtil, consulte el artículo del blog de TechNet, "Cómo obtener SEFAutil en ejecución". en <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.



</div>

<div>

## <a name="to-deploy-sefautil"></a>Para implementar SEFAUtil

1.  Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  La herramienta SEFAUtil solo se puede ejecutar en un equipo que forme parte de un grupo de aplicaciones de confianza. Si es necesario, defina un grupo de aplicaciones de confianza para el grupo de servidores front-end en el que tiene previsto ejecutar SEFAUtil. En la línea de comandos, ejecute:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Defina la herramienta SEFAUtil como aplicación de confianza. En la línea de comandos, ejecute:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Si es preciso, puede usar otro puerto.

    
    </div>

5.  Habilite la topología con los cambios. En la línea de comandos, ejecute:
    
        Enable-CsTopology

6.  Instale las herramientas del kit de recursos de Lync Server 2013 en un servidor front-end que se encuentra en el grupo de aplicaciones de confianza que creó en el paso 3.

7.  Compruebe que la herramienta SEFAUtil funcione correctamente, tal como se indica:
    
    1.  Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para que aparezca la configuración de reenvío de llamadas de un usuario en la implementación.
        
        <div>
        

        > [!NOTE]  
        > La herramienta se encuentra en \Archivos de Programa\microsoft Lync Server 2013 \ reskit.

        
        </div>
    
    2.  Muestre la configuración de reenvío de llamadas de un usuario. En la línea de comandos, ejecute:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Aparecerá la configuración de reenvío de llamadas del usuario.

</div>

</div>

<span> </span>

</div>

</div>

</div>

