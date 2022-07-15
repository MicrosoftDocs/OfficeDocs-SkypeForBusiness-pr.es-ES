---
title: Configurar el panel de calidad de llamadas (CQD)
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Obtenga información sobre cómo activar y usar el panel de calidad de llamadas y obtener informes resumidos de la calidad de las llamadas.
ms.openlocfilehash: 052b38634d17aa6d0086c80ed2a638a7818a729f
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66797385"
---
# <a name="set-up-call-quality-dashboard"></a>Configurar el panel de calidad de llamadas

Abra el Panel de calidad de llamadas de Microsoft (CQD) en [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (inicie sesión con sus credenciales de administrador). O vaya al Centro de administración de Teams y seleccione **Análisis & informes** > **Panel de calidad de llamadas**.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas en el Centro de administración de Teams.":::

En la página que se abre, haga clic **en Iniciar sesión** y escriba la información de su cuenta de administrador global o de la cuenta de administrador de Microsoft Teams. Después de iniciar sesión por primera vez, el CQD comenzará a recopilar y procesar datos. Tenga en cuenta que puede tardar una o más horas en procesar los datos suficientes para mostrar resultados significativos en los informes.

El CQD muestra la calidad de las llamadas y reuniones a nivel de toda la organización para Microsoft Teams, Skype Empresarial Online y Skype Empresarial Server 2019. 

> [!IMPORTANT]
> Para usar el CQD con Skype Empresarial Server 2019, tendrá que [configurar el conector de datos de llamadas](/skypeforbusiness/hybrid/configure-call-data-connector). Consulte [Planear el conector de datos de llamadas](/skypeforbusiness/hybrid/plan-call-data-connector) antes de empezar.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Asignar roles de administrador para el acceso al CQD

Asigne [roles](/microsoft-365/admin/add-users/about-admin-roles) para acceder al CQD a las personas que necesitan usarlo.

Si quiere que los usuarios que no sean administradores (como los ingenieros de soporte técnico y los agentes del departamento de soporte técnico) usen el panel de calidad de llamadas, puede asignar a esos usuarios uno de los siguientes roles, que proporciona acceso al CQD. 


|&nbsp;  |Ver informes  |Ver campos DE LA UEII  |Crear informes  |Cargar datos de compilación  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador global     |Sí         |Sí         |Sí         |Sí         |
|Administrador de Teams     |Sí         |Sí         |Sí         |Sí         |
|Administrador de comunicaciones de Teams     |Sí         |Sí         |Sí         |Sí         |
|Ingeniero de soporte en comunicaciones de Teams     |Sí         |Sí         |Sí         |No         |
|Especialista en soporte técnico de comunicaciones de Teams     |Sí         |No         |Sí         |No         |
|administrador de Skype Empresarial     |Sí         |Sí         |Sí         |Sí         |
|Lector global |Sí         |Sí         |Sí         |No         |
|Lector de informes<sup>1</sup>     |Sí         |No         |Sí         |No         |

<sup>1</sup> Además de leer los informes del CQD, el lector de informes puede ver todos los [informes de actividades](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) en el centro de administración y los informes del [paquete de contenido de adopción de Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Si no ve [EUII (información identificable para el usuario final)](CQD-data-and-reports.md#euii-data) y tiene uno de los roles que se permite ver esta información, tenga en cuenta que el CQD solo mantiene la EUII durante 28 días. Se elimina todo lo que supera los 28 días.

Para obtener más información sobre estos roles, vea [Acerca de Office 365 roles de administrador](/office365/admin/add-users/about-admin-roles).


Después de iniciar sesión por primera vez, el CQD comenzará a recopilar y procesar datos.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar Power BI para analizar datos del CQD

Novedades de enero de 2020: [Descargar plantillas de consulta de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Plantillas personalizables de Power BI que puede usar para analizar e informar de los datos del CQD.

Lea [Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md) para obtener más información.

## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Cargar datos de inquilinos y compilación](CQD-upload-tenant-building-data.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)
