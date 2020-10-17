---
title: Configuración del equipo de Lync Server para participar en la detección de System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9783b8054c74b071c927cc42f32d05700877daad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532377"
---
# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Configuración del equipo de Lync Server 2013 para participar en la detección de System Center

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Para asegurarse de que el nuevo agente de Lync Server participa en el proceso de detección para System Center Operations Manager, debe completar el siguiente procedimiento en cada equipo en el que se haya instalado la consola de System Center Operations Manager:

1.  En la pestaña **Administración**, haga clic en **Agente administrado**.

2.  Haga clic con el botón secundario en el nombre del equipo y, a continuación, haga clic en  **Propiedades**. En el cuadro de diálogo **Propiedades**, en la pestaña **Seguridad**, seleccione **Permitir a este agente que actúe como proxy ay detecte objetos administrados en otros equipos** y luego haga clic en **Aceptar**.

Luego de completar el paso 2, reinicie el servicio Agente de estado. (Reiniciar el servicio “obligará” a que se detecte la nueva máquina. Si no reinicia el servicio, podría demorar hasta 4 horas la detección de la nueva máquina por parte de System Center Operations Manager). Una vez que se haya reiniciado el servicio, verifique que no se registra ningún evento de error en el registro de eventos de Operations Manager en ese equipo.

</div>

<span> </span>

</div>

</div>

</div>

