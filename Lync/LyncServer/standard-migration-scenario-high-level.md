---
title: Escenario de migración estándar - Alto nivel
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
ms.openlocfilehash: 68ff7110cc7e14ccc76ab7d0c0125e723477934a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>Escenario de migración estándar - Alto nivel

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Use los siguientes elementos como punto de partida al migrar Lync Server 2010, chat grupal u Office Communications Server 2007 R2 chat grupal a Lync Server 2013, servidor de chat persistente. La ruta de migración estándar de Lync Server 2013 es la siguiente:

  - Su organización ha implementado previamente Lync Server 2010, chat grupal o chat grupal de Office Communications Server 2007 R2 y desea implementar Lync Server 2013, servidor de chat persistente.

  - Implemente Lync Server 2013 y, a continuación, implemente grupos de servidores de chat persistentes.

  - Prepare y planifique la migración de sus salones de chat persistentes y determine el momento adecuado para apagar el sistema para la migración.

  - Ejecute los cmdlets de Windows PowerShell para la migración (**Export-CsPersistentChatData** e **Import-CsPersistentChatData**) para mover el contenido a un servidor de chat persistente.

  - Comprobar que la migración se ha realizado correctamente.

  - Dar de baja la implementación heredada.

  - Configure el servidor de chat persistente para que los clientes heredados puedan conectarse a Lync Server 2013, servidor de chat persistente. Esto es necesario porque lleva tiempo implementar nuevos clientes y quiere permitir que los usuarios existentes con clientes heredados tengan acceso a sus salones de chat tan pronto como sea posible.

  - Implemente nuevos clientes y siga ayudando a garantizar que los trabajadores con chat grupal heredado (clientes) puedan acceder a sus salones de chat.

</div>

<span> </span>

</div>

</div>

</div>

