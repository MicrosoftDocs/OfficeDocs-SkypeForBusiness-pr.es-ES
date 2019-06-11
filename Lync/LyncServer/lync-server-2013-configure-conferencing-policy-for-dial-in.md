---
title: 'Lync Server 2013: Configurar la directiva de conferencias para el acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74621fee97a1e6721f8772b265761b62b1b9f266
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Configurar la directiva de conferencias para el acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-21_

Las directivas de conferencias son una opción de cuenta de usuario que especifica la experiencia de conferencia de los participantes. Puede crear directivas de conferencia cuyo ámbito sea de sitio o de usuario. La configuración de directiva de conferencias abarca muchos aspectos de la programación de conferencias y de la participación en ellas. Varias configuraciones de directiva de conferencias admiten las conferencias de acceso telefónico local para los participantes. Cuando configure la característica de conferencia de acceso telefónico local, debe comprobar que estos campos estén definidos de la forma apropiada para su organización, y modificarlos según sea necesario.

Compruebe los siguientes campos de su Directiva de Conferencia:

  - **Permitir a los participantes invitar a usuarios anónimos**   esta configuración permite a los organizadores de reuniones invitar a reuniones anónimos (es decir, no autenticados). Esta configuración es opcional para las conferencias de acceso telefónico local. Esta opción está seleccionada de forma predeterminada en la Directiva de conferencia global predeterminada.

  - **Habilitar Conferencia**   de acceso telefónico PSTN esta configuración permite a los usuarios unirse a la parte de audio de una conferencia mediante el marcado desde la RTC. Esta configuración es necesaria para las conferencias de acceso telefónico local. Esta opción está seleccionada de forma predeterminada en la Directiva de conferencia global predeterminada.

  - **Permitir a los participantes anónimos marcar**   esta configuración permite que los usuarios anónimos que ya se hayan unido a la reunión llamen a un número de teléfono para unirse a la parte de audio de la Conferencia. Esta configuración es opcional para las conferencias de acceso telefónico local. Esta opción no está seleccionada de forma predeterminada en la Directiva de conferencia global predeterminada.

  - **Permitir**   que los participantes que no están habilitados para la telefonía IP empresarial Marque esta configuración permite a los participantes de la reunión y los organizadores que no están habilitados para la telefonía IP empresarial llamar a un número de teléfono para unirse a la parte de audio de la Conferencia. La llamada de acceso telefónico es autorizada en función de la Directiva de voz asignada al organizador. Esta opción no está seleccionada de forma predeterminada en la Directiva de conferencia global predeterminada. El valor predeterminado de configuración es deshabilitado.
    
    <div>
    

    > [!NOTE]  
    > Para habilitar esta función, un organizador de la reunión que no está habilitado para Enterprise Voice debe tener asignada una directiva de voz adecuada para autorizar cualquier acceso telefónico desde una conferencia organizada por dicho usuario. Se puede asignar una directiva de voz a un usuario que no está habilitado para telefonía IP empresarial desde el shell de administración de Lync Server. Si el usuario no tiene una política de voz asignada explícitamente, la Directiva de voz del sitio se usará para autorizar la solicitud de aceptación de llamada. Si no hay ninguna directiva de voz del sitio, se usará la política de voz global.&nbsp;

    
    </div>

En el procedimiento de esta sección se explica cómo modificar la Directiva de conferencia. Para obtener más información sobre cómo configurar todas las opciones que definen la experiencia de participante en la Directiva de conferencia predeterminada, vea [crear o modificar una colección de opciones de configuración de reuniones en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Para obtener más información sobre cómo crear una directiva de conferencia para un usuario específico o un grupo de usuarios, vea [crear o modificar una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Para obtener una lista de todas las configuraciones de directiva de conferencia disponibles, consulte [referencia de configuración de directiva de conferencia para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>Para modificar la Directiva de conferencia para el acceso telefónico

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **CS-ServerAdministrator** o **CsAdministrator** .

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia**.

4.  En la pestaña **Directiva de conferencia** , haga doble clic en un nombre de directiva de conferencia para abrir el cuadro de diálogo **Editar Directiva de conferencia** .

5.  Compruebe que los campos de las conferencias de acceso telefónico local son adecuados para su organización y modifique la configuración si es necesario.

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

