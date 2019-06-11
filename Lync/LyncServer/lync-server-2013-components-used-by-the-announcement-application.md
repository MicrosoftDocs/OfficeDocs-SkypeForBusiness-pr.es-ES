---
title: 'Lync Server 2013: Componentes que usa la aplicación Anuncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e8e4a0fdfe0dcdd69a3f371aed338caf7f73348
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Componentes que usa la aplicación Anuncio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-13_

En Lync Server 2013, la aplicación de anuncios es un componente de la aplicación de grupo de respuesta. Al implementar Enterprise Voice, la aplicación de anuncio se instala y se activa automáticamente junto con la aplicación de grupo de respuesta. En esta sección se describen los componentes que admiten la aplicación de anuncios.

<div>

## <a name="announcement-application-components"></a>Componentes de la aplicación de anuncios

Los siguientes componentes de Lync Server son compatibles con la aplicación de anuncios:

  - ****   El servicio de aplicación de servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas. El servicio de aplicaciones se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en todos los servidores Standard Edition.

  - **Aplicación de grupo de respuesta**   la aplicación de grupo de respuesta es una de las aplicaciones de comunicaciones unificadas que se hospedan en el servicio de aplicación. Cuando se configura un intervalo de números de teléfono sin asignar para que se dirija a un anuncio, se necesita la aplicación de grupo de respuesta para enrutar las llamadas hechas al número de teléfono. (La aplicación de grupo de respuesta no es necesaria si todos los intervalos están configurados para enrutar a mensajería unificada de Exchange (UM)).

  - **Archivos de audio**   se usan archivos de audio para los anuncios.

  - **Almacén de archivos**   la aplicación de anuncios usa el almacén de archivos para almacenar sus archivos de audio.

  - **Panel de control de Lync Server**   puede usar el panel de control de Lync Server para configurar la tabla de números sin asignar.

  - **Shell de administración de Lync Server**   puede usar los cmdlets del shell de administración de Lync Server para establecer la configuración de la presentación y la tabla de números sin asignar.

</div>

</div>

<span> </span>

</div>

</div>

</div>

