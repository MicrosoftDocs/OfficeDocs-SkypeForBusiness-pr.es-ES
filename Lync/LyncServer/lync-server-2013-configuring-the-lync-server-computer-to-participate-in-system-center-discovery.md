---
title: Configurar el equipo de Lync Server para que participe en la detección de System Center
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
ms.openlocfilehash: 8cec18903f1621d5a616debbbdd16f3c834ac21c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Configurar el equipo de Lync Server 2013 para que participe en la detección de System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Para asegurarse de que el nuevo agente de Lync Server participa en el proceso de detección de System Center Operations Manager, debe completar el siguiente procedimiento en cada equipo en el que se haya instalado la consola de System Center Operations Manager:

1.  En la pestaña **Administración** , haga clic en **agente administrado**.

2.  Haga clic con el botón secundario en el nombre del equipo y, a continuación, haga clic en **Propiedades**. En el cuadro de diálogo **propiedades** , en la pestaña **seguridad** , seleccione **permitir que este agente actúe como proxy y descubrir objetos administrados en otros equipos**y, a continuación, haga clic en **Aceptar**.

Después de completar el paso 2, reinicie el servicio del agente de estado. (Si reinicia el servicio, "forzará" el descubrimiento de la nueva máquina. Si no reinicia el servicio, puede demorar hasta 4 horas antes de que System Center Operations Manager Descubra la nueva máquina.). Después de que el servicio se haya reiniciado, compruebe que no se graban eventos de error en el registro de eventos de Operations Manager de ese equipo.

</div>

<span> </span>

</div>

</div>

</div>

