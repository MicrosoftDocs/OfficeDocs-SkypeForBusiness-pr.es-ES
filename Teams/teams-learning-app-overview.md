---
title: Instalar, administrar y asignar permisos para la aplicación de aprendizaje de Teams (versión preliminar privada)
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
description: Use la aplicación de aprendizaje de Microsoft Teams para crear un concentrador central para aprender dónde los empleados pueden compartir, asignar y aprender de las bibliotecas de contenido en una organización.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703461"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>Instalar, administrar y asignar permisos para la aplicación de aprendizaje de Teams (versión preliminar privada)

*Este artículo contiene contenido preliminar para la aplicación de aprendizaje de Teams, que se encuentra en la versión preliminar privada.*

La aplicación de aprendizaje de Microsoft Teams (versión preliminar privada) permite a los equipos y a las personas de su organización facilitar el aprendizaje de forma natural. La aplicación crea un concentrador central en Teams en el que los empleados pueden compartir, asignar y aprender de las bibliotecas de contenido de su organización. Los administradores establecen permisos y permiten orígenes de contenido de aprendizaje para la aplicación. El aprendizaje del contenido puede incluir LinkedIn Learning, aprendizaje de Microsoft, aprendizaje de Microsoft 365, el contenido de su organización almacenado en SharePoint Online y proveedores de terceros que son compatibles con la aplicación.

Para configurar la aplicación de aprendizaje de Teams (versión preliminar privada), tendrá que incluir lo siguiente:

-   Administración del centro de administración de Teams
-   Administrador del centro de administración de Microsoft 365 (es decir, un administrador global)
-   Administrador de conocimientos (un nuevo rol del centro de administración de Microsoft 365 que un administrador global (también conocido como administrador de ti o administrador de Microsoft 365) pueda asignar a cualquier persona de la organización. Esta función administra las fuentes de contenido de aprendizaje de la organización a través del centro de administración de Microsoft 365.) 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>Administrar la aplicación de aprendizaje de Teams (versión preliminar privada) en el centro de administración de Teams

El administrador de Teams instala la aplicación de aprendizaje de Teams (versión preliminar privada) desde el App Store y aplica las directivas de configuración, administración y permisos de la aplicación a través del centro de administración de Teams.

### <a name="manage-the-teams-learning-app-private-preview"></a>Administrar la aplicación de aprendizaje de Teams (vista previa privada)

Para administrar la configuración de la aplicación, siga estos pasos:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**.

   ![Navegación izquierda en el centro de administración de teams que muestra la sección aplicaciones de Teams y administrar aplicaciones](media/learning-app-teams-manage-apps-nav.png)

2. En la página **Manage apps** , en el cuadro de búsqueda, escriba *Learning* para buscar la aplicación de aprendizaje de Teams (versión preliminar privada).

   ![Página Administrar aplicaciones en el centro de administración de teams que muestra el cuadro de búsqueda](media/learning-app-teams-manage-apps-page.png)

3. En la página de **aprendizaje** :
   1. En **Estado**, seleccione **permitido** activar la aplicación.
   2. En la pestaña **configuración** , en la sección configuración de la **aplicación** , vaya al centro de administración de Microsoft 365 para configurar orígenes de contenido de aprendizaje.

   ![Página de aprendizaje en el centro de administración de teams que muestra la sección configuración de la aplicación y estado](media/learning-app-teams-learning-page.png)

4. Después de administrar la configuración de la **aplicación** , vaya a **permisos y directivas de configuración** para conceder permisos a los empleados que deberían tener acceso a la aplicación como parte de la participación de su organización en la versión preliminar privada.

> [!NOTE]
>  Si su organización está en anillo 4,0 como parte del programa Team TAP100, es posible que tenga que hacer lo siguiente para habilitar a los usuarios aprobados en ring 3,0 para acceder a la aplicación de aprendizaje de Teams (versión preliminar privada).

Como parte de la versión preliminar privada, la aplicación de aprendizaje de Teams (Private Preview) se publica en el anillo 3,0. Si su organización está en timbre 4,0, no verá la aplicación en App Store. Para probar la aplicación, debe crear una directiva de permisos de aplicaciones personalizadas, establecerla para **permitir todas las aplicaciones** y asignarla a timbre 3,0 usuarios aprobados.

   ![TOQUE-AppsPermission-Plcy página que muestra permitir todas las aplicaciones seleccionadas](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Configurar orígenes de contenido de aprendizaje en el centro de administración de Microsoft 365

Los administradores del centro de administración de Microsoft 365 (ya sea por sí solos o asignando el rol de administrador de conocimiento a determinadas personas de su organización) pueden administrar la configuración relacionada con la aplicación de aprendizaje de Teams (versión preliminar privada) y pueden configurar los orígenes de contenido de aprendizaje.

> [!TIP]
> El administrador de conocimiento debe ser moderadomente técnico y tener credenciales de administrador de SharePoint, preferiblemente alguien que esté bien en la experiencia de educación, aprendizaje, formación o empleados de la organización.
 
El administrador selecciona qué orígenes de contenido de aprendizaje (como LinkedIn Learning o SharePoint) estarán disponibles en la aplicación. Después, el administrador configura esos orígenes para asegurarse de que el contenido esté disponible para la búsqueda y la detección y que los empleados que usen la aplicación puedan examinarlo.

### <a name="assign-the-knowledge-admin-role-optional"></a>Asignar el rol de administrador de conocimiento [opcional]

El administrador del centro de administración de Microsoft 365 debe realizar estos pasos.

1.  En el centro de navegación izquierdo del centro de administración de Microsoft 365, vaya a **roles**.

2.  En la página **roles** , en la pestaña **Azure ad** , seleccione **Administrador de conocimiento**.
 
3.  En la página **Administración de conocimientos** , en la sección **administradores asignados** , seleccione **Agregar** y, a continuación, agregue la persona que elija para el rol.

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>Establecer la configuración de los orígenes de contenido de aprendizaje para la aplicación

Estos pasos son realizados por el administrador de Microsoft 365 o el administrador de la información.

1.  En el centro de navegación izquierdo del centro de administración de Microsoft 365, vaya a **configuración** de la  >  **organización configuración**.

2.  En la página **configuración** , en la pestaña **servicios & complementos** , seleccione aplicación de **aprendizaje**.

   ![Página configuración en el centro de administración de Microsoft 365 que muestra la aplicación de aprendizaje de la lista](media/learning-app-365-settings-page.png)

3.  En el panel de la **aplicación de aprendizaje** , seleccione los orígenes de contenido de aprendizaje que desea configurar para la organización y, a continuación, seleccione **Guardar**.

   ![Panel de la aplicación de aprendizaje en el centro de administración de Microsoft 365 que muestra las opciones de orígenes de contenido](media/learning-app-365-settings-learning-app-panel.png)

Entre todas las fuentes de aprendizaje que existen, algunas estarán habilitadas de forma predeterminada. Estas afectan a los siguientes aspectos, entre otros:

- LinkedIn Learning (contenido gratuito)
- Aprendizaje de Microsoft
- Formación de Microsoft 365

> [!NOTE]
> Si su organización tiene una suscripción estándar o Pro de LinkedIn Learning, el repositorio de contenido se desbloqueará para los empleados de su organización. Solo aquellos empleados que tengan permiso podrán usar todo el repositorio de contenido.

Es posible que otros orígenes deban habilitarse o configurarse de forma manual. Las fuentes de aprendizaje que no son de Microsoft tienen una licencia independiente entre su organización y el tercero. Tendrá que comprobar que se ha suscrito a su aprendizaje para usted y sus usuarios.

Para habilitar o deshabilitar un origen de contenido de aprendizaje, active la casilla situada junto al origen. Si un origen está habilitado, aparecerá una marca de verificación.

## <a name="configure-sharepoint-as-a-learning-content-source"></a>Configurar SharePoint como origen de contenido de aprendizaje

La configuración de SharePoint como origen de contenido de aprendizaje para la aplicación de aprendizaje de Teams (Private Private Preview) en el centro de administración de Microsoft 365.

### <a name="overview"></a>Información general

El administrador de conocimiento proporciona una dirección URL de sitio en la que el servicio de aprendizaje puede crear un repositorio de contenido centralizado de aprendizaje en forma de una lista estructurada de SharePoint. Esta lista puede ser usada por la organización para hospedar vínculos a carpetas de SharePoint entre empresas que contengan contenido de aprendizaje. Los administradores son responsables de recopilar y organizar una lista de direcciones URL para las carpetas. Estas carpetas solo deben incluir contenido que pueda estar disponible en la aplicación de aprendizaje de Teams (versión preliminar privada).

### <a name="permissions"></a>Permisos

Las direcciones URL de carpeta se pueden recopilar desde cualquier sitio de SharePoint de la organización. El contenido dentro de estas carpetas se puede buscar, pero solo se puede usar el contenido al que tiene permiso el empleado individual.
 
### <a name="learning-service"></a>Servicio de aprendizaje

El servicio de aprendizaje usa las direcciones URL de carpeta proporcionadas para obtener metadatos de todo el contenido almacenado en esas carpetas. Dentro de las 24 horas de suministrar la URL de la carpeta en el repositorio centralizado, los empleados pueden buscar y usar el contenido de la compañía dentro de la aplicación. En este punto no se admite la eliminación de contenido del repositorio. El contenido de superficie no intencional solo se puede quitar si se proporciona una nueva dirección URL de sitio de SharePoint en el centro de administración de Microsoft 365.

### <a name="configure-sharepoint-as-a-source"></a>Configurar SharePoint como origen

Estos pasos son realizados por el administrador de Microsoft 365 o el administrador de la información.

1.  En el centro de navegación izquierdo del centro de administración de Microsoft 365, vaya a **configuración**.
 
2.  En la página **configuración** , en la pestaña **servicios & complementos** , seleccione aplicación de **aprendizaje**.

   ![Página configuración en el centro de administración de Microsoft 365 que muestra la aplicación de aprendizaje de la lista](media/learning-app-365-settings-page.png)

3.  En el panel de la **aplicación de aprendizaje** , proporcione la dirección URL del sitio al sitio de SharePoint donde quiere que la aplicación cree un repositorio centralizado.

   ![Panel de la aplicación de aprendizaje en el centro de administración de Microsoft 365 que muestra SharePoint seleccionado](media/learning-app-365-panel-sharepoint-selected.png)

4.  Se crea automáticamente una lista de SharePoint dentro del sitio de SharePoint de la organización proporcionada. En el sitio de navegación izquierdo del sitio de SharePoint, seleccione repositorio de contenido de la **aplicación de aprendizaje**. 

   ![Navegación izquierda en SharePoint que muestra la sección repositorio de contenido de la aplicación de aprendizaje](media/learning-app-content-repository-nav.png)

 
5. En la página del repositorio de contenido de la **aplicación de aprendizaje** , rellene la lista de SharePoint con direcciones URL para las carpetas de contenido de aprendizaje.

   1.   Seleccione **nuevo** para ver el panel de **elementos nuevos** . 

   ![Página del repositorio de contenido de la aplicación de aprendizaje de SharePoint que muestra la opción nuevo](media/learning-app-content-repository-new.png)
 
   2.   En el panel **nuevo elemento** , en el campo **título** , agregue un nombre de directorio de su elección. En el campo **dirección URL** de la carpeta, agregue la dirección URL a la carpeta de contenido de aprendizaje. Seleccione **Guardar**.

   ![Nuevo panel de elementos en SharePoint que muestra los campos de dirección URL de título y carpeta](media/learning-app-new-item-panel.png)

   3. La página del repositorio de contenido de la aplicación de aprendizaje se actualiza con el nuevo contenido de aprendizaje.

   ![Página del repositorio de contenido de la aplicación de aprendizaje de SharePoint que muestra la información actualizada](media/learning-app-content-repository-populated.png)


 


