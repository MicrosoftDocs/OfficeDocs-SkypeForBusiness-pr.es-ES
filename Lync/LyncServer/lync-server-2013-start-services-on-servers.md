---
title: 'Lync Server 2013: iniciar servicios en servidores'
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
ms.openlocfilehash: 4cab7d2e53b981cc971284cfad37f89ca4749590
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>Inicie los servicios en los servidores para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-09-03_

Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario miembro del grupo RTCUniversalServerAdmins o tener los permisos correctos delegados. Para obtener más información sobre cómo delegar permisos, consulte el tema [permisos para delegar la instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Después de instalar el almacén de configuración local en los servidores, instalar los componentes de Lync Server 2013 y configurar los certificados en un servidor front-end o en un servidor front-end, debe iniciar los servicios de Lync Server 2013 en el servidor. Use el siguiente procedimiento para iniciar servicios en cada servidor front-end de su implementación de.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Para iniciar servicios en un servidor Standard Edition o front-end

1.  En el Asistente para la implementación de Lync Server, en la página **Lync server 2013** , haga clic en **Ejecutar** junto al **paso 4: iniciar servicios**.

2.  En la página **iniciar servicios** , haga clic en **siguiente** para iniciar los servicios de Lync Server en el servidor.

3.  En la página **Ejecución de comandos**, una vez que todos los servicios se hayan iniciado correctamente, haga clic en **Finalizar**.
    
    <div>
    

    > [!IMPORTANT]  
    > El comando para iniciar los servicios en el servidor es un método de "mejor esfuerzo" para informar de que los servicios ya se han iniciado. Es posible que no refleje el estado actual del servicio. Se recomienda llevar a cabo el paso <STRONG>Estado del servicio (opcional)</STRONG> justo después de <STRONG>Iniciar servicios</STRONG> para abrir Microsoft Management Console (MMC) y comprobar si los servicios se han iniciado correctamente. Si algún servicio de Lync Server no se ha iniciado, puede hacer clic con el botón secundario en el servicio en MMC y, a continuación, hacer clic en <STRONG>iniciar</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

