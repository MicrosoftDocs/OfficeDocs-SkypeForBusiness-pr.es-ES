---
title: Implementar el portal web administrativo de SRS v1 en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: El portal web administrativo de Sistemas de salas de Skype Empresarial Server v1 (SRS v1, anteriormente conocido como Sistema de salas de Lync) es un portal web que las organizaciones pueden usar para mantener sus salas de conferencias de Sistemas de salas de Skype. Los administradores pueden usar el portal web administrativo de SRS v1 para supervisar el estado del dispositivo, por ejemplo mediante la supervisión de dispositivos de audio y vídeo. Con este portal, los administradores pueden recopilar de forma remota información de diagnóstico para supervisar el estado de la sala de conferencias.
ms.openlocfilehash: 7d7bef99149d09ebf72c9b633370f262e535b23f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804540"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Implementar el portal web administrativo de SRS v1 en Skype Empresarial Server

El portal web administrativo de Sistemas de salas de Skype Empresarial Server v1 (SRS v1, anteriormente conocido como Sistema de salas de Lync) es un portal web que las organizaciones pueden usar para mantener sus salas de conferencias de Sistemas de salas de Skype. Los administradores pueden usar el portal web administrativo de SRS v1 para supervisar el estado del dispositivo, por ejemplo mediante la supervisión de dispositivos de audio y vídeo. Con este portal, los administradores pueden recopilar de forma remota información de diagnóstico para supervisar el estado de la sala de conferencias.

Para usar esta característica, el portal web administrativo de SRS v1 debe implementarse en cada servidor front-end de Skype Empresarial Server. En esta guía se proporcionan instrucciones para los administradores sobre cómo instalar y configurar el Portal web administrativo de SRS. Está pensado para administradores que tienen conocimientos de administración de Skype Empresarial Server y que tienen derechos de usuario de administrador para modificar la topología de Skype Empresarial Server.

Después de implementar el portal web administrativo de SRS v1 en el servidor, los administradores pueden comprobar el estado de los dispositivos SRS v1 iniciando sesión en el sitio desde sus propios equipos o portátiles.

> [!IMPORTANT]
> Descargue el portal web administrativo de [Microsoft Skype Room Systems v1 para Skype Empresarial Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)

En este tema:

- [Configurar el entorno para el portal web administrativo de SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Instalar el portal web administrativo de SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Usar el portal web administrativo de SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Configurar el entorno para el portal web administrativo de SRS v1
<a name="Config_Env"> </a>

Para usar el portal web administrativo de SRS v1, deberá instalar o configurar los siguientes requisitos previos.

> [!IMPORTANT]
> Si el servidor está configurado con la autenticación Kerberos y NTLM, y SRS se ejecuta en un equipo que no está unido al dominio, se producirá un error en la autenticación Kerberos y el usuario no verá el estado de SRS en el portal administrativo. Para resolver este problema, configure el servidor con autenticación NTLM o autenticación NTLM y TLS-DSK (sin Kerberos) o una el equipo SRS al dominio.

1. Instale las actualizaciones acumulativas de Skype Empresarial Server en la topología de Skype Empresarial Server.

    Para obtener la actualización o ver lo que incluye, consulte Actualizaciones [de Skype Empresarial Server 2015.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)

2. Cree un usuario de Active Directory habilitado para SIP.

    El portal web administrativo de SRS v1 usa estas credenciales para consultar información de Skype Empresarial Server. El nombre de usuario de los ejemplos especificados es LRSApp.

3. Cree un grupo de seguridad de Active Directory con el nombre LRSSupportAdminGroup.

    Cree el grupo con el ámbito de grupo global y el tipo de grupo como seguridad. Los usuarios habilitados para SIP que se agregan a este grupo estarán autorizados a ver la lista de salas y ejecutar determinados comandos, como la recopilación de registros.

4. Cree un grupo de seguridad de Active Directory con el nombre LRSFullAccessAdminGroup.

    Cree el grupo con ámbito de grupo global y tipo de grupo como usuarios habilitados para Security.SIP que se agregan a este grupo están autorizados a usar todas las funciones del portal de administración en una sola sala de Skype. Para incluir compatibilidad para la administración masiva de salas de Skype, consulte el paso 5.

     ![Lista de grupos de administradores con rol de grupo de seguridad](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Cree un grupo de seguridad de Active Directory con el nombre LRSPowerUserAdminsGroup.

    Cree el grupo con el ámbito de grupo global y el tipo de grupo como seguridad. Los usuarios habilitados para SIP que se agregan a este grupo están autorizados a usar todas las funciones del portal de administración, incluida la administración masiva de salas de Skype Empresarial.

6. Agregue LRSFullAccessAdminGroup como miembro de LRSSupportAdminGroup.

     ![Página de miembros de propiedades LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Cree un usuario de Active Directory habilitado para SIP con el nombre LRSSupport. Agregue este usuario a LRSSupportAdminGroup.

     ![Página de miembros de propiedades LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Instale [ASP.NET MVC 4 para Visual Studio 2010 SP1 y Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Instalar el portal web administrativo de SRS v1
<a name="Install_SRS"> </a>

Descargue el portal web administrativo de [Microsoft Skype Room Systems v1 para Skype Empresarial Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)

Para instalar el portal web administrativo de SRS v1, siga estos pasos.

1. Configure el puerto de aplicación de confianza ejecutando el siguiente cmdlet en el Shell de administración de Skype Empresarial Server:

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Para instalar el Portal de salas de reuniones, **MeetingRoomPortalInstaller.msi** y, a continuación, ejecutarlo como administrador.

3. Abra el Web.config archivo desde la siguiente ubicación:

    %Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\

4. En el archivo Web.Config, cambie portalUserName por el nombre de usuario creado en el paso 2 en la sección " Configurar el entorno para el portal web administrativo de[SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (el nombre recomendado en el paso es LRSApp):

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Dado que el Portal de administración de SRS v1 es una aplicación de confianza, no es necesario proporcionar la contraseña en la configuración del portal. Si este usuario usa un registrador diferente al registrador local, debe especificar el registrador para él agregando la siguiente línea en el archivo Web.Config local:

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Si el puerto usado es distinto de 5061, agregue la siguiente línea en el Web.Config archivo:

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Comprobar la instalación del portal web administrativo de SRS

Para comprobar la instalación del portal web administrativo de SRS v1, haga lo siguiente:

1. En un servidor front-end, vaya a la siguiente dirección URL:

    https:// \<fe-server\> /lrs

    No debería ver ningún error, como se muestra en la siguiente imagen:

     ![Pantalla de inicio de sesión del Portal de administración del sistema Lync Room](../../media/LRS_AdminPortalSignIn.png)

2. Si no ve ningún error, intente obtener acceso a la siguiente dirección URL desde cualquier otro equipo de la topología:

    https:// \<fe-server\> /lrs

    Para obtener acceso a la página, deberá agregar los registros DNS tal como se describe en "Registros DNS necesarios para el inicio de sesión automático[del cliente".](https://go.microsoft.com/fwlink/p/?LinkId=318056)

## <a name="use-the-srs-administrative-web-portal"></a>Usar el portal web administrativo de SRS
<a name="Use_Portal"> </a>

Después de implementar SRS en el servidor, puede comprobar el estado de todas las salas de SRS iniciando sesión en el portal web administrativo de SRS v1 desde un explorador.

### <a name="sign-in"></a>Iniciar sesión

1. Vaya a la siguiente dirección URL:

    https:// \<fe-server\> /lrs

2. Escriba las credenciales de la cuenta LRSSupport o una cuenta que se agregó al grupo de seguridad LRSSupportAdminGroup.

![Pantalla de inicio de sesión del Portal de administración del sistema Lync Room](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Página de resumen del portal web administrativo de SRS

La página de resumen proporciona la siguiente información para todas las salas de SRS implementadas en el servidor:

- **Tag** El nombre personalizado que el administrador da a la sala. La etiqueta se puede establecer en el portal haciendo clic en el nombre de la sala.

- **Estado** El estado de mantenimiento de la sala, que se deriva del estado de mantenimiento agregado de la sala, que se muestra en la sección Estado de la página Configuración de la sala.

- **Próxima reunión** Fecha y hora en que se programa la siguiente reunión.

- **Versión de SRS, fabricante, modelo** Estos valores están preestablecidos en SRS. Según el fabricante, es posible que estos campos se dejaron en blanco.

- **Última actualización** Muestra la última vez que se actualizó la página web.

![Vista de resumen del Portal de administración del sistema de Lync Room](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Solo verá el menú Administración masiva si forma parte del grupo de seguridad LRSPowerUserAdminsGroup.

### <a name="srs-room-information"></a>Información de la sala de SRS

La sección Información de la sala del portal le permite ver y configurar salas SRS individuales. Contiene cuatro secciones: Configuración, Detalles, Registro y Estado.

#### <a name="settings"></a>Configuración

En la sección Configuración, puedes establecer la contraseña, la etiqueta de la sala y los niveles de volumen predeterminados para la sala. Si configura estas opciones, los cambios solo se replicarán después de reiniciar la consola de SRS. Solo verá la configuración de actualizaciones del sistema para dispositivos SRS con la versión 15.12 y posteriores.

![Configuración de la sala del portal de administración del sistema Lync Room](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Detalles

La sección Detalles proporciona un resumen de solo lectura de la configuración de la sala de SRS, incluido: la hora de la última actualización; siguiente reunión; últimas actualizaciones, mantenimiento y calibración; configuración predeterminada del altavoz, micrófono y sonido; versión; URI de SIP; número de pantallas y detalles sobre cada pantalla; estado y actividad.

![Vista de detalles del Portal de administración del sistema de Lync Room](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Solución de problemas

La sección de solución de problemas se puede usar para recopilar registros de forma remota y guardarlos en una ubicación especificada. También puede reiniciar la consola de SRS (interfaz de usuario de SRS) o reiniciar todo el sistema. Para recopilar registros, proporcione una ruta de acceso de carpeta en el formato especificado y asegúrese de que la carpeta tenga permisos de escritura concedidos a la cuenta del equipo SRS. Si el tamaño del registro es demasiado grande, puede tardar hasta 5 minutos en finalizar la recopilación de registros. La actualización de la página le dará el estado más reciente.

#### <a name="health"></a>Salud

La sección Estado proporciona una indicación visual del estado de la conexión de Skype Empresarial Server, el dispositivo de audio, el dispositivo de vídeo, el estado de resistencia y el dispositivo de pantalla.

![Lync Room System Admin Portal Room Health](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Notas adicionales sobre el portal web administrativo

> [!NOTE]
>  Los cambios de configuración solo se aplican después de reiniciar el sistema SRS.> Si la contraseña de la cuenta LRSApp expira, no podrá ver el estado de las salas. Configure la contraseña de la cuenta LRSAppuser para que nunca expire o asegúrese de actualizar la contraseña cuando esté a punto de expirar.> El portal web administrativo de SRS solo es compatible con implementaciones locales.

### <a name="bulk-management"></a>Administración masiva

La administración masiva de salas de SRS es una característica diseñada para administradores avanzados de TI, para simplificar su flujo de trabajo y habilitarlas con una cómoda herramienta de ahorro de tiempo para administrar de forma remota varias salas de forma masiva.

Para poder ver esta funcionalidad, es necesario aprovisionar al usuario como miembro del grupo de seguridad especial **LRSPowerUserAdminsGroup**.

No hay ningún límite en el número de salas de SRS que puede seleccionar para la administración masiva. Sin embargo, solo puede realizar una operación de administración masiva a la vez.

Para realizar una operación de administración masiva, seleccione las salas que desea supervisar y haga clic en el menú Administración masiva.

### <a name="frequently-asked-questions"></a>Preguntas más frecuentes

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>¿Por qué no puedo iniciar sesión en el portal web administrativo?

Al abrir, podrá ver la página de inicio de sesión, pero cuando escriba sus credenciales, no https://localhost/lrs podrá iniciar sesión. En este caso, debe abrir para https://FQDNofFEserver/SRS iniciar sesión en el portal web administrativo.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>¿Por qué no puedo ver SRS v1 en el portal web administrativo?

- Asegúrese de que tiene cuentas srs en la implementación y de que se crean de acuerdo con las recomendaciones de implementación del Portal web administrativo de SRS. Asegúrese de que las cuentas de SRS se aprovisionan mediante Enable-CsMeetingRoom, no Enable-CsUser, en Skype Empresarial Server.

- Si ha creado cuentas de SRS y no puede ver las cuentas en el portal web administrativo, recopile los registros del servidor mediante la herramienta de registro de Skype Empresarial Server con el componente **MeetingPortal** seleccionado y envíelas al contacto de soporte técnico de SRS.

- Si ha creado cuentas srs y no puede ver las cuentas en el portal web administrativo, recopile los registros de cliente con Fiddler, copie también el registro de consola desde las herramientas de desarrollo del explorador y, a continuación, envíelas al contacto de soporte técnico de SRS. También puede modificar el valor del nivel de seguimiento en el Web.config para obtener un registro más detallado.

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>¿Por qué no puedo ver el estado de SRS en el portal web administrativo?

- Asegúrese de que la cuenta de usuario LRSApp está habilitada para SIP.

- Si sigue teniendo problemas, recopile el archivo **Trace.log** en el sistema SRS de D:\Tracing\LRSAdminLogs y envíelo al contacto de soporte técnico \, de SRS.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>¿Por qué no puedo ver los menús de administración masiva de SRS en el portal web administrativo?

Asegúrese de que la cuenta de usuario LRSApp está habilitada para SIP y forma parte del grupo de seguridad LRSPowerUserAdminsGroup.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>¿El portal web administrativo de SRS v1 funciona con salas de Microsoft Teams?

No.


