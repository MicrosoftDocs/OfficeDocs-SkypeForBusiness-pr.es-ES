---
title: 'Lync Server 2013: Proteger IIS'
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
ms.openlocfilehash: 03d0f3e736284970bf22fe813093e0e54accd29e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Proteger IIS en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-05_

En Microsoft Office Communications Server 2007 y Microsoft Office Communications Server 2007 R2, servicios de Internet Information Server (IIS) se ejecutó con una cuenta de usuario estándar. Esto tenía el potencial de causar problemas: Si la contraseña ha expirado, podrías perder los servicios Web, un problema que a menudo era difícil de diagnosticar. Para evitar el problema de caducidad de las contraseñas, Microsoft Lync Server 2013 le permite crear una cuenta de equipo (para un equipo que realmente no existe) que puede ser el principal de autenticación de todos los equipos de un sitio que ejecutan IIS. Dado que estas cuentas usan el protocolo de autenticación Kerberos, se llaman cuentas Kerberos y el nuevo proceso de autenticación se denomina autenticación web Kerberos. Esto permite administrar todos los servidores IIS usando una única cuenta.

Para ejecutar los servidores en esta entidad de autenticación, primero debe crear una cuenta de equipo mediante el cmdlet New-CsKerberosAccount; a continuación, esta cuenta se asigna a uno o varios sitios. Después de realizar la asignación, la asociación entre la cuenta y el sitio de Lync Server 2013 se habilita al ejecutar el cmdlet enable-CsTopology. Entre otras cosas, esto crea el nombre principal de servicio (SPN) necesario en servicios de dominio de Active Directory (AD DS). Los SPN ofrecen a las aplicaciones cliente una manera de ubicar un servicio en particular. Para obtener más información, vea [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) en la documentación de operaciones.

<div>

## <a name="best-practices"></a>Procedimientos recomendados

Para ayudar a mejorar la seguridad de IIS, recomendamos implementar una cuenta de Kerberos para IIS. Si no implementa una cuenta de Kerberos, IIS se ejecutará con una cuenta de usuario estándar.

</div>

</div>

<span> </span>

</div>

</div>

</div>

