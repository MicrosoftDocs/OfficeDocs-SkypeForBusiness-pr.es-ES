---
title: 'Lync Server 2013: habilitar a los usuarios para la telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31b9cffef7dbb9338c1019b965fb398a0f72ed34
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Después de instalar los archivos de uno o varios servidores de mediación, configurar el enrutamiento de llamadas salientes y, opcionalmente, implementar una o más características avanzadas de Enterprise Voice, puede usar los siguientes procedimientos para permitir que un usuario realice llamadas mediante la telefonía IP empresarial:

<div>


> [!NOTE]  
> De los procedimientos siguientes, solo el primero se puede realizar mediante el panel de control de Lync Server. Para el resto de los procedimientos, solo puede usar el shell de administración de Lync Server.



</div>

  - Habilitar la cuenta de usuario para la telefonía IP empresarial.

  - (Opcional) Asignar a la cuenta de usuario una directiva de voz específica para el usuario.

  - (Opcional) Asignar a la cuenta de usuario un plan de marcado específico para el usuario.

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>Para habilitar una cuenta de usuario para telefonía IP empresarial

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desee habilitar para la telefonía IP empresarial.

6.  En el menú **Editar**, haga clic en **Mostrar detalles**.

7.  En la página **Editar usuario de Lync Server**, en **Telefonía**, haga clic en **Telefonía IP empresarial**.

8.  Haga clic en **URI de línea** y, a continuación, escriba un número de teléfono exclusivo y normalizado (por ejemplo, tel:+14255550200).

9.  Haga clic en **Confirmar**.

Para terminar de habilitar a un usuario para la telefonía IP empresarial, asegúrese de que el usuario tiene asignada una directiva de voz y un plan de marcado, ya sea global (asignado de forma predeterminada) o específico del usuario.

De manera predeterminada, a todos los usuarios se les asigna una directiva de voz global y un plan de marcado. Si ya hubiera una directiva de voz o un plan de marcado a nivel de sitio para el sitio en el que se hospeda la cuenta de usuario, se aplicarán automáticamente al usuario. Para aplicar una directiva de voz o plan de marcado por usuario a un usuario, deberá ejecutar los cmdlets **Grant-CsVoicePolicy** y **Grant-CsDialPlan**. Para obtener más información, consulte la documentación del [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="voice-policy-assignment"></a>Asignación de directivas de voz

Las directivas de voz globales y de nivel de sitio se asignan automáticamente a todas las cuentas de usuario habilitadas para la telefonía IP empresarial. También puede crear directivas de voz aplicables a usuarios o grupos específicos. Estas directivas por usuario deben estar explícitamente asignadas a los usuarios o grupos. Si desea usar la Directiva de voz global o del sitio para todos los usuarios que están habilitados para telefonía IP empresarial, puede omitir esta sección y seguir marcando la sección asignación de plan más adelante en este tema.

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>Para asignar una directiva de voz específica del usuario

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Para asignar una directiva de voz de usuario existente a un usuario, ejecute lo siguiente en el símbolo del sistema:
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Por ejemplo:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    En este ejemplo, al usuario con el nombre para mostrar Bob Kelly se le asigna la Directiva de voz con el nombre **VoicePolicyJapan**.

Para obtener información detallada sobre cómo asignar una directiva de voz específica del usuario o acerca de la ejecución del cmdlet **Grant-CsVoicePolicy** , consulte la documentación del [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>Asignación de planes de marcado

Para completar la configuración de cuentas de usuario para los usuarios de Telefonía IP empresarial o para los usuarios de conferencias de acceso telefónico local, asigne un plan de marcado. Las cuentas de usuario emplearán automáticamente el plan de marcado global o, si existe, el plan de marcado del sitio, en los casos en los que no se asigne explícitamente un plan de marcado creado particularmente para el usuario. Si desea usar el plan de marcado global o del sitio para todos los usuarios que están habilitados para telefonía IP empresarial, puede omitir esta sección.

<div>

## <a name="to-assign-a-dial-plan"></a>Para asignar un plan de marcado

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Para asignar un plan de marcado específico del usuario, ejecute lo siguiente en el símbolo del sistema:
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Por ejemplo:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    En este ejemplo, al usuario con el nombre para mostrar Bob Kelly se le asigna el plan de marcado del usuario con el nombre **DialPlanJapan**.

Para obtener información detallada acerca de la asignación de un plan de marcado de usuario o de la ejecución del cmdlet **Grant-CsDialPlan** , consulte la documentación del [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Deshabilitar a un usuario para la telefonía IP empresarial en Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

