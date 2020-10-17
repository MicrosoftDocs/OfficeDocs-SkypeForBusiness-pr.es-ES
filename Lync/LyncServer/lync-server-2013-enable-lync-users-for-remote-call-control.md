---
title: 'Lync Server 2013: habilitar a los usuarios de Lync para el control remoto de llamadas'
description: 'Lync Server 2013: habilite a los usuarios de Lync para el control remoto de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84b76d0d899da8ca25f42b5bed450914890f4b27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559606"
---
# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Habilitar a los usuarios de Lync para el control remoto de llamadas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Puede configurar los usuarios de Lync para el control remoto de llamadas mediante directivas de aprovisionamiento en banda que se basan en el servidor. Puede administrar la configuración de aprovisionamiento en banda mediante el panel de control de Lync Server o la interfaz de línea de comandos del shell de administración de Lync Server. Estas herramientas sustituyen el complemento instrumental de administración de Windows (WMI) que se usó para administrar la configuración de la Directiva de grupo en versiones anteriores.

Si prefiere que los usuarios configuren su propia configuración de control remoto de llamadas en Lync, puede establecer la configuración de control remoto de llamadas para los usuarios del servidor sin especificar los valores URI del **servidor de línea** y **URI de línea** . Asegúrese de comunicar los valores adecuados del URI del **servidor de línea** y del **URI de línea** a los usuarios y proporcione a los usuarios las instrucciones para configurar estas opciones. Para consultar el procedimiento para configurar manualmente el control remoto de llamadas en Lync Server, consulte "set phone Options and Numbers" en <https://go.microsoft.com/fwlink/p/?linkid=210132> la documentación del cliente de Lync en el sitio web de Microsoft Office.

Si dispone de una implementación existente de Communications Server 2007 R2 o Communications Server 2007, los clientes de Communicator 2007 R2 y Communicator 2007 seguirán usando la Directiva de grupo durante la migración en paralelo. Sin embargo, si desea que la configuración de directivas se lleve a cabo en los clientes de Lync, debe configurar la configuración de aprovisionamiento en banda de Lync Server equivalente.

<div>


> [!NOTE]  
> Para habilitar un usuario para el control remoto de llamadas, debe proporcionar al usuario un URI de línea y un URI de servidor de línea. Como se describe en <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment Tasks for Remote Call control in Lync Server 2013</A>, debe asegurarse de usar la sintaxis que la puerta de enlace requiere para estas opciones.<BR>Asegúrese de que el dominio del URI del servidor de línea es el mismo que el dominio de destino que especificó en el parámetro MatchUri al configurar la ruta estática a la puerta de enlace.<BR>El URI de línea especifica el número de teléfono asignado al usuario en formato E. 164, con el prefijo "TEL:" (por ejemplo, Tel: + 14255550150). Si desea configurar un número de extensión, el formato es tel:+14255550150;ext=111. Si anteriormente había configurado el URI de línea y no se había cambiado el valor, no hace falta especificar el URI de línea cuando se habilite al usuario para control remoto de llamadas.



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>Para configurar usuarios para control remoto de llamadas mediante el Shell de administración

1.  Inicie sesión en un equipo en el que esté instalado shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o como un rol de control de acceso basado en roles al que haya asignado el cmdlet **set-CsUser** .

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Para usar el cmdlet **Set-CsUser** con el fin de configurar el control remoto de llamadas para un usuario habilitado para Lync, efectúe lo siguiente:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Por ejemplo:
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>Para configurar usuarios para control remoto de llamadas mediante el Panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios** , escriba todo (o la primera parte) del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desee modificar.

6.  En el menú **Editar**, haga clic en **Modificar**.

7.  En **Telefonía**, lleve a cabo uno de los siguientes procedimientos:
    
      - Para habilitar el control remoto de llamadas para permitir que el usuario controle el teléfono de la central de conmutación (PBX) de Lync 2013 para realizar llamadas de audio de equipo a equipo y llamadas de equipo a teléfono, haga clic en **control remoto de llamadas**. En **URI de línea**, especifique el número de teléfono del usuario. En **URI de servidor de línea**, especifique el URI del SIP de la puerta de enlace SIP/CSTA.
    
      - Para habilitar el control remoto de llamadas, pero para deshabilitar las llamadas de audio de PC a PC y permitir que solo el usuario controle su teléfono PBX desde Lync 2013 para realizar llamadas de equipo a teléfono, haga clic en **control remoto de llamadas únicamente**. En **URI de línea**, especifique el número de teléfono del usuario. En **URI de servidor de línea**, especifique el URI del SIP de la puerta de enlace SIP/CSTA.

8.  Cuando termine, haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

