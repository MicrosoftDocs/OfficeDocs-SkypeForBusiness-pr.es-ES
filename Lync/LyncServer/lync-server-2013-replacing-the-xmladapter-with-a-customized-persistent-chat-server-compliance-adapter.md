---
title: 'Lync Server 2013: reemplazar XmlAdapter por un adaptador de cumplimiento del servidor de chat persistente personalizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e9cd9f2e950e835a113f64795022753e44e3ff5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Reemplazar el XmlAdapter por un adaptador de cumplimiento del servidor de chat persistente personalizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Puede escribir un adaptador personalizado en lugar de usar XmlAdapter que se instala con el servidor de chat persistente. Para ello, debe proporcionar un ensamblado de .NET Framework que contenga una clase pública que implemente la interfaz **IComplianceAdapter** . Debe situar este ensamblado en la carpeta de instalación del servidor de chat persistente de cada servidor del grupo de servidores de chat persistente. Cualquiera de los servidores de cumplimiento puede proporcionar datos de cumplimiento a su adaptador, pero los servidores de cumplimiento no proporcionarán datos de cumplimiento duplicados a varias instancias del adaptador.

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>Implementación de la interfaz IComplianceAdapter

La interfaz se define en el ensamblado Compliance. dll del espacio `Microsoft.Rtc.Internal.Chat.Server.Compliance`de nombres. La interfaz define dos métodos que debe implementar su adaptador personalizado.

    void SetConfig(AdapterConfig config)

El servidor de cumplimiento de chat persistente llamará a este método cuando se cargue el adaptador por primera vez. El `AdapterConfig` contiene la configuración de cumplimiento de chat persistente que es relevante para el adaptador de cumplimiento.

    void Translate(ConversationCollection conversations)

El servidor de cumplimiento de chat persistente llama a este método a intervalos periódicos siempre que haya datos nuevos para traducir. Este intervalo de tiempo es igual al `RunInterval` establecido en la configuración de cumplimiento de chat persistente.

El `ConversationCollection` contiene la información de la conversación que se recopiló desde la última vez que se llamó a este método.

</div>

</div>

<span> </span>

</div>

</div>

</div>

