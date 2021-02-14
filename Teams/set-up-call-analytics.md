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
description: Configure análisis de llamadas por usuario para identificar y solucionar problemas de calidad de llamadas de Microsoft Teams.
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581111"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurar análisis de llamadas para Microsoft Teams

Como administrador de Microsoft Teams, puede usar el análisis de llamadas por usuario para solucionar problemas de conexión y calidad de llamadas de Teams para **usuarios individuales.** Para aprovechar al máximo el análisis de llamadas, configure lo siguiente:
  
- Asigne roles de soporte técnico especializados a personas, como agentes del departamento de soporte técnico, para que puedan ver análisis de llamadas para los usuarios. Estos roles de soporte técnico no pueden tener acceso al resto del Centro de administración de Teams. 
    
- Agregue información de creación, sitio e inquilino a los análisis de llamadas por usuario cargando un archivo de datos .tsv o .csv.
    
Cuando esté listo para empezar a usar el análisis de llamadas por usuario, lea Usar análisis de llamadas por usuario para solucionar problemas de [mala calidad de las llamadas.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Conceder permiso al personal de soporte técnico y al departamento de soporte técnico

Como administrador de Teams, tiene acceso total a la información de análisis de llamadas de todos los usuarios. Hemos creado algunos roles especializados de Azure Active Directory que puede asignar a los agentes del departamento de soporte técnico y al personal de soporte técnico para que también puedan acceder al análisis de llamadas por usuario (sin tener acceso al resto del centro de administración de Teams). Asigne el rol **de especialista de** soporte técnico de comunicaciones de Teams a los usuarios que deberían tener una vista limitada del análisis de llamadas por usuario (soporte técnico de nivel 1). Asigne el rol **de ingeniero de soporte técnico de** comunicaciones de Teams a los usuarios que necesiten acceso total al análisis de llamadas por usuario (soporte técnico de nivel 2). Ninguno de los roles tiene acceso al resto del centro de administración de Teams.

Para saber qué hace cada uno de estos roles, lea [¿Qué hace cada rol de soporte técnico de Teams?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)

Para obtener más información sobre los roles de administrador de [Teams, consulte Usar roles de administrador de Teams para administrar Teams.](using-admin-roles.md) Para obtener información sobre cómo asignar roles de administrador en Azure Active Directory, vea [Ver y asignar roles en Azure Active Directory.](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)

Para obtener información sobre cómo asignar roles administrativos en Azure Active Directory, vea [Ver y asignar roles en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Cargar un archivo .tsv o .csv para agregar información de edificio, sitio e inquilino

Puede agregar información de creación, sitio e inquilino a los análisis de llamadas por usuario cargando un archivo .csv o .tsv. Con toda esta información, el análisis de llamadas puede asignar direcciones IP a ubicaciones físicas. Los administradores y agentes del departamento de soporte pueden usar esta información para detectar tendencias en los problemas de las llamadas. Por ejemplo, ¿por qué los usuarios del mismo edificio tienen problemas de calidad de llamadas similares? 

Si es administrador de Teams o Skype Empresarial, puede usar un inquilino existente y crear un archivo de datos desde el panel de calidad de llamadas de Teams o Skype Empresarial ( CQD). Primero, descargue el archivo desde el CQD y, a continuación, súbalo para realizar análisis de llamadas. 

- Para descargar un archivo de datos existente, vaya a Cargar ahora el panel de calidad de llamadas del centro de administración de **Microsoft**  >    >  Teams. En la **lista Mis cargas,** haga clic **en Descargar** junto al archivo que desee. 

- Para cargar el nuevo archivo, vaya a Ubicaciones del centro de administración de **Microsoft Teams** y, a continuación, seleccione Cargar datos de  >  ubicación **o** Reemplazar datos **de ubicación.**
  
Si está creando el archivo .tsv o .csv desde cero, vea Cargar inquilino [y generar datos.](CQD-upload-tenant-building-data.md)
  
## <a name="related-topics"></a>Temas relacionados

[Usar análisis de llamadas por usuario para solucionar problemas de mala calidad de las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
