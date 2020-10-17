---
title: 'Lync Server 2013: configurar la telefonía para un usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86eade8f7a2ac1db627668ca78b8fb7869e6da71
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520377"
---
# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Configurar la telefonía para un usuario en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

La configuración de telefonía es una de las configuraciones individuales de una cuenta de usuario que se puede configurar en el panel de control de Lync Server para el usuario (es decir, si el usuario individual se ha habilitado para Lync Server 2013 y la organización admite telefonía).

Entre las opciones de telefonía de usuario de Lync Server se incluyen las siguientes:

  - **Audio y vídeo deshabilitados**     El usuario no puede realizar llamadas con audio y vídeo.

  - Solo de equipo **a equipo**     El usuario solo puede realizar llamadas de audio o vídeo de PC a PC.

  - **Telefonía IP empresarial**     El usuario puede usar la infraestructura de Lync Server 2013 para enrutar todas las llamadas entrantes y salientes. También puede realizar llamadas de equipo a equipo.

  - Control remoto de **llamadas**     El usuario puede usar Lync Server 2013 para controlar el teléfono de escritorio y también puede realizar llamadas de equipo a equipo.

Para obtener más información sobre cómo configurar la telefonía para una organización, vea [Configure Telephony for a User in Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) e [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) en la documentación sobre implementación.

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>Para configurar la telefonía para una cuenta de usuario específica

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desee modificar.

6.  En el menú **Editar**, haga clic en **Modificar**.

7.  En **Telefonía**, siga este procedimiento:
    
      - Para deshabilitar las llamadas de audio y vídeo del usuario, haga clic en **Audio y vídeo deshabilitados**.
    
      - Para habilitar las comunicaciones de audio de equipo a equipo para el usuario, pero no el control remoto de llamadas ni la Telefonía IP empresarial, haga clic en **Solo de equipo a equipo**. Especifique un valor para **URI de línea** para el teléfono que usa el usuario para comunicaciones de audio de equipo a equipo.
    
      - Para enrutar las llamadas de teléfono del usuario mediante la infraestructura de Lync Server 2010 de acuerdo con la Directiva de clase de servicio, incluida la comunicación de audio de PC a PC, haga clic en **telefonía IP empresarial**. En **URI de línea**, especifique el número de teléfono para la Telefonía IP empresarial. En **Directiva de plan de marcado** y **Directiva de voz**, especifique las directivas adecuadas para el usuario. Para especificar las reglas de normalización para convertir los números de teléfono que marque el usuario a formato E.164, seleccione el perfil de ubicación apropiado en **Directiva de ubicación**.
    
      - Para habilitar el control remoto de llamadas, que permite a los usuarios controlar su línea telefónica de escritorio desde Lync Server 2013 para realizar llamadas de equipo a equipo y llamadas de equipo a teléfono, haga clic en **control remoto de llamadas**. En **URI de línea**, especifique el número de teléfono para el control remoto de llamadas. El usuario debe tener un teléfono de escritorio y una conexión de central de conmutación (PBX) para el enrutamiento de llamadas.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Modificación de las propiedades de la cuenta de usuario en Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

