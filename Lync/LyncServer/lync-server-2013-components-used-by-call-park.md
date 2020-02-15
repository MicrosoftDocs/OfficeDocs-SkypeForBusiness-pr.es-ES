---
title: 'Lync Server 2013: componentes que usa el estacionamiento de llamadas'
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
ms.openlocfilehash: 4a0b6d6bece5fa107e0fe130aab983458acbc0a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a>Componentes que usa el estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-13_

La aplicación estacionamiento de llamadas se instala automáticamente al implementar la telefonía IP empresarial. Puede habilitar el estacionamiento de llamadas mediante la configuración de la Directiva de voz. Los siguientes componentes de Lync Server 2013 admiten la aplicación estacionamiento de llamadas:

  - ****   El servicio de aplicación de servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas, como la aplicación de estacionamiento de llamadas. El servicio de aplicación se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en cada servidor Standard Edition.

  - **Aplicación estacionamiento de llamadas**   la aplicación de estacionamiento de llamadas es una de las aplicaciones de comunicaciones unificadas que se hospedan en el servicio de aplicación. Se incluye automáticamente al implementar la Telefonía IP empresarial. Los parques de estacionamiento de llamadas y recuperan llamadas y administran órbitas de estacionamiento de llamadas.

  - **Música en espera-archivo**   si la música está habilitada, el archivo de música se reproduce mientras se estaciona una llamada. Se incluye un archivo de música predeterminado cuando se instala la aplicación de estacionamiento de llamadas.

  - **Almacén de archivos**   la aplicación estacionamiento de llamadas usa el almacén de archivos para guardar los archivos de audio personalizados.

  - **Panel de control de Lync Server**   puede usar el panel de control de Lync Server para configurar la tabla de órbitas de estacionamiento de llamadas y habilitar el estacionamiento de llamadas para los usuarios.

  - **Shell de administración de Lync Server**   toda la configuración de la aplicación estacionamiento de llamadas se puede realizar mediante los cmdlets del shell de administración de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

