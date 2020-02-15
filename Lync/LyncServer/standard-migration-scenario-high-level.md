---
title: 'Escenario de migración estándar: alto nivel'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34084de0af0971018043f230c260adb514f1d460
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>Escenario de migración estándar: alto nivel

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Use los siguientes elementos como punto de partida al migrar Lync Server 2010, Group chat u Office Communications Server 2007 R2 Group chat a Lync Server 2013, servidor de chat persistente. La ruta de migración estándar de Lync Server 2013 es la siguiente:

  - Su organización ha implementado anteriormente Lync Server 2010, Group chat o un chat en grupo de Office Communications Server 2007 R2 y desea implementar Lync Server 2013, servidor de chat persistente.

  - Implemente Lync Server 2013 y, a continuación, implemente grupos de servidores de chat persistente.

  - Prepare y planifique la migración de sus salones de chat persistente y determine el momento adecuado para apagar el sistema para la migración.

  - Ejecute los cmdlets de Windows PowerShell para la migración (**Export-CsPersistentChatData** y **Import-CsPersistentChatData**) para mover el contenido al servidor de chat persistente.

  - Compruebe que la migración se haya efectuado correctamente.

  - Dé de baja la implementación heredada.

  - Configure el servidor de chat persistente para que los clientes heredados puedan conectarse a Lync Server 2013, el servidor de chat persistente. Esto es necesario porque se tarda tiempo en implementar nuevos clientes y probablemente quiera habilitar los usuarios existentes con clientes heredados para que obtengan acceso a sus salones de chat lo más pronto posible.

  - Implemente nuevos clientes, a la vez que sigue contribuyendo a garantizar que los trabajadores con chat de grupo heredado (clientes) puedan acceder a sus salones de chat.

</div>

<span> </span>

</div>

</div>

</div>

