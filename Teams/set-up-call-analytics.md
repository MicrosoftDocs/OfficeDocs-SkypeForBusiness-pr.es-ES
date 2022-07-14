---
title: Configurar análisis de llamadas para Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configure análisis de llamadas por usuario para identificar y solucionar problemas de calidad de llamadas de Microsoft Teams.
ms.openlocfilehash: bcfe39ccdd9a1a751b49cdc8d0f433e3707635e3
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789945"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurar análisis de llamadas para Microsoft Teams

Como administrador de Microsoft Teams, puede usar análisis de llamadas por usuario para solucionar problemas de conexión y calidad de las llamadas de Teams para **usuarios individuales**. Para aprovechar al máximo el análisis de llamadas, configure lo siguiente:
  
- Asigne roles de soporte técnico especializados a personas, como agentes del departamento de soporte técnico, para permitirles ver el análisis de llamadas de los usuarios. Estos roles de soporte técnico no pueden acceder al resto del Centro de administración de Teams. 
    
- Agregue información de compilación, sitio e inquilino al análisis de llamadas por usuario cargando un archivo de datos .tsv o .csv.
    
Cuando esté listo para empezar a usar el análisis de llamadas por usuario, lea Usar análisis de [llamadas por usuario para solucionar problemas de mala calidad de llamada](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Conceder permiso al personal de soporte técnico y soporte técnico

Como administrador de Teams, tiene acceso completo a la información de análisis de llamadas para todos los usuarios. Hemos creado algunos roles de Azure Active Directory especializados que puede asignar para dar soporte al personal y a los agentes del departamento de soporte técnico para que también puedan acceder al análisis de llamadas por usuario (sin tener acceso al resto del centro de administración de Teams). Asigne el rol **de especialista en soporte** técnico de comunicaciones de Teams a los usuarios que deberían tener una vista limitada del análisis de llamadas por usuario (soporte técnico de nivel 1). Asigne el rol de ingeniero de soporte técnico de **comunicaciones de Teams** a los usuarios que necesitan acceso total al análisis de llamadas por usuario (soporte técnico de nivel 2). Ninguno de los roles tiene acceso al resto del Centro de administración de Teams.

Para saber qué hace cada uno de estos roles, lea [¿Qué hace cada rol de soporte técnico de Teams](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Para obtener más información sobre los roles de administrador de Teams, consulte [Usar roles de administrador de Teams para administrar Teams](using-admin-roles.md). Para obtener información sobre cómo asignar roles de administrador en Azure Active Directory, vea [Ver y asignar roles en Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Para obtener información sobre cómo asignar roles administrativos en Azure Active Directory, consulte [Ver y asignar roles en Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Cargar un archivo .tsv o .csv para agregar información de inquilino, sitio y compilación

Puede agregar información de inquilino, sitio y compilación al análisis de llamadas por usuario cargando un archivo .csv o .tsv. Con toda esta información, los análisis de llamadas pueden asignar direcciones IP a ubicaciones físicas. Los administradores y los agentes del departamento de soporte técnico pueden usar esta información para ayudar a detectar tendencias en los problemas de llamada. Por ejemplo, ¿por qué los usuarios del mismo edificio tienen problemas similares con la calidad de las llamadas? 

Si es administrador de Teams o Skype Empresarial, puede usar un inquilino existente y crear un archivo de datos desde Teams o Skype Empresarial Panel de calidad de llamadas (CQD). En primer lugar, descargue el archivo desde el CQD y, después, cárguelo para llamar al análisis. 

- Para descargar un archivo de datos existente, vaya a **Análisis del** Centro  >  de **administración de Microsoft Teams**& informes **Cargar ahora** el **panel** >  >  de calidad de llamadas. En la lista **Mis cargas** , haga clic en **Descargar** junto al archivo que desee. 

- Para cargar el nuevo archivo, vea [Agregar y actualizar etiquetas de informes](/microsoftteams/learn-more-about-site-upload).
  
Si va a crear el archivo .tsv o .csv desde cero, consulte [Cargar inquilinos y generar datos](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Temas relacionados

[Usar análisis de llamadas por usuario para solucionar problemas de calidad de llamadas deficientes](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)
