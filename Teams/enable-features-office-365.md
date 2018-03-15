---
title: "Habilitar características de Microsoft Teams en su organización de Office 365"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "Conozca todas las características de Microsoft Teams que puede activar o desactivar en su organización de Office 365, incluidos la configuración en todo el inquilino, la integración del correo electrónico, las aplicaciones, el almacenamiento en nube y mucho más."
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87871cb46c1b9e584308b75376622473a3131888
ms.sourcegitcommit: 50446359cd7c359eb2536176545291c723392e47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2018
---
<a name="turn-on-microsoft-teams-features-in-your-office-365-organization"></a>Habilitar características de Microsoft Teams en su organización de Office 365
======================================================

Microsoft Teams tiene varios parámetros de configuración que se pueden habilitar o deshabilitar a nivel de inquilino de Office 365. Si Microsoft Teams está habilitado para un inquilino, cualquier usuario que esté también habilitado para Teams heredará del nivel de inquilino.

A continuación puede ver una lista de las características que los administradores de Office 365 pueden activar o desactivar en Microsoft Teams. 

A menos que se indique lo contrario, el valor predeterminado para una opción es Activado.

> [!NOTE] 
> Para ajustar la configuración de la administración en Microsoft Teams, vaya al Centro de administración de Office 365, abra **Configuración** > **Servicios y complementos**, y seleccione **Microsoft Teams**. Si ha iniciado sesión como administrador de Office 365, puede acceder con este vínculo: 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

> [!IMPORTANT]
> Un administrador de Office 365 puede desactivar Microsoft Teams en cualquier momento mediante el Centro de administración de Office 365. Tenga en cuenta que los usuarios con licencias activas de Microsoft Teams seguirán viendo el icono de la aplicación Microsoft Teams, aunque lo desactive. Para ver información detallada sobre cómo quitar licencias de los usuarios, consulte [Administrar el acceso de los usuarios a las licencias de Microsoft Teams](user-access.md). En cuanto Microsoft Teams se deshabilita, el acceso desde su cliente se bloquea, pero los datos que estén disponibles a través de otros clientes y servicios, como los archivos a través de SharePoint o OneDrive, seguirán estando disponibles. Todos los datos continuarán en su lugar, a menos que los equipos se eliminen explícitamente.

<a name="office-365-tenant-wide-settings"></a>Configuración a nivel de inquilino de Office 365 
---------------------

En **Configuración de todos los inquilinos** puede activar o desactivar las opciones que se encuentran en General, Integración de correo electrónico, Aplicaciones y Almacenamiento en nube personalizado.

Para editar **la configuración a nivel de inquilino** para Microsoft Teams, vaya al Centro de administración de Office 365. Después, elija **Configuración** > **Servicios y complementos** > **Microsoft Teams**.

### <a name="general"></a>General

La sección General le permite establecer la siguiente configuración para su organización.

> ![Captura de pantalla de la sección General en la configuración para todos los inquilinos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   **Mostrar el organigrama en el perfil personal:** si esta opción está activada, se muestra el icono del organigrama en la tarjeta de contacto del usuario. Al hacer clic en él, se muestra el organigrama detallado.

    ![Captura de pantalla del icono de organigrama en la tarjeta de contacto de un usuario.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![Captura de pantalla de un organigrama.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-  **Usar Skype Empresarial para los destinatarios que no tienen Microsoft Teams:** si esta opción está activada, las conversaciones de Microsoft Teams se muestran automáticamente en Skype Empresarial a los usuarios que no pueden utilizar Microsoft Teams.  

-   **Permitir mensajes de ayuda proactivos de T-bot:** si esta opción está activada, T-bot inicia una sesión de chat privado con los usuarios para ayudarlos a utilizar Microsoft Teams.

    ![Captura de pantalla de la sección T-Bot en la interfaz de Microsoft Teams.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a>Integración del correo electrónico
-----------------

Active esta característica para que los usuarios puedan enviar un correo electrónico a un canal en Microsoft Teams mediante la dirección de correo electrónico del canal. Los usuarios pueden hacer esto para cualquier canal que pertenezca a un equipo que sea de su posesión. Los usuarios también pueden enviar correos electrónicos a cualquier canal de un equipo que tenga conectores habilitados para los miembros del equipo. Aunque un usuario no tenga permiso para crear una dirección de correo electrónico en un canal, si alguien que sí tiene permiso crea esa dirección, el usuario sin permiso de creación podrá acceder a ella desde el menú **Más opciones** de ese canal.

Establezca la siguiente configuración de **Integración de correo electrónico** para su organización: 

   ![Captura de pantalla de la sección de integración del correo electrónico en la configuración para todos los inquilinos.](media/QS-edu-email-integration.png)

-   **Permitir que los usuarios puedan enviar correo electrónico a los canales:** si esta opción está activada, se habilitan los enlaces de correo electrónico y los usuarios pueden publicar mensajes en un canal enviando un correo electrónico a la dirección de correo electrónico del canal de Microsoft Teams. 

 
-   **Permitir que los usuarios puedan enviar correo electrónico a los canales:** si está habilitada esta opción, los enlaces de correo electrónico se habilitan también y los usuarios pueden publicar mensajes en un canal enviando un correo electrónico a la dirección de correo electrónico del canal de Microsoft Teams. 

    Para buscar la dirección de correo electrónico de un canal, haga clic en el menú **Más opciones** del canal y después seleccione **Obtener dirección de correo electrónico**. 

-   **Lista de remitentes restringidos:** los dominios de los remitentes se pueden restringir aún más para garantizar que solo los dominios SMTP permitidos puedan enviar correos electrónicos a los canales de Microsoft Teams.

<a name="apps"></a>Aplicaciones
----

Las aplicaciones son fichas, conectores, bots o cualquier combinación de estos tres elementos que proporciona un servicio de terceros. Hay directivas de administración de Microsoft Teams que se pueden configurar en el Centro de administración de Office 365 para controlar qué aplicaciones externas de terceros están permitidas. Estas directivas permiten especificar qué aplicaciones están permitidas y cuáles no, el comportamiento de las aplicaciones nuevas externas y si se permite la instalación de prueba de aplicaciones. 

La sección **Aplicaciones** le permite establecer la siguiente configuración para su organización: 

![Captura de pantalla de la sección Aplicaciones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **Permitir aplicaciones externas en Microsoft Teams:** si este conmutador está activado, los usuarios pueden agregar las fichas y los bots que estén disponibles al inquilino de Office 365. 
 
    ![Captura de pantalla del control para permitir aplicaciones externas en la sección Aplicaciones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **Habilitar nuevas aplicaciones externas de manera predeterminada**: si este conmutador está activado, los usuarios pueden activar nuevas aplicaciones en cuanto estas se agregan al catálogo de aplicaciones de Microsoft Teams. Desactive este conmutador si quiere controlar las aplicaciones nuevas. Si lo desactiva, deberá recordar revisar periódicamente las nuevas incorporaciones para que su organización no se pierda las nuevas aplicaciones de interés. 

- **Permitir la instalación de prueba de aplicaciones externas:** si este conmutador está activado, los usuarios pueden instalar y habilitar bots y fichas personalizados. 

Para obtener más información, consulte [Configurar la administración para aplicaciones en Microsoft Teams](admin-settings.md). 



<a name="custom-cloud-storage"></a>Almacenamiento en nube personalizado
--------------------

Las opciones de almacenamiento en nube en Microsoft Teams actualmente incluyen Box, Dropbox, Google Drive y ShareFile. Los usuarios pueden cargar y compartir archivos de los servicios de almacenamiento en nube en los canales y chats de Microsoft Teams. Active el conmutador de los proveedores de almacenamiento en nube que quiera usar su organización. 

![Captura de pantalla de la sección de almacenamiento en nube personalizado.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a>Configuración de usuario por licencia
------------------------

En **Configuración de usuario por licencia**, puede activar o desactivar las opciones que se encuentran en Equipos y canales, Llamadas y reuniones, y Mensajes.

<a name="teams-and-channels"></a>Equipos y canales
------------------

El equipo está diseñado para reunir un grupo de personas que trabajan juntos para conseguir completar sus funciones. Los equipos pueden ser dinámicos para el trabajo basado en proyectos (por ejemplo, iniciar un producto o crear un centro de operaciones digital). Los equipos también pueden ser continuos para reflejar la estructura interna de la organización.

Actualmente, el número máximo de equipos que puede tener un inquilino de Office 365 es 500.000. Un administrador global puede crear un número ilimitado de equipos. Un usuario puede crear 250 equipos. Un propietario de equipo puede agregar 2500 miembros a un equipo.

Como administrador, puede administrar los propietarios y los miembros de equipos mediante el panel Grupos del Centro de administración de Office 365. Para obtener más información, haga clic en **Usar el panel Grupos del Centro de administración de Office 365 para administrar equipos** en **Equipos y canales**.

Puede controlar qué usuarios de la organización pueden crear equipos en Microsoft Teams. La misma configuración de creación definida por los grupos de Office 365 se aplica a Microsoft Teams. Si desea más información sobre la administración de los grupos de Office 365, consulte [Crear grupos de Office 365](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) y [Controlar quién puede crear grupos de Office 365](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

> [!NOTE]
> Los equipos no se pueden crear desde el panel Grupos. Los equipos se deben crear mediante el cliente de escritorio de Microsoft Teams o la aplicación web.

De manera predeterminada, todos los usuarios pueden crear un equipo o un grupo. Los usuarios pueden crear equipos seleccionando **Equipos** en el lado izquierdo del cliente de Microsoft Teams (cliente de escritorio o aplicación web) y, a continuación, eligiendo **Crear equipo y unirse a él** en la parte inferior del cliente, debajo de la lista de equipos.

![Captura de pantalla de la sección de configuración de usuario por licencia.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

Los canales son subcategorías de los equipos. Cualquier persona del equipo puede agregar un canal y participar en la conversación en un canal. Los canales se pueden crear para una actividad o para un departamento. Las conversaciones, los archivos y las páginas wiki son específicas de cada canal, pero todos los miembros del equipo podrán verlos.

## <a name="calls-and-meetings"></a>Llamadas y reuniones

Establezca la siguiente configuración de **Llamadas y reuniones** para su organización:

![Captura de pantalla de la sección de llamadas y reuniones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

El número máximo de personas que pueden participar en una reunión es 80. Puede haber hasta 20 miembros en un chat privado, incluido el usuario que lo creó.

-   **Permitir la programación de reuniones privadas:** si esta opción está activada, los usuarios pueden programar reuniones privadas que no se indiquen en ningún canal.

-   **Permitir reuniones ad-hoc del canal**: cuando se activa, los usuarios pueden iniciar rápidamente una reunión para un canal que se haya creado para un fin inmediato o específico.

-   **Permitir la programación de reuniones de canal:** si está habilitada esta opción, los usuarios pueden programar una reunión de un canal a la que pueden unirse fácilmente todos los miembros del canal con un solo clic.

-   **Permitir vídeos en reuniones:** especifica si se permite el uso de vídeo en las reuniones.

-   **Permitir pantalla compartida en reuniones:** especifica si se permite compartir la pantalla en las reuniones.

-   **Permitir llamada privada:** si esta opción está activada, los usuarios pueden realizar llamadas privadas.

## <a name="messaging"></a>Mensajes 

La sección Mensajes le permite establecer la siguiente configuración para su organización.

![Captura de pantalla de la sección de mensajes.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   **Habilitar Giphy para que los usuarios puedan agregar imágenes gif en las conversaciones:** si esta opción está activada, los usuarios pueden usar imágenes animadas en las conversaciones.

-   **Clasificación de contenido**: si las imágenes animadas están activadas, la clasificación de contenido se puede aplicar para restringir el tipo de imágenes animadas que se pueden mostrar en las conversaciones Las opciones de clasificación de contenido disponibles son:

    -   Sin restricciones
    -   Moderado (valor predeterminado)
    -   Estricto

-   **Habilitar memes para que los usuarios puedan editarlos y agregarlos a las conversaciones:** si esta opción está activada, los usuarios pueden usar memes de Internet para publicar entradas humorísticas.

-   **Habilitar adhesivos para que los usuarios puedan editarlos y agregarlos a las conversaciones:** si esta opción está activada, los usuarios pueden publicar imágenes con texto editable para llamar la atención de los miembros del canal.

-   **Permitir que los propietarios eliminen todos los mensajes:** si esta opción está activada, los propietarios del canal pueden quitar todos los mensajes de un canal.

-   **Permitir que los usuarios editen sus propios mensajes:** si esta opción está activada, los usuarios pueden editar sus propios mensajes.

-   **Permitir que los usuarios eliminen sus propios mensajes:** si esta opción está activada, los usuarios pueden eliminar sus propios mensajes.

-   **Permitir que los usuarios chateen en privado:** si esta opción está activada, los usuarios pueden participar en chats privados que solo son visibles para los participantes del chat, en vez de para todos los miembros del equipo.


| |  |  |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |Punto de decisión         |¿Qué configuración de Microsoft Teams habilitará su organización?         |
|![Icono de Siguientes pasos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |Siguientes pasos        |Registre estas decisiones en la tabla que se encuentra en [Asignar roles y permisos en Microsoft Teams](assign-roles-permissions.md).         |

