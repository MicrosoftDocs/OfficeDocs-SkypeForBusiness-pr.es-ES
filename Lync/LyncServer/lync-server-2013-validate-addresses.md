---
title: 'Lync Server 2013: validar direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 397c1037937e100f1981a689f0860362d852ed10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a>Validar direcciones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Antes de publicar la base de datos de ubicación, debe validar nuevas ubicaciones en relación con la guía de dirección maestra (MSAG) que mantiene su tronco de SIP o la red de telefonía pública conmutada (RTC) E9-1-1 proveedor de servicios.

Para obtener más información sobre los proveedores de servicios E9-1-1 de SIP, consulte [elección de un proveedor de servicios de E9-1-1 para Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Para obtener detalles sobre la validación de direcciones, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Prueba-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>Para validar direcciones ubicadas en la base de datos de ubicaciones

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute los cmdlets siguientes para configurar la conexión de proveedor de servicios de emergencia.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Ejecute el cmdlet siguiente para validar las direcciones en la base de datos de ubicaciones.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    También puede usar el cmdlet **Test-CsLisCivicAddress** para validar direcciones individuales.

</div>

</div>

<span> </span>

</div>

</div>

</div>

