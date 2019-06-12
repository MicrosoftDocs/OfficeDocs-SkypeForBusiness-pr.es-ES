---
title: 'Lync Server 2013: comprobar las comunicaciones con un cliente de Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6707139535ab30909f74b1a3fa51cce24374d09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>Comprobar las comunicaciones con un cliente de Lync Online en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-08_

Para permitir que los usuarios de la organización de Lync se comuniquen con los usuarios de un cliente de Microsoft Lync Online 2010, debe haber completado los siguientes pasos:

  - Cumple con todos los requisitos previos. Esto incluye implementar los servidores internos y perimetrales, habilitar la compatibilidad con la Federación de su organización y configurar cuentas de usuario. Para obtener más información, consulte [requisitos previos para federar con un cliente de Lync Online en Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).

  - Compatibilidad con el acceso a dominios configurado en la implementación interna. Esto incluye la creación de una entrada de proveedor de host y la configuración de la implementación para permitir el acceso desde el dominio del cliente de Lync Online. Para obtener más información, vea [configurar la compatibilidad de Federación para un dominio de Lync Online en Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).

  - Configuró las cuentas de usuario para admitir la Federación. Para obtener más información, vea [configurar el acceso de usuarios para la Federación con un cliente de Lync Online en Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).

Después de completar todos estos pasos y el administrador del cliente de Lync Online 2010 completa toda la configuración de sus servicios en línea para admitir la Federación con su organización, comprobar las comunicaciones entre una usuario de la organización y un usuario del cliente de Lync Online. Si la comunicación no se realiza correctamente, use la herramienta de registro de su servidor perimetral para capturar archivos de registro y de seguimiento a fin de solucionar el problema. Para obtener información detallada sobre el uso de la herramienta registro, consulte [abrir las herramientas administrativas de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md) en la documentación de operaciones. Para obtener más información sobre la herramienta de registro, consulte la documentación de la herramienta de registro de Lync [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Server 2010 en la biblioteca de TechNet en.

</div>

<span> </span>

</div>

</div>

</div>

