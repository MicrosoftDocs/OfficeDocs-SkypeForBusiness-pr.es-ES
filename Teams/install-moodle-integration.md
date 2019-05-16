---
title: Instalar Moodle integración con Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 05/01/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Obtenga información sobre cómo instalar y configurar la aplicación de integración de Moodle para Microsoft Teams.
keywords: Complemento de integración de aplicación de los equipos Moodle
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto: Microsoft Teams
ms.openlocfilehash: 92259a9ef01232aaeca67089b5d654fe302f1224
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "34055371"
---
# <a name="install-moodle-integration-with-microsoft-teams"></a>Instalar Moodle integración con Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), el origen más popular y open del sistema de administración de aprendizaje (LMS) en el mundo, ahora se integra con Microsoft Teams! Esta integración ayuda a educadores y profesores colaboran alrededor de Moodle cursos, formular preguntas acerca de sus notas y asignaciones y mantengan actualizados con notificaciones--todos dentro de los equipos!

Para ayudar a los administradores de TI a configurar fácilmente esta integración, hemos actualizado nuestro complemento de Office 365 Moodle de código abierto con las siguientes capacidades:

- Registro automático de su servidor Moodle con Azure AD
- Implementación de un solo clic de su bot Moodle Ayudante en Azure
- Aprovisionamiento automático de los equipos y la sincronización automática de inscripción de equipo para todos los o seleccione Moodle cursos
- Instalación automática de la ficha Moodle y el robot Moodle asistente en cada equipo sincronizada (próximamente)
- Publicación de un solo clic de la aplicación Moodle en su almacén de aplicación de los equipos privados (próximamente)

## <a name="prerequisites"></a>Requisitos previos

Para instalar y configurar esta aplicación que necesitará:

- Credenciales de administrador de Moodle
- Credenciales de administrador de Azure AD
- Una suscripción a Azure que se pueden crear nuevos recursos en

## <a name="step-1-install-the-office-365-moodle-plugin"></a>Paso 1: Instalar el complemento de Office 365 Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

La integración de Moodle en Microsoft Teams funciona con el [complemento de Office 365 Moodle](https://github.com/Microsoft/o365-moodle)de código abierto. Para instalar el complemento en el servidor de Moodle:

1. Descargue el [complemento de Office 365 establece](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) y guárdelo en su equipo local. Debe utilizar la versión 3.5 o más reciente.
2. Inicie sesión en el servidor de Moodle como administrador y seleccione **administración de sitios** en el panel de navegación izquierdo.
3. Seleccione la ficha **complementos** y, a continuación, haga clic en **instalar complementos**.
4. Haga clic en el botón **Elegir un archivo** en la sección **Instalar complemento desde el archivo ZIP** .
5. Seleccione las opciones de **cargar un archivo** desde el panel de navegación izquierdo, busque el archivo descargado anteriormente y haga clic en **cargar este archivo**.
6. Seleccione la opción de **administración de sitios** en el panel de navegación izquierdo para volver al panel de administración. Desplácese hacia abajo hasta los **complementos Local** y haga clic en el vínculo de **Integración de Microsoft Office 365** . Mantenga abierto en una ficha independiente del explorador esta página de configuración: se usará con en el resto de este proceso.

Puede encontrar más información sobre cómo instalar complementos Moodle en la [documentación de Moodle](https://docs.moodle.org/34/en/Installing_plugins).

> [!IMPORTANT]
> Mantenga abierto en una ficha independiente del explorador la página de configuración de complemento de Office 365 Moodle: debe devolver para este conjunto de páginas a lo largo de este proceso.

¿Ya no tiene un sitio de Moodle? Es posible que desee desproteger nuestra Moodle en Azure [repo](https://github.com/azure/moodle) donde rápidamente puede implementar una instancia de Moodle en Azure y personalizar según sus necesidades.

## <a name="step-2-configure-the-connection-between-the-office-365-plugin-and-azure-active-directory"></a>Paso 2: Configurar la conexión entre el complemento de Office 365 y Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

A continuación que necesita registrar Moodle como una aplicación en Azure Active Directory (AD Azure). Adjuntamos una secuencia de comandos de PowerShell para ayudar a completar este proceso. La secuencia de comandos de PowerShell aprovisiona un Azure nueva aplicación de AD para el inquilino de Office 365, que se utilizará en el complemento de Office 365 Moodle. La secuencia de comandos va a aprovisionar la aplicación para el inquilino de Office 365, configurar todas las direcciones URL de respuesta y el permisos para la aplicación aprovisionado necesarios y devolver el AppID y la clave. Puede usar el AppID generado y la clave en la página del programa de instalación de complemento de O365 Moodle para configurar su servidor Moodle con Azure AD. Si desea ver los pasos manuales detallados que es la automatización de la secuencia de comandos de PowerShell, puede encontrarlos en la [documentación para el complemento](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)de completa.

1. En la página del complemento de integración con Microsoft Office 365, seleccione la ficha **programa de instalación** .
2. Haga clic en el botón **Descargar el PowerShell Script** y guardar la secuencia de comandos en el equipo local.
3. Debe preparar el script de PowerShell desde el archivo ZIP. Para hacer esto:
    1. Descargue y extraiga el archivo Moodle-AzureAD-Powershell.zip.
    2. Abra la carpeta extraída.
    3. Haga clic en el archivo Moodle-AzureAD-Script.ps1 y seleccione **Propiedades**.
    4. En la ficha **General** de la ventana Propiedades, active la casilla **desbloquear** junto al atributo de **seguridad** en la parte inferior.
    5. Haga clic en **Aceptar**.
    6. Copie la ruta de acceso del directorio de la carpeta extraída.
4. A continuación, podrá ejecutar PowerShell como administrador:
    1. Haga clic en Inicio.
    2. Tipo **PowerShell**.
    3. Haga clic en **Windows PowerShell**.
    4. Haga clic en **Ejecutar como administrador**.
5. Navegue hasta el directorio descomprimido escribiendo `cd ...\...\Moodle-AzureAD-Powershell` donde `...\...` es la ruta de acceso al directorio.
6. Ejecute el script de PowerShell:
    1. Escriba `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    2. Escriba `.\Moodle-AzureAD-Script.ps1`.
    3. Inicie sesión en su cuenta de administrador de O365 en la ventana emergente.
    4. Escriba el nombre de la aplicación de Azure AD (por ejemplo, el **complemento de Moodle/Moodle**).
    5. Escriba la dirección URL de su servidor Moodle.
    6. Copie el **Identificador de aplicación** y la **Clave de aplicación** generado por la secuencia de comandos y guardarlos.
7. A continuación necesitará agregar el identificador y la clave para el complemento de Office 365 Moodle. Volver a la página de administración del complemento (**administración de sitios** > **complementos** > **Integración con Microsoft Office 365**).
8. En la ficha **programa de instalación** , agregue el **Identificador de aplicación** y la **Clave de la aplicación** que copió anteriormente y, a continuación, haga clic en **Guardar cambios**.
9. Una vez la página se actualiza, debería ver una nueva sección denominada **Elegir método de conexión**. Haga clic en la casilla de verificación con la etiqueta **predeterminada**y, a continuación, haga clic en **Guardar los cambios**.
10. Una vez la página se actualiza, verá una nueva sección denominada **administración consentimiento de & obtener información adicional**.
    1. Haga clic en el vínculo de **Proporcionar administración da su consentimiento** , escriba sus credenciales de administrador Global de ventas3 regional 365 y, a continuación, haga clic en **Aceptar** para conceder los permisos.
    2. Junto al campo de **Azure AD inquilino** , haga clic en el botón **detectar** .
    3. Junto a **OneDrive para la dirección URL de negocio**, haga clic en el botón **detectar** .
    4. Una vez que rellenan los campos, haga clic en el botón **Guardar cambios** .
11. Haga clic en el botón **Actualizar** para comprobar la instalación y, a continuación, haga clic en **Guardar cambios**.
12. A continuación que necesitará para sincronizar usuarios entre el servidor de Moodle y Azure AD. Dependiendo de su entorno, puede seleccionar diferentes opciones durante esta etapa. Tenga en cuenta que la configuración que establezca aquí se ejecutará con cada cron Moodle ejecutar (normalmente, una vez al día) para mantener todo sincronizado. Para empezar:
    1. Cambiar a la **ficha de configuración de sincronización**.
    2. En la sección **sincronizar los usuarios con Azure AD** , seleccione las casillas de verificación que se aplican a su entorno. Normalmente, hay que seleccionar al menos:
        - **Crear cuentas en Moodle para los usuarios en Azure AD**
        - **Actualizar todas las cuentas en Moodle para los usuarios en Azure AD**
    3. En la sección **Restricción de creación de usuario** , puede configurar un filtro para limitar los usuarios de Azure AD que se sincronizará con Moodle.
    4. La sección **Asignación de campo de usuario** le permitirá personalizar Azure AD para asignación de campo de perfil de usuario de Moodle.
    5. En la sección **Sincronización de los equipos** puede elegir crear automáticamente grupos (es decir, los equipos) para algunos o todos los cursos Moodle existentes.
13. Para validar los trabajos cron (y ejecutarlos de forma manual si desea para el primer segmento), haga clic en el vínculo de la **página de administración de tareas programadas** en la sección **sincronizar los usuarios con Azure AD** . Esto le llevará a la página de **Tareas programadas** .
    1. Desplácese hacia abajo y busque el trabajo de **sincronización de los usuarios con Azure AD** de trabajo y haga clic en **Ejecutar ahora**.
    2. Si elige crear grupos basados en los cursos existentes, también puede ejecutar el trabajo de **crear grupos de usuarios en Office 365** .
14. Volver a la página de administración del complemento (**administración de sitios** > **complementos** > **Integración con Microsoft Office 365**) y seleccione la página de **Configuración de los equipos** . Debe configurar algunas opciones de seguridad para habilitar la integración de la aplicación de los equipos.
    1. Para habilitar OpenID conectarse, haga clic en el vínculo **Administrar la autenticación** y haga clic en el icono de ojo en la línea **OpenId conectarse** si se está atenuada.
    2. Para habilitar marco incrustación de objetos, haga clic en el vínculo de la **Seguridad de HTTP** y, a continuación, seleccione la casilla de verificación situada junto a **permitir incrustación de marco**.
    3. Habilitar los servicios web (que se va a habilitar las características de la API de Moodle). Haga clic en el vínculo de **Características avanzadas** y, a continuación, compruebe que está activada la casilla de verificación situada junto a **Habilitar los servicios web** .
    4. Habilitar los servicios externos para Office 365. Haga clic en el vínculo de **servicios externos** y a continuación:
        1. Haga clic en **Editar** en la fila **Moodle Office 365 Webservices** .
        2. Seleccione la casilla de verificación situada junto **activada**y, a continuación, haga clic en **Guardar cambios**
    5. Por último, debe editar los permisos de usuario autenticado para permitir a los usuarios crear tokens de servicio web. Haga clic en el vínculo de **usuario autenticado de función de edición** . Desplácese hacia abajo y busque la capacidad de **crear un token de servicio web** y Active la casilla de verificación **Permitir** .

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Paso 3: Implementar el robot Moodle Ayudante en Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

El robot de Ayudante Moodle gratuita para Microsoft Teams ayuda a los profesores y los alumnos responder a preguntas acerca de los cursos, asignaciones, remuneración y otra información en Moodle. El robot también envía Moodle notificaciones a los alumnos y profesores derecho dentro de los equipos. Este componente es un proyecto de código abierto mantenido por Microsoft y está [disponible en depósito](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
. En esta sección se van a implementar recursos a su suscripción de Azure y todos los recursos se configurarán con el nivel gratuito. Según el uso de su bot, debe escalar estos recursos. Si desea usar solo la ficha Moodle sin el robot, vaya al [paso 4](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Flujo de información de bot Moodle

Para instalar el robot, debe registrarlo en la [Plataforma de identidad de Microsoft](https://identity.microsoft.com/Landing). Esto permite su bot para autenticarse con los extremos de Microsoft. Para registrar su bot:

1. Volver a la página de administración del complemento (**administración de sitios** > **complementos** > **Integración con Microsoft Office 365**) y seleccione la ficha **Configuración de los equipos** .
2. Haga clic en el vínculo de **Portal de registro de aplicación de Microsoft** y el inicio de sesión con su Microsoft ID.
3. Escriba un nombre para la aplicación (por ejemplo, MoodleBot) y haga clic en el botón **crear** .
4. Copie el **Identificador de aplicación** y péguelo en el campo de **Identificador de aplicación de Bot** en la página **Configuración del equipo** .
5. Haga clic en el botón **Generar nueva contraseña** . Copie la contraseña generada y péguelo en el campo **Contraseña Bot de la aplicación** en la página **Configuración del equipo** .
6. Desplácese hasta la parte inferior del formulario y haga clic en **Guardar cambios**.

Ahora que ha generado el identificador de aplicación y la contraseña, es el momento de implementar su bot en Azure. Haga clic en el botón de **implementar en Azure** y completar el formulario con la información necesaria (el identificador de bot y la contraseña se encuentran en la página **Configuración del equipo** , y es la información de Azure en la página **el programa de instalación** ). Una vez que el formulario rellenado, haga clic en la casilla de verificación está de acuerdo con los términos y condiciones y, a continuación, haga clic en el botón de **compra** (todos los recursos de Azure se implementan en el nivel gratuito).

Después de que los recursos se complete la implementación en Azure, que necesitará para configurar el complemento de Office 365 Moodle con su extremo de mensajería. En primer lugar, necesitará obtener el extremo desde su bot en Azure. Para hacer esto:

1. Si no se ha iniciado sesión en ya, para iniciar sesión en el [portal de Azure](https://portal.azure.com).
2. En el panel izquierdo, seleccione **grupos de recursos**.
3. En la lista, seleccione el grupo de recursos sólo utilizar (o crea) durante la implementación de su componente.
4. Seleccione el recurso de **WebApp Bot** de la lista de recursos en el grupo.
5. Copie el **Extremo de mensajería** de la sección **información general** .
6. En Moodle, abra la página de **Configuración del equipo** de su complemento de Office 365 Moodle.
7. En el campo **Extremo Bot** , pegue la dirección URL que acaba de copiar y cambiar los *mensajes* de word a *webhook*. La dirección URL debe tener el siguiente aspecto: `https://botname.azurewebsites.net/api/webhook`.
8. Haga clic en **Guardar cambios**.
9. Una vez que se guardan los cambios, vuelva a la ficha de **Configuración del equipo** , haga clic en el botón de **archivo de manifiesto de descarga** y guardar el paquete de manifiesto en el equipo (se utilizará en el paso siguiente).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Paso 4: Implementación de la aplicación de los equipos de Microsoft

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Ahora que ha implementado el bot en Azure y lo ha configurado para comunicarse con su servidor Moodle, es momento de implementar la aplicación de Microsoft Teams. Para ello podrá cargar el archivo de manifiesto que descargó desde la página de **Configuración del equipo** del complemento de Office 365 Moodle en el paso anterior.

Antes de instalar la aplicación, debe asegurarse de que esté habilitado aplicaciones externas y sideloading de aplicaciones. Para ello, siga [estos pasos](https://docs.microsoft.com/en-us/MicrosoftTeams/admin-settings). Una vez que se ha asegurado de que estén habilitadas aplicaciones externas, siga estos pasos para implementar la aplicación.

1. Abra los equipos de Microsoft.
2. Haga clic en el icono de **almacén** en la inferior izquierda de la barra de navegación.
3. Haga clic en el vínculo **cargar una aplicación personalizada** de la lista de opciones. 
   > [!NOTE]
   > Si se haya iniciado sesión como administrador global, tendrá la opción de carga de la aplicación a la tienda de aplicaciones de la organización; en caso contrario, sólo podrá cargar la aplicación para los equipos es una parte de (*sideloading*).
4. Seleccione el paquete de manifest.zip que ha descargado anteriormente y haga clic en **Guardar**. Si aún no ha descargado el paquete de manifiesto, puede hacerlo desde la ficha de **Configuración del equipo** de la página de configuración del complemento en Moodle.

Ahora que tiene la aplicación instalada, puede agregar la ficha a cualquier canal que tienen acceso a. Para ello, navegue hasta el canal, haga clic en el **+** símbolo y seleccione la aplicación de la lista. Siga las indicaciones para terminar de agregar la ficha de curso Moodle a un canal.

¡Eso es todo! Usted y su equipo, ahora puede empezar a trabajar con los cursos Moodle directamente desde Microsoft Teams.

Para compartir las solicitudes de característica en contacto con nosotros o proporcionar comentarios, visite nuestra [página de voz del usuario](https://microsoftteams.uservoice.com/forums/916759-moodle).