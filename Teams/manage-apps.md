---
title: Administrar las aplicaciones en el centro de administración de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Obtener información sobre cómo administrar las aplicaciones de Teams en la página Administrar aplicaciones del centro de administración de Microsoft Teams
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 7884aa033d3d137ac36fe86a47a2861732b50bb5
ms.sourcegitcommit: ad82786076cc965e75b1ec5ffd4bc9bf75437340
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45028096"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Administrar las aplicaciones en el centro de administración de Microsoft Teams
======================================================

Como administrador, la página **Manage apps** en el centro de administración de Microsoft Teams es donde puede ver y administrar todas las aplicaciones de Teams en el catálogo de aplicaciones de su organización. Aquí puede ver el estado de la organización y las propiedades de las aplicaciones, cargar nuevas aplicaciones personalizadas en el catálogo de aplicaciones de inquilino, bloquear o permitir aplicaciones en el nivel de la organización y administrar la configuración de la aplicación en toda la organización.

La página **Manage apps** le ofrece una vista de todas las aplicaciones disponibles en el catálogo de inquilinos, y le proporciona la información que necesita para decidir qué aplicaciones quiere permitir o bloquear en su organización. Después, puede usar [las directivas de permisos](teams-app-permission-policies.md)de la aplicación, [las directivas de configuración](teams-app-setup-policies.md)de la aplicación y [las directivas de aplicaciones personalizadas y la configuración](teams-custom-app-policies-and-settings.md) para configurar la experiencia de la aplicación para usuarios específicos de su organización.

En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**. Debe ser administrador global o administrador de servicios de equipo para poder acceder a la página.

## <a name="view-apps-in-your-tenant-app-catalog"></a>Ver aplicaciones en el catálogo de aplicaciones de inquilino

Puede ver todas las aplicaciones en el catálogo de aplicaciones de inquilino, incluida la siguiente información sobre cada aplicación.

![Captura de pantalla de la página aplicaciones administradas](media/manage-apps.png)

- **Name**: el nombre de la aplicación. Haga clic en el nombre de la aplicación para ver más información sobre la aplicación. Esto incluye una descripción de la aplicación, si está permitida o bloqueada, la versión, las categorías que se aplican a la aplicación, el estado de la certificación, las características admitidas y el identificador de aplicación. Aquí se muestra un ejemplo:<br> 
![Captura de pantalla de la página de detalles de aplicaciones de una aplicación](media/manage-apps-app-details.png)
- **Certificación**: Si la aplicación ha superado la certificación, verá la atestación de **Microsoft 365** o la **atestación de Publisher**. Haga clic en el vínculo para ver los detalles de certificación de la aplicación. Si ves " **--** ", no tenemos información de certificación de la aplicación. Para obtener más información sobre las aplicaciones certificadas en Teams, lea el [programa de certificación de aplicaciones de Microsoft 365](https://docs.microsoft.com/teams-app-certification/all-apps).  
- **Categorías**: categorías que se aplican a la aplicación.
- **Estado**de la aplicación: estado de la aplicación en el nivel de la organización, que puede ser uno de los siguientes:
    - **Permitido**: la aplicación está disponible para todos los usuarios de la organización.
    - **Bloqueado**: la aplicación está bloqueada y no está disponible para los usuarios de su organización.
    - **Organización bloqueada**: la aplicación está bloqueada en la configuración de la aplicación en toda la organización. <br>
Es importante saber que esta columna representa el estado permitido y bloqueado de las aplicaciones que anteriormente se encontraban en el panel **configuración de toda la organización** . Ahora ve, bloquea y permite aplicaciones en el ámbito de la organización en la página **Manage apps** . 
- **Versión**: versión de la aplicación.

Para ver la información que desea en la tabla, haga clic en **Editar columna** , en la esquina superior derecha, para agregar o quitar columnas a la tabla.

## <a name="upload-a-new-app"></a>Cargar una nueva aplicación

Puede usar el catálogo de aplicaciones para probar y distribuir aplicaciones personalizadas que se hayan creado específicamente para su organización. Un paquete de la aplicación de Teams se crea con [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Cuando tenga el paquete de la aplicación, puede agregarlo al catálogo de aplicaciones. Mientras todos los usuarios de su organización pueden ver el catálogo de aplicaciones, solo los administradores globales y los administradores de servicios de equipos pueden publicar y administrarlo.

Para cargar una nueva aplicación personalizada en el catálogo de aplicaciones de inquilino, haga clic en **cargar nueva aplicación** para cargar el paquete de la aplicación en formato. zip. La aplicación no se resalta después de cargarse, por lo que necesitará buscar en el catálogo de la aplicación para encontrarla.

Para actualizar una aplicación después de que se cargue, en la lista de aplicaciones de la página **Administrar aplicaciones** , haga clic en el nombre de la aplicación y, a continuación, haga clic en **Actualizar**. Esto reemplaza la aplicación existente en el catálogo de aplicaciones y todas las directivas de permisos de aplicaciones y directivas de configuración de la aplicación siguen aplicándose para la aplicación actualizada.

Para obtener más información, vea [administrar las aplicaciones personalizadas en Teams](manage-your-custom-apps.md).

## <a name="allow-and-block-apps"></a>Permitir y bloquear aplicaciones

La página **Manage apps** es donde permite o bloquea aplicaciones individuales en el nivel de organización. Muestra todas las aplicaciones disponibles y el estado actual de la aplicación en el nivel de organización. (El bloqueo y la autorización de aplicaciones en el nivel de organización se han movido del panel de configuración de la **aplicación de toda la organización** a aquí).

Para permitir o bloquear una aplicación, selecciónela y, a continuación, haga clic en **permitir** o en **bloquear**. Cuando bloquea una aplicación, todas las interacciones con esa aplicación se deshabilitan y la aplicación no aparece en Teams para ninguno de los usuarios de su organización.

Cuando bloquea o permite una aplicación en la página **Administrar aplicaciones** , la aplicación está bloqueada o está permitida para todos los usuarios de su organización.  Al bloquear o permitir una aplicación en una directiva de permisos de la aplicación de Teams, se bloquea o permite a los usuarios que tienen asignada esa Directiva. Para que un usuario pueda instalar e interactuar con cualquier aplicación, debe permitir la aplicación en el nivel de la organización en la página **Administrar aplicaciones** y en la Directiva de permisos de la aplicación que está asignada al usuario.

 > [!NOTE]
 > Para desinstalar una aplicación, haga clic con el botón derecho en la aplicación y, a continuación, haga clic en **desinstalar** o use el menú **más aplicaciones** en el lado de LeftHand. 

## <a name="manage-org-wide-app-settings"></a>Administrar la configuración de la aplicación en toda la organización

Use la configuración de la aplicación en toda la organización para controlar si los usuarios pueden instalar aplicaciones de terceros y si los usuarios pueden cargar o interactuar con aplicaciones personalizadas de su organización. La configuración de la aplicación en toda la organización rige el comportamiento de todos los usuarios y anula cualquier otra directiva de permisos de aplicación asignada a los usuarios. Puede usarlos para controlar aplicaciones malintencionadas o problemáticas.

1. En la página **Administrar aplicaciones** , seleccione **configuración**de la aplicación en toda la organización. Puede establecer la configuración que desee en el panel.

    ![Captura de pantalla de la configuración de aplicación de toda la organización](media/manage-apps-org-wide-app-settings.png)
    
2. En **aplicaciones de terceros**, desactive o Active esta configuración para controlar el acceso a las aplicaciones de terceros:

    - **Permitir aplicaciones de terceros**: controla si los usuarios pueden usar aplicaciones de terceros. Si desactiva esta configuración, los usuarios no podrán instalar ni usar ninguna aplicación de terceros y el estado de la aplicación de estas aplicaciones aparecerá **bloqueado: todo el mundo** en la tabla.

        > [!NOTE]
        > En una implementación de Teams de Microsoft 365 pública-GCC, la opción **permitir aplicaciones de terceros** está desactivada de forma predeterminada.

        Cuando se desactivan las **aplicaciones de terceros** , los enlaces de correo [salientes](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) están deshabilitados, lo que significa que los usuarios no pueden crearlos. Cuando esta configuración está activada, los webhooks salientes se habilitan para todos los usuarios, independientemente de si la configuración está activada o desactivada en la Directiva de permisos de la aplicación de los usuarios.
    - **Permitir que todas las aplicaciones de terceros se publiquen en la tienda de forma predeterminada**: controla si las nuevas aplicaciones de terceros publicadas en la tienda de aplicaciones de Teams se encuentran disponibles automáticamente en Teams. Solo puede establecer esta opción si permite aplicaciones de terceros.

3. En **aplicaciones personalizadas**, desactive o desactive la **opción permitir la interacción con aplicaciones personalizadas**. Esta configuración controla si los usuarios pueden interactuar con aplicaciones personalizadas. Para obtener más información, vea [administrar la configuración y las directivas de la aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md).
4. Haga clic en **Guardar** para que la configuración de la aplicación de toda la organización surta efecto.

## <a name="related-topics"></a>Temas relacionados

- [Configurar la administración para aplicaciones en Teams](admin-settings.md)
