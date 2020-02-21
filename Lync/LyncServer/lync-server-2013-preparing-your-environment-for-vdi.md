---
title: 'Lync Server 2013: preparar el entorno para VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1797dfb3388b4f443b505eb0a82c75f887e1759c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a>Preparar el entorno de Lync Server 2013 para VDI

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Para preparar el entorno para el complemento de VDI de Lync, el administrador debe realizar los siguientes pasos.

1.  En Lync Server 2013, asegúrese de que EnableMediaRedirection está establecido en TRUE para todos los usuarios de VDI. Para obtener más información, consulte los temas de ayuda del cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) y el cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

2.  En el equipo del centro de datos, instale el cliente de Lync 2013 en todas las máquinas virtuales.

3.  En los equipos locales, instale el complemento de VDI de Lync.

</div>

<span> </span>

</div>

</div>

</div>

