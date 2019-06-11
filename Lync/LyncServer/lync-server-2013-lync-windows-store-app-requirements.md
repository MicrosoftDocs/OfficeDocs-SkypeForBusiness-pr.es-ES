---
title: 'Lync Server 2013: requisitos de la aplicación de la tienda Windows de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806fb7a71232492be7ef01474136817b7808111e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Requisitos de la aplicación de la tienda Windows de Lync para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-03_

Las organizaciones con una implementación local de Lync Server deben cumplir los siguientes requisitos para admitir la aplicación de la tienda Windows de Lync.

<div>


> [!NOTE]  
> Para Lync Server 2010, ejecute la actualización acumulativa para Lync Server 2010: febrero de 2012 (disponible en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>) o posterior en todos los servidores. Para permitir que los usuarios se unan a reuniones, ejecute la actualización acumulativa para Lync Server 2010:2012 de octubre (disponible en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>) en los servidores.



</div>

  - Habilite la detección automática, Lync Web App y los servicios de vale Web en el servidor.

  - Habilitar la autenticación de certificados en el servidor front-end o en el grupo de servidores front-end. (El proceso de registro del usuario en el servidor front-end o en el grupo de servidores front-end se suele denominar registrar). Para obtener más información, consulte [crear opciones de configuración de registrar en Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

  - Publique los registros de recursos de alias DNS (CNAME) del servicio Detección automática.

  - Ya no es necesario asegurarse de que el punto de distribución (CDP) de la lista de revocación de certificados (CRL) para los certificados emitidos para Lync Server apunta a un recurso HTTP en lugar de a un recurso LDAP. Sin embargo, asegúrese de que los equipos cliente tienen instaladas las actualizaciones más recientes de Windows.

  - Configure servidores proxy HTTP en la empresa para permitir el tráfico HTTP relacionado con Lync Server.Agregue excepciones para la detección automática, Lync Web App y servicios webticket, si es necesario.

  - En los clientes, instale Windows 8,1 y la última versión de la aplicación de la tienda Windows de Lync para corregir un problema de inicio de sesión que generalmente se produce al usar varios dominios (por ejemplo, cuando el URI SIP está **Usera@domainZ.com** , pero el servidor perimetral es **SIP.domainX.com**).

Si su organización se suscribe a Lync Online u Office 365 y está usando su propio nombre de dominio, debe realizar algunos pasos adicionales para configurar la red para el descubrimiento automático de los servidores de Lync. Los requisitos de configuración de red son los mismos para la aplicación de la tienda Windows de Lync y Lync en dispositivos móviles. Siga las instrucciones "configurar su red" en el artículo de Office 365 wiki "configurar dispositivos móviles de Lync", disponible en [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).

<div>

## <a name="see-also"></a>Vea también


[Implementación de la aplicación de la tienda Windows de Lync en Lync Server 2013](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

