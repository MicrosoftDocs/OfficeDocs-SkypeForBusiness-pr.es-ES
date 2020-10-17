---
title: 'Lync Server 2013: componentes que usa la aplicación de anuncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84fb2d57e03965acff9d647854b86d7a5a528246
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517717"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Componentes usados por la aplicación de anuncio en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-13_

En Lync Server 2013, la aplicación de anuncio es un componente de la aplicación de grupo de respuesta. Al implementar la telefonía IP empresarial, la aplicación del anuncio se instala y se activa automáticamente junto con la aplicación grupo de respuesta. En esta sección se describen los componentes que admiten la aplicación de anuncio.

<div>

## <a name="announcement-application-components"></a>Componentes de la aplicación de anuncio

Los siguientes componentes de Lync Server admiten la aplicación de anuncio:

  - **Servicio**     de aplicación El servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar las aplicaciones de comunicaciones unificadas. El servicio de aplicación se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en cada servidor Standard Edition.

  - Aplicación de grupo de **respuesta**     La aplicación de grupo de respuesta es una de las aplicaciones de comunicaciones unificadas que se hospedan en el servicio de aplicación. Cuando se configura un intervalo de números de teléfono sin asignar para redirigir a un anuncio, se requiere la aplicación de grupo de respuesta para enrutar las llamadas realizadas al número de teléfono. (La aplicación grupo de respuesta no es necesaria si todos los intervalos están configurados para enrutar a la mensajería unificada de Exchange).

  - **Archivos**     de audio Los archivos de audio se usan para los anuncios.

  - **Almacén**     de archivos La aplicación de anuncio usa el almacén de archivos para almacenar sus archivos de audio.

  - Panel de control de **Lync Server**     Puede usar el panel de control de Lync Server para configurar la tabla de números sin asignar.

  - Shell de administración de **Lync Server**     Puede usar los cmdlets del shell de administración de Lync Server para configurar las opciones de anuncio y la tabla de números sin asignar.

</div>

</div>

<span> </span>

</div>

</div>

</div>

