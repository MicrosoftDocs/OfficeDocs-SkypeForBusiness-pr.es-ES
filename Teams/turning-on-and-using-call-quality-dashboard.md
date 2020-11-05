---
title: Configurar el panel de calidad de llamadas (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Más información sobre cómo activar y usar el panel de calidad de llamadas y obtener informes de Resumen de la calidad de las llamadas.
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918643"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Configurar el panel de calidad de llamadas (CQD)

Abra el panel de calidad de llamadas de Microsoft (CQD) en [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (inicie sesión con sus credenciales de administrador). O vaya al centro de administración de Teams y seleccione **Panel de calidad de llamadas**. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de pantalla del botón panel de calidad de llamadas en el centro de administración de Teams":::

En la página que se abre, haga clic en **iniciar sesión** y escriba la información de la cuenta de administrador del servicio Microsoft Teams o la cuenta de administrador global. Después de iniciar sesión por primera vez, el CQD comenzará a recopilar y procesar datos. Tenga en cuenta que es posible que tarde una o varias horas en procesar los datos suficientes para mostrar resultados significativos en los informes.

El CQD muestra la calidad de las llamadas y reuniones, en el nivel de toda la organización, de Microsoft Teams, Skype empresarial online y Skype empresarial Server 2019. 

> [!IMPORTANT]
> Para usar el CQD con Skype empresarial Server 2019, tendrá que configurar el [conector de datos de llamada](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector). Consulte [planificar llamada a un conector de datos](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) antes de empezar.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Asignar roles de administrador para el acceso al CQD

Asigne [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) para acceder al CQD a las personas que necesitan usarlo.

Si desea que los usuarios que no sean administradores (como los ingenieros de soporte técnico y los agentes de asistencia al usuario) usen el panel de calidad de llamadas, puede asignar a esos usuarios una de las siguientes funciones, que conceden acceso al CQD. 


|  |Ver informes  |Ver campos de EUII  |Crear informes  |Cargar datos de compilación  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador global de Office 365     |Sí         |Sí         |Sí         |Sí         |
|Administrador de servicios de Teams     |Sí         |Sí         |Sí         |Sí         |
|Administrador de comunicaciones de Teams     |Sí         |Sí         |Sí         |Sí         |
|Ingeniero de soporte en comunicaciones de Teams     |Sí         |Sí         |Sí         |No         |
|Especialista de soporte técnico de comunicaciones de Teams     |Sí         |No         |Sí         |No         |
|Administrador de Skype empresarial     |Sí         |Sí         |Sí         |Sí         |
|Lector global de Azure AD |Sí         |Sí         |Sí         |No         |
|Lector de informes de Office 365<sup>1</sup>     |Sí         |No         |Sí         |No         |

<sup>1</sup> además de leer los informes de CQD, el lector de informes de Office 365 puede ver todos los [informes de actividades](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) en el centro de administración y los informes del paquete de contenido de [adopción de Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Si no ve [EUII (información identificable por el usuario final)](CQD-data-and-reports.md#euii-data) y tiene una de las funciones que pueden ver esta información, tenga en cuenta que el CQD solo mantiene el EUII por 28 días. Se eliminará cualquier antigüedad anterior a 28 días.

Para obtener más información acerca de estos roles, consulte [acerca de los roles de administrador de Office 365](/office365/admin/add-users/about-admin-roles).


Después de iniciar sesión por primera vez, el CQD comenzará a recopilar y procesar datos. A partir del 2019 de diciembre, aún puede acceder a la versión anterior del CQD (cqd.lync.com), aunque el portal heredado le ofrece un vínculo al último CQD (cqd.teams.microsoft.com). Finalmente, la versión anterior del CQD se recargará. A partir del 1 de julio de 2020, la versión anterior del CQD accede a los datos desde el CQD más reciente.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrar datos e informes de la versión anterior del CQD

> [!IMPORTANT]
> A partir del 1 de julio de 2020, ya no puede migrar datos e informes desde el antiguo CQD ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar Power BI para analizar los datos del CQD

Novedades de enero de 2020: [Descargue las plantillas de consulta de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Plantillas de Power BI personalizables que puede usar para analizar y notificar los datos de CQD.

Leer [use Power BI para analizar los datos del CQD](CQD-Power-BI-query-templates.md) y obtener más información.


## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas de los equipos](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Cargar inquilino y datos de compilación](CQD-upload-tenant-building-data.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de las llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de flujo en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar los datos del CQD](CQD-Power-BI-query-templates.md)
