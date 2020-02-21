---
title: Requisitos previos y permisos para la configuración de conferencias de acceso telefónico local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 791fa7e697622a4274655a77a2f02a6cdee140cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Requisitos previos y permisos de configuración para conferencias de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-20_

La Conferencia de acceso telefónico local es un componente opcional de la carga de trabajo de conferencia de Lync Server 2013. Los componentes que debe instalar para poder configurar la Conferencia de acceso telefónico local se implementan al usar el generador de topologías para diseñar la topología y, a continuación, configurar el grupo de servidores front-end o el servidor Standard Edition. En este tema se describe lo que debe hacer antes de poder configurar la Conferencia de acceso telefónico local.

En esta sección se presupone que ha leído las secciones de planeación relacionadas con la carga de trabajo de conferencia y las conferencias de acceso telefónico local en particular.

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>Requisitos previos para la configuración de conferencias de acceso telefónico local

La Conferencia de acceso telefónico local requiere los siguientes componentes de Lync Server 2013:

  - Servicio de aplicación de comunicaciones unificadas (UCAS) (denominado *servicio de aplicación*)

  - Aplicación Operador de conferencia

  - Aplicación de anuncio de conferencia

  - Página Web de configuración de conferencia de acceso telefónico local

  - Al menos un servidor de mediación de Lync Server 2013 y al menos una puerta de enlace RTC

Estos componentes se implementan cuando se usa el generador de topologías para definir y publicar la topología y, a continuación, implementar un grupo de servidores front-end o un servidor Standard Edition. Si va a implementar la telefonía IP empresarial, debe implementarla antes de configurar la Conferencia de acceso telefónico local. Si no está implementando la telefonía IP empresarial, puede implementar un servidor de mediación y una puerta de enlace de red telefónica conmutada (RTC) al implementar el grupo de servidores front-end o el servidor Standard Edition.

<div>


> [!NOTE]
> Si va a actualizar desde Office Communications Server 2007 R2 a Lync Server 2013, implemente conferencias de acceso telefónico local en cada grupo de servidores que planea usar para hospedar conferencias de Lync Server 2013. Para obtener más información sobre cómo migrar las conferencias de acceso telefónico local, vea <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migración desde Office Communications server 2007 R2 a Lync Server 2013</A>.



</div>

En esta sección se presupone que ha hecho lo siguiente:

  - Se aplicaron las actualizaciones más recientes en el entorno de Office Communications Server 2007 R2, si va a migrar a Lync Server 2013.

  - Se usó el generador de topologías para diseñar y configurar la topología. Mientras especifica la carga de trabajo de conferencia, seleccionó la opción de conferencia de acceso telefónico local. Para obtener información detallada sobre cómo definir la topología, consulte [Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) en la documentación sobre implementación.

  - Publicó la topología y configure el grupo de servidores front-end o el servidor Standard Edition. Para obtener información detallada sobre la publicación de la topología y la instalación de Lync Server 2013, consulte [Deploying Lync server 2013](lync-server-2013-deploying-lync-server.md) en la documentación sobre implementación.
    
    <div>
    

    > [!NOTE]
    > Al instalar su topología publicada, la Página Web de configuración de conferencia de acceso telefónico local se instala en el servidor front-end o el servidor Standard Edition como parte de los servicios Web.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Si cambia la ruta de acceso al almacén de archivos en el generador de topologías después de implementar Lync Server 2013, deberá reiniciar las aplicaciones del operador de conferencia y del anuncio de conferencia para usar la nueva ruta de acceso.

    
    </div>

  - Se implementó la telefonía IP empresarial. Si no está implementando la telefonía IP empresarial, combina un servidor de mediación en el servidor front-end Enterprise Edition o en el servidor Standard Edition, o bien ha implementado un servidor de mediación independiente y ha implementado una puerta de enlace RTC. Para obtener más información sobre la implementación de Enterprise Voice, consulte [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) en la documentación sobre implementación. Para obtener información detallada sobre la instalación de un servidor de mediación independiente y una puerta de enlace RTC, consulte [Deploying Mediation Servers and Defining Peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) en la documentación sobre implementación.

El siguiente diagrama de flujo muestra los pasos que debe realizar antes de poder configurar la Conferencia de acceso telefónico local y los pasos que debe realizar para configurar la Conferencia de acceso telefónico local.

**Implementación de la Conferencia de acceso telefónico local**

![Diagrama de flujo de implementación de conferencias de acceso telefónico local](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Diagrama de flujo de implementación de conferencias de acceso telefónico local")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>Permisos de conferencia de acceso telefónico local

Para configurar la Conferencia de acceso telefónico local, debe usar las siguientes herramientas administrativas:

  - Panel de control de Lync Server 2013

  - Shell de administración de Communications Server

Use estas herramientas administrativas para configurar la configuración de conferencias de acceso telefónico local y los planes de marcado, las directivas y otras opciones que requiere la Conferencia de acceso telefónico local.

La configuración de la Conferencia de acceso telefónico local requiere cualquiera de los siguientes roles administrativos, en función de la tarea:

  - **CsVoiceAdministrator**   este rol de administrador puede crear, configurar y administrar configuraciones y directivas relacionadas con la voz.

  - **CsUserAdministrator**   este rol de administrador puede habilitar y deshabilitar usuarios para Lync Server y asignar directivas existentes, como directivas de conferencia y directivas de PIN, a los usuarios.

  - **CsAdministrator**   este rol de administrador puede realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.

</div>

<div>

## <a name="see-also"></a>Consulta también


[Implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

