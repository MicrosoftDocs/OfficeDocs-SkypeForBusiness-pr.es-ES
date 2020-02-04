---
title: 'Lync Server 2013: Configurar la autenticación Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c644dd613b3186b314e8fc78b42197709286200
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Configurar la autenticación Kerberos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Lync Server 2013 admite la autenticación NTLM y Kerberos para los servicios Web. Office Communications Server 2007 y Office Communications Server 2007 R2 usaron el RTCComponentService predeterminado y RTCService como las cuentas de usuario para ejecutar los grupos de aplicaciones de servicios Web, lo que permite que se asigne un nombre principal de servicio (SPN) al usuario. y para actuar como entidad de autenticación. Lync Server usa NetworkService para ejecutar servicios web y NetworkService no puede tener SPN asignados.

Para solucionar el problema de no tener objetos de Active Directory para retener los SPN, el panel de control de Lync Server puede usar objetos de cuenta de equipo para este propósito. Los objetos de cuenta de equipo pueden contener los SPN y no están sujetos a la expiración de contraseña, lo cual fue un problema al usar cuentas de usuario en versiones anteriores.

Use los cmdlets de Windows PowerShell para configurar los objetos de equipo para proporcionar autenticación Kerberos.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Requisitos previos para habilitar la autenticación Kerberos en Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Crear una cuenta de autenticación Kerberos en Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Asignar una cuenta de autenticación Kerberos a un sitio en Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Configurar las contraseñas de cuenta de autenticación Kerberos en Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Agregar autenticación Kerberos a otros sitios en Lync Server 2013](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Quitar la autenticación Kerberos de un sitio en Lync Server 2013](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Comprobar y notificar el estado y asignación de la autenticación Kerberos en Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

