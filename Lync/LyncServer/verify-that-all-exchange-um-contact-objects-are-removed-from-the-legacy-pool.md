---
title: Comprobar que todos los objetos de contacto de mensajería unificada de Exchange se han quitado del grupo heredado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae8f82016f8dd78c3ecd568e34c3cc408a204ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515957"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>Comprobar que todos los objetos de contacto de mensajería unificada de Exchange se han quitado del grupo heredado

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

Use la herramienta **OCSUmUtil** o el cmdlet **Get-CsExumContact** para comprobar que los objetos de contacto de mensajería unificada de Exchange se han quitado del grupo de Office Communications Server 2007 R2 heredado. **OCSUmUtil** se encuentra en la siguiente carpeta:

% Program Files% \\ archivos comunes \\ Lync Server 2013 \\ soporte \\OcsUMUtil.exe

**OCSUmUtil** debe ejecutarse desde una cuenta de usuario que tenga:

  - Pertenencia a los grupos RTCUniversalServerAdmins y RTCUniversalUserAdmins (que incluyen derechos para leer la configuración de mensajería unificada de Exchange Server)

  - Derechos de dominio para crear objetos de contacto en el contenedor especificado de la unidad organizativa.

Para obtener información detallada sobre cómo usar el cmdlet **Get-CsExumContact** , vea [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) en la documentación del shell de administración de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

