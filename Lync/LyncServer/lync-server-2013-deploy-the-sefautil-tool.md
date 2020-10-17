---
title: 'Lync Server 2013: implementar la herramienta SEFAUtil'
description: 'Lync Server 2013: implementar la herramienta SEFAUtil.'
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
ms.openlocfilehash: 311f14f33dff30b388836a7f02483c4afe5da1b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558616"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Implementar la herramienta SEFAUtil en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Para implementar y administrar la recogida de llamadas de grupo, debe usar la herramienta del kit de recursos de SEFAUtil. La herramienta forma parte de las herramientas del kit de recursos de Lync Server 2013. Para poder instalar SEFAUtil, debe tener un grupo de aplicaciones de confianza en la topología, especificar SEFAUtil como aplicación de confianza y habilitar la topología.

<div>


> [!IMPORTANT]  
> El SDK de la API administrada de comunicaciones unificadas (UCMA) 3,0 de Microsoft debe estar instalado en cualquier equipo en el que tenga previsto ejecutar la herramienta SEFAUtil.



</div>

Puede ejecutar el SEFAUtil en cualquier grupo de servidores front-end en su implementación de.

<div>


> [!NOTE]  
> Para obtener más información sobre cómo ejecutar SEFAUtil, vea el artículo del blog de TechNet sobre cómo obtener SEFAutil en ejecución. en <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A> .



</div>

<div>

## <a name="to-deploy-sefautil"></a>Para implementar SEFAUtil

1.  Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  La herramienta SEFAUtil solo puede ejecutarse en un equipo que forme parte de un grupo de aplicaciones de confianza. Si es necesario, defina un grupo de aplicaciones de confianza para el grupo de servidores front-end en el que planea ejecutar SEFAUtil. En la línea de comandos, ejecute:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Defina la herramienta SEFAUtil como una aplicación de confianza. En la línea de comandos, ejecute:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Puede usar un puerto diferente si es necesario.

    
    </div>

5.  Habilite la topología con los cambios. En la línea de comandos, ejecute:
    
        Enable-CsTopology

6.  Instale las herramientas del kit de recursos de Lync Server 2013 en un servidor front-end que se encuentra en el grupo de aplicaciones de confianza que creó en el paso 3.

7.  Compruebe que la herramienta SEFAUtil se está ejecutando correctamente, de la siguiente manera:
    
    1.  Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para mostrar la configuración de desvío de llamadas de un usuario en la implementación.
        
        <div>
        

        > [!NOTE]  
        > La herramienta se encuentra en \Archivos de Programa\microsoft Lync Server 2013 \ reskit.

        
        </div>
    
    2.  Muestra la configuración de desvío de llamadas de un usuario. En la línea de comandos, ejecute:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Se mostrará la configuración de desvío de llamadas para el usuario.

</div>

</div>

<span> </span>

</div>

</div>

</div>

