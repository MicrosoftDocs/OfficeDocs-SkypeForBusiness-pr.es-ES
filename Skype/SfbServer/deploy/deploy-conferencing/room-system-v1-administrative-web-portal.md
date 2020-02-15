---
title: Implementar el portal web administrativo de SRS V1 en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: El portal web administrativo de Skype empresarial Server V1 (SRS v1, anteriormente conocido como Lync Room System) es un portal web que las organizaciones pueden usar para mantener sus salas de conferencias de sistemas de salas de Skype. Los administradores pueden usar el portal web administrativo de SRS V1 para supervisar el estado de los dispositivos, por ejemplo, mediante la supervisión de dispositivos de audio y vídeo. Con este portal, los administradores pueden recopilar información de diagnóstico de forma remota para supervisar el estado de la sala de conferencias.
ms.openlocfilehash: d718adb60437fdd7e08724a5ba5fc48fa120425e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045903"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Implementar el portal web administrativo de SRS V1 en Skype empresarial Server

El portal web administrativo de Skype empresarial Server V1 (SRS v1, anteriormente conocido como Lync Room System) es un portal web que las organizaciones pueden usar para mantener sus salas de conferencias de sistemas de salas de Skype. Los administradores pueden usar el portal web administrativo de SRS V1 para supervisar el estado de los dispositivos, por ejemplo, mediante la supervisión de dispositivos de audio y vídeo. Con este portal, los administradores pueden recopilar información de diagnóstico de forma remota para supervisar el estado de la sala de conferencias.

Para usar esta característica, el portal web administrativo de SRS V1 debe estar implementado en todos los servidores front-end de Skype empresarial Server. En esta guía se proporcionan instrucciones para los administradores sobre cómo instalar y configurar el portal web administrativo de SRS. Está destinada a los administradores que tienen conocimientos sobre la administración de Skype empresarial Server y que tienen derechos de usuario administrador para modificar la topología de Skype empresarial Server.

Una vez implementado el portal web administrativo de SRS V1 en el servidor, los administradores pueden comprobar los dispositivos de estado SRS v1 iniciando sesión en el sitio desde sus propios equipos o portátiles.

> [!IMPORTANT]
> Descargue el [portal web administrativo de sistemas de salas de Skype V1 de Microsoft para Skype empresarial Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).

En este tema:

- [Configurar el entorno para el portal web administrativo de SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Instalación del portal web administrativo de SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Usar el portal web administrativo de SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Configurar el entorno para el portal web administrativo de SRS v1
<a name="Config_Env"> </a>

Para usar el portal web administrativo de SRS v1, tendrá que instalar o configurar los siguientes requisitos previos.

> [!IMPORTANT]
> Si el servidor está configurado con autenticación Kerberos y NTLM, y SRS se está ejecutando en un equipo que no está unido al dominio, se producirá un error en la autenticación Kerberos y el usuario no podrá ver el estado de SRS en el portal administrativo. Para resolver este problema, configure el servidor con autenticación NTLM o la autenticación NTLM y TLS-DSK (sin Kerberos), o bien, una el equipo SRS al dominio.

1. Instale las actualizaciones acumulativas de Skype empresarial Server en la topología de Skype empresarial Server.

    Para obtener la actualización o ver lo que se incluye con ella, consulte [actualizaciones para Skype empresarial Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

2. Cree un usuario de Active Directory habilitado para SIP.

    El portal web administrativo de SRS v1 usa estas credenciales para consultar información de Skype empresarial Server. El nombre de usuario en los ejemplos indicados es LRSApp.

3. Cree un grupo de seguridad de Active Directory con el nombre LRSSupportAdminGroup.

    Cree el grupo con el ámbito de grupo global y el tipo de grupo como seguridad. Los usuarios habilitados para SIP que se agreguen a este grupo tendrán autorización para ver la lista de salas y ejecutar determinados comandos, como la recopilación de registros.

4. Cree un grupo de seguridad de Active Directory con el nombre LRSFullAccessAdminGroup.

    Cree el grupo con el ámbito de grupo global y el tipo de grupo como seguridad. los usuarios habilitados para SIP que se agregan a este grupo tienen autorización para usar todas las funciones del portal de administración en un único salón de Skype. Para incluir la compatibilidad con la administración masiva de salones de Skype, consulte el paso 5.

     ![Lista de grupos de administración con rol de grupo de seguridad](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Cree un grupo de seguridad de Active Directory con el nombre LRSPowerUserAdminsGroup.

    Cree el grupo con el ámbito de grupo global y el tipo de grupo como seguridad. Los usuarios habilitados para SIP que se agregan a este grupo tienen autorización para usar todas las funciones del portal de administración, incluida la administración masiva de salones de Skype empresarial.

6. Agregue LRSFullAccessAdminGroup como miembro de LRSSupportAdminGroup.

     ![Página de miembros de propiedades de LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Cree un usuario de Active Directory habilitado para SIP con el nombre LRSSupport. Agregue este usuario a LRSSupportAdminGroup.

     ![Página de miembros de propiedades de LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Instale [ASP.NET MVC 4 para Visual Studio 2010 SP1 y Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Instalación del portal web administrativo de SRS v1
<a name="Install_SRS"> </a>

Descargue el [portal web administrativo de sistemas de salas de Skype V1 de Microsoft para Skype empresarial Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).

Para instalar el portal web administrativo de SRS v1, siga estos pasos.

1. Configure el puerto de la aplicación de confianza mediante la ejecución del siguiente cmdlet en el shell de administración de Skype empresarial Server:

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Para instalar el portal de la sala de reuniones, descargue **MeetingRoomPortalInstaller. msi** y, a continuación, ejecútelo como administrador.

3. Abra el archivo Web. config desde la siguiente ubicación:

    % Program Programa%\skype for Business Server 2015 \ Web Components\Meeting Room Portal\Int\Handler\

4. En el archivo Web. config, cambie PortalUserName por el nombre de usuario creado en el paso 2 en la sección "[configurar el entorno para el portal web administrativo de SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (el nombre recomendado en el paso es LRSApp):

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Dado que el portal de administración de SRS V1 es una aplicación de confianza, no es necesario proporcionar la contraseña en la configuración del portal. Si este usuario usa un registrador diferente que el registrador local, debe especificar el registrador para él agregando la siguiente línea en el archivo Web. config:

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Si el puerto usado es distinto de 5061, agregue la siguiente línea en el archivo Web. config:

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Comprobación de la instalación del portal web administrativo de SRS

Para comprobar la instalación del portal web administrativo de SRS v1, haga lo siguiente:

1. En un servidor front-end, vaya a la siguiente dirección URL:

    https://\<fe-servidor\>/LRS

    No debería ver ningún error, como se muestra en la siguiente imagen:

     ![Pantalla de inicio de sesión del portal de administración del sistema Lync Room](../../media/LRS_AdminPortalSignIn.png)

2. Si no ve ningún error, intente acceder a la siguiente dirección URL desde cualquier otro equipo de la topología:

    https://\<fe-servidor\>/LRS

    Para obtener acceso a la página, deberá agregar los registros DNS tal y como se describe en "[registros DNS necesarios para el inicio de sesión automático de cliente](https://go.microsoft.com/fwlink/p/?LinkId=318056)".

## <a name="use-the-srs-administrative-web-portal"></a>Usar el portal web administrativo de SRS
<a name="Use_Portal"> </a>

Después de implementar SRS en el servidor, puede comprobar el estado de todos los salones de SRS iniciando sesión en el portal web administrativo de SRS v1 desde un explorador.

### <a name="sign-in"></a>Iniciar sesión

1. Vaya a la siguiente dirección URL:

    https://\<fe-servidor\>/LRS

2. Escriba las credenciales de la cuenta LRSSupport o de una cuenta que se haya agregado al grupo de seguridad LRSSupportAdminGroup.

![Pantalla de inicio de sesión del portal de administración del sistema Lync Room](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Página de resumen del portal web administrativo de SRS

La página de Resumen proporciona la siguiente información para todas las salas de SRS implementadas en el servidor:

- **Etiqueta** El nombre personalizado que el administrador da al salón. La etiqueta se puede establecer en el portal haciendo clic en el nombre del salón.

- **Estado** de El estado de mantenimiento de la sala, que se deriva del estado de mantenimiento agregado de la sala, que se muestra en la sección estado de la página Configuración de la sala.

- **Próxima reunión** La fecha y la hora en que se programó la próxima reunión.

- **Versión del SRS, fabricante, modelo** Estos valores están preestablecidos en SRS. Según el fabricante, estos campos podrían dejarse en blanco.

- **Última actualización** Muestra la última vez que se actualizó la Página Web.

![Vista de resumen del portal de administración del sistema Lync Room](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Solo verá el menú Administración en masa si forma parte del grupo de seguridad LRSPowerUserAdminsGroup.

### <a name="srs-room-information"></a>Información de la sala de SRS

La sección de información de la sala del portal permite ver y configurar salones de SRS individuales. Contiene cuatro secciones: configuración, detalles, registro y estado.

#### <a name="settings"></a>Configuración

En la sección configuración, puede establecer la contraseña, la etiqueta de salón y los niveles de volumen predeterminados para el salón. Si configura estas opciones, los cambios solo se replican después de reiniciar la consola de SRS. Solo verá la configuración de actualizaciones del sistema para dispositivos SRS con la versión 15,12 y posteriores.

![Configuración del salón del portal de administración del sistema de Lync Room](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Detalles

La sección de detalles proporciona un resumen de solo lectura de la configuración de la sala de SRS, que incluye: la hora de la última actualización; próxima reunión; últimas actualizaciones, mantenimiento y calibración; configuración predeterminada de altavoces, micrófono y timbre; versi URI DE SIP; número de pantallas y detalles de cada pantalla; Estado y actividad.

![Vista detallada del portal de administración del sistema Lync Room](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Solución de problemas

La sección de solución de problemas se puede usar para recopilar registros de forma remota y guardarlos en una ubicación específica. También puede reiniciar la consola de SRS (interfaz de usuario de SRS) o reiniciar todo el sistema. Para recopilar registros, especifique una ruta de acceso a la carpeta en el formato especificado y asegúrese de que la carpeta tiene permisos de escritura en la cuenta del equipo SRS. Si el tamaño del registro es demasiado grande, puede tardar hasta 5 minutos en finalizar la recopilación de registros. La actualización de la página le dará el estado más reciente.

#### <a name="health"></a>Salud

La sección estado ofrece una indicación visual del estado de la conexión de Skype empresarial Server, el dispositivo de audio, el dispositivo de vídeo, el estado de resistencia y el dispositivo de pantalla.

![Portal de administración del sistema Lync Room Health Room](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Notas adicionales sobre el portal web administrativo

> [!NOTE]
>  Los cambios de configuración sólo se aplican después de reiniciar el sistema SRS. > si expira la contraseña de la cuenta LRSApp, no podrá ver el estado de las salas. Configure la contraseña de la cuenta LRSAppuser para que nunca expire o asegúrese de actualizar la contraseña cuando esté a punto de expirar. > el portal web administrativo de SRS solo es compatible con las implementaciones locales.

### <a name="bulk-management"></a>Administración en masa

La administración masiva de salones de SRS es una característica diseñada para los administradores de ti avanzados, para simplificar su flujo de trabajo y habilitarla con una herramienta conveniente para ahorrar tiempo para administrar de forma remota varios salones de manera masiva.

Para poder ver esta funcionalidad, el usuario debe estar aprovisionado como miembro del grupo de seguridad especial **LRSPowerUserAdminsGroup**.

No hay ningún límite en el número de salones de SRS que puede seleccionar para la administración en masa. Sin embargo, solo puede realizar una operación de administración en masa a la vez.

Para realizar una operación de administración en masa, seleccione las salas que quiera supervisar y haga clic en el menú Administración de masa.

### <a name="frequently-asked-questions"></a>Preguntas más frecuentes

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>¿Por qué no puedo iniciar sesión en el portal web administrativo?

Al abrir https://localhost/lrs, podrás ver la página de inicio de sesión, pero, cuando escribas tus credenciales, no podrás iniciar sesión. En este caso, debe abrir https://FQDNofFEserver/SRS para iniciar sesión en el portal web administrativo.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>¿Por qué no puedo ver SRS V1 en el portal web administrativo?

- Asegúrese de que tiene cuentas SRS en su implementación y de que se crean de acuerdo con las recomendaciones de implementación del portal web administrativo de SRS. Asegúrese de que las cuentas de SRS se aprovisionan con enable-CsMeetingRoom, no enable-CsUser, en Skype empresarial Server.

- Si ha creado cuentas de SRS y no puede ver las cuentas del portal web administrativo, recopile los registros del servidor mediante la herramienta de registro de Skype empresarial Server con el componente **MeetingPortal** seleccionado y, a continuación, envíelos al contacto de soporte técnico de SRS.

- Si ha creado cuentas de SRS y no puede ver las cuentas en el portal web administrativo, recopile los registros del cliente con Fiddler, copie el registro de la consola de las herramientas de desarrollo del explorador y, a continuación, envíelo al contacto de soporte técnico de SRS. También puede modificar el valor del nivel de seguimiento en el archivo Web. config para obtener un registro más detallado.

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>¿Por qué no veo el estado de SRS en el portal web administrativo?

- Asegúrese de que la cuenta de usuario de LRSApp esté habilitada para SIP.

- Si sigue teniendo problemas, recopile el archivo **Trace. log** en el sistema SRS desde D:\Tracing\LRSAdminLogs\, y, a continuación, envíelo al contacto de soporte técnico de SRS.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>¿Por qué no veo los menús de administración en masa para SRS en el portal web administrativo?

Asegúrese de que la cuenta de usuario de LRSApp está habilitada para SIP y de que forma parte del grupo de seguridad LRSPowerUserAdminsGroup.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>¿El portal web administrativo de SRS V1 funciona con salas de Microsoft Teams?

No.


