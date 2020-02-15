---
title: Volver a activar el servidor después de que el Asistente para configuración de seguridad cierre los puertos en IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 388a39c81af2f7e3ca4e0c61f468b283deaa7a4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Volver a activar el servidor después de que el Asistente para configuración de seguridad cierre los puertos en IIS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Algunas funciones de Lync Server 2013 ejecutan servicios web en el puerto 4443 de Internet Information Services (IIS). Al ejecutar el Asistente para la implementación de Lync Server, Bootstrapper. exe, o mediante el cmdlet **enable-CsComputer** , se crea una excepción en el firewall y se abre el puerto. Si, a continuación, ejecuta el Asistente para configuración de seguridad de Windows Server 2008 R2 (u otros scripts de protección), se bloqueará el puerto 4443 y los clientes externos no podrán contactar con los servicios Web. Para volver a abrir el puerto, puede modificar la excepción del firewall directamente o reactivar el servidor.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>Para reactivar el servidor mediante el Asistente para la implementación

1.  En la página Asistente para la implementación de Lync Server, haga clic en **Ejecutar** junto al **paso 2: configurar o quitar componentes de Lync Server**.

2.  En la página **Instalar componentes de Lync Server**, haga clic en **Siguiente**.

3.  Cuando el estado de la tarea aparezca como completado en la página **Ejecución de comandos**, haga clic en **Finalizar**.
    
    <div>
    

    > [!NOTE]
    > Para reactivar el servidor, también puede usar bootstrapper.exe o <STRONG>Enable-CsComputer</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

