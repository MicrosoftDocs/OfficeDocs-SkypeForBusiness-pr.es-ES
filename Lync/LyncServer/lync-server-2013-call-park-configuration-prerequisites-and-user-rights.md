---
title: 'Lync Server 2013: requisitos previos de configuración del estacionamiento de llamadas y derechos de usuario'
description: 'Lync Server 2013: requisitos previos de configuración del estacionamiento de llamadas y derechos de usuario.'
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
ms.openlocfilehash: b01187ad32fa7338765c0fa5b409b4e185e8ad35
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563536"
---
# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Requisitos previos de configuración del estacionamiento de llamadas y derechos de usuario en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-10_

El estacionamiento de llamadas es una característica de administración de llamadas que se instala de forma predeterminada al implementar la telefonía IP empresarial. En este tema se describe lo que necesita tener en su ubicación antes de poder configurar el estacionamiento de llamadas y los derechos de usuario que necesita para realizar las tareas de configuración.

<div>


> [!IMPORTANT]  
> No se realiza una copia de seguridad de los archivos de música en espera personalizados de la aplicación de estacionamiento de llamadas como parte del proceso de recuperación ante desastres de Lync Server 2013, y los archivos se perderán si los archivos cargados en el grupo están dañados, dañados o borrados. Guarde siempre una copia de seguridad independiente de los archivos de música en espera que haya cargado para Estacionamiento de llamadas.



</div>

En esta sección se da por sentado que ha leído la documentación de planeación relacionada con el parque de llamadas (consulte [planeación de las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="call-park-configuration-prerequisites"></a>Requisitos previos de configuración del estacionamiento de llamadas

El estacionamiento de llamadas requiere los siguientes componentes:

  - Servicio de aplicación

  - Aplicación Estacionamiento de llamadas

Estos componentes se instalan automáticamente al implementar la telefonía IP empresarial.

Si desea que los autores de las llamadas oigan música mientras la llamada está estacionada, también se requiere un archivo de música en espera. El archivo de música en espera predeterminado se instala automáticamente al implementar la telefonía IP empresarial. Puede sustituir el archivo predeterminado por su propio archivo de música en espera. El estacionamiento de llamadas usa el almacén de archivos para guardar el archivo de audio.

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>Derechos de usuario de configuración del estacionamiento de llamadas

Puede usar las siguientes herramientas administrativas para configurar el estacionamiento de llamadas:

  - Panel de control de Lync Server

  - Shell de administración de Lync Server

Use estas herramientas para configurar la tabla de órbitas de estacionamiento de llamadas y configurar otras opciones que usa el estacionamiento de llamadas.

La configuración del estacionamiento de llamadas requiere cualquiera de los siguientes roles administrativos, en función de la tarea:

  - **CsVoiceAdministrator:** Este rol de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con la voz.

  - **CsUserAdministrator:** Este rol de administrador puede habilitar el estacionamiento de llamadas en la Directiva de voz. De igual modo, permite el acceso de vista de solo lectura a todas las configuraciones de voz.

  - **CsServerAdministrator:** Este rol de administrador puede administrar, supervisar y solucionar problemas de servidores y servicios.

  - **CsAdministrator:** Este rol de administrador puede realizar todas las tareas de CsVoiceAdministrator, CsServerAdministrator y CsUserAdministrator.

<div>


> [!NOTE]  
> Para obtener más información sobre los derechos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> en la documentación referente a la planeación.



</div>

</div>

<div>

## <a name="see-also"></a>Consulte también


[Implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Planeación de características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

