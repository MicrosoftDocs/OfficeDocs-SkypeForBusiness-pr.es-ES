---
title: Configurar certificados y directivas de acceso por puerta de enlace XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49733819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e17634a8836a56ce7002e3d0cf57440f72c60f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar certificados y directivas de acceso por puerta de enlace XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-15_

XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:

  - MI y presencia, solo persona a persona

  - Creación de contactos federados XMPP en el cliente Lync

When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.

<div>


> [!NOTE]  
> Para comenzar la migración de la puerta de enlace XMPP, debe implementar la puerta de enlace XMPP de Lync Server 2013 y configurar directivas de acceso para habilitar a los usuarios para la puerta de enlace XMPP de Lync Server 2013. Es necesario mover todos los usuarios a la implementación de Lync Server 2013 antes de realizar estos pasos. Para obtener más información, consulte <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Configure XMPP Gateway on Lync Server 2013</A>.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Configurar una directiva de acceso externo para habilitar usuarios para la puerta de enlace XMPP de Lync Server 2013

1.  Abra Panel de control de Lync Server

2.  En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y en **Directiva de acceso externo**.

3.  Haga clic en **Nuevo** y en **Directiva de usuario**.

4.  Indique un nombre para la directiva de usuario de acceso externo.

5.  Indique una descripción para la directiva de usuario de acceso externo.

6.  Seleccione **Habilitar comunicaciones con usuarios federados**.

7.  Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.

8.  Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o de usuario.

</div>

</div>

<span> </span>

</div>

</div>

</div>

