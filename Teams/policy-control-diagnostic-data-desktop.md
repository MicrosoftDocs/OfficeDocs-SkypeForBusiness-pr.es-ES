---
title: Datos de diagnóstico de cliente de escritorio necesarios para Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Una lista de propiedades de escritorio y eventos para los controles de directiva para Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbac20caa3f1eff0ead7ef0bf7f11d55b7718903
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136116"
---
# <a name="required-desktop-diagnostic-data-for-microsoft-teams"></a>Datos de diagnóstico de escritorio necesarios para Microsoft Teams

El artículo siguiente contiene una lista de eventos de Microsoft Teams para escritorio, y listas de propiedades que recopila cada evento.

## <a name="events"></a>Eventos

> [!NOTE]
> Existen propiedades comunes para todos los eventos que se muestran a continuación. Para poder revisarlas, consulte [Propiedades que se envían con todos los eventos](#properties-sent-with-all-events).

### <a name="logging"></a>Registro

> [!NOTE]
> Para obtener información sobre las propiedades de los eventos de registro, consulte[propiedades que se envían con los eventos de registro](#properties-sent-with-logging-events).

- **adal-anonymous-mac.ts:this.logger.logError**: registra que se ha producido un error genérico de SSO al iniciar sesión de forma anónima en un dispositivo Mac.
- **adalAnonymousUtil.ts:loggingService.getInstance**: graba el registro de declaraciones de error acerca de que la aplicación no pudo iniciar la autenticación de usuario anónimo.
- **adal-anonymous-windows.ts:this.logger.logError**: registra que se ha producido un error SSO genérico al iniciar sesión de manera anónima en un dispositivo Windows.
- **adalBase.ts:this.loggingService.logError**: registra información necesaria para determinar si el perfil de usuario es nulo o está vacío.
- **adal-impl-mac.ts:this.loggingService.logError**: registra que se ha producido un problema al analizar la telemetría recibida durante la autenticación o el error SSO genérico al intentar iniciar sesión en un dispositivo Mac.
- **adal-rigel-windows.ts:this.logger.logError**: declaración de registro general que indica que se ha producido un error genérico de SSO al iniciar sesión en el dispositivo de la sala de reuniones.
- **adal-sso-windows.ts:this.loggingService.logError**: registra que se ha producido un error genérico de SSO al iniciar sesión en un dispositivo Windows, errores al iniciar el servicio de chat, o la información de error de registro.
- **appOnlineService.ts:loggingService.getInstance**: registra que se ha producido un error debido a una configuración que no se pudo analizar durante el inicio, o con la descarga de la autenticación de preusuario, configuración autorizada de manera previa.
- **appStart.ts:loggingService.logError**: registra que se ha producido un error al no poder iniciarse la aplicación, error de espacio en disco, error de certificado válido o error al buscar el certificado correcto; y reiniciar la aplicación.
- **browserWindowHttp.ts:this.loggingService.logError**: registra información para indicar que la aplicación no se pudo actualizar debido a problemas con el sistema de archivos.
- **contextInstallService.ts:loggingService.getInstance**: registra la aparición de un error cuando:
  - se intenta analizar o leer un archivo, o resolver una dirección URL crítica para la característica de instalación contextual.
  - la función de acortar una dirección URL intenta ejecutar la característica de instalación contextual.
- **crashManager.ts:loggingService.logError**: registra información para determinar la causa de un error cuando se bloquea la aplicación.
- **localStorageService.ts:loggingService.getInstance**: registra la aparición de un error cuando los datos de arranque básicos no se cargan de forma correcta para ejecutar la aplicación.
- **logProviders\pageDumpProvider.ts:loggingService.getInstance**: registra la información de error cuando la aplicación se bloquea.
- **multiWindowManager.ts:this.logError**: registra la aparición de un error cuando los datos de arranque básicos no se cargan de forma correcta para ejecutar la aplicación.
- **nativeElectronNotifications\osNotificationService.ts:this.loggingService.logError**: este evento registra la aparición de un error al intentar enviar una notificación sobre un error.
- **OutlookMeetingAddinHelper.ts:loggingService.getInstance**: registra la aparición de un error al intentar conectarse a una reunión con el complemento de reunión de Outlook.
- **recoveryManager.ts:loggingService.getInstance**: registra la aparición de un error durante la desinstalación de la actualización.
- **renderer\startPage\startPage.ts:this.logger.logError**: registra la aparición de un error en la página de inicio de la aplicación.
- **settingsService.ts:loggingService.getInstance**: registra la aparición de un error en la configuración de la aplicación.
- **updateInfo.ts:loggingService.getInstance**: registra la aparición de un error en la transmisión de actualizaciones.
- **updatenotification.js:this._loggingService.logError**: registra la aparición de problemas de espacio en disco.
- **utility.ts:loggingService.logError**: registra un error al acceder a un archivo local (un archivo de la aplicación).
- **utility.ts:loggingService.getInstance**: registra un error en el espacio en disco disponible, problemas de visualización, problemas de URL, problemas de cookies, protocolos, o problemas de clave de registro en el equipo para cargar la aplicación.
- **windowmanager.js:this._loggingService.logError**: registra la aparición de problemas con las cookies, de pantalla en blanco, con la comunicación entre el escritorio y el shell, de URL, errores de carga de mensajes de página, de renderización de procesos, y los problemas de conectividad de red.
- **windowmanager.js:loggingService.getInstance**: registra información para indicar cuándo no se puede mostrar la ventana de recuperación.

### <a name="outlook-addin"></a>Complemento de Outlook

> [!NOTE]
> Para obtener información sobre las propiedades de los eventos del complemento de Outlook, consulte[Propiedades que se envían con los eventos del complemento de Outlook](#properties-sent-with-outlook-addin-events).

- **joinmeetingoperation**: registra la información necesaria para unir a un usuario a una reunión.
- **meetingaddinapplifecycle**: registra la información sobre el estado de la aplicación, como el inicio o la salida.
- **meetingaddinloadtime**: registra el tiempo que demora cargar información de la reunión de Outlook.
- **openmeetingoperation**: registra la información necesaria para abrir una reunión programada.
- **savemeetingoperation**: registra la información necesaria para guardar la reunión mientras se la programa.

### <a name="scenario"></a>Escenario

> [!NOTE]
> Para obtener información sobre las propiedades de los eventos de escenario, consulte[propiedades que se envían con los eventos de escenario](#properties-sent-with-scenario-events).

- **desktop_app_load**: registra la información necesaria para determinar que se ha iniciado la aplicación de escritorio, que el servicio se debe inicializar, y que se puede inicializar.
- **desktop_app_not_ready**: registra la información necesaria para determinar que la aplicación de escritorio no está preparada para funcionar.
- **desktop_install**: registra la información necesaria para determinar que la aplicación de escritorio se ha instalado de manera correcta, o si se ha producido un error durante la instalación.
- **desktop_previous_lifecycle_invalid**: registra la información necesaria para determinar que la aplicación de escritorio se reinició después de haber estado activa de manera previa y que, después, se bloqueó.

### <a name="tracking"></a>Seguimiento

> [!NOTE]
> Para obtener información sobre las propiedades de los eventos de seguimiento, consulte[Propiedades que se envían con los eventos de seguimiento](#properties-sent-with-tracking-events).

- **deeplink_scenario_missing**: se inició Teams desde un vínculo profundo, pero la telemetría o el diagnóstico no está presente.
- **desktop_app_initialized**: registra la información necesaria para determinar si la aplicación se inició de forma correcta cuando se inicializa la aplicación de escritorio.
- **desktop_app_quit_exception**: se ha bloqueado la aplicación mientras se intentaba cerrar.
- **desktop_blankScreenDetected**: registra la información necesaria para determinar los errores cuando la aplicación de escritorio muestra una pantalla en blanco.
- **desktop_blankScreenDetectedAfterRepaint**: se detectó que la página se puso en blanco al detectar el intento de renderización.
- **desktop_blankScreenRecoveredAfterRepaint**: se recuperó de un problema de renderización en el que la pantalla no se renderizó de manera previa.
- **desktop_configuration_failed_to_save**: recopila la información necesaria para determinar los errores de configuración cuando la configuración del escritorio no se guarda.
- **desktop_navigation_error_recovery**: recopila la información necesaria para determinar los errores de navegación de escritorio cuando una página no se carga después de cinco intentos.
- **desktop_previous_gpu_crashed**: registra la información necesaria para determinar los errores de la unidad de procesamiento gráfico cuando el escritorio se bloquea.
- **desktop_previous_plugin_host_crashed**: recopila la información necesaria para determinar los problemas de la pila de medios asociados con los bloqueos de aplicaciones de escritorio.
- **desktop_recovery_cleared_user_data**: registra el bloqueo de la aplicación en varias ocasiones, y que la aplicación tuvo que borrar la memoria caché local para recuperarse.
- **desktop_settings_blank_on_load**: este es un error que indica que las opciones de configuración de las aplicaciones no están presentes.
- **desktop_settings_failed_to_load**: recopila la información necesaria para determinar la causa cuando no se puede cargar la configuración del escritorio.
- **desktop_silent_restart**: la actualización del cliente se ha escalonado, y el cliente se ha actualizado sin interrumpir al usuario.
- **desktop_terminated**: registra la información necesaria para determinar si la comunicación entre procesos se ha desconectado cuando el usuario cierra la aplicación de escritorio.
- **desktop_uncaught_exception**: llamada de función en un objeto no definido. Se producirá un error o el reinicio de la aplicación.
- **desktop_write_storage_failed**: registra la información necesaria para determinar los errores de disco cuando la aplicación de escritorio no puede escribir en el almacenamiento.
- **registration_failed**: registra la información necesaria para resolver errores de registro de complementos.
- **registration_success**: registra la información necesaria para determinar si existen registros de complementos, en caso de que se hayan realizado de manera correcta.
- **security_unsupported_ipc_channel**: el mensaje entre procesos que no se permitió era un mensaje de llegada.
- **sfb_running_not_connected**: detectó que la aplicación de Skype Empresarial no está en ejecución.
- **sfb_not_running**: registra que el tiempo de espera de respuesta a la llamada a Skype Empresarial finalizó.
- **sfb_never_replied**: no se registra ninguna respuesta de la API durante el seguimiento al comunicarse con Skype Empresarial.
- **server_error_hit**: realiza un seguimiento de un error de las tuberías IPC que se comunican con Skype Empresarial.
- **unexpected_sfb_ipc_disconnection**: registra la información necesaria para determinar si se ha producido un error en la conexión al servicio.
- **unregister_failed**: registra la información necesaria para determinar errores al anular el registro del complemento de la reunión de Outlook.

## <a name="userbi-panelaction"></a>UserBI panelaction

> [!NOTE]
> Para obtener información sobre las propiedades de los eventos UserBI panelaction, consulte[Propiedades que se envían con los eventos UserBI panelaction](#properties-sent-with-userbi-panelaction-events).

- **inlinereply**: registra la información acerca de si un usuario respondió desde la notificación.
- **toastclick**: registra el clic que hace un usuario para desplazarse hacia la entrada del mensaje a las notificaciones del sistema para supervisar el SLA del servicio y cargar la respuesta adecuada a la notificación del sistema.
- **toastdismiss**: registra la información necesaria para determinar errores y retrasos cuando el usuario descarta la renderización de una notificación del sistema.

- **toast_skip**: registra la información necesaria para evitar que se transmita una notificación del sistema con demora.
- **toasttimeout**: registra la información necesaria para determinar los errores y retrasos cuando se ha agotado el tiempo de espera de la renderización de una notificación del sistema.

### <a name="userbi-panelview"></a>UserBI panelview

> [!NOTE]
> Para obtener información sobre las propiedades de los eventos UserBI panelview, consulte[Propiedades que se envían con los eventos UserBI panelview](#properties-sent-with-userbi-panelview-events).

- **toastshow**: registra la información necesaria para determinar si se presentó una notificación del sistema.

## <a name="property-lists"></a>Listas de propiedades

### <a name="properties-sent-with-all-events"></a>Propiedades enviadas con todos los eventos

| Nombre de la propiedad                              | Descripción                                                        |
|--------------------------------------------|--------------------------------------------------------------------|
| EventInfo_Time                             | Hora de generación del evento:                                              |
| EventInfo_Name                             | Nombre del evento: se usa para diferenciar entre los tipos de evento             |
| EventInfo_BaseType/name                    | Nombre del evento: se usa para diferenciar entre los tipos de evento en un evento |
| EventInfo_Sequence                         | Secuencia del evento                                              |
| userAgent                                  | Cadena del agente del explorador                                               |
| userpdclevel                               | Configuración de control de datos de privacidad del usuario                           |
| eventpdclevel                              | Nivel de categorización del control de datos de privacidad del evento             |
| AppInfo_Language                           | Idioma de la aplicación                                                       |
| clientType/AppInfo_ClientType              | Tipo de cliente en el que se ejecuta la aplicación                               |
| environment/AppInfo_Environment            | El entorno de ingeniería que atendió la solicitud del usuario               |
| clientVersion/appversion/AppInfo_Version/desktopBuildVersion | Versión de la aplicación                               |
| buildtime                                  | Marca de tiempo de la creación de la aplicación en sistemas de ingeniería            |
| osversion/DeviceInfo_OsVersion             | Versión del sistema operativo                                                         |
| AppInfo_ProcessArchitecture                | Arquitectura del sistema (32 bits o 64 bits)                                  |
| preferredLocales                           | configuración regional preferida para el usuario                                      |
| locale/AppInfo_Locale                      | Configuración regional de la aplicación                                                         |
| os/DeviceInfo_OsName                       | Nombre del sistema operativo                                                            |
| UserInfo_Language                          | Idioma del usuario seleccionado                                             |
| UserInfo_Id                                | Id. de usuario                                                            |
| UserInfo_TenantId/TenantId                 | Id. del espacio empresarial                                                          |
| ring/UserInfo_Ring                         | Un concepto que le permite ofrecer la aplicación de forma escalonada          |
| región                                     | Región del centro de datos que atiende la solicitud del usuario                       |
| UserInfo_ConfigIds/UserInfo_Etag           | Id.que le ayuda a identificar a los usuarios de diferentes experimentos e implementaciones     |
| DeviceInfo_BrowserName                     | Nombre del explorador                                                       |
| DeviceInfo_BrowserVersion                  | Versión del explorador                                                    |
| DeviceInfo_Id/machineId/DeviceInfo_IdV2    | Id. que le ayuda a identificar el dispositivo                                  |
| totalMemory                                | Memoria de hardware del dispositivo                                      |
| núcleos                                      | Núcleos de hardware del dispositivo                                       |
| cpuspeed                                   | Velocidad del hardware CPU del dispositivo                                   |
| DeviceInfo_CpuArchitecture/cpuarchitecture | Arquitectura CPU del dispositivo                                     |
| UserRole                                   | Ayuda a identificar el rol del usuario en un espacio empresarial                               |
| DeviceInfo_WindowsMode                     | Ayuda a identificar el modo de seguridad de Windows                               |
| desktopSession/Session_Id                  | Ayuda a identificar una sesión                                           |
| dbOpen                                     | Captura el estado de la base de datos local                               |
| UserInfo_Upn                               | Un valor hash unilateral de un identificador de usuario                                  |

### <a name="properties-sent-with-logging-events"></a>Propiedades enviadas con los eventos de registro

| Nombre de la propiedad         | Descripción                                                        |
|-----------------------|--------------------------------------------------------------------|
| message               | Captura un mensaje detallado sobre el registro                          |

### <a name="properties-sent-with-scenario-events"></a>Propiedades enviadas con los eventos de escenario

| Nombre de la propiedad                     | Descripción                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------|
| Scenario_Status                   | Estado de un escenario                                                               |
| Scenario_Step                     | Paso en un escenario                                                                 |
| sequence                          | Número de secuencia del escenario                                                    |
| delta                             | El tiempo necesario para completar diferentes pasos de un escenario                               |
| elapsed                           | Tiempo transcurrido desde que se inició el escenario                                                    |
| escenario                          | Identificar un escenario de forma exclusiva                                                       |
| Scenario_Name                     | Nombre del escenario                                                               |
| errorInfo                         | Información del error que puede haberse producido durante un escenario                       |
| session                           | Id. de sesión único                                                                  |
| freeMemory                        | Captura la memoria libre disponible                                                     |
| processMemory                     | Captura la memoria del proceso                                                            |
| scenarioDelta                     | Captura un tiempo diferente entre dos pasos del escenario                                   |
| Session_DesktopId                 | Id. de sesión único                                                                  |
| machineLocked                     | Captura si el equipo se bloqueó o no                                          |
| windowIsVisible                   | Captura si la ventana de la aplicación fue visible para el uso                                      |
| appStates/webAppStates            | registra una lista de estados de la aplicación por los que ha pasado la aplicación. Esto ayuda con la investigación acerca del bloqueo, ya que podemos ver cuál era el estado de la aplicación |
| crashDesktopSession               | Captura el Id. de la sesión bloqueada                                                 |
| appRuntime                        | Captura el tiempo de ejecución de la aplicación                                                        |
| diagnosticEvents                  | Últimos 50 eventos de diagnóstico de la aplicación web antes del bloqueo de la aplicación                                 |
| activities                        | Últimos 50 nombres de escenario de usuario que ocurrieron antes del bloqueo                            |
| crashSession                      | Captura el Id. de la sesión bloqueada                                                 |
| crashId                           | Captura el Id. de la sesión bloqueada                                                 |
| isPreviousLifecycleValid          | Si las aplicaciones anteriores se inicializaron completamente y finalizaron de forma correcta             |
| isSettingValid                    | Si la configuración de autenticación previa es válida                                                 |
| rollbackReason                    | Motivo por el que se revirtió la aplicación                                            |
| deeplinkType                      | Tipo de vínculo profundo                                                               |
| watchdogCrash                     | Si se bloqueó la aplicación debido a un colapso                                                    |
| protocols                         | Protocolo usado para iniciar la aplicación                                                    |
| electronBuild                     | Versión de compilación de la aplicación de electrones                                                      |
| distribution                      |  Si Teams se instaló a través de exe, msi, dmg o pkg, etc.                    |
| updateTimeOfDay                   | Hora en la que se actualizó la aplicación                                                           |
| launchPath                        | Si Teams está instalado en %LOCALAPPDATA%, %PROGRAMFILES%, u otras ubicaciones   |
| loggedIn                          | Si el usuario había iniciado sesión                                                          |
| envType/complianceEnvironmentType | Nube comercial o privada (por ejemplo, DoD, GCC-High, etc.).                              |
| cpuusage                          | Uso de CPU                                                                          |
| installationSource                | Tipo de instalación que el usuario tiene                                                      |
| adalVersion                       | Versión de la biblioteca de autenticación                                                        |
| asyncStart                        | Si la aplicación usa un inicio sincrónico o asíncrono                                 |
| attempts                          | Número de intentos de comprobación en línea para el usuario antes de que se muestre una pantalla de bloqueo |

### <a name="properties-sent-with-tracking-events"></a>Propiedades enviadas con los eventos de seguimiento

| Nombre de la propiedad                      | Descripción                                                                      |
|------------------------------------|----------------------------------------------------------------------------------|
| name2                              | Captura el nombre del evento de seguimiento                                              |
| numVisibleNotifications            | Número de notificaciones de aplicación visibles                                      |
| giphyEnabled                       | Si se habilitó el servicio giphy                                                |
| error                              | Captura detalles de error relacionados con el evento de seguimiento                             |
| method                             | Método de protocolo GET o POST                                                      |
| channel                            | Captura el canal de comunicación entre procesos dentro de la aplicación                      |
| windowTitle                        | Tipo de ventana de visualización asociada con el evento                                     |
| message                            | El tipo de mensaje de error                                                        |
| crashSession/crashDesktopSession/crashId/Session_DesktopId/Session_DesktopBackgroundId | Captura un Id. único para propósitos de depuración de sesión |
| responseCode                       | Captura el código de respuesta de la llamada de servicio.                                      |
| errorUrl                           | La dirección URL que no se pudo cargar                                                      |
| errorCode                          | Captura el código de error                                                              |
| ssoEventData                       | Estado y estado de autenticación                                                  |
| correlationId                      | Identificador para correlacionar los eventos con el lado del servicio para fines de depuración                      |
| errorDescription                   | Captura la descripción del errorcode (código de error)                                            |
| source                             | Método para obtener la aplicación Teams y el tipo de paquete desde el que se instaló Teams       |
| windowIsDestroyed                  | Estado "true" o "false" de la aplicación Windows durante el evento                             |
| windowIsFocused                    | Estado "true" o "false" de la aplicación Windows durante el evento                             |
| windowIsVisible                    | Si la aplicación estuvo visible cuando ocurrió el evento                                  |
| windowIsMinimized                  | Estado "true" o "false" de la aplicación Windows durante el evento                             |
| windowIsMaximized                  | Estado "true" o "false" de la aplicación Windows durante el evento                             |
| windowIsFullscreen                 | Estado "true" o "false" de la aplicación Windows durante el evento                             |
| distSrc                            | Captura el origen de distribución del ingreso del usuario en la aplicación.                    |
| retries                            | Número de reintentos al intentar conectarse a un punto de conexión                            |
| uses_slimcore                      | "True" o "false" si la llamada web está utilizando slimcore                                      |
| persistCookieExpiresIn             | Tiempo restante en la validez de la cookie de la aplicación web                             |
| tenantName                         | Nombre del espacio empresarial del usuario de la aplicación                                       |
| appStartReason                     | Cómo se inició la sesión de la aplicación, como si la inició el usuario, después de la actualización, etc. |
| machineLocked                      | Si se ha bloqueado o no un equipo durante el evento                        |
| data                               | Captura los datos técnicos para la investigación del escenario                               |
| appRuntime                         | Captura el tiempo de ejecución de la aplicación                                                      |
| activities                         | Últimos 50 nombres de escenario de usuario que ocurrieron antes del bloqueo                          |
| timeSinceActivity                  | Tiempo transcurrido desde la última actividad del usuario                                                    |
| appStates                          | Registra una lista de estados de la aplicación por los que pasó la aplicación de escritorio, lo que sirve para las investigaciones sobre bloqueos, ya que muestra cuál era el estado de la aplicación de escritorio |
| timeSinceAppState                  | Tiempo transcurrido desde que el estado de la aplicación cambió                                                 |
| webAppStates                       | Registra una lista de estados de la aplicación por los que pasó el cliente web, lo que sirve para las investigaciones sobre bloqueos, ya que muestra cuál era el estado de la aplicación de escritorio |
| timeSinceWebAppState               | Tiempo transcurrido desde que el estado de la aplicación web cambió                                             |
| diagnosticEvents                   | Últimos 50 eventos de diagnóstico de la aplicación web antes del bloqueo de la aplicación                               |
| timeSinceLastDiagnosticEvent       | Tiempo transcurrido desde la última vez que se envió el evento de diagnóstico                                            |
| timeSinceSecondLastDiagnosticEvent | Tiempo transcurrido desde la penúltima vez que se envió el evento de diagnóstico                                     |
| appInitialized                     | Si la aplicación web se ha iniciado                                               |
| targetVersion                      | Versión de la aplicación a la cual se actualizará                                    |
| port                               | Número de puerto de mensaje de Internet                                                     |
| originalUrl                        | Ubicación original de la página que se está procesando                                         |
| deeplinkId                         | GUID para el tipo de destino del vínculo de Teams                                          |
| appSessionEnd                      | Si el evento se ha producido al final de la sesión de la aplicación                             |
| eventData                          | Captura el estado del equipo y la configuración de la aplicación para ayudar a la depuración en caso de problemas        |
| deeplinkType                       | Tipo de vínculo profundo (chat, reunión, canal)                                    |
| previousUpdateUrl                  | Ubicación desde la que la aplicación recuperó por última vez su actualización                        |
| previousUpdateVersion              | Última versión a la que se actualizó la aplicación                                          |
| previousUpdateTime                 | Cuándo se actualizaron por última vez los archivos binarios de la aplicación                                      |
| protocol                           | Tipo de controlador para el vínculo, como archivo o como imagen                                     |
| files                              | Tipo de archivo asociado con un evento, como la caché de aplicación o la caché del GPU    |
| Perf_WorkingSetSizeKB              | Tamaño del caché de la memoria                                                             |
| isTimeboxingWebAppInitialize       | Si se inicializó la aplicación antes de que se agote el tiempo del cuadro                          |
| isExp                              | Si la versión de la aplicación en uso forma parte de un experimento                          |
| deviceType                         | Captura el tipo de dispositivo                                                      |
| sanitizedErr                       | Captura una versión saneada de la información del error                              |
| rigelVersion                       | Captura la versión del dispositivo rigel                                                 |
| DeviceInfo_OsSku                   | Captura la información de SKU del sistema operativo                                                      |
| isLoggedOut                        | Captura si el usuario ha cerrado la sesión                                               |
| complianceEnvironmentType          | Nube comercial o privada (por ejemplo, DoD, GCC-High, etc.).                           |
| restartTimes                       | Horas exactas de reinicios anteriores                                                 |
| Skype_ResultCode                   | Captura el resultado de la comunicación entre operaciones entre Skype y Teams                 |
| cpumodel                           | Captura un modelo de CPU                                                            |
| isSlimCoreRunningOutproc           | Si se está ejecutando el componente Slimcore en su propio proceso                         |
| isSlimCoreStartedAsync             | Tipo de lanzamiento de la pila de audio o vídeo (A/V) interna                               |
| networkState                       | Captura el estado de la red                                                    |
| desktopBuildAge                    | Antigüedad de la compilación de la aplicación al momento del evento                                   |
| vdiMode                            | Captura si la aplicación se está ejecutando en modo VDI                                       |

### <a name="properties-sent-with-userbi-panelview-events"></a>Propiedades enviadas con eventos UserBI PanelView

| Propiedad           | Description                                              |
|--------------------|----------------------------------------------------------|
| Panel_Uri          | Uri del panel entregado al usuario                   |
| Panel_Type         | Tipo de panel al que accedió el usuario                          |
| Team_Id            | Id. del equipo en el que el usuario ha realizado la acción |
| Thread_Id          | Id.del hilo al que obtuvo acceso el usuario               |
| Panel_PreviousUri  | URI del panel anterior                                |
| Panel_Region       | Región donde se hospeda el panel en la aplicación             |
| Panel_LaunchMethod | Método a través del cual se inició el panel              |
| Panel_PreviousType | Tipo de panel anterior                               |
| Thread_Type        | Tipo de hilo al que tuvo acceso el usuario                          |
| Panel_LaunchSource | Información de origen del panel que se inició        |
| Tab_Type           | Tipo de ventana a la que tuvo acceso el usuario                         |
| Team_Type          | Tipo de equipo al que accedió el usuario                            |

### <a name="properties-sent-with-userbi-panelaction-events"></a>Propiedades enviadas con eventos UserBI panelaction

| Nombre de la propiedad         | Descripción                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | Uri del recurso al que tiene acceso la acción del usuario                  |
| Panel_Uri             | Uri del panel entregado al usuario                             |
| Action_Gesture        | Tipo de gesto que realiza el usuario en la aplicación                       |
| Action_ScenarioType   | Agrupación de características que está relacionada con la métrica empresarial de la característica       |
| Panel_Type            | Tipo de panel al que accedió el usuario                                    |
| Action_Outcome        | Resultado de la acción que realizó el usuario                            |
| Team_Id               | Id. del equipo en el que el usuario ha realizado la acción           |
| Module_Type           | Tipo de módulo que ha alojado la acción del usuario                        |
| Module_Name           | Nombre de módulo que ha alojado la acción del usuario                        |
| Module_Summary        | Resumen del módulo que ha alojado la acción del usuario                       |
| Thread_Id             | Id.del hilo al que obtuvo acceso el usuario                         |
| Panel_PreviousUri     | URI del panel anterior                                          |
| Panel_Region          | Región donde se hospeda el panel en la aplicación                       |
| Panel_LaunchMethod    | Método a través del cual se inició el panel                        |
| Panel_PreviousType    | Tipo de panel anterior                                         |
| Thread_Type           | Tipo de hilo al que tuvo acceso el usuario                                    |
| Module_State          | Estado del módulo al que tiene acceso el usuario                               |
| Action_Scenario       | Característica en un grupo de características que está relacionada con la métrica empresarial |
| Panel_LaunchSource    | Información de origen del panel que se inició                  |
| Tab_Type              | Tipo de ventana a la que tuvo acceso el usuario                                   |
| Team_Type             | Tipo de equipo al que accedió el usuario                                      |

### <a name="properties-sent-with-outlook-addin-events"></a>Propiedades enviadas con los eventos del complemento de Outlook

| Nombre de la propiedad                   | Descripción                                                              |
|---------------------------------|--------------------------------------------------------------------------|
| AccountComparisonFailedReason   | El complemento compara la cuenta con la cuenta de Teams para ver si se permite la creación. Este evento se envía si se produce un error en la comparación |
| AccountComparisonSuccessful     | El complemento compara la cuenta con la cuenta de Teams para ver si se permite la creación. Este evento se envía si la comparación se realiza de forma correcta |
| AdalVersion                     | Versión de la biblioteca de autenticación usada                               |
| AddinBitness                    | Versión del complemento                                                         |
| AddinLanguage                   | Lenguaje de las cadenas de complemento usado                                     |
| AggregatorSetupCompletedTime    | Tiempo de configuración para el cargador del complemento                                              |
| AppDomainCreatedTime            | Hora en la que el cargador del complemento inicia el dominio de aplicación                            |
| AppointmentDisplayTime          | Hora en la que se mostró el elemento de cita durante la creación de la reunión |
| AuthenticationCompletedTime     | Hora en la que se proporcionó la autenticación para una solicitud determinada            |
| ConnectionMode                  | Indica el modo de conexión de la cuenta de Exchange principal del usuario     |
| ConnectionStartedTime           | Hora en la que Outlook llama a OnConnection                                     |
| ErrorDetails                    | Captura detalles del error                                            |
| ErrorName                       | Captura el nombre del error.                                               |
| ExchangeVersion                 | Captura la versión de Exchange                                             |
| IsSmtpFormatError               | Error en la dirección SMTP                                                    |
| IsTeamsRunning                  | Captura si existe un proceso de Teams en ejecución                             |
| IsTeamsUserLoggedOut            | Captura si el usuario ha cerrado la sesión en Teams                              |
| LanguageSetupCompletedTime      | Hora en la que finalizó la configuración del idioma                               |
| ManagedConnectTime              | Hora en la que el complemento administrado ha recibido la respuesta de conexión               |
| ManagedOnStartupTime            | Hora en la que se dio el inicio                                    |
| MTFetchCompleted                | Hora de finalización de la solicitud de las opciones de reunión de MT                        |
| NetFrameworkVersion             | marco de .NET usado                                                      |
| NetworkAvailable                | Si la red está disponible                                                     |
| OperationStartTime              |  Hora en la que comenzaron distintas operaciones                                  |
| OsBitness                       | Bits del sistema operativo                                                            |
| OutlookLanguage                 | Captura el idioma de la aplicación Outlook                                     |
| OutlookVersion                  | Captura la versión de la aplicación Outlook                                          |
| OwnerResolutionTime             | Hora para resolver el propietario de la reunión                                        |
| ParseResponseCompletedTime      | Hora al analizar la respuesta completada                                  |
| RecipientResolutionError        | Detalles del error al solucionar un destinatario                                 |
| RecipientsResolutionTime        | Tiempo total para resolver todos los destinatarios                                     |
| RehydrateCompletedTime          | Hora en la que las propiedades se leen desde Outlook                               |
| SaveToOutlookCompletedTime      | Hora en la que las propiedades se guardan desde Outlook                                |
| ServiceRequestStartTime         | Hora de inicio de la solicitud de servicio                                        |
| ServiceResponseReceiveTime      | Hora de respuesta del servicio                                        |
| SettingsInitializeCompletedTime | Hora de inicio de la configuración                                           |
| SetupLoggingCompletedTime       | Hora de configuración del registro                                             |
| ShutdownBeginTime               | Hora de comienzo del apagado del complemento                                       |
| ShutdownCompletedTime           | Hora de finalización del apagado                                             |
| StartupBeginTime                | Hora de comienzo del inicio del complemento                                        |
| StartupCompletedTime            | Hora de finalización del inicio                                              |
| TeamsDeployment                 | Implementación del cliente de Teams (Dev, Prod)                                   |
| TeamsRing                       | Anillo del usuario actual conectado al cliente de Teams                            |
| TeamsVersion                    | Captura la versión de la aplicación Teams                                            |
| TelemetrySetupCompletedTime     | Hora de finalización de la configuración de telemetría                                   |
| UpnMismatch                     | Si no existe una coincidencia UPN entre Outlook y Teams                  |
| UserDomain                      | Dominio del usuario                                                       |
| ViewUpdatedTime                 | Hora en la que se actualizó la vista                                           |
