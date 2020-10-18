---
title: 'Lync Server 2013: componentes y topologías para mensajería unificada local'
description: 'Lync Server 2013: componentes y topologías para mensajería unificada local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fe2ca16ec9fbd39e9245fd366e1f7046dd16d42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576826"
---
# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Componentes y topologías para mensajería unificada local en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-25_

En este tema se describen los componentes de Microsoft Exchange Server 2013 necesarios para proporcionar características de mensajería unificada (MU) de Exchange a la implementación de Lync Server 2013. También se describen las topologías admitidas para la integración local de mensajería unificada de Exchange.

<div>

## <a name="exchange-server-components"></a>Componentes de Exchange Server

Para proporcionar las características y los servicios de mensajería unificada de Exchange descritos en [características de mensajería unificada integrada y Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) a los usuarios de Enterprise Voice de su organización, debe implementar un servidor de buzones de correo y un servidor de acceso de cliente de Microsoft Exchange, que hospeda los buzones de usuario y proporciona una única ubicación de almacenamiento para el correo electrónico y el correo de voz La mensajería unificada de Exchange se ejecuta como un servicio en los servidores de buzones y de acceso de cliente de Exchange.

Para obtener más información acerca de los componentes de mensajería unificada de Exchange en Microsoft Exchange Server 2007 y Microsoft Exchange Server 2010, consulte [Deploying on-premises Exchange um to Provide Lync Server 2013 Voice Mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) en la documentación sobre implementación.

</div>

<div>

## <a name="supported-topologies"></a>Topologías admitidas

Puede implementar Lync Server 2013 y mensajería unificada de Exchange (UM) en el mismo bosque o en varios bosques. Si la implementación abarca varios bosques, debe realizar los pasos de integración de Exchange para cada bosque de mensajería unificada de Exchange. Además, debe configurar cada bosque de Microsoft Exchange para que confíe en el bosque de Lync Server 2013 y en el bosque de Lync Server 2013 para confiar en cada bosque de mensajería unificada de Exchange. Además de esta confianza de bosque, la configuración de mensajería unificada de Exchange para todos los usuarios debe establecerse en los objetos de usuario del bosque de Lync Server 2013.

Lync Server 2013 admite las siguientes topologías para la integración de mensajería unificada de Exchange:

  - Bosque único

  - Dominio único (es decir, un único bosque con un único dominio). Lync Server 2013, Microsoft Exchange y todos los usuarios residen en el mismo dominio.

  - Varios dominios (es decir, un dominio raíz con uno o más dominios secundarios). Lync Server 2013 y los servidores de Microsoft Exchange se implementan en dominios diferentes del dominio donde se crean los usuarios. Los servidores de mensajería unificada de Exchange se pueden implementar en dominios diferentes del grupo de Lync Server 2013 que admiten.

  - Varios bosques (es decir, un bosque de recursos). Lync Server 2013 se implementa en un único bosque y, a continuación, los usuarios se distribuyen en varios bosques. Los atributos de mensajería unificada de Exchange de los usuarios deben replicarse en el bosque de Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Exchange se puede implementar en varios bosques. Cada organización de Exchange puede proporcionar la mensajería unificada de Exchange a sus usuarios o se puede implementar la mensajería unificada de Exchange en el mismo bosque que Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

