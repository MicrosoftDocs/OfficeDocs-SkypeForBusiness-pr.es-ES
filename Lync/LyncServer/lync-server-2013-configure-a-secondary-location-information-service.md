---
title: 'Lync Server 2013: configurar un servicio de información de ubicación secundaria'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50d63d8316c9ce18bdf8677686a655046601b326
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>Configurar un servicio de información de ubicación secundaria en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

Lync Server 2013 proporciona una interfaz de servicio Web que puede usar para apuntar el servicio de información de ubicaciones a una base de datos de origen de ubicación secundario (SLS). La interfaz de servicio Web que se conecta a la base de datos de SLS debe cumplir con el servicio de información de ubicación WSDL. Si se configuran una base de datos de ubicación y una base de datos de ubicación secundaria, el servicio de información de ubicación primero consulta la base de datos de ubicaciones y, si no se encuentra ninguna coincidencia, envía la solicitud de ubicación desde el cliente a la base de datos de SLS. Si la ubicación existe en SLS, el servicio de información de ubicación entonces devuelve la ubicación de vuelta al cliente.

Para obtener más información, consulte la documentación del shell de administración de Lync Server para el siguiente cmdlet:

  - **Set-CsWebServiceConfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>Para configurar la base de datos de ubicación secundaria

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

