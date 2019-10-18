---
title: Ejecutar un informe para mostrar el uso de StaffHub activo
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo ejecutar un informe para obtener una lista de los usuarios activos de StaffHub en su organización.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49091f7d8ada565adea61bf8219c6da828358893
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569668"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a>Ejecutar un informe para mostrar el uso de StaffHub activo

> [!IMPORTANT]
> A partir del 31 de diciembre de 2019, Microsoft StaffHub se retirará. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo. StaffHub dejará de funcionar para todos los usuarios el 31 de diciembre de 2019. Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams. Para obtener más información, consulte [Microsoft StaffHub para que se retirará](microsoft-staffhub-to-be-retired.md).  

Siga los pasos descritos en este artículo para ejecutar un informe para obtener una lista de los usuarios activos de StaffHub de su organización. Esta información puede resultar útil cuando se prepara para [mover los equipos de StaffHub a Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md). En el informe, sabrá quién tiene que incluir en las comunicaciones al cambiar de StaffHub a teams.

Para realizar los pasos de este artículo, debe tener Azure AD Premium.

1. Inicie sesión en el portal de Azure.
2. En el panel de la izquierda, haga clic en el recurso **Azure Active Directory** .
3. En **supervisión**, haga clic en **inicios de sesión**.
4. En **aplicación**, escriba **Microsoft StaffHub**.
5. Establezca el intervalo de fechas que desee para el informe y, a continuación, haga clic en **aplicar**. 

    ![Captura de pantalla que muestra los pasos para mostrar el uso activo de StaffHub](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a>Temas relacionados

- [Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md)
