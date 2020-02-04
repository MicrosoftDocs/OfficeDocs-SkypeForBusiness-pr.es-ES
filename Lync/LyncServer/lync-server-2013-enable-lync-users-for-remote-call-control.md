---
title: 'Lync Server 2013: Habilitar a los usuarios de Lync para el control remoto de llamadas'
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
ms.openlocfilehash: 260cfc2d3a0b185d58e90f4944162ea23135a0b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Habilitar a los usuarios de Lync para el control remoto de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Puede configurar los usuarios de Lync para el control remoto de llamadas mediante directivas de aprovisionamiento en banda basadas en el servidor. Puede administrar la configuración de aprovisionamiento en banda con el panel de control de Lync Server o la interfaz de línea de comandos del shell de administración de Lync Server. Estas herramientas reemplazan al complemento instrumental de administración de Windows (WMI) que se usó para administrar la configuración de la Directiva de grupo en versiones anteriores.

Si prefiere permitir que los usuarios configuren su propia configuración de control de llamadas remotas en Lync, puede configurar la configuración de control de llamadas remotas para los usuarios del servidor sin especificar valores **URI del servidor de líneas** y URI de **línea** . Asegúrese de comunicar los valores correctos de **URI del servidor de línea** y URI de **línea** a los usuarios, y proporcione a los usuarios las instrucciones para establecer esta configuración. Para obtener información sobre cómo configurar manualmente el control remoto de llamadas en Lync Server, consulte "set phone Options <http://go.microsoft.com/fwlink/p/?linkid=210132> and Numbers" en la documentación del cliente de Lync en el sitio web de Microsoft Office.

Si tiene una implementación existente de Communications Server 2007 R2 o Communications Server 2007, los clientes de Communicator 2007 R2 y Communicator 2007 continuarán usando la Directiva de grupo durante la migración en paralelo. Sin embargo, si desea que la configuración de directivas se lleve a cabo para los clientes de Lync, debe configurar la configuración de aprovisionamiento en banda de Lync Server equivalente.

<div>


> [!NOTE]  
> Para habilitar un usuario para el control remoto de llamadas, debe proporcionar al usuario un URI de línea y un URI de servidor de línea. Como se describe en <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">tareas de implementación para el control remoto de llamadas en Lync Server 2013</A>, debe asegurarse de usar la sintaxis requerida por la puerta de enlace para esta configuración.<BR>Asegúrese de que el dominio del URI del servidor de línea es el mismo que el dominio de destino que especificó en el parámetro MatchUri cuando configuró la ruta estática a la puerta de enlace.<BR>El URI de línea especifica el número de teléfono asignado al usuario en formato E. 164, con el prefijo "TEL:" (por ejemplo, Tel: + 14255550150). Si desea configurar un número de extensión, el formato es Tel: + 14255550150; ext = 111. Si previamente ha configurado el URI de la línea del usuario y el valor no ha cambiado, no es necesario especificar el URI de línea cuando habilita al usuario para el control remoto de llamadas.



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>Para habilitar el control remoto de llamadas para los usuarios habilitados para Lync mediante el shell de administración

1.  Inicie sesión en un equipo en el que esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o como un rol de control de acceso basado en roles al que haya asignado el cmdlet **set-CsUser** .

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Para usar el cmdlet **set-CsUser** para configurar el control remoto de llamadas para un usuario existente habilitado para Lync, haga lo siguiente:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Por ejemplo:
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>Para configurar usuarios para el control remoto de llamadas con el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios** , escriba todos (o la primera parte) del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desea modificar.

6.  En el menú **Editar** , haga clic en **modificar**.

7.  En **telefonía**, realice una de las siguientes acciones:
    
      - Para habilitar el control remoto de llamadas para permitir que el usuario pueda controlar su teléfono de central de conmutación (PBX) de Lync 2013 para hacer llamadas de audio de PC a PC y llamadas de PC a teléfono, haga clic en **control remoto de llamadas**. En **URI de línea**, especifique el número de teléfono del usuario. En **line URI del servidor**, especifique el URI de SIP de la puerta de enlace SIP/CSTA.
    
      - Para habilitar el control remoto de llamadas, pero deshabilitar las llamadas de audio de PC a PC y permitir que solo el usuario controle su teléfono PBX desde Lync 2013 para hacer llamadas de equipo a teléfono, haga clic en **control remoto de llamadas únicamente**. En **URI de línea**, especifique el número de teléfono del usuario. En **line URI del servidor**, especifique el URI de SIP de la puerta de enlace SIP/CSTA.

8.  Cuando haya terminado, haga clic en **confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

