---
title: 'Lync Server 2013: protección de IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 612945a8ad69cffa8401cb64367d8b860d556a19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Proteger IIS en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-05_

En Microsoft Office Communications Server 2007 y Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) se ejecutó con una cuenta de usuario estándar. Esto podía provocar problemas: si la contraseña expiraba, se podían perder los servicios web, un problema que a menudo era difícil de diagnosticar. Para evitar un problema de expiración de contraseñas, Microsoft Lync Server 2013 permite crear una cuenta de equipo (para un equipo que no existe realmente) que puede servir como entidad de autenticación para todos los equipos de un sitio que ejecutan IIS. Dado que estas cuentas usan el protocolo de autenticación Kerberos, se llaman cuentas Kerberos, mientras que el nuevo proceso de autenticación se denomina autenticación web Kerberos. Esto le permite administrar todos sus servidores IIS usando una sola cuenta.

Para ejecutar los servidores con esta entidad de seguridad de autenticación, antes debe crear una cuenta de equipo usando el cmdlet New-CsKerberosAccount; a continuación, esta cuenta se asigna a uno o más sitios. Una vez realizada la asignación, se habilita la asociación entre la cuenta y el sitio de Lync Server 2013 mediante la ejecución del cmdlet enable-CsTopology. Esta acción crea, entre otras cosas, el nombre de entidad de seguridad de servicio (SPN) necesario en los servicios de dominio de Active Directory (AD DS). Los SPN ofrecen un modo para que las aplicaciones cliente ubiquen un servicio concreto. Para obtener más información, consulte [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) en la documentación de operaciones.

<div>

## <a name="best-practices"></a>Recomendaciones

Para contribuir a mejorar la seguridad de IIS, le recomendamos que implemente una cuenta Kerberos para IIS. Si no implementa una cuenta Kerberos, IIS se ejecutará con una cuenta de usuario estándar.

</div>

</div>

<span> </span>

</div>

</div>

</div>

