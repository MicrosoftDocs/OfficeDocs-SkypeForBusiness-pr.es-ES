---
title: Requisitos previos y permisos de configuración para conferencias de acceso telefónico
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a60fc58e0ec40dadff044257d43629c2f3cb01ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Requisitos previos y permisos de configuración para conferencias de acceso telefónico en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-20_

Conferencias de acceso telefónico local es un componente opcional de la carga de trabajo de conferencia de Lync Server 2013. Los componentes que necesita instalar para poder configurar las conferencias de acceso telefónico local se implementan al usar el generador de topología para diseñar su topología y, a continuación, configurar su grupo de servidores front-end o servidor Standard Edition. En este tema se describe lo que debe hacer antes de poder configurar las conferencias de acceso telefónico local.

En esta sección se supone que ha leído las secciones de planeación relacionadas con la carga de trabajo de conferencia y la Conferencia de acceso telefónico local en particular.

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>Requisitos previos de configuración de conferencias de acceso telefónico local

Las conferencias de acceso telefónico local requieren los siguientes componentes de Lync Server 2013:

  - Servicio de aplicaciones de comunicaciones unificadas (UCAS) (denominado el *servicio de aplicación*)

  - Aplicación Operador de conferencia

  - Aplicación de anuncio de conferencia

  - Página web de configuración de la conferencia de acceso telefónico local

  - Al menos un servidor de mediación de Lync Server 2013 y una puerta de enlace PSTN como mínimo

Estos componentes se implementan al usar el generador de topología para definir y publicar la topología y, a continuación, implementar un grupo de servidores front-end o un servidor Standard Edition. Si va a implementar la telefonía IP empresarial, debe implementarla antes de configurar la Conferencia de acceso telefónico local. Si no va a implementar la telefonía IP empresarial, puede implementar un servidor de mediación y una puerta de enlace de red telefónica conmutada (RTC) al implementar el grupo de servidores front-end o el servidor Standard Edition.

<div>


> [!NOTE]
> Si va a actualizar de Office Communications Server 2007 R2 a Lync Server 2013, implemente conferencias de acceso telefónico local en todos los grupos que planea usar para hospedar conferencias de Lync Server 2013. Para obtener más información sobre cómo migrar conferencias de acceso telefónico local, consulte <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migración de Office Communications server 2007 R2 a Lync Server 2013</A>.



</div>

En esta sección se presupone que ha realizado lo siguiente:

  - Aplicó las últimas actualizaciones al entorno de Office Communications Server 2007 R2, si va a migrar a Lync Server 2013.

  - Se usó el generador de topología para diseñar y configurar su topología. Mientras especifica la carga de trabajo de la Conferencia, seleccionó la opción de conferencia de acceso telefónico local. Para obtener más información sobre cómo definir su topología, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) en la documentación de implementación.

  - Publicó su topología y configure el grupo de servidores front-end o el servidor Standard Edition. Para obtener más información sobre la publicación de la topología y la instalación de Lync Server 2013, consulte [implementación de Lync server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.
    
    <div>
    

    > [!NOTE]
    > Al instalar su topología publicada, la página de configuración de conferencias de acceso telefónico local se instala en el servidor front-end o en el servidor Standard Edition como parte de los servicios Web.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Si cambia la ruta de acceso del almacén de archivos en el generador de topología después de implementar Lync Server 2013, tendrá que reiniciar el operador de conferencia y las aplicaciones de anuncios de conferencia para usar la nueva ruta de acceso.

    
    </div>

  - Implementación de telefonía IP empresarial. Si no está implementando la telefonía IP empresarial, ya ha colocado un servidor de mediación en el servidor front-end Enterprise Edition o en el servidor Standard Edition, o si ha implementado un servidor de mediación independiente y ha implementado una puerta de enlace RTC. Para obtener detalles sobre la implementación de telefonía IP empresarial, consulte [implementación de telefonía empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) en la documentación de implementación. Para obtener detalles sobre la instalación de un servidor de mediación independiente y una puerta de enlace RTC, consulte [implementar servidores de mediación y definir pares en Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) en la documentación de implementación.

En el siguiente diagrama de flujo se muestran los pasos que debe realizar para poder configurar las conferencias de acceso telefónico local y los pasos que realiza para configurar las conferencias de acceso telefónico local.

**Implementación de conferencias de acceso telefónico local**

![Diagrama de flujo de implementación de conferencias de acceso telefónico local] (images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Diagrama de flujo de implementación de conferencias de acceso telefónico local")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>Permisos de conferencia de acceso telefónico local

Para configurar las conferencias de acceso telefónico local, tiene que usar las siguientes herramientas administrativas:

  - Panel de control de Lync Server 2013

  - Shell de administración de Communications Server

Use estas herramientas administrativas para configurar la configuración de conferencias de acceso telefónico local, así como los planes de marcado, las directivas y otras opciones que requiere la Conferencia de acceso telefónico local.

La configuración de conferencias de acceso telefónico local requiere cualquiera de los siguientes roles administrativos, en función de la tarea:

  - **CsVoiceAdministrator**   esta función de administrador puede crear, configurar y administrar directivas y configuración relacionadas con las voz.

  - **CsUserAdministrator**   esta función de administrador puede habilitar y deshabilitar usuarios para Lync Server y asignar directivas existentes, como directivas de conferencia y directivas de PIN, a los usuarios.

  - **CsAdministrator**   esta función de administrador puede realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.

</div>

<div>

## <a name="see-also"></a>Vea también


[Implementación de telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

