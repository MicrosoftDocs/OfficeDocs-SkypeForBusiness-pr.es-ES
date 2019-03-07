---
title: Configurar el Análisis de llamadas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Configurar y usar el análisis de llamada para identificar y solucionar problemas de Skype para profesionales y Microsoft Teams problemas de calidad de llamada.
ms.openlocfilehash: e54668afc6e71b519f1656443a25e17274b22fb2
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462836"
---
# <a name="set-up-call-analytics"></a>Configurar el Análisis de llamadas

Como un equipos o Skype para administración en línea de negocio, puede usar el análisis de llamadas para solucionar problemas de Skype para la empresa y Microsoft Teams llamar a problemas de calidad y de conexión. Es posible que encuentre útil para configurar las siguientes funciones en análisis de llamadas:
  
- Establecer los permisos que permiten que a otros personal, por ejemplo, los agentes del departamento de soporte técnico, use llamar análisis, pero impedir que obtener acceso al resto del centro de administración de Microsoft Teams. 
    
- Agregar información del inquilino, de sitio y de creación para llamar a análisis al cargar un archivo de datos .tsv o .csv.
    
**Análisis de llamar ahora está disponible en el centro de administración de equipos de Microsoft**. Para ver toda la información de llamada y los datos para un usuario, utilice la ficha **Historial de llamadas** . Para ello, ¿está buscando en la página de perfil del usuario, realice una de las siguientes opciones:

- Para el usuario desde el panel de búsqueda.
  
   ![Captura de pantalla de búsqueda de usuarios en el panel](media/set-up-call-analytics-image-1.png)

-  Seleccione **los usuarios** en el panel de navegación izquierdo.

   ![Captura de pantalla de exploración izquierda](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>Establecer permisos de análisis de llamadas
<a name="BKMK_SetCAPerms"></a>

Como la administración, obtener acceso completo a todas las características de análisis de llamadas. Además, puede asignar funciones de Azure Active Directory para el personal de soporte técnico. Asignar la función de especialista de soporte de comunicaciones de los equipos a los usuarios que deben tener una vista limitada del análisis de llamadas. Asigne la función de ingeniero de soporte de comunicaciones de los equipos a los usuarios que necesitan tener acceso a la funcionalidad completa de análisis de llamadas. Ambos niveles de permisos impiden el acceso al resto del centro de administración de Microsoft Teams.

> [!NOTE]
> La función de especialista en soporte técnico de communications es equivalente a soporte técnico de nivel 1 y la función de ingeniero de soporte técnico de comunicaciones es equivalente a soporte técnico de nivel 2.

Para obtener más información acerca de las funciones de administración de equipos, vea [roles de administrador de equipos de uso de Microsoft para administrar los equipos](using-admin-roles.md). 
  
Especialistas en soporte técnico de comunicaciones controlan problemas básicos de calidad de la llamada. No investigar los problemas con las reuniones. En su lugar, puedan recopilan información relacionada y, a continuación, pasar a un ingeniero de soporte técnico de comunicaciones. Los ingenieros de soporte técnico de comunicaciones vea información en el registro de llamadas detallada que está oculta de communications especialistas en soporte técnico. En la siguiente tabla se proporciona una introducción a información disponible a ingenieros de soporte técnico comunicaciones y especialistas en soporte técnico de comunicaciones al usar análisis de llamadas.

|**Actividad**|**Información de análisis de llamada**|**¿Qué las comunicaciones admiten especialista verá**|**¿Qué las comunicaciones admiten ingeniero verá**|
|:-----|:-----|:-----|:-----|
|**Llamadas** <br/> |Nombre del autor de la llamada  <br/> |El nombre del usuario para el que desea buscar el agente.  <br/> |Nombre de usuario.  <br/> |
||Nombre del destinatario  <br/> |Se muestra como usuario interno o externo.  <br/> |Nombre del destinatario.  <br/> |
||Número de teléfono del autor de la llamada  <br/> |Número de teléfono completo, excepto los últimos tres dígitos son confusos con los símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |Número de teléfono completo, excepto los últimos tres dígitos son confusos con los símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |
||Número de teléfono del destinatario  <br/> |Número de teléfono completo, excepto los últimos tres dígitos son confusos con los símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |Número de teléfono completo, excepto los últimos tres dígitos son confusos con los símbolos de asterisco. Por ejemplo, 15552823 ***.  <br/> |
||**Detalles de llamadas** > ficha**Opciones avanzadas** <br/> |Información que no se muestra.  <br/> |Todos los detalles que se muestran, como los nombres de dispositivo, dirección IP, asignación de subred y mucho más.  <br/> |
||**Detalles de llamadas** > **Avanzadas** > ficha**Depurar** <br/> |Información que no se muestra.  <br/> |Todos los detalles que se muestran como sufijo DNS y SSID.  <br/> |
|**Reuniones** <br/> |Nombres de los participantes  <br/> |El nombre del usuario para el que desea buscar el agente. Demás participantes identificados como usuario interno o externo.  <br/> |Todos los nombres que se muestran.  <br/> |
||Recuento de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalles de la sesión  <br/> |Detalles de la sesión se muestra con excepciones. Se muestra sólo el nombre del usuario para el que desea buscar el agente. Demás participantes identificados como usuario interno o externo. Los últimos tres dígitos del número de teléfono confusos con los símbolos de asterisco.  <br/> |Detalles de la sesión que se muestra. Los nombres de usuario y se muestra detalles de la sesión. Los últimos tres dígitos del número de teléfono confusos con los símbolos de asterisco.  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>Configurar los permisos mediante la asignación de roles de administrador
<a name="BKMK_SetUpTier"> </a>

Para obtener información sobre cómo asignar funciones administrativas en Azure Active Directory, vea [Ver y asignar funciones en Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Cargue un archivo .tsv o .csv para agregar la creación de sitios y la información de inquilinos
<a name="BKMK_UploadFiles"> </a>

Puede agregar información del inquilino, de sitio y de creación para análisis de llamar a cargar un archivo .csv o .tsv. Con toda esta información, llame al análisis puede asignar direcciones IP a ubicaciones físicas. Usted o departamento de soporte técnico los agentes pueden encontrar esta información útil para ayudar a las tendencias de manchas de color en problemas de llamada. Por ejemplo, ¿por qué son similares de muchos usuarios en el mismo edificio tener llamar a problemas de calidad? 

Si es un equipos y Skype para administración empresarial, puede usar un archivo de datos existente desde el & los equipos Skype para Business Dashboard de calidad de llamadas. En primer lugar, descargue el archivo desde el panel de calidad de llamadas y, a continuación, cárguela en análisis de llamadas. 

- Para descargar un archivo de datos existente, vaya al **Centro de administración de equipos de Microsoft** > **Panel de calidad de llamada** > **Cargar ahora**. En la lista **Mis cargas** , haga clic en **Descargar** junto al archivo que desee.

- Para cargar el nuevo archivo, vaya a **Centro de administración de equipos de Microsoft** > **ubicaciones**y, a continuación, seleccione **cargar datos de ubicación** o **reemplazar los datos de ubicación**.
  
Si está creando el archivo .tsv o .csv desde el principio, vea [formato y estructura de archivos de datos de creación de archivos de datos de inquilinos](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Temas relacionados
<a name="BKMK_UploadFiles"> </a>

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análisis de llamadas y Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
