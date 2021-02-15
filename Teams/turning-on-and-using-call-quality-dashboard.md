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
description: Obtenga información sobre cómo activar y usar el panel de calidad de llamadas y obtener informes de resumen de la calidad de las llamadas.
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112843"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Configurar el panel de calidad de llamadas (CQD)

Abra el panel de calidad de llamadas (CQD) de Microsoft [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) en (inicie sesión con sus credenciales de administrador). O bien, vaya al Centro de administración de Teams y seleccione **Panel de calidad de llamadas.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas en el Centro de administración de Teams":::

En la página que se abre, haga clic en **Iniciar sesión** y escriba la información de su cuenta de administrador global o de administrador de servicios de Microsoft Teams. Después de iniciar sesión por primera vez, el CQD comenzará a recopilar y procesar datos. Tenga en cuenta que puede tardar una o más horas en procesar los datos suficientes para mostrar resultados significativos en los informes.

El CQD muestra la calidad de las llamadas y reuniones, a nivel de toda la organización, para Microsoft Teams, Skype Empresarial Online y Skype Empresarial Server 2019. 

> [!IMPORTANT]
> Para usar el CQD con Skype Empresarial Server 2019, tendrá que configurar el conector de [datos de llamadas.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector) Vea [Planear conector de datos de llamadas](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) antes de empezar.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Asignar roles de administrador para obtener acceso al CQD

Asigne [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) para acceder al CQD a las personas que necesitan usarlo.

Si desea que los usuarios que no son administradores (como ingenieros de soporte técnico y agentes del departamento de soporte técnico) usen el panel de calidad de llamadas, puede asignar a esos usuarios uno de los siguientes roles, que le da acceso al panel de calidad de llamadas. 


|  |Ver informes  |Ver campos EUII  |Crear informes  |Cargar datos de creación  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador global     |Sí         |Sí         |Sí         |Sí         |
|Administrador de servicios de Teams     |Sí         |Sí         |Sí         |Sí         |
|Administrador de comunicaciones de Teams     |Sí         |Sí         |Sí         |Sí         |
|Ingeniero de soporte en comunicaciones de Teams     |Sí         |Sí         |Sí         |No         |
|Especialista de soporte de comunicaciones de Teams     |Sí         |No         |Sí         |No         |
|Administrador de Skype Empresarial     |Sí         |Sí         |Sí         |Sí         |
|Lector global |Sí         |Sí         |Sí         |No         |
|Lector de<sup>informes 1</sup>     |Sí         |No         |Sí         |No         |

<sup>1</sup> Además de leer los informes del CQD, el Lector de informes puede ver todos los informes de actividad en el centro de administración y los informes del paquete de contenido Adopción de [Microsoft 365.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f) [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)

> [!NOTE]
> Si no ve [EUII (información](CQD-data-and-reports.md#euii-data) de identificación del usuario final) y tiene una de las funciones a las que se permite ver esta información, tenga en cuenta que el CQD solo mantiene EUII durante 28 días. Se elimina cualquier cosa que sobresala más de 28 días.

Para obtener más información sobre estos roles, consulte [Acerca de los roles de administrador de Office 365.](/office365/admin/add-users/about-admin-roles)


Después de iniciar sesión por primera vez, el CQD comenzará a recopilar y procesar datos. A partir de diciembre de 2019, aún puede acceder a la versión anterior del CQD (cqd.lync.com), aunque el portal heredado le proporciona un vínculo al último CQD (cqd.teams.microsoft.com). Finalmente, se retirará la versión anterior del CQD. Desde el 1 de julio de 2020, la versión anterior del CQD accede a los datos del último CQD.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrar datos e informes de creación de la versión anterior del CQD

> [!IMPORTANT]
> A partir del 1 de julio de 2020, ya no puede migrar los datos de creación e informes desde el CQD antiguo ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar Power BI para analizar datos del CQD

Novedades de enero de 2020: Descargar plantillas de consulta [de Power BI para el CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Las plantillas personalizables de Power BI que puede usar para analizar e informar sobre los datos del CQD.

Lea [Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md) para obtener más información.


## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas en Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Cargar datos de inquilino y de edificio](CQD-upload-tenant-building-data.md)

[Informes y datos del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de las llamadas y las reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)
