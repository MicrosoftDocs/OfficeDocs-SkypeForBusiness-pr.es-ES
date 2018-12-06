---
title: "Lync Server 2013: Habilitar a los usuarios de Lync para el control remoto de llamadas"
TOCTitle: Habilitar a los usuarios de Lync para el control remoto de llamadas
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48277166
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar a los usuarios de Lync para el control remoto de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Puede configurar a los usuarios de Lync para control remoto de llamadas mediante directivas de aprovisionamiento en banda basadas en servidor. La configuración de aprovisionamiento en banda puede administrarse mediante Panel de control de Lync Server o la interfaz de línea de comandos de Shell de administración de Lync Server. Estas herramientas sustituyen al complemento de WMI (Instrumental de administración de Windows) que se usa para administrar la configuración de directivas de grupo en las versiones anteriores.

Si prefiere permitir que los usuarios definan su propia configuración de llamadas remotas en Lync, puede definir la configuración de control remoto de llamadas en el servidor sin especificar los valores de **URI de servidor de línea** y **URI de línea**. Comunique a los usuarios los valores de **URI de servidor de línea** y **URI de línea** correspondientes. Asimismo, facilíteles las instrucciones para definir estas configuraciones. Si desea información sobre la configuración manual del control de llamadas remotas en Lync Server, consulte "Definir opciones y números de teléfono" en <http://go.microsoft.com/fwlink/p/?linkid=210132> en la documentación sobre clientes de Lync en el sitio web de Microsoft Office.

Si tiene una implementación existente de Communications Server 2007 R2 o Communications Server 2007, los clientes de Communicator 2007 R2 y Communicator 2007 seguirán usando la directiva de grupo durante la migración en paralelo. Sin embargo, si desea que la configuración de la directiva se aplique a los clientes de Lync, deberá configurar las opciones de aprovisionamiento en banda equivalentes de Lync Server.


> [!NOTE]
> Para que un usuario pueda habilitarse para control remoto de llamadas, debe tener un URI de servidor de línea y un URI de línea. Como se explica en <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Implementación de tareas para el control remoto de llamadas en Lync Server 2013</A>, compruebe que se use la sintaxis que la puerta de enlace necesita para esta configuración.<BR>Compruebe que el dominio del URI de servidor de línea sea el mismo que el dominio de destino especificado en el parámetro MatchUri al configurar la ruta estática a la puerta de enlace.<BR>El URI de línea especifica el número de teléfono asignado al usuario en formato E.164, con el prefijo “TEL:” . Por ejemplo, tel:+14255550150. Si desea configurar un número de extensión, el formato es tel:+14255550150;ext=111. Si anteriormente había configurado el URI de línea y no se había cambiado el valor, no hace falta especificar el URI de línea cuando se habilite al usuario para control remoto de llamadas.



## Para configurar usuarios para control remoto de llamadas mediante el Shell de administración

1.  Inicie sesión en un equipo en el que Shell de administración de Lync Server esté instalado como miembro del grupo RTCUniversalServerAdmins o un rol de control de acceso basado en roles al que haya asignado el cmdlet **Set-CsUser**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para usar el cmdlet **Set-CsUser** con el fin de configurar el control remoto de llamadas para un usuario habilitado para Lync, efectúe lo siguiente:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Por ejemplo:
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

## Para configurar usuarios para control remoto de llamadas mediante el Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desee modificar.

6.  En el menú **Editar**, haga clic en **Modificar**.

7.  En **Telefonía**, lleve a cabo uno de los siguientes procedimientos:
    
      - Para habilitar el control remoto de llamadas y que el usuario pueda controlar su línea de teléfono de escritorio desde Lync 2013 para realizar llamadas de equipo a equipo y de equipo a teléfono, haga clic en **Control remoto de llamada**. En **URI de línea**, especifique el número de teléfono del usuario. En **URI de servidor de línea**, especifique el URI del SIP de la puerta de enlace SIP/CSTA.
    
      - Para habilitar el control remoto de llamadas, deshabilitar la llamadas de equipo a equipo y que solo el usuario pueda controlar su línea de teléfono de escritorio desde Lync 2013 para realizar llamadas de equipo a teléfono, haga clic en **Control remoto solo de llamada**. En **URI de línea**, especifique el número de teléfono del usuario. En **URI de servidor de línea**, especifique el URI del SIP de la puerta de enlace SIP/CSTA.

8.  Cuando termine, haga clic en **Confirmar**.

