---
title: 'Lync Server 2013: componentes que usa el estacionamiento de llamadas'
description: 'Lync Server 2013: componentes que usa el estacionamiento de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 285af316fa2d49e8bebf68e11de6d9526e12ae29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576776"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a>Componentes que usa el estacionamiento de llamadas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-13_

La aplicación estacionamiento de llamadas se instala automáticamente al implementar la telefonía IP empresarial. Puede habilitar el estacionamiento de llamadas mediante la configuración de la Directiva de voz. Los siguientes componentes de Lync Server 2013 admiten la aplicación estacionamiento de llamadas:

  - **Servicio**     de aplicación El servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas, como la aplicación de estacionamiento de llamadas. El servicio de aplicación se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en cada servidor Standard Edition.

  - Aplicación de estacionamiento de **llamadas**     La aplicación de estacionamiento de llamadas es una de las aplicaciones de comunicaciones unificadas que hospeda el servicio de aplicación. Se incluye automáticamente al implementar la Telefonía IP empresarial. Los parques de estacionamiento de llamadas y recuperan llamadas y administran órbitas de estacionamiento de llamadas.

  - **Música en espera-archivo**     Si la música está habilitada, el archivo de música se reproduce mientras se estaciona una llamada. Se incluye un archivo de música predeterminado cuando se instala la aplicación de estacionamiento de llamadas.

  - **Almacén**     de archivos La aplicación estacionamiento de llamadas usa el almacén de archivos para guardar los archivos de audio personalizados.

  - Panel de control de **Lync Server**     Puede usar el panel de control de Lync Server para configurar la tabla de órbitas de estacionamiento de llamadas y habilitar el estacionamiento de llamadas para los usuarios.

  - Shell de administración de **Lync Server**     Toda la configuración de la aplicación estacionamiento de llamadas se puede realizar mediante los cmdlets del shell de administración de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

