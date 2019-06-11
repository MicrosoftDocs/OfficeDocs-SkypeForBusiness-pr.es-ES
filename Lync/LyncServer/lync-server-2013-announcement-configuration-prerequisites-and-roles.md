---
title: 'Lync Server 2013: Requisitos previos y roles para configurar anuncios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb5f909170e1de2566e21e9305175211c306fee6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34843039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Requisitos previos y roles para configurar anuncios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

El anuncio es una característica de administración de llamadas de voz de empresa. En este tema se describe lo que debe tener en cuenta antes de poder configurar el anuncio y las asignaciones de roles que necesita para realizar tareas de configuración.

En esta sección se supone que ha leído la documentación de planeación relacionada con el anuncio (vea [planear las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="announcement-configuration-prerequisites"></a>Requisitos previos de configuración del anuncio

La aplicación de anuncios requiere los siguientes componentes:

  - Servicio de aplicaciones

  - Aplicación de grupo de respuesta

  - Almacén de archivos, para mantener los archivos de audio

Todos estos componentes se instalan de forma predeterminada al implementar la telefonía IP empresarial.

</div>

<div>

## <a name="announcement-configuration-roles"></a>Roles de configuración de anuncio

Puede usar las siguientes herramientas administrativas para configurar anuncios:

  - Panel de control de Lync Server

  - Shell de administración de Communications Server

La configuración de la aplicación de anuncio requiere uno de los siguientes roles administrativos:

  - **CsVoiceAdministrator**   esta función de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con la voz, incluyendo la configuración de la presentación.

  - **CsServerAdministrator**   esta función de administrador puede administrar, supervisar y solucionar problemas con servidores y servicios, y configurar todas las opciones de presentación.

  - **CsAdministrator**   esta función de administrador puede realizar todas las tareas administrativas y modificar toda la configuración.

  - **CsViewOnlyAdministrator**   este rol de administrador puede ver la implementación para supervisar el estado de implementación.

<div>


> [!NOTE]  
> Para obtener más información sobre los derechos de usuario administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync Server 2013</A> en la documentación de planeación.



</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Implementación de telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Planeamiento de las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

