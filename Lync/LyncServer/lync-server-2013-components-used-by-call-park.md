---
title: 'Lync Server 2013: Componentes que usa el estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f74161230504ee3f24ed19780e0a62ad4e7d08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a>Componentes que usa el estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-13_

La aplicación de estacionamiento de llamadas se instala automáticamente al implementar la telefonía IP empresarial. Para habilitar el parque de llamadas, configure la Directiva de voz. Los siguientes componentes de Lync Server 2013 son compatibles con la aplicación estacionamiento de llamadas:

  - ****   El servicio de aplicación de servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas, como la aplicación de estacionamiento de llamadas. El servicio de aplicaciones se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en todos los servidores Standard Edition.

  - **Aplicación de estacionamiento de llamadas**   la aplicación de estacionamiento de llamadas es una de las aplicaciones de comunicaciones unificadas que se hospedan en el servicio de aplicación. Se incluye automáticamente al implementar la telefonía IP empresarial. Llama a parques de aparcamiento y recupera llamadas y administra las órbitas del parque de llamadas.

  - **Música en espera-archivo**   si la música está habilitada, el archivo de música se reproduce mientras se estaciona una llamada. Cuando se instala la aplicación de estacionamiento de llamadas, se incluye un archivo de música predeterminado.

  - **Almacén de archivos**   la aplicación de estacionamiento de llamadas usa el almacén de archivos para almacenar los archivos de audio personalizados.

  - **Panel de control de Lync Server**   puede usar el panel de control de Lync Server para configurar la tabla orbital de llamadas y para habilitar el parque de llamadas para los usuarios.

  - **Shell de administración de Lync Server**   toda la configuración de la aplicación estacionamiento de llamadas se puede realizar mediante los cmdlets del shell de Lync Server Management.

</div>

<span> </span>

</div>

</div>

</div>

