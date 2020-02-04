---
title: 'Lync Server 2013: Iniciar servicios en servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e6474071e7f95228f3c04c4931b4f899df68b40
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>Iniciar servicios en servidores para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-09-03_

Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins o tener los permisos configurados correctamente. Para obtener más información sobre la delegación de permisos, vea el tema [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Después de instalar el almacén de configuración local en los servidores, instalar los componentes de Lync Server 2013 y configurar certificados en un servidor front-end o un servidor front-end, debe iniciar los servicios de Lync Server 2013 en el servidor. Use el siguiente procedimiento para iniciar servicios en cada servidor front-end de su implementación.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Para iniciar servicios en un servidor Standard Edition o front-end

1.  En el Asistente para la implementación de Lync Server, en la página de **Lync server 2013** , haga clic en **Ejecutar** junto al **paso 4: iniciar servicios**.

2.  En la página **iniciar servicios** , haga clic en **siguiente** para iniciar los servicios de Lync Server en el servidor.

3.  En la página **Ejecución de comandos**, una vez que todos los servicios se hayan iniciado correctamente, haga clic en **Finalizar**.
    
    <div>
    

    > [!IMPORTANT]  
    > El comando para iniciar los servicios en el servidor es el mejor método para notificar que los servicios se han iniciado. Es posible que no refleje el estado actual del servicio. Le recomendamos que use el estado de servicio de Step <STRONG>(opcional)</STRONG> inmediatamente después de <STRONG>iniciar los servicios</STRONG> para abrir Microsoft Management Console (MMC) y confirmar que los servicios se han iniciado correctamente. Si algún servicio de Lync Server no se ha iniciado, puede hacer clic con el botón secundario en el servicio en la MMC y, a continuación, hacer clic en <STRONG>iniciar</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

