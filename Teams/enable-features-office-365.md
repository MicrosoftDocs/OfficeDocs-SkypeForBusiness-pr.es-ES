---
title: "Habilitar características de Microsoft Teams en su organización de Office 365 | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Conozca todas las características de Microsoft Teams que puede habilitar en su organización de Office 365, incluidos la configuración en todo el inquilino, la integración del correo electrónico, las aplicaciones, el almacenamiento en nube y mucho más."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7c626acc5e9fe4d19d7198ea023df155ff427f40
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2017
---
<a name="enable-microsoft-teams-features-in-your-office-365-organization"></a>Habilitar características de Microsoft Teams en su organización de Office 365
======================================================

Microsoft Teams tiene varios parámetros de configuración que se pueden habilitar o deshabilitar a nivel de inquilino. Con Teams habilitado para el inquilino, cualquier usuario que esté también habilitado para Teams heredará la configuración desde el nivel de inquilino.

A continuación puede ver una lista de características que un administrador de Office 365 puede elegir para habilitar o deshabilitar en Teams.

A menos que se indique lo contrario, el valor predeterminado para una opción es Activado.

> [!NOTE]
> Un administrador de Office 365 puede desactivar Microsoft Teams en cualquier momento mediante el Centro de administración de Office 365. Tenga en cuenta que los usuarios con licencias activas de Microsoft Teams seguirán viendo el icono de la aplicación Teams, aunque lo desactive. Para ver información detallada sobre cómo quitar licencias de los usuarios, consulte [Gestionar acceso de los usuarios a Microsoft Teams](user-access.md). En cuanto Teams se deshabilita, el acceso desde su cliente se bloquea, pero los datos que estén disponibles a través de otros clientes y servicios, como SharePoint o OneDrive, seguirán estando disponibles. Todos los datos continuarán en su lugar, a menos que los equipos se eliminen explícitamente.

<a name="tenant-wide-settings"></a>Configuración de todos los inquilinos 
---------------------

En **Configuración de todos los inquilinos** puede activar o desactivar las opciones que se encuentran en General, Integración de correo electrónico, Aplicaciones y Almacenamiento en nube personalizado.

### <a name="general"></a>General

La sección General le permite establecer la siguiente configuración para su organización.

> ![Captura de pantalla de la sección General en la configuración para todos los inquilinos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   **Mostrar el organigrama en el perfil personal:** Cuando esta configuración esté habilitada, se mostrará el organigrama en la tarjeta de contacto del usuario. Cuando se haga clic en ella, mostrará el organigrama detallado.

    ![Captura de pantalla del icono de organigrama en la tarjeta de contacto de un usuario.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![Captura de pantalla de un organigrama.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-   **Usar Skype Empresarial para los destinatarios que no tengan Microsoft Teams:** Cuando esta configuración esté habilitada, se permitirá a los usuarios de Microsoft Teams ponerse en contacto con otros usuarios en la organización que no tengan permiso para Microsoft Teams mediante Skype Empresarial.

-   **Permitir mensajes de ayuda proactivos de T-bot:** Cuando esta configuración esté habilitada, T-bot iniciará una sesión de chat privado con los usuarios para guiarlos en el uso de Microsoft Teams.

    ![Captura de pantalla de la sección T-Bot en la interfaz de Microsoft Teams.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a>Integración del correo electrónico
-----------------

Active esta característica para que los usuarios puedan enviar un correo electrónico a un canal en Microsoft Teams mediante la dirección de correo electrónico del canal. Los usuarios pueden hacer esto para cualquier canal que pertenezca a un equipo que sea de su posesión. Los usuarios también pueden enviar correos electrónicos a cualquier canal de un equipo que tenga conectores habilitados para los miembros del equipo. Aunque un usuario no tenga permiso para crear una dirección de correo electrónico del canal, si alguien que sí tiene permiso crea esa dirección, podrá acceder a ella desde el menú \<icono de más\> de ese canal.

La integración del correo electrónico le permite establecer la siguiente configuración para su organización.

   ![Captura de pantalla de la sección de integración del correo electrónico en la configuración para todos los inquilinos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image5.png)

-   **Permitir que los usuarios puedan enviar correo electrónico a los canales:** Cuando está habilitado, los enlaces de correo electrónico se habilitarán también y los usuarios podrán publicar mensajes a un canal enviando un correo electrónico a la dirección de correo electrónico del canal de Microsoft Teams.

> Para buscar la dirección de correo electrónico de un canal, haga clic en **Más opciones** junto al nombre del canal y después seleccione **Obtener dirección de correo electrónico**.

-   **Lista de remitentes restringidos:** Los dominios de los remitentes se pueden restringir aún más para garantizar que solo los dominios SMTP permitidos puedan enviar correos electrónicos a los canales de Microsoft Teams.

<a name="apps"></a>Aplicaciones
----

Las aplicaciones en Microsoft Teams son una forma genial de integrar las herramientas y los servicios que son importantes para su equipo directamente en un canal o chat.

La sección **Aplicaciones** le permite establecer la siguiente configuración para su organización:

![Captura de pantalla de la sección Aplicaciones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

-   **Permitir aplicaciones externas en Microsoft Teams:** Cuando esté habilitado, los usuarios podrán agregar fichas y bots que estén disponibles al inquilino de Office 365.
![Captura de pantalla del control para permitir aplicaciones externas en la sección Aplicaciones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

-   **Permitir la instalación de prueba de aplicaciones externas:** cuando esté habilitado, los usuarios podrán instalar y habilitar bots y fichas personalizados.

<a name="custom-cloud-storage"></a>Almacenamiento en nube personalizado
--------------------

Las opciones de almacenamiento en nube en Microsoft Teams actualmente incluyen Box, Dropbox, Google Drive y ShareFile. Los usuarios pueden cargar y compartir archivos de los servicios de almacenamiento en nube en los canales y chats de Microsoft Teams. Pulse o haga clic en el botón de alternancia que hay al lado de los proveedores de almacenamiento en nube que quiera usar su organización.

![Captura de pantalla de la sección de almacenamiento en nube personalizado.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a>Configuración de usuario por licencia
------------------------

En **Configuración de usuario por licencia**, puede activar o desactivar las opciones que se encuentran en Equipos y canales, Llamadas y reuniones, y Mensajes.

<a name="teams-and-channels"></a>Equipos y canales
------------------

El equipo está diseñado para reunir un grupo de personas que trabajan juntos para conseguir completar sus funciones. Los equipos pueden ser dinámicos para el trabajo basado en proyectos (por ejemplo, iniciar un producto o crear un centro de operaciones digital). Los equipos también pueden ser continuos para reflejar la estructura interna de la organización.

Como administrador, puede administrar propietarios y miembros de equipos mediante el panel Grupos del portal del Centro de administración de Office 365. En la sección Equipos y canales, haga clic en el vínculo de **Usar el panel Grupos del centro de administración para administrar equipos**.

Puede controlar qué usuarios de la organización pueden crear equipos en Microsoft Teams. La misma configuración de creación definida por los grupos de Office 365 se aplica a Microsoft Teams. Si desea más información sobre la administración de los grupos de Office 365, consulte [Crear grupos de Office 365](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) y [Controlar quién puede crear grupos de Office 365](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

NOTA: Los equipos no se pueden crear desde el panel Grupos. Deben crearse mediante el cliente de escritorio de Microsoft Teams o la aplicación web.

De manera predeterminada, todos los usuarios pueden crear un equipo o un grupo. Los usuarios pueden crear equipos seleccionando Equipos en el lado izquierdo del cliente de Microsoft Teams (cliente de escritorio o aplicación web) y, a continuación, eligiendo Crear equipo en la parte inferior del cliente, debajo de la lista de equipos.

Actualmente, el número máximo predeterminado de equipos que puede tener un inquilino de Office 365 es 500.000. Un administrador global puede crear un número ilimitado de equipos. Un usuario puede crear 250 equipos. Un propietario de equipo puede agregar 2500 miembros a un equipo.

![Captura de pantalla de la sección de configuración de usuario por licencia.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

Los canales son subcategorías de los equipos. Cualquier persona del equipo puede agregar un canal y participar en la conversación en un canal. Los canales se pueden crear para una actividad o para un departamento. Las conversaciones, los archivos y las páginas wiki son específicas de cada canal, pero todos los miembros del equipo podrán verlos.

### <a name="calls-and-meetings"></a>Llamadas y reuniones

Los canales son subcategorías de los equipos. Cualquier persona del equipo puede agregar un canal y participar en la conversación en un canal. Los canales se pueden crear para una actividad o para un departamento. Las conversaciones, los archivos y las páginas wiki son específicas de cada canal, pero todos los miembros del equipo podrán verlos.

La sección **Llamadas y reuniones** le permite establecer la siguiente configuración para su organización:

> ![Captura de pantalla de la sección de llamadas y reuniones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

-   **Permitir la programación de reuniones privadas:** Cuando está habilitado, los usuarios pueden programar reuniones privadas que no se indican en ningún canal.

-   **Permitir reuniones ad-hoc del canal:**

-   **Permitir la programación de reuniones de canal:** Cuando está habilitado, los usuarios pueden programar una reunión de un canal a la que pueden unirse fácilmente todos los miembros del canal con un solo clic.

-   **Permitir vídeos en reuniones:** Especifica si se permite el uso de vídeo en las reuniones.

-   **Permitir pantalla compartida en reuniones:** Especifica si se permite compartir la pantalla en las reuniones.

-   **Permitir llamada privada:** Cuando está habilitado, los usuarios pueden realizar llamadas privadas.

El número máximo de personas que pueden participar en una reunión es 80. Puede haber hasta 20 miembros en un chat privado, incluido el usuario que lo creó.

### <a name="messaging"></a>Mensajes 

La sección Mensajes le permite establecer la siguiente configuración para su organización.

![Captura de pantalla de la sección de mensajes.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   **Habilitar Giphy para que los usuarios puedan agregar imágenes gif en las conversaciones:** Cuando está habilitado, los usuarios pueden usar imágenes animadas en las conversaciones.

    -   **Clasificación de contenido:** Cuando las imágenes animadas están activadas, la clasificación de contenido se puede aplicar para restringir el tipo de imágenes animadas que se pueden mostrar en las conversaciones Las opciones de clasificación de contenido disponibles son:

        -   Sin restricciones

        -   Moderado (valor predeterminado)

        -   Estricto

-   **Habilitar memes para que los usuarios puedan editarlos y agregarlos a las conversaciones:** Cuando está habilitado, los usuarios pueden usar memes de Internet para publicar entradas humorísticas.

-   **Habilitar adhesivos para que los usuarios puedan editarlos y agregarlos a las conversaciones:** Cuando está habilitado, los usuarios pueden publicar imágenes con texto editable para llamar la atención de los miembros del canal.

-   **Permitir que los propietarios eliminen todos los mensajes:** Cuando está habilitado, los propietarios del canal pueden quitar todos los mensajes de un canal.

-   **Permitir que los usuarios editen sus propios mensajes:** Cuando está habilitado, los usuarios pueden editar sus propios mensajes.

-   **Permitir que los usuarios eliminen sus propios mensajes:** Cuando está habilitado, los usuarios pueden eliminar sus propios mensajes.

-   **Permitir que los usuarios chateen en privado:** Cuando está habilitado, los usuarios pueden participar en chats privados que solo son visibles a los participantes del chat, en vez de todos los miembros del equipo.


| |  |  |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |Punto de decisión         |¿Qué configuración de Microsoft Teams habilitará su organización?         |
|![Icono de Siguientes pasos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |Siguientes pasos        |Registre estas decisiones en la tabla que se encuentra en [Asignar roles y permisos en Microsoft Teams](assign-roles-permissions.md).         |

