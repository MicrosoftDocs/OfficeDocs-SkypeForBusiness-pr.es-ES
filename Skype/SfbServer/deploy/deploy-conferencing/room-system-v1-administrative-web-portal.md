---
title: Implementar el portal web administrativo SRS V1 en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: El portal web administrativo de Skype empresarial Server V1 (SRS v1, anteriormente conocido como Lync Room System) es un portal web que las organizaciones pueden usar para mantener salas de conferencias de sistemas de salas de Skype. Los administradores pueden usar el portal web administrativo SRS V1 para supervisar el estado del dispositivo, por ejemplo, mediante la supervisión de los dispositivos de audio o vídeo. Con este portal, los administradores también pueden recopilar información de diagnóstico de forma remota para supervisar el estado de las salas de conferencias.
ms.openlocfilehash: 5ad4ffb08ecbc32feaa87aa2f7d48d82003e2e3e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307164"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Implementar el portal web administrativo SRS V1 en Skype empresarial Server

El portal web administrativo de Skype empresarial Server V1 (SRS v1, anteriormente conocido como Lync Room System) es un portal web que las organizaciones pueden usar para mantener salas de conferencias de sistemas de salas de Skype. Los administradores pueden usar el portal web administrativo SRS V1 para supervisar el estado del dispositivo, por ejemplo, mediante la supervisión de los dispositivos de audio o vídeo. Con este portal, los administradores también pueden recopilar información de diagnóstico de forma remota para supervisar el estado de las salas de conferencias.

Para usar esta característica, el portal web administrativo SRS V1 debe implementarse en todos los servidores front-end de Skype empresarial Server. Esta guía proporciona instrucciones para administradores sobre cómo instalar y configurar el portal web administrativo de SRS. Está destinada a los administradores que tienen conocimiento de la administración de Skype empresarial Server y que tienen derechos de usuario administrador para modificar la topología de Skype empresarial Server.

Después de implementar el portal web administrativo SRS V1 en el servidor, los administradores pueden comprobar los dispositivos de estado SRS v1 iniciando sesión en el sitio desde sus propios equipos o portátiles.

> [!IMPORTANT]
> Descargue el [portal de administración de Microsoft Skype Room Systems V1 para Skype empresarial Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).

En este tema:

- [Configurar el entorno para el portal web administrativo de SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Instalar el portal web administrativo de SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Usar el portal web administrativo de SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Configurar el entorno para el portal web administrativo de SRS v1
<a name="Config_Env"> </a>

Para usar el portal web administrativo de SRS v1, tendrá que instalar o configurar los siguientes requisitos previos.

> [!IMPORTANT]
> Si el servidor está configurado con la autenticación Kerberos y NTLM, y se está ejecutando SRS en un equipo que no está unido al dominio, la autenticación Kerberos generará un error y el usuario no verá el estado de SRS en el portal administrativo. Para resolver este problema, configure el servidor con autenticación NTLM o autenticación NTLM y TLS-DSK (sin Kerberos), o una el equipo SRS al dominio.

1. Instale las actualizaciones acumulativas de Skype empresarial Server en la topología de Skype empresarial Server.

    Para obtener la actualización o ver lo que incluye, consulte [actualizaciones para Skype empresarial Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

2. Cree un usuario de Active Directory habilitado para usar SIP.

    El portal web administrativo SRS v1 usa estas credenciales para consultar información de Skype empresarial Server. El nombre de usuario de los ejemplos es LRSApp.

3. Cree un grupo de seguridad de Active Directory con el nombre LRSSupportAdminGroup.

    Cree el grupo con el ámbito de grupo Global y el tipo de grupo Seguridad. Los usuarios habilitados para usar SIP que se agreguen a este grupo estarán autorizados para ver la lista de salones y ejecutar algunos comandos, como la recopilación de registros.

4. Cree un grupo de seguridad de Active Directory con el nombre LRSFullAccessAdminGroup. 

    Cree el grupo con el ámbito de grupo Global y el tipo de grupo Seguridad. Los usuarios habilitados para usar SIP que se agreguen a este grupo estarán autorizados para usar toda la funcionalidad del portal administrativo en una sala de Skype. Para incluir compatibilidad con la administración en masa de salas de Skype, consulte el paso 5. 

     ![Lista de grupos de administración con el rol de grupo de seguridad](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Cree un grupo de seguridad de Active Directory con el nombre LRSPowerUserAdminsGroup.

    Cree el grupo con el ámbito de grupo Global y el tipo de grupo Seguridad. Los usuarios habilitados para SIP que se agregan a este grupo tienen autorización para usar todas las funciones del portal de administración, incluida la administración masiva de salas de Skype para empresas.

6. Agregue LRSFullAccessAdminGroup como miembro de LRSSupportAdminGroup.

     ![Página de miembros de la propiedad LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Cree un usuario de Active Directory habilitado para usar SIP con el nombre LRSSupport. Agregue este usuario a LRSSupportAdminGroup.

     ![Página de miembros de la propiedad LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Instale [ASP.NET MVC 4 para Visual Studio 2010 SP1 y Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Instalar el portal web administrativo de SRS v1
<a name="Install_SRS"> </a>

Descargue el [portal de administración de Microsoft Skype Room Systems V1 para Skype empresarial Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).

Para instalar el portal web administrativo de SRS v1, use los pasos siguientes.

1. Configure el puerto de la aplicación de confianza ejecutando el siguiente cmdlet en el shell de administración de Skype empresarial Server:

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Para instalar el portal de salas de reuniones, descargue **MeetingRoomPortalInstaller.msi** y ejecútelo como administrador.

3. Abra el archivo Web.config, que se encuentra en la siguiente ubicación:

    %Archivos de programa%\Skype Empresarial Server 2015\Web Components\Meeting Room Portal\Int\Handler\

4. En el archivo Web. config, cambie PortalUserName por el nombre de usuario creado en el paso 2, en la sección "[configurar el entorno del portal web administrativo SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (el nombre recomendado en el paso es LRSApp):

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Dado que el portal administrativo de SRS v1 es una aplicación de confianza, no es necesario que proporcione la contraseña en la configuración del portal. Si este usuario utiliza un registrador diferente del local, deberá especificar el registrador que utilizará agregando la siguiente línea en el archivo Web.Config: 

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Si utiliza un puerto diferente de 5061, agregue la siguiente línea en el archivo Web.Config: 

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Verificar la instalación del portal web administrativo de SRS

Para verificar la instalación del portal web administrativo de SRS v1 haga lo siguiente:

1. En un servidor front-end, vaya a la siguiente URL:

    https://\<fe: servidor\>/LRS

    No debería ver ningún error, como se muestra en la imagen siguiente:

     ![Pantalla de inicio de sesión en el portal de administración del sistema Lync Room](../../media/LRS_AdminPortalSignIn.png)

2. Si no ve ningún error, intente acceder a la siguiente URL desde cualquier otro equipo de la topología:

    https://\<fe: servidor\>/LRS

    Para obtener acceso a la página, tendrá que agregar los registros DNS tal y como se describe en "[registros DNS necesarios para el inicio de sesión de cliente automático](https://go.microsoft.com/fwlink/p/?LinkId=318056)".

## <a name="use-the-srs-administrative-web-portal"></a>Usar el portal web administrativo de SRS
<a name="Use_Portal"> </a>

Después de implementar SRS en el servidor, puede comprobar el estado de todas las salas de SRS iniciando sesión en el portal web administrativo de SRS v1 desde un explorador.

### <a name="sign-in"></a>Iniciar sesión

1. Vaya a la siguiente dirección URL:

    https://\<fe: servidor\>/LRS

2. Escriba las credenciales de la cuenta LRSSupport o de una cuenta que se haya agregado a su grupo de seguridad LRSSupportAdminGroup.

![Pantalla de inicio de sesión en el portal de administración del sistema Lync Room](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Página de resumen del portal web administrativo de SRS

La página de resumen ofrece la siguiente información sobre todas las salas de SRS implementadas en el servidor:

- **Etiqueta** El nombre personalizado que el administrador da al salón. Para establecer la etiqueta en el portal, haga clic en el nombre de la sala.

- **Estado** El estado de mantenimiento de la sala, que se deriva del estado de mantenimiento acumulado de la sala, que se muestra en la sección estado de la página Configuración de la sala.

- **Reunión siguiente** La fecha y hora en la que se programa la próxima reunión.

- **Versión del SRS, fabricante, modelo** Estos valores están preestablecidos en SRS. Según el fabricante, estos campos pueden dejarse en blanco.

- **Última actualización** Muestra la última vez que se actualizó la Página Web.

![Vista resumida del portal de administración del sistema Lync Room](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Solo verá el menú de administración de almacenaje si forma parte del grupo de seguridad LRSPowerUserAdminsGroup.

### <a name="srs-room-information"></a>Información sobre salas de SRS

La sección de información sobre salas del portal le permite ver y configurar salas de SRS individuales. Contiene cuatro secciones: Configuración, Detalles, Registro y Mantenimiento.

#### <a name="settings"></a>Configuración

En la sección de configuración, puede establecer la contraseña, la etiqueta de la sala y los valores de volumen predeterminados de la sala. Si configura estas opciones, los cambios solo se replican al reiniciar la consola de SRS. Solo verá los ajustes Actualizaciones del sistema para dispositivos de SRS que utilicen la versión 15.12 y posteriores.

![Configuración de salones del portal de administración del sistema Lync Room](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Detalles

La sección de detalles proporciona un resumen de solo lectura de la configuración de la sala de SRS, que incluye la hora de la última actualización; reunión siguiente; últimas actualizaciones, mantenimiento y calibración; configuración predeterminada de timbre, micrófono y altavoz; versión URI DEL SIP; número de pantallas y detalles de cada pantalla; Estado y actividad.

![Vista en detalle del portal de administración del sistema Lync Room](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Solución de problemas

La sección de solución de problemas se puede usar para recopilar remotamente registros y guardarlos en una ubicación especificada. También puede reiniciar la consola de SRS (interfaz de usuario de SRS) o el sistema completo. Para recopilar registros, proporcione la ruta a una carpeta en el formato especificado y asegúrese de que la cuenta del equipo de SRS tiene permisos de escritura en esta carpeta. Si el tamaño de los registros es muy grande, la recopilación de registros puede tardar hasta 5 minutos. Actualice la página para ver el estado actualizado.

#### <a name="health"></a>Mantenimiento

La sección estado ofrece una indicación visual del estado de la conexión, el dispositivo de audio, el dispositivo de vídeo, el estado de resistencia y el dispositivo de pantalla de Skype empresarial Server.

![Estado de los salones del portal de administración del sistema Lync Room](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Notas adicionales sobre el portal web administrativo

> [!NOTE]
>  Los cambios de configuración solo se aplican después de que se reinicie el sistema SRS. > si la contraseña de la cuenta LRSApp expira, no podrá ver el estado de las salas. Configure la contraseña de la cuenta LRSAppuser para que nunca expire, o asegúrese de actualizar la contraseña cuando esté cerca de la fecha de expiración. > el portal web administrativo SRS solo es compatible con las implementaciones locales.

### <a name="bulk-management"></a>Administración en masa 

La administración en masa de salas de SRS es una característica diseñada para los administradores de TI avanzados, con la finalidad de simplificar su flujo de trabajo y ofrecerles una herramienta práctica y rápida para administrar remotamente varias salas de forma masiva.

Para ver esta característica, el usuario debe ser miembro del grupo de seguridad especial, **LRSPowerUserAdminsGroup**.  

No hay límite en el número de salas de SRS que se puede seleccionar para la administración en masa. Sin embargo, no se puede realizar más de una operación en masa a la vez.

Para realizar una operación de administración en masa, seleccione las salas que quiera supervisar y haga clic en el menú Administración de masa. 

### <a name="frequently-asked-questions"></a>Preguntas más frecuentes

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>¿Por qué no puedo iniciar sesión en el portal web administrativo?

Al abrir https://localhost/lrs, podrá ver la página de inicio de sesión pero, cuando escriba sus credenciales, no podrá iniciar sesión. En este caso, debe abrir https://FQDNofFEserver/SRS para iniciar sesión en el portal web administrativo.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>¿Por qué no puedo ver SRS V1 en el portal web administrativo?

- Asegúrese de que su implementación tiene cuentas de SRS y de que estas se han creado según las recomendaciones de implementación del portal web administrativo de SRS. Asegúrese de que las cuentas de SRS se aprovisionan mediante enable-CsMeetingRoom, not enable-CsUser, en Skype empresarial Server.

- Si ha creado cuentas de SRS y no puede ver las cuentas en el portal web administrativo, recopile los registros de servidor con la herramienta de registro de Skype empresarial Server con el componente **MeetingPortal** seleccionado y, a continuación, envíelos al contacto de soporte del SRS.

- Si ha creado cuentas de SRS y no las ve en el portal web administrativo, recopile los registros de cliente usando Fiddler, copie el registro de la consola de las herramientas de desarrollo del explorador y luego envíe esta información a su contacto de soporte técnico de SRS. También puede modificar el valor del nivel de seguimiento en el archivo Web.Config para obtener un registro más detallado.

  ```
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

- Asegúrese de que la cuenta de usuario LRSApp esté habilitada para SIP.

- Si sigue teniendo problemas, recopile el archivo **Trace. log** en el sistema SRS de D:\Tracing\LRSAdminLogs\, y, a continuación, envíelo a su contacto de soporte técnico de SRS.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>¿Por qué no puedo ver los menús de administración masiva para SRS en el portal web administrativo?

Asegúrese de que la cuenta de usuario LRSApp está habilitada para SIP y forma parte del grupo de seguridad LRSPowerUserAdminsGroup.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>¿Funciona el portal web administrativo SRS v1 con salas de Microsoft Teams?

No.


