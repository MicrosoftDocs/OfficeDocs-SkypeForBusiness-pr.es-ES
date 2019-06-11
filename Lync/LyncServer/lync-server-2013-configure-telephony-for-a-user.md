---
title: 'Lync Server 2013: configurar telefonía para un usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97f4fc79b871a962fe498d6dbd908b75f6b2fecd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Configurar la telefonía de un usuario en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

La configuración de telefonía es una parte de la configuración individual de una cuenta de usuario que se puede configurar en el panel de control de Lync Server para el usuario (es decir, si el usuario individual se ha habilitado para Lync Server 2013 y la organización admite telefonía).

Entre las opciones de telefonía de usuario de Lync Server se incluyen las siguientes:

  - **Audio/vídeo**   deshabilitado el usuario no puede hacer llamadas con audio y vídeo.

  - **Solo de PC a PC**   el usuario solo puede hacer videollamadas o videollamadas de PC a PC.

  - **Telefonía IP**   empresarial el usuario puede usar la infraestructura de Lync Server 2013 para enrutar todas las llamadas entrantes y salientes. El usuario también puede hacer llamadas de PC a PC.

  - **Control de llamada remota**   el usuario puede usar Lync Server 2013 para controlar el teléfono de escritorio y también puede hacer llamadas entre equipos.

Para obtener detalles sobre la configuración de telefonía para una organización, vea [configurar la telefonía de un usuario en Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) e implementar la telefonía [IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) en la documentación de implementación.

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>Para configurar telefonía para una cuenta de usuario específica

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar. **.

5.  En la tabla, haga clic en la cuenta de usuario que desea modificar.

6.  En el menú **Editar** , haga clic en **modificar**.

7.  En **telefonía**, haga lo siguiente:
    
      - Para deshabilitar las llamadas de audio y vídeo para el usuario, haga clic en **audio/vídeo**deshabilitado.
    
      - Para habilitar las comunicaciones de audio de PC a PC para el usuario, pero no para el control remoto de llamadas ni para la telefonía IP empresarial, haga clic en **solo de PC a PC**. Especifique un valor para el **URI de línea** del teléfono que usa el usuario para las comunicaciones de audio de PC a PC.
    
      - Para enrutar las llamadas telefónicas del usuario mediante la infraestructura de Lync Server 2010 de acuerdo con la Directiva de clase de servicio, incluida la comunicación de audio de PC a PC, haga clic en **telefonía IP empresarial**. En **URI de línea**, especifique el número de teléfono de la telefonía IP empresarial. En **Directiva de plan de marcado** y **Directiva de voz**, especifique las directivas apropiadas para el usuario. Para especificar las reglas de normalización para traducir números de teléfono marcados por el usuario al formato E. 164, seleccione el perfil de ubicación adecuado en la **política de ubicación**.
    
      - Para habilitar el control remoto de llamadas, que permite a los usuarios controlar la línea telefónica de escritorio de Lync Server 2013 para hacer llamadas de PC a PC y llamadas de PC a teléfono, haga clic en **control remoto de llamadas**. En **URI de línea**, especifique el número de teléfono para el control de llamada remota. El usuario debe tener una conexión de teléfono de escritorio y de central de conmutación (PBX) para el enrutamiento de llamadas.

</div>

<div>

## <a name="see-also"></a>Vea también


[Modificar las propiedades de la cuenta de usuario en Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

