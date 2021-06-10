---
title: Instalar la integración de Moodle con Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Obtenga más información sobre cómo instalar y configurar la aplicación del sistema de administración del aprendizaje de fuente abierta de Moodle (LMS) para Microsoft Teams.
keywords: Complemento de integración de aplicaciones de Teams Moodle
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d547d3c811f499faee5727634068a7807566293
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948716"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Instalación de la integración de Moodle con Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), el sistema de administración del aprendizaje (LMS) más popular y de fuente abierta que está disponible en todo el mundo, está ahora integrado con Microsoft Teams. Esta integración permite a los profesores y maestros colaborar en cursos Moodle, plantear preguntas sobre sus calificaciones y tareas, y mantenerlos actualizados con las notificaciones, directamente desde el equipo.

Para ayudar a los administradores de ti a configurar fácilmente esta integración, hemos actualizado nuestro complemento de Moodle de código abierto con las siguientes características:

* Registro automático de su servidor Moodle con Azure AD.
* Implementación con un clic de su bot de Moodle Assistant en Azure.
* Aprovisionamiento automático de equipos y sincronización automática de inscripciones de equipo para todos o seleccione cursos moodle.
* Instalación automática de la pestaña Moodle y el bot moodle Assistant en cada equipo sincronizado. (Próximamente)
* Publicación con un solo clic de la aplicación de Moodle en su tienda de aplicaciones de equipos privados. (Próximamente)

Para obtener más información sobre la funcionalidad que proporciona esta integración, vea Instalar la integración [de Moodle con Microsoft Teams](/microsoftteams/platform/resources/moodleinstructions).

## <a name="prerequisites"></a>Requisitos previos

Para instalar y configurar esta aplicación necesitará:

1. Credenciales de administrador de Moodle
2. Credenciales de administrador de Azure AD
3. Una suscripción de Azure puede crear recursos nuevos en

## <a name="step-1-install-the-moodle-plugin"></a>Paso 1: Instalar el complemento Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

La integración de Moodle en Microsoft Teams está impulsada por el [conjunto de complementos de Moodle](https://github.com/Microsoft/o365-moodle) de código abierto. Para instalar el complemento en el servidor Moodle:

1. En primer lugar, descargue el [conjunto de complementos de Moodle](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) y guárdelo en su equipo local. Tendrá que usar la versión 3,5 o posterior.
    * Al instalar el complemento local_o365, también se instalará el [auth_oidc](https://moodle.org/plugins/auth_oidc) y complementos [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams).
1. Inicie sesión en el servidor de Moodle como administrador y seleccione **Administración del sitio** en el panel de navegación izquierdo.
1. Seleccione la pestaña **complementos** y, después, haga clic en **instalar complementos**.
1. En la sección **Instalar complemento de archivo ZIP** haga clic en el botón **Elegir un archivo**.
1. Seleccione la **Upload de** un archivo en el panel de navegación izquierdo, busque el archivo que descargó anteriormente y haga clic Upload **este archivo.**
1. Seleccione la opción **Administración del sitio** en el panel de navegación izquierdo para volver al panel de administración. Desplácese hacia abajo hasta el **Complementos locales** y haga clic en el vínculo **Integración con Microsoft Office 365**. Mantenga esta página de configuración abierta en una pestaña del explorador independiente, ya que la usará durante el resto de este proceso.

Puede encontrar más información sobre cómo instalar complementos de Moodle en la [Documentación de Moodle](https://docs.moodle.org/34/en/Installing_plugins).

**Nota importante:** vaya a la página de configuración del complemento de Microsoft 365 u Office 365 Moodle abierta en una pestaña del explorador independiente, ya que regresará a este conjunto de páginas en todo este proceso.

*¿Todavía no tiene un sitio de Moodle?* Es posible que desee consultar nuestro [repositorio](https://github.com/azure/moodle) Moodle en Azure en el que puede implementar rápidamente una instancia de Moodle en Azure y personalizarla según sus necesidades.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>Paso 2: Configurar la conexión entre el complemento de Microsoft 365 u Office 365 y Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

A continuación, tendrá que registrarse en Moodle como una aplicación en Azure Active Directory. Hemos proporcionado un script de PowerShell para ayudarle a completar este proceso. El script de PowerShell proporciona una nueva aplicación de Azure AD para su organización de Microsoft 365 u Office 365, que será utilizada por el complemento de Moodle. El script aprovisionará la aplicación para su inquilino de Microsoft 365 u Office 365, configurará todas las URL de respuesta y los permisos necesarios para la aplicación aprovisionada y devolverá el AppID y la clave. Puede usar el AppID y la clave generadas en la página Configuración de complemento de Moodle para configurar el servidor de Moodle con Azure AD. Si desea ver los pasos manuales detallados que está automatizando el script de PowerShell, puede encontrarlos en la documentación completa de [para el complemento](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application).

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Pestaña Moodle del flujo de información de Microsoft Teams

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Ilustración de la pestaña Moodle para el flujo de información de Microsoft Teams" />

1. En la página de Microsoft 365 o el complemento de Office 365, seleccione la pestaña **Configuración**.
1. Haga clic en el botón **Descargar script de PowerShell** y guarde el archivo en el equipo local.
1. Tendrá que preparar el script de PowerShell desde el archivo ZIP. Para hacerlo:
    * Descargar y extraer el `Moodle-AzureAD-Powershell.zip`archivo
    * Abra la carpeta extraída.
    * Haga clic con el botón derecho en el `Moodle-AzureAD-Script.ps1`archivo y seleccione **Propiedades**.
    * En la pestaña **General** de la ventana Propiedades, active la `Unblock`casilla junto al atributo de **Seguridad** de la parte inferior.
    * Haga clic en **Aceptar**.
    * Copie la ruta de acceso al directorio de la carpeta extraída.
1. A continuación, ejecutará PowerShell como administrador:
    * Haga clic en Iniciar.
    * Escriba PowerShell.
    * Haga clic derecho en Windows PowerShell.
    * Haga clic en «Ejecutar como administrador».
1. Vaya al directorio descomprimido escribiendo `cd ...\...\Moodle-AzureAD-Powershell` donde `...\...` está la ruta de acceso al directorio.
1. Ejecute el script de PowerShell por medio de:
    * Enter`Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    * Enter`.\Moodle-AzureAD-Script.ps1`.
    * Inicie sesión en su cuenta de administrador de Microsoft 365 u Office 365 en la ventana emergente.
    * Escriba el nombre de la aplicación de Azure AD (ej. Complemento Moodle/Moodle).
    * Escriba la dirección URL de su servidor Moodle.
    * Copie el **ID. de la aplicación** y la **clave de aplicación** generada por el script y guárdelas.
1. A continuación, debe agregar el identificador y la clave al complemento Moodle. Vuelva a la página de administración del complemento (administración de sitios > Complementos > la integración de Microsoft 365).
1. En la pestaña **Configuración** agregue el **ID. de aplicación** y la **Clave de aplicación** copiada anteriormente y, a continuación, haga clic en **Guardar cambios**.
1. Una vez que se haya actualizado la página, debería ver una nueva sección **Elegir el método de conexión**. Haga clic en la casilla de verificación etiquetada **Predeterminada** y, después, haga clic en **Guardar los cambios**.
1. Una vez que se actualice la página, verá otra sección nueva **Consentimiento del administrador e información adicional**.
    * Haga clic en el vínculo **Proporcionar consentimiento de administración**, escriba sus credenciales de administrador global de Microsoft 365 u Office 365 y, a continuación, **Aceptar** para conceder los permisos.
    * Junto al campo **Espacio empresarial de Azure AD** haga clic en el botón **Detectar**.
    * Junto a la **URL de OneDrive para la Empresa** haga clic en el botón **Detectar**.
    * Cuando se rellenen los campos, haga clic en el botón **Guardar cambios**.
1. Haga clic en el botón **Actualizar** para comprobar la instalación y, a continuación, **Guardar los cambios**.
1. A continuación, deberá sincronizar los usuarios entre el servidor de Moodle y Azure Active Directory. Dependiendo de su entorno, puede seleccionar diferentes opciones durante esta fase. Tenga en cuenta que la configuración que defina aquí se ejecutará con cada Moodle, por lo general, una vez al día para mantenerlo todo sincronizado. Para empezar:
    * Cambiar a la **pestaña Configuración de sincronización**
    * En la sección **Sincronizar usuarios con Azure AD**, active las casillas de verificación correspondientes a su entorno. Por lo general, tendría que seleccionar como mínimo:
        * Crear cuentas en Moodle para usuarios en Azure AD
        * Actualizar todas las cuentas en Moodle para los usuarios en Azure AD
    * En la **sección Restricción de creación de** usuarios puede configurar un filtro para limitar los usuarios de Azure AD que se sincronizarán con Moodle.
    * La sección **Asignación de campos de usuario** le permite personalizar Azure AD para Moodle asignación de campos de Perfil de usuario.
    * En la sección **Sincronizar los equipos** puede elegir crear automáticamente grupos (por ejemplo, Teams) para algunos o todos los cursos de Moodle existentes.
1. Para validar los trabajos de cron (y ejecutarlos de forma manual si lo desea, para la primera ejecución), haga clic en la página **Administración de tareas programadas** en la sección **Sincronizar usuarios con Azure AD**. Esto le llevará a la página **Tareas programadas**.
    * Desplácese hacia abajo y busque el trabajo **Sincronizar los usuarios con Azure AD** y haga clic en **Ejecutar ahora**.
    * Si eligió crear grupos basándose en cursos existentes, también puede ejecutar el trabajo **Crear grupos de usuarios en Office 365**.
1. Vuelva a la página de administración de plug and Settings (administración de sitios > Complementos > la integración con Microsoft 365) y seleccione la página **Configuraciones de equipo**. Tendrá que configurar algunas opciones de seguridad para habilitar la integración de la aplicación equipos.
    * Para habilitar OpenID Connect, haga clic en el vínculo **Administrar la autenticación** y, después, haga clic en el icono de ojo de la línea de **OpenId Connect** si está atenuada.
    * A continuación, debe habilitar la incrustación de Marcos. Haga clic en el vínculo **Seguridad HTTP** y, después, haga clic en la casilla de verificación situada junto a **Permitir incrustar marco**.
    * El siguiente paso es habilitar los servicios web que habilitarán las características de la API Moodle. Haga clic en el vínculo **Características avanzadas** y, después, asegúrese de que la casilla de verificación situada junto a **Habilitar los servicios web** está activada.
    * Por último, tendrá que habilitar los servicios externos para Microsoft 365 o Office 365. Haga clic en el vínculo **Servicios externos** :
        * Haga clic en **Editar** en la fila **Moodle Webservices de Office 365**.
        * Marque la casilla de verificación situada junto a **Activada** y, a continuación, haga clic en **Guardar cambios.**
    * A continuación, tendrá que editar los permisos de usuario autenticados para permitirles crear tokens de servicio Web. Haga clic en el vínculo **Función de edición "usuario autenticado"**. Desplácese hacia abajo y busque la función **crear un token de servicio Web** y marque la casilla de verificación **Permitir**.

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Paso 3: implementar el bot Moodle Assistant en Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

El bot de Moodle Assistant gratuito para Microsoft Teams ayuda a los profesores y a los alumnos a responder a preguntas sobre sus cursos, tareas, calificaciones y demás información en Moodle. El bot también envía notificaciones Moodle a estudiantes y profesores directamente desde Teams. Este bot es un proyecto de origen abierto mantenido por Microsoft, y [está disponible en GitHub](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> En esta sección, va a implementar recursos en su suscripción de Azure y todos los recursos se configurarán con el nivel **gratuito**. Según el uso del bot, es posible que tenga que escalar estos recursos.
> Si solo quiere usar la pestaña Moodle sin el bot, vaya al [paso 4](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Flujo de información de bot Moodle

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Ilustración de Moodle bot para Microsoft Teams flujos de información" />


Para instalar el bot, en primer lugar debe registrarlo en la [Plataforma de identidad de Microsoft](https://identity.microsoft.com/Landing). Esto permite a los robots autenticarse en los puntos de conexión de Microsoft. Para registrar su aplicación:

1. Vuelva a la página de administración del complemento (administración de sitios > Complementos > la integración de Microsoft 365) y seleccione la pestaña **Configuración de Teams**.
1. Haga clic en el **Portal de registro de aplicaciones de Microsoft** vínculo e inicie sesión con su ID. de Microsoft.
1. Escriba un nombre para la aplicación (por ejemplo. MoodleBot) y haga clic en el botón **Crear**.
1. Copie el **Identificador de la aplicación** y péguela en el campo **ID. de aplicación de robots** en la página **Configuración del equipo**.
1. Haga clic en el botón **Generar nueva contraseña**. Copie la contraseña generada y péguela en el campo Contraseña de la aplicación **bot** en la **página De Configuración** equipo.
1. Desplácese hasta la parte inferior del formulario y haga clic en **Guardar cambios**.

Ahora que ha generado el identificador de la aplicación y la contraseña, es el momento de implementar el bot en Azure. Haga clic en el botón **Implementar en Azure** y rellene el formulario con la información necesaria (el ID. de aplicación de bot, la contraseña de la aplicación de Bot y el secreto de Moodle se encuentran en la página **Configuración de equipo** y la información de Azure se encuentra en la página **instalación**). Cuando haya rellenado el formulario, haga clic en la casilla de verificación para aceptar los términos y condiciones y, a continuación, haga clic en el botón **Comprar** (todos los recursos de Azure se implementan en el nivel gratuito).

Una vez que los recursos terminen de implementarse en Azure, deberá configurar el complemento Moodle con su punto de conexión de mensajería. En primer lugar, tendrá que obtener el extremo de su bot en Azure. Siga estos pasos:

1. Si aún no lo ha hecho, inicie sesión en el[Microsoft Azure Portal](https://portal.azure.com).
2. En el panel izquierdo, seleccione **Grupos de recursos**.
3. En la lista, seleccione el grupo de recursos que acaba de usar (o que creó) durante la implementación de su bot.
4. Seleccione el recurso **WebApp bot** de la lista de recursos en el grupo.
5. Copie el **Extremo de mensajería** de la sección **Información general**.
6. En Moodle, abra la página **Configuración de equipo** del complemento Moodle.
7. En el cuadro **Extremo del bot**, pegue la dirección URL que acaba de copiar y cambie la palabra *mensajes* a *webhook*. La dirección URL ahora tiene un aspecto similar al siguiente. `https://botname.azurewebsites.net/api/webhook`
8. Haga clic en **Guardar cambios**.
9. Una vez que haya guardado los cambios, vuelva a la pestaña **Configuración de equipo**, haga clic en el botón de **Archivo de manifiesto de descarga** y guarde el paquete de manifiesto en el equipo (lo usará en la sección siguiente).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Paso 4: implementar la aplicación de Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Ahora que ya ha implementado el bot en Azure y está configurado para hablar con el servidor Moodle, es el momento de implementar la aplicación de Microsoft Teams. Para hacerlo, debe cargar el archivo de manifiesto que ha descargado desde la página Configuración del equipo de complementos de Moodle en el paso anterior.

Antes de poder instalar la aplicación, debe asegurarse de que las aplicaciones externas y la instalación de prueba de aplicaciones estén habilitadas. Para realizar esta acción, puede seguir [estos pasos](./admin-settings.md). Cuando haya asegurado de que las aplicaciones externas estén habilitadas, puede seguir los pasos que se indican a continuación para implementar la aplicación.

1. Abra Microsoft Teams.
2. Haga clic en **el icono** Tienda en la parte inferior izquierda de la barra de navegación.
3. Haga clic en el vínculo **Cargar una aplicación personalizada** de la lista de opciones. *Nota:* si ha iniciado sesión como administrador global, tiene la opción de cargar la aplicación en la tienda de aplicaciones de su organización, de lo contrario, solo podrá cargar la aplicación de los equipos de los que forme parte ("transferencia local").
4. Seleccione el `manifest.zip`paquete que ha descargado previamente y haga clic en **Guardar**. Si aún no ha descargado el paquete del manifiesto, puede hacerlo desde la pestaña **Configuración del equipo** de la página Configuración del complemento en Moodle.

Ahora que ya tiene instalada la aplicación, puede Agregar la pestaña a cualquier canal al que tenga acceso. Para hacerlo, vaya al canal y haga clic en el **+** símbolo y seleccione la aplicación en la lista. Siga las indicaciones para terminar de agregar la ficha del curso Moodle a un canal.

¡Y eso es todo! Usted y su equipo ahora pueden empezar a trabajar con sus cursos de Moodle directamente desde Microsoft Teams.

Para compartir todas las solicitudes de características o comentarios con nosotros, visite nuestra [Página voz de usuario](https://microsoftteams.uservoice.com/forums/916759-moodle).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]