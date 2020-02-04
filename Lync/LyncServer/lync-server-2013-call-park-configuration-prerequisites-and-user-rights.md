---
title: 'Lync Server 2013: Requisitos previos de configuración del estacionamiento de llamadas y derechos de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 485c8ee5ba2f7d788ef2917488ebfd86607d48d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Requisitos previos de configuración del estacionamiento de llamadas y derechos de usuario en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-10_

Estacionamiento de llamadas es una característica de administración de llamadas que se instala de forma predeterminada al implementar la telefonía IP empresarial. En este tema se describe lo que debe tener en cuenta antes de poder configurar el parque de llamadas y los derechos de usuario que necesita para realizar las tareas de configuración.

<div>


> [!IMPORTANT]  
> No se realiza una copia de seguridad de los archivos personalizados de música en espera para la aplicación de estacionamiento de llamadas como parte del proceso de recuperación de desastres de Lync Server 2013, y los archivos se perderán si los archivos cargados en el grupo están dañados, están dañados o se han borrado. Guarda siempre una copia de seguridad independiente de los archivos de música en espera personalizados que haya cargado para el estacionamiento de llamadas.



</div>

En esta sección se supone que ha leído la documentación de planificación relacionada con Call Park (consulte [planificación de las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="call-park-configuration-prerequisites"></a>Requisitos previos de configuración del parque de llamadas

El parque de llamadas requiere los siguientes componentes:

  - Servicio de aplicaciones

  - Aplicación de estacionamiento de llamadas

Estos componentes se instalan automáticamente al implementar la telefonía IP empresarial.

Si desea que las personas que llaman oigan música mientras se estaciona la llamada, también se necesita un archivo de música en espera. El archivo de música en espera predeterminada se instala automáticamente al implementar la telefonía IP empresarial. Puede sustituir el archivo predeterminado con su propio archivo de música en espera. El parque de llamadas usa el almacén de archivos para almacenar el archivo de audio.

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>Derechos de usuario de configuración de estacionamiento de llamadas

Puede usar las siguientes herramientas administrativas para configurar el parque de llamadas:

  - Panel de control de Lync Server

  - Shell de administración de Communications Server

Use estas herramientas para configurar la tabla de llamadas en órbita y para configurar otras opciones que usa el parque de llamadas.

La configuración de estacionamiento requiere cualquiera de los siguientes roles administrativos, en función de la tarea:

  - **CsVoiceAdministrator:** Esta función de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con las voz.

  - **CsUserAdministrator:** Esta función de administrador puede habilitar el parque de llamadas en la política de voz. Esta función de administrador también tiene acceso de vista de solo lectura a todas las configuraciones de voz.

  - **CsServerAdministrator:** Esta función de administrador puede administrar, supervisar y solucionar problemas de servidores y servicios.

  - **CsAdministrator:** Esta función de administrador puede realizar todas las tareas de CsVoiceAdministrator, CsServerAdministrator y CsUserAdministrator.

<div>


> [!NOTE]  
> Para obtener más información sobre los derechos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync Server 2013</A> en la documentación de planeación.



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

