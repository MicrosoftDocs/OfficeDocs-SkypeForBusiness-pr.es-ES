---
title: Configurar panel de calidad de llamadas (CQD)
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
description: Obtenga información sobre cómo activar y usar el Panel de calidad de llamadas y obtener informes de resumen de la calidad de las llamadas.
ms.openlocfilehash: cf4c6d56e4fa646495383b4998e80789d9cdaca67b9cc35d07f613cda4e70b85
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300456"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>Cómo configurar el Panel de calidad de llamadas

Abra el Panel de calidad de llamadas de Microsoft (CQD) en [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (inicie sesión con sus credenciales de administrador). O vaya al Centro Teams administración y seleccione **Panel de calidad de llamadas.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas en Teams centro de administración":::

En la página que se abre, haga clic en **Iniciar sesión** e introduzca su cuenta de administrador global o Microsoft Teams cuenta de administrador. Después de la primera vez que inicie sesión, CQD empezará a recopilar y procesar datos. Tenga en cuenta que puede tardar una o más horas en procesar los datos suficientes para mostrar resultados significativos en los informes.

CQD muestra la calidad de las llamadas y reuniones, a nivel de toda la organización, para Microsoft Teams, Skype Empresarial Online y Skype Empresarial Server 2019. 

> [!IMPORTANT]
> Para usar CQD con Skype Empresarial Server 2019, tendrá que [configurar Call Data Connector](/skypeforbusiness/hybrid/configure-call-data-connector). Consulte [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) antes de empezar.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Asignar roles de administrador para el acceso a CQD

Asigne [roles](/microsoft-365/admin/add-users/about-admin-roles) para obtener acceso a CQD a las personas que necesitan usarlo.

Si desea que los usuarios que no son administradores (como ingenieros de soporte técnico y agentes de soporte técnico) usen el Panel de calidad de llamadas, puede asignar a esos usuarios uno de los siguientes roles, que da acceso a CQD. 


|&nbsp;  |Ver informes  |Ver campos EUII  |Crear informes  |Upload datos de creación  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador global     |Sí         |Sí         |Sí         |Sí         |
|Teams Administrador     |Sí         |Sí         |Sí         |Sí         |
|Administrador de comunicaciones de Teams     |Sí         |Sí         |Sí         |Sí         |
|Ingeniero de soporte en comunicaciones de Teams     |Sí         |Sí         |Sí         |No         |
|Especialista de soporte en comunicaciones de Teams     |Sí         |No         |Sí         |No         |
|Administrador de Skype Empresarial     |Sí         |Sí         |Sí         |Sí         |
|Lector global |Sí         |Sí         |Sí         |No         |
|Lector de<sup>informes 1</sup>     |Sí         |No         |Sí         |No         |

<sup>1</sup> Además de leer informes de CQD, [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) el Lector de informes puede ver todos los informes de actividad en el centro de administración y los informes del paquete de contenido de [adopción](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)de Microsoft 365 .

> [!NOTE]
> Si no ve [EUII (información](CQD-data-and-reports.md#euii-data) de identificación del usuario final) y tiene uno de los roles permitidos para ver esta información, tenga en cuenta que CQD solo conserva EUII durante 28 días. Se elimina cualquier cosa anterior a 28 días.

Para obtener más información acerca de estos roles, [vea About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).


Después de la primera vez que inicie sesión, CQD empezará a recopilar y procesar datos. A partir de diciembre de 2019, todavía puede acceder a la versión anterior de CQD (cqd.lync.com), aunque el portal heredado le proporciona un vínculo al último CQD (cqd.teams.microsoft.com). Finalmente, se retirará la versión anterior de CQD. A partir del 1 de julio de 2020, la versión anterior de CQD tiene acceso a los datos del CQD más reciente.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrar datos e informes de creación desde la versión anterior de CQD

> [!IMPORTANT]
> A partir del 1 de julio de 2020, ya no puede migrar los datos de creación y los informes del antiguo CQD ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar Power BI para analizar los datos de Panel de calidad de llamadas

Nuevo en enero de 2020: [Descargar Power BI plantillas de consulta para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Plantillas Power BI personalizables que puede usar para analizar e informar de los datos de CQD.

Lea [Usar Power BI para analizar los datos de CQD](CQD-Power-BI-query-templates.md) para obtener más información.


## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Cargar espacio empresarial y crear datos](CQD-upload-tenant-building-data.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de las llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de secuencia en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar los datos de CQD](CQD-Power-BI-query-templates.md)
