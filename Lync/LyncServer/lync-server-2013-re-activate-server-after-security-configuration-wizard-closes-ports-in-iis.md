---
title: Volver a activar el servidor después de que el Asistente para la configuración de la seguridad cierre los puertos en IIS
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
ms.openlocfilehash: f6642906c1855575fb8077846eef6646bfb37531
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Volver a activar el servidor después de que el Asistente para la configuración de la seguridad cierre los puertos en IIS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Algunas funciones de Lync Server 2013 ejecutan servicios web en el puerto 4443 de Internet Information Services (IIS). Al ejecutar el Asistente para la implementación de Lync Server, Bootstrapper. exe, o mediante el cmdlet **enable-CsComputer** , se crea una excepción en el firewall y se abre el puerto. Si, a continuación, ejecuta el Asistente para la configuración de seguridad de Windows Server 2008 R2 (u otros scripts de refuerzo), el puerto 4443 se bloqueará y los clientes externos no podrán comunicarse con los servicios Web. Para volver a abrir el puerto, puede modificar la excepción del firewall directamente o reactivar el servidor.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>Para volver a activar el servidor mediante el Asistente para la implementación

1.  En la página Asistente para la implementación de Lync Server, haga clic en **Ejecutar** junto al **paso 2: configurar o quitar los componentes de Lync Server**.

2.  En la página **configuración de los componentes de Lync Server** , haga clic en **siguiente**.

3.  En la página **comandos en ejecución** , cuando el estado de la tarea se muestre como completado, haga clic en **Finalizar**.
    
    <div>
    

    > [!NOTE]
    > También puede usar Bootstrapper. exe o <STRONG>enable-CsComputer</STRONG> para volver a activar el servidor.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

