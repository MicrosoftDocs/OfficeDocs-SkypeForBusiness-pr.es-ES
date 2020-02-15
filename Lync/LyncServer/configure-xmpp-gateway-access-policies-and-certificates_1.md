---
title: Configurar las directivas y los certificados de acceso a puertas de enlace XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 9f622ed573a6d30d35b55d2c07ec21ef79b46424
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar las directivas y los certificados de acceso a puertas de enlace XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-15_

La federación XMPP define una implementación externa basada en el Protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios de Lync obtener acceso a los usuarios de dominio XMPP mediante:

  - MI y presencia, solo persona a persona

  - Creación de contactos federados XMPP en el cliente Lync

Cuando se configuran directivas para admitir socios federados del protocolo extensible de mensajería y presencia (XMPP), las directivas se aplican a los usuarios de los dominios federados de XMPP, pero no a los usuarios de los proveedores de servicio de mensajería instantánea (MI) del protocolo de inicio de sesión (SIP) (por ejemplo, Windows Live) o dominios federados de SIP. Se debe configurar un socio federado de XMPP para cada dominio federado de XMPP al que desea permitir que los usuarios agreguen contactos y con el que desea que se comuniquen. Una vez aplicadas las directivas, debe configurar los certificados de puerta de enlace XMPP.

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

