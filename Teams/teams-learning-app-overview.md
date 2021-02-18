---
title: Instalar, administrar y asignar permisos para la aplicación Teams Learning (versión preliminar privada)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Use la aplicación Aprendizaje de Microsoft Teams para crear un centro central para aprender dónde los empleados pueden compartir, asignar y aprender de las bibliotecas de contenido de una organización.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6dd82c786c30fb4f2ac2ae70f2df6810cfe5d6ad
ms.sourcegitcommit: 75d710e3858f79ef601cd92e435a4a29dae0aba0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50285624"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>Instalar, administrar y asignar permisos para la aplicación Teams Learning (versión preliminar privada)

*Este artículo contiene contenido preliminar para la aplicación Teams Learning, que está en versión preliminar privada.*

La aplicación Microsoft Teams Learning (versión preliminar privada) permite a los equipos y a las personas de su organización hacer que el aprendizaje sea parte natural de su día. La aplicación crea un concentrador central en Teams donde los empleados pueden compartir, asignar y aprender de bibliotecas de contenido en toda su organización. Los administradores establecen permisos y permiten orígenes de contenido de aprendizaje para la aplicación. El contenido de aprendizaje puede incluir LinkedIn Learning, Microsoft Learn, formación de Microsoft 365, el contenido almacenado en SharePoint Online de su organización y proveedores de terceros compatibles con la aplicación.

Para configurar la aplicación Teams Learning (versión preliminar privada), tendrá que implicar:

-   Administrador del centro de administración de Teams
-   Administrador del centro de administración de Microsoft 365 (es decir, administrador global)

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>Administrar la aplicación Teams Learning (versión preliminar privada) en el Centro de administración de Teams

El administrador de Teams instala la aplicación Teams Learning (versión preliminar privada) desde la tienda de aplicaciones y aplica las directivas de configuración, administración y permisos de la aplicación a través del Centro de administración de Teams.

### <a name="manage-the-teams-learning-app-private-preview"></a>Administrar la aplicación Teams Learning (versión preliminar privada)

Para administrar la configuración de la aplicación, siga estos pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones**  >  **de** Teams.

   ![Panel de navegación izquierdo del Centro de administración de Teams que muestra la sección Aplicaciones de Teams y Administrar aplicaciones](media/learning-app-teams-manage-apps-nav.png)

2. En la **página Administrar aplicaciones,** en el cuadro de búsqueda, escriba *"aprendizaje"* para buscar la aplicación Teams Learning (versión preliminar privada).

   ![Página Administrar aplicaciones en el Centro de administración de Teams que muestra el cuadro de búsqueda](media/learning-app-teams-manage-apps-page.png)

3. En la **página aprendizaje:**
   1. En **Estado,** seleccione **Permitido** para activar la aplicación.
   2. En la **pestaña Configuración,** en la sección **Configuración de** la aplicación, vaya al Centro de administración de Microsoft 365 para configurar orígenes de contenido de aprendizaje.

   ![Página de aprendizaje del Centro de administración de Teams que muestra la sección Configuración de estado y aplicación](media/learning-app-teams-learning-page.png)

4. Después **de administrar** la configuración de la aplicación, vaya a Permisos y directivas de configuración para conceder permisos a los **empleados** que deberían tener acceso a la aplicación como parte de la participación de su organización en la versión preliminar privada.

> [!NOTE]
>  Si su organización se encuentra en el anillo 4.0 como parte del programa TAP100 de Teams, es posible que tenga que hacer lo siguiente para permitir que los usuarios aprobados en el anillo 3.0 puedan acceder a la aplicación Teams Learning (versión preliminar privada).

Como parte de la versión preliminar privada, la aplicación Teams Learning (versión preliminar privada) se publica en el anillo 3.0. Si su organización está en el anillo 4.0, no verá la aplicación en la tienda de aplicaciones. Para probar la aplicación, debe crear una directiva de permisos de aplicaciones personalizada, establecerla en Permitir todas las aplicaciones y asignarla a los usuarios aprobados de Llamada 3.0.

   ![Página TAP-AppsPermission-Plcy que muestra Permitir todas las aplicaciones seleccionadas](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Configurar orígenes de contenido de aprendizaje en el Centro de administración de Microsoft 365

Los administradores del Centro de administración de Microsoft 365 pueden administrar la configuración relacionada con la aplicación Teams Learning (versión preliminar privada) y pueden configurar los orígenes de contenido de aprendizaje.

El administrador puede seleccionar qué orígenes de contenido de aprendizaje adicionales (por ejemplo, SharePoint u orígenes de proveedores de contenido de terceros compatibles) estarán disponibles para los usuarios de la aplicación. A continuación, el administrador configura esos orígenes para asegurarse de que el contenido está disponible para la búsqueda y detección y puede ser examinada por los empleados que usan la aplicación.

> [!NOTE]
>  Los usuarios inician sesión en aprendizajes que no son de Microsoft y LinkedIn Learning Pro en un explorador o en un visor incrustado. Este aprendizaje configurado está sujeto a los términos de licencia, privacidad y servicio independientes entre su organización y los terceros, y no a los términos de aprendizaje (versión preliminar). Antes de seleccionar este aprendizaje en Aprendizaje (versión preliminar), compruebe que tiene un acuerdo para su organización y los usuarios.

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>Configurar las opciones de los orígenes de contenido de aprendizaje para la aplicación

Estos pasos los debe realizar el administrador de Microsoft 365.

1.  En el panel de navegación izquierdo del Centro de administración de Microsoft 365, vaya a **Configuración de**  >  **la organización.**

2.  En la **página** Configuración, en la pestaña **& complementos,** seleccione **Aplicación de aprendizaje.**

   ![Página de configuración del Centro de administración de Microsoft 365 que muestra la aplicación Aprendizaje enumerada](media/learning-app-365-settings-page.png)

3.  En el **panel de la aplicación** Aprendizaje, seleccione los orígenes de contenido de aprendizaje que quiera configurar para la organización y, después, haga clic en **Guardar.**

   ![Panel de la aplicación Aprendizaje del Centro de administración de Microsoft 365 que muestra las opciones de orígenes de contenido](media/learning-app-365-settings-learning-app-panel.png)

Entre todas las fuentes de aprendizaje que existen, algunas de ellas estarán habilitadas de forma predeterminada. Estas afectan a los siguientes aspectos, entre otros:

- LinkedIn Learning (contenido gratuito)
- Microsoft Learn
- Aprendizaje de Microsoft 365

> [!NOTE]
> Si su organización tiene una suscripción a LinkedIn Learning Standard o Pro, se desbloqueará el repositorio de contenido para los empleados de la organización. Solo los empleados con permisos podrán usar todo el repositorio de contenido.

Es posible que otros orígenes deba habilitarse o configurarse manualmente. Las fuentes de aprendizaje que no son de Microsoft tienen licencia por separado entre su organización y los terceros. Deberá comprobar que se ha registrado para su aprendizaje para usted y sus usuarios.

Para habilitar o deshabilitar un origen de contenido de aprendizaje, active la casilla situada junto al origen. Si un origen está habilitado, se podrá ver una marca de verificación.

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a>Configurar SharePoint como un origen de contenido de aprendizaje (Próximamente)

Configure SharePoint como un origen de contenido de aprendizaje para la aplicación Teams Learning (versión preliminar privada) en el Centro de administración de Microsoft 365.

### <a name="overview"></a>Información general

El administrador proporciona una dirección URL de sitio a la que el Servicio de aprendizaje puede crear un repositorio de contenido de aprendizaje centralizado vacío en forma de lista estructurada de SharePoint. Esta lista la puede usar la organización para hospedar vínculos a carpetas de SharePoint entre empresas que contienen contenido de aprendizaje. Los administradores son responsables de recopilar y curar una lista de direcciones URL de las carpetas. Estas carpetas solo deben incluir contenido que pueda estar disponible en la aplicación Teams Learning (versión preliminar privada).

### <a name="permissions"></a>Permisos

Las direcciones URL de carpeta se pueden recopilar desde cualquier sitio de SharePoint de la organización. Se podrá buscar cualquier contenido dentro de estas carpetas, pero solo se podrá usar el contenido para el que cada empleado tenga permisos.
 
### <a name="learning-service"></a>Servicio de aprendizaje

El Servicio de aprendizaje usa las direcciones URL de carpeta proporcionadas para obtener metadatos de todo el contenido almacenado en esas carpetas. 24 horas después de proporcionar la dirección URL de la carpeta en el repositorio centralizado, los empleados pueden buscar y usar el contenido de la empresa dentro de la aplicación. En este momento no se admite la eliminación de contenido del repositorio. El contenido en superficie no involuntara solo se puede quitar suministrando una nueva DIRECCIÓN URL del sitio de SharePoint en el Centro de administración de Microsoft 365.

### <a name="configure-sharepoint-as-a-source"></a>Configurar SharePoint como origen

Estos pasos los realizará el administrador de Microsoft 365.

1.  En el panel de navegación izquierdo del Centro de administración de Microsoft 365, vaya a **Configuración.**
 
2.  En la **página** Configuración, en la pestaña **& complementos,** seleccione **Aplicación de aprendizaje.**

   ![Página de configuración del Centro de administración de Microsoft 365 que muestra la aplicación Aprendizaje enumerada](media/learning-app-365-settings-page.png)

3.  En el panel **de la aplicación** Aprendizaje, proporcione la dirección URL del sitio al sitio de SharePoint donde quiera que la aplicación cree un repositorio centralizado.

   ![Panel de la aplicación de aprendizaje en el Centro de administración de Microsoft 365 que muestra SharePoint seleccionado](media/learning-app-365-panel-sharepoint-selected.png)

4.  Una lista de SharePoint se crea automáticamente en el sitio de SharePoint de la organización proporcionada. En el panel de navegación izquierdo del sitio de SharePoint, seleccione Repositorio **de contenido de aplicaciones de aprendizaje.** 

   ![Navegación izquierda en SharePoint que muestra la sección Repositorio de contenido de la aplicación de aprendizaje](media/learning-app-content-repository-nav.png)

 
5. En la **página Repositorio de contenido de la aplicación** de aprendizaje, rellene la lista de SharePoint con direcciones URL para las carpetas de contenido de aprendizaje.

   1.   Seleccione **Nuevo** para ver el **panel Nuevo** elemento. 

   ![Página de repositorio de contenido de la aplicación de aprendizaje en SharePoint que muestra la nueva opción](media/learning-app-content-repository-new.png)
 
   2.   En el **panel Nuevo elemento,** en el **campo Título,** agregue el nombre del directorio que prefiera. En el **campo Dirección URL de** la carpeta, agregue la dirección URL a la carpeta de contenido de aprendizaje. Seleccione **Guardar**.

   ![Panel Nuevo elemento en SharePoint que muestra los campos Título y Dirección URL de carpeta](media/learning-app-new-item-panel.png)

   3. La página repositorio de contenido de la aplicación de aprendizaje se actualiza con el nuevo contenido de aprendizaje.

   ![Página de repositorio de contenido de la aplicación de aprendizaje en SharePoint que muestra la información actualizada](media/learning-app-content-repository-populated.png)


 


