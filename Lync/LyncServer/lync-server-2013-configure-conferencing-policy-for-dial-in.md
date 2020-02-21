---
title: 'Lync Server 2013: configurar la Directiva de conferencias para el acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33f84ec3cb900b4283f30d67e318ab10d3625326
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Configurar la Directiva de conferencias para el acceso telefónico en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-21_

Las directivas de conferencias son una opción de cuenta de usuario que especifica la experiencia de conferencia de los participantes. Puede crear directivas de conferencia cuyo ámbito sea de sitio o de usuario. La configuración de directiva de conferencias abarca muchos aspectos de la programación de conferencias y de la participación en ellas. Varias configuraciones de directiva de conferencias admiten las conferencias de acceso telefónico local para los participantes. Cuando configure la característica de conferencia de acceso telefónico local, debe comprobar que estos campos estén definidos de la forma apropiada para su organización, y modificarlos según sea necesario.

Compruebe los campos siguientes en la directiva de conferencias:

  - **Permitir a los participantes invitar a usuarios anónimos**   esta configuración permite a los organizadores de reuniones invitar a las reuniones a los participantes anónimos (es decir, no autenticados). No es obligatoria para las conferencias de acceso telefónico local. Esta opción está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada.

  - **Habilitar Conferencia**   de acceso telefónico local RTC esta configuración permite a los usuarios unirse a la parte de audio de una conferencia mediante el marcado desde la RTC. Esta opción es obligatoria para las conferencias de acceso telefónico local. Esta opción está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada.

  - **Permitir que los participantes anónimos marquen**   esta configuración permite a los usuarios anónimos que ya están Unidos a la reunión llamar a un número de teléfono para unirse a la parte de audio de la Conferencia. No es obligatoria para las conferencias de acceso telefónico local. Esta opción no está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada.

  - **Permitir que los participantes no habilitados para telefonía IP empresarial marquen**   esta configuración permite a los participantes de la reunión y los organizadores que no están habilitados para telefonía IP empresarial llamar a un número de teléfono para unirse a la parte de audio de la Conferencia. La llamada de salida se autoriza según la directiva de voz asignada por el organizador. Esta opción no está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada. El valor predeterminado está deshabilitado.
    
    <div>
    

    > [!NOTE]  
    > Para habilitar esta función, un organizador de la reunión que no está habilitado para Enterprise Voice debe tener asignada una directiva de voz adecuada para autorizar cualquier aceptación de llamada desde una conferencia organizada por dicho usuario. Se puede asignar una directiva de voz a un usuario que no está habilitado para telefonía IP empresarial desde el shell de administración de Lync Server. Si el usuario no tiene una directiva de voz asignada explícitamente, se usará la Directiva de voz del sitio para autorizar la solicitud de acceso telefónico. Si no hay ninguna directiva de voz de sitio, se usará la Directiva de voz global.&nbsp;

    
    </div>

El procedimiento descrito en esta sección explica cómo modificar la directiva de conferencia. Para obtener más información sobre cómo configurar todas las opciones que definen la experiencia del participante en la Directiva de conferencia predeterminada, vea [crear o modificar una colección de opciones de configuración de reuniones en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Para obtener más información sobre cómo crear una directiva de conferencia para un usuario o grupo de usuarios específico, vea [Create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Para obtener una lista de todas las opciones de configuración de directivas de conferencia disponibles, consulte [referencia de configuración de directivas de conferencia para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>Para modificar la directiva de conferencias para el acceso telefónico

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia**.

4.  En la pestaña **Directiva de conferencias**, haga doble clic en el nombre de una directiva de conferencias para abrir el cuadro de diálogo **Editar directiva de conferencia**.

5.  Compruebe que los campos de conferencia de acceso telefónico local sean adecuados para su organización y modifique la configuración si es necesario.

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

