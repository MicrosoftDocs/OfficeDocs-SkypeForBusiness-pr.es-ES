---
title: 'Lync Server 2013: requisitos previos y roles de configuración del anuncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 037625d0efea2ae53cd4923a0a7cccce4a890098
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Requisitos previos y roles de configuración del anuncio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

El anuncio es una característica de administración de llamadas de telefonía IP empresarial. En este tema se describe lo que necesita tener en su ubicación antes de poder configurar el anuncio y las asignaciones de roles que necesita para realizar tareas de configuración.

En esta sección se da por sentado que ha leído la documentación de planeación relacionada con el anuncio (consulte [planeación de las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="announcement-configuration-prerequisites"></a>Requisitos previos de configuración del anuncio

La aplicación de anuncio requiere los siguientes componentes:

  - Servicio de aplicación

  - Aplicación de grupo de respuesta

  - Almacenamiento de archivos, para los archivos de audio

Todos estos componentes se instalan de forma predeterminada al implementar Enterprise Voice.

</div>

<div>

## <a name="announcement-configuration-roles"></a>Roles de configuración de anuncios

Puede usar las siguientes herramientas administrativas para configurar anuncios:

  - Panel de control de Lync Server

  - Shell de administración de Lync Server

La configuración de la aplicación de anuncio requiere uno de los siguientes roles administrativos:

  - **CsVoiceAdministrator**   este rol de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con la voz, incluida la configuración del anuncio.

  - **CsServerAdministrator**   este rol de administrador puede administrar, supervisar y solucionar problemas de servidores y servicios, además de configurar todas las opciones de anuncio.

  - **CsAdministrator**   este rol de administrador puede realizar todas las tareas administrativas y modificar toda la configuración.

  - **CsViewOnlyAdministrator**   este rol de administrador puede ver la implementación para supervisar el estado de la implementación.

<div>


> [!NOTE]  
> Para obtener más información sobre los derechos de usuario administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> en la documentación de planeación.



</div>

</div>

<div>

## <a name="see-also"></a>Consulta también


[Implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Planeación de características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

