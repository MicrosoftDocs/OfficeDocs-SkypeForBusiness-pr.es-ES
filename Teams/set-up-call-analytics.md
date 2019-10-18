---
title: Configurar el Análisis de llamadas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
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
f1keywords: None
ms.custom:
- Reporting
description: Configure y use el análisis de llamadas para identificar y solucionar problemas de calidad de llamadas de Skype empresarial y Microsoft Teams.
ms.openlocfilehash: 7a91bc0d8503d313ae3b3dfa7ddd32b6a8c5207a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571254"
---
# <a name="set-up-call-analytics"></a>Configurar el Análisis de llamadas

Como administrador de equipos o de Skype empresarial online, puede usar el análisis de llamadas para solucionar problemas de Skype empresarial y problemas de conexión y calidad de llamadas de Microsoft Teams. Es posible que le resulte útil configurar las siguientes capacidades en el análisis de llamadas:
  
- Establezca permisos que permitan a otros personal, como los agentes de asistencia al usuario, usar el análisis de llamadas, pero evitar que tengan acceso al resto del centro de administración de Microsoft Teams. 
    
- Agregue información sobre el edificio, el sitio y el espacio empresarial a los análisis de llamadas mediante la carga de un archivo de datos. TSV o. csv.
    
**El análisis de llamadas ahora está disponible en el centro de administración de Microsoft Teams**. Para ver toda la información de las llamadas y los datos de un usuario, use la pestaña **historial de llamadas** . Para hacerlo, consulte la página de perfil del usuario siguiendo uno de estos procedimientos:

- Busque el usuario desde el panel.
  
   ![Captura de pantalla de búsqueda de usuario en el panel](media/set-up-call-analytics-image-1.png)

-  Seleccione **los usuarios** en la barra de navegación izquierda.

   ![Captura de pantalla del navegación izquierda](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>Establecer permisos de análisis de llamadas
<a name="BKMK_SetCAPerms"></a>

Como administrador, tiene acceso completo a todas las características de análisis de llamadas. Además, puede asignar roles de Azure Active Directory al personal de soporte técnico. Asigne el rol de especialista de soporte de comunicaciones de Teams a los usuarios que deban tener una vista limitada de análisis de llamadas. Asigne el rol de Ingeniero de soporte de comunicaciones de Teams a los usuarios que necesiten acceder a la funcionalidad completa de análisis de llamadas. Ambos niveles de permisos impiden el acceso al resto del centro de administración de Microsoft Teams.

> [!NOTE]
> El rol de especialista en soporte técnico de comunicaciones es equivalente al soporte de nivel 1 y el rol de Ingeniero de soporte técnico de comunicaciones es equivalente al soporte técnico de nivel 2.

Para obtener más información sobre los roles de administrador de Teams, consulte [usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md). 
  
Los especialistas de soporte técnico de comunicaciones tratan problemas básicos de la calidad de la llamada. No investiguen los problemas de las reuniones. En su lugar, recopilan información relacionada y, a continuación, se comunican con un ingeniero de soporte de comunicaciones. Los ingenieros de soporte técnico de comunicaciones ven información en registros de llamadas detallados que están ocultos para los especialistas de soporte técnico de comunicaciones. En la tabla siguiente se ofrece una descripción general de la información que están disponibles para los especialistas de soporte técnico de comunicaciones y los ingenieros de soporte técnico de comunicaciones cuando usan análisis de llamadas.

|**Actividades**|**Información en el análisis de llamadas**|**Qué ve el especialista de soporte de comunicaciones**|**Lo que ve el ingeniero de soporte técnico de comunicaciones**|
|:-----|:-----|:-----|:-----|
|**Llamadas** <br/> |Nombre de la persona que llama  <br/> |Solo el nombre del usuario para el que buscó el agente.  <br/> |Nombre de usuario.  <br/> |
||Nombre del destinatario  <br/> |Muestra como usuario interno o usuario externo.  <br/> |Nombre del destinatario.  <br/> |
||Número de teléfono de la persona que llama  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, se ofuscan con símbolos de asterisco. Por ejemplo, 15552823 * * *.  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, se ofuscan con símbolos de asterisco. Por ejemplo, 15552823 * * *.  <br/> |
||Número de teléfono del destinatario  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, se ofuscan con símbolos de asterisco. Por ejemplo, 15552823 * * *.  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, se ofuscan con símbolos de asterisco. Por ejemplo, 15552823 * * *.  <br/> |
||**Pestaña detalles** > de la llamada**avanzada** <br/> |La información no se muestra.  <br/> |Se muestran todos los detalles, como los nombres de los dispositivos, la dirección IP, la asignación de subred, etc.  <br/> |
||**** > Pestaña de**depuración** **avanzada** > detalles de llamadas <br/> |La información no se muestra.  <br/> |Se muestran todos los detalles, como el sufijo DNS y SSID.  <br/> |
|**Reuniones** <br/> |Nombres de los participantes  <br/> |Solo el nombre del usuario para el que buscó el agente. Otros participantes identificados como usuario interno o usuario externo.  <br/> |Se muestran todos los nombres.  <br/> |
||Recuento de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalles de la sesión  <br/> |Detalles de la sesión que se muestran con excepciones. Solo se muestra el nombre del usuario para el que se ha buscado el agente. Otros participantes identificados como usuario interno o usuario externo. Los últimos tres dígitos de número de teléfono que se han ofuscado con símbolos de asterisco.  <br/> |Detalles de la sesión mostrados. Nombres de usuario y detalles de la sesión mostrados. Los últimos tres dígitos de número de teléfono que se han ofuscado con símbolos de asterisco.  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>Configurar permisos mediante la asignación de roles de administrador
<a name="BKMK_SetUpTier"> </a>

Para obtener información sobre cómo asignar roles administrativos en Azure Active Directory, vea [ver y asignar roles en Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Cargar un archivo. TSV o. csv para agregar información de creación, sitio y espacio empresarial
<a name="BKMK_UploadFiles"> </a>

Puede agregar información de edificio, de sitio y de inquilino a análisis de llamadas al cargar un archivo. csv o. TSV. Con toda esta información, el análisis de llamadas puede asignar direcciones IP a ubicaciones físicas. Usted o los agentes del Departamento de soporte técnico pueden encontrar útil esta información para ayudar a detectar tendencias en los problemas de llamadas. Por ejemplo, ¿por qué muchos usuarios del mismo edificio tienen problemas similares con la calidad de las llamadas? 

Si es un equipo de administración y un administrador de Skype empresarial, puede usar un archivo de datos existente de Teams & el panel de calidad de llamadas de Skype empresarial. En primer lugar, descargue el archivo desde el panel de calidad de llamadas y, a continuación, cárguelo en análisis de llamadas. 

- Para descargar un archivo de datos existente, vaya a la**carga**del**Panel** > de administración > de llamadas de **Microsoft Teams**. En la lista **mis cargas** , haga clic en **Descargar** junto al archivo que desee.

- Para cargar el nuevo archivo, vaya a > **ubicaciones**del **centro de administración de Microsoft Teams**y, a continuación, seleccione **cargar datos de ubicación** o **reemplazar datos de ubicación**.
  
Si va a crear el archivo. TSV o. csv desde el principio, vea [formato del archivo de datos de inquilinos y creación de una estructura de archivo de datos](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Temas relacionados
<a name="BKMK_UploadFiles"> </a>

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análisis de llamadas y Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
