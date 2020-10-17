---
title: 'Lync Server 2013: requisitos de la aplicación de Lync para la tienda Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3707c0074425411353a22b51d62251d33a4e31fd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534607"
---
# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Requisitos de aplicaciones de la tienda Windows Lync para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-03_

Las organizaciones con una implementación local de Lync Server deben cumplir los siguientes requisitos para admitir la aplicación de la tienda Windows de Lync.

<div>


> [!NOTE]  
> Para Lync Server 2010, ejecute la actualización acumulativa para Lync Server 2010: febrero de 2012 (disponible en <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2670352</A>) o posterior en todos los servidores. Para permitir que los usuarios se unan a reuniones, ejecute la actualización acumulativa para Lync Server 2010: octubre de 2012 (disponible en <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2737915</A>) en los servidores.



</div>

  - Habilite la detección automática, Lync Web App y los servicios de vale Web en el servidor.

  - Habilitar la autenticación de certificados en el servidor front-end o en el grupo de servidores front-end. (A menudo, el proceso de registro de usuario en el servidor front-end o el grupo de servidores front-end se denomina registrador). Para obtener más información, consulte [Create registrar configuración en Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

  - Publique los registros de recursos de alias DNS (CNAME) para el servicio Detección automática.

  - Ya no es necesario asegurarse de que el punto de distribución de la lista de revocación de certificados (CRL) para los certificados emitidos a Lync Server apunte a un recurso HTTP en lugar de a un recurso LDAP. Sin embargo, asegúrese de que los equipos cliente tengan instaladas las últimas actualizaciones de Windows.

  - Configure proxy HTTP en la empresa para permitir el tráfico HTTP relacionado con Lync Server.Agregue excepciones para los servicios de detección automática, Lync Web App y webticket, si es necesario.

  - En los clientes, instale Windows 8,1 y la versión más reciente de la aplicación de la tienda Windows de Lync para corregir un problema de inicio de sesión que suele producirse cuando se usan varios dominios (por ejemplo, cuando el URI del SIP es **Usera@domainZ.com** pero el servidor perimetral es **SIP.domainX.com**).

Si su organización se suscribe a Lync Online o Microsoft 365 y está usando su propio nombre de dominio, debe realizar algunos pasos adicionales para configurar la red para la detección automática de los servidores de Lync. Los requisitos de configuración de red son los mismos para la aplicación de la tienda Windows de Lync y Lync en dispositivos móviles.

<div>

## <a name="see-also"></a>Consulte también


[Implementación de la aplicación Lync de la tienda Windows en Lync Server 2013](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
