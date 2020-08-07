---
title: Configurar análisis de llamadas para Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configure los análisis de llamadas por usuario para identificar y solucionar problemas de calidad de llamadas de Microsoft Teams.
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581111"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurar análisis de llamadas para Microsoft Teams

Como administrador de Microsoft Teams, puede usar análisis de llamadas por usuario para solucionar problemas de calidad y problemas de conexión de **los equipos de los usuarios individuales**. Para sacar el máximo provecho de los análisis de llamadas, configure lo siguiente:
  
- Asigne roles de soporte técnico especializados a personas, como agentes de asistencia, para permitirles ver análisis de llamadas para los usuarios. Estos roles de soporte no pueden acceder al resto del centro de administración de Teams. 
    
- Agregue información sobre edificios, sitios y espacios empresariales a análisis de llamadas por usuario al cargar un archivo de datos. TSV o. csv.
    
Cuando esté listo para empezar a usar análisis de llamadas por usuario, lea [usar análisis de llamadas por usuario para solucionar problemas de baja calidad de las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Otorgar permiso al personal de soporte técnico y de asistencia

Como administrador de equipos, tiene acceso completo a información de análisis de llamadas para todos los usuarios. Hemos creado algunos roles de Azure Active Directory especializados que puede asignar al personal de soporte técnico y a los agentes del Departamento de soporte técnico para que también puedan tener acceso al análisis de llamadas por usuario (sin tener acceso al resto del centro de administración de Teams). Asigne el rol de **especialista de soporte de comunicaciones de Teams** a los usuarios que tengan una vista limitada de análisis de llamadas por usuario (soporte técnico de nivel 1). Asigne el rol de **Ingeniero de soporte de comunicaciones de Teams** a los usuarios que necesiten acceso total a análisis de llamadas por usuario (soporte técnico de nivel 2). Ninguna de las funciones tiene acceso al resto del centro de administración de Teams.

Para obtener información sobre lo que hace cada uno de estos roles, vea [¿Qué hace cada equipo con soporte técnico](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Para obtener más información sobre los roles de administrador de Teams, vea [usar roles de administrador de Teams para administrar equipos](using-admin-roles.md). Para obtener información sobre cómo asignar roles de administrador en Azure Active Directory, vea [ver y asignar roles en Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Para obtener información sobre cómo asignar roles administrativos en Azure Active Directory, vea [ver y asignar roles en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Cargar un archivo. TSV o. csv para agregar información de creación, sitio y espacio empresarial

Puede agregar información de creación, sitio y espacio empresarial a análisis de llamadas por usuario al cargar un archivo. csv o. TSV. Con toda esta información, el análisis de llamadas puede asignar direcciones IP a ubicaciones físicas. Los administradores y los agentes del Departamento de soporte técnico pueden usar esta información para ayudar a detectar tendencias en problemas de llamadas. Por ejemplo, ¿por qué los usuarios del mismo edificio tienen problemas similares con la calidad de las llamadas? 

Si es un equipo de administración o un administrador de Skype empresarial, puede usar un inquilino existente y crear un archivo de datos de los equipos o del panel de calidad de llamadas de Skype empresarial (CQD). En primer lugar, descargará el archivo desde el CQD y luego lo cargará en el análisis de llamadas. 

- Para descargar un archivo de datos existente, vaya a la carga del panel de administración de llamadas de **Microsoft Teams**  >  **Call Quality Dashboard**  >  **Upload now**. En la lista **mis cargas** , haga clic en **Descargar** junto al archivo que desee. 

- Para cargar el nuevo archivo, vaya a ubicaciones del **centro de administración de Microsoft Teams**  >  **Locations**y, a continuación, seleccione **cargar datos de ubicación** o **reemplazar datos de ubicación**.
  
Si va a crear el archivo. TSV o. csv desde el principio, vea [cargar espacio empresarial y datos de compilación](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Temas relacionados

[Usar análisis de llamadas por usuario para solucionar problemas de baja calidad de las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
