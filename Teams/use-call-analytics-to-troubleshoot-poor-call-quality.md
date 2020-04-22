---
title: Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
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
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Use los detalles de análisis de llamadas sobre dispositivos, redes y conectividad para solucionar problemas de los usuarios con Microsoft Teams y las llamadas y reuniones de Skype empresarial.
ms.openlocfilehash: 05af82a942d54e0f97f2be2b176091f19186cbf4
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43749567"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas

El análisis de llamadas le ayuda a solucionar problemas de llamadas o de conexión con Microsoft Teams y Skype empresarial. El análisis de llamadas muestra información detallada sobre los dispositivos, las redes y la conectividad de las llamadas y reuniones de cada usuario en su cuenta de Office 365. Si la información de creación, sitio y espacio empresarial se ha agregado a análisis de llamadas, también se mostrará para cada llamada y sesión. La información que se ofrece a través de análisis de llamadas puede ayudarte a determinar por qué un usuario tenía una mala llamada o una experiencia de reunión. 
  
## <a name="call-analytics-permissions"></a>Permisos de análisis de llamadas

Como administrador, tiene acceso total a todas las características de análisis de llamadas. Además, puede asignar roles de Azure Active Directory al personal de soporte técnico. Asigne el rol de especialista de soporte de comunicaciones de Teams a los usuarios que deban tener una vista limitada de análisis de llamadas. Asigne el rol de Ingeniero de soporte de comunicaciones de Teams a los usuarios que necesiten acceder a la funcionalidad completa de análisis de llamadas. Ambos niveles de permisos impiden el acceso al resto del centro de administración de Microsoft Teams.

Los especialistas de soporte técnico de comunicaciones tratan problemas básicos de la calidad de la llamada. No investiguen los problemas de las reuniones. En su lugar, recopilan información relacionada y, a continuación, se comunican con un ingeniero de soporte de comunicaciones. Los ingenieros de soporte técnico de comunicaciones ven información en registros de llamadas detallados que están ocultos para los especialistas de soporte técnico de comunicaciones. En la tabla siguiente se ofrece una descripción general de la información que están disponibles para los especialistas de soporte técnico de comunicaciones y los ingenieros de soporte técnico de comunicaciones cuando usan análisis de llamadas.

El nivel de permisos que se le asigna determina el tipo de información a la que tiene acceso en el análisis de llamadas:
  
- **Administrador de servicios de Teams o administrador de comunicaciones**de Teams: tiene acceso a toda la información de análisis de llamadas y del centro de administración de Microsoft Teams.
    
- **Especialista de soporte técnico de comunicaciones de Teams**: en el análisis de llamadas verá un conjunto limitado de datos. Puede solucionar problemas de llamadas, pero podrá entregar problemas con las reuniones a un ingeniero de soporte técnico de comunicaciones de Teams. No tiene acceso al resto del centro de administración de Microsoft Teams.
    
- **Ingeniero de soporte técnico de comunicaciones de Teams**: puede ver todos los datos disponibles en el análisis de llamadas y puede ayudarle a solucionar problemas con las llamadas y las reuniones. No tiene acceso al resto del centro de administración de Microsoft Teams.
    
> [!NOTE]
> El rol de especialista en soporte técnico de comunicaciones es equivalente al soporte de nivel 1 y el rol de Ingeniero de soporte técnico de comunicaciones es equivalente al soporte técnico de nivel 2.

Para obtener más información sobre los roles de administrador de Teams, consulte [usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md). Para obtener una comparación detallada de los roles de Ingeniero de soporte de comunicaciones de Teams y Team Communications support, consulte [configurar análisis de llamadas](set-up-call-analytics.md#set-call-analytics-permissions) 
  
Consulte sus equipos y el administrador de Skype empresarial si necesita ayuda con los permisos.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Solucionar problemas de calidad de llamadas con el análisis de llamadas

1. Inicie sesión con el soporte técnico de comunicaciones de Teams o las credenciales de administrador de Teams.

2. En el explorador Web, vaya *https://admin.teams.microsoft.com*a.
    
3. En el **Panel**, en **búsqueda de usuario**, empiece a escribir el nombre o la dirección SIP del usuario cuyas llamadas desea solucionar o seleccione **Ver usuarios** para ver una lista de usuarios.
    
    ![Captura de pantalla del cuadro de búsqueda de usuario de análisis de llamadas](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. Seleccione el usuario de la lista.

5. Seleccione **historial de llamadas**y, a continuación, seleccione la llamada o la reunión que desea solucionar.  Se devolverá un máximo de 500 registros.
    
    ![Captura de pantalla de la página del historial de llamadas de un usuario.](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. Seleccione la pestaña **avanzado** y, a continuación, busque los elementos amarillos y rojos que indican una mala calidad de la llamada o problemas de conexión.
    
    En los detalles de la sesión de cada llamada o reunión, los problemas secundarios aparecen en amarillo. (Por ejemplo, en la siguiente captura de pantalla, los valores están en amarillo para las vibraciones medias, la vibración máxima y la tasa de pérdida de paquetes promedio.) Si algo es amarillo, está fuera del rango normal y puede estar contribuyendo al problema, pero probablemente no sea la causa principal del problema. Si algo está rojo, es un problema importante y es probable que sea la causa principal de la mala calidad de la llamada para esta sesión. 
    
    ![Captura de pantalla de la pestaña avanzadas del historial de llamadas de un usuario ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
En raras ocasiones, no se reciben datos sobre la calidad de la experiencia de las sesiones de audio. A menudo, esto se debe a la cancelación de la llamada y a la conexión con el cliente que finaliza. Cuando esto sucede, la clasificación de la sesión **no está disponible**.
  
En el caso de las sesiones de audio que tienen los datos de calidad de la experiencia (QoE), en la tabla siguiente se describen problemas importantes que califican una sesión como **mala**.
  
|**Problema**|**Área**|**Descripción**|
|:-----|:-----|:-----|
|Configuración de llamadas  <br/> |Sesión  <br/> |El código de error MS-Diag 20-29 indica que se produjo un error en la configuración de la llamada. El usuario no pudo unirse a la llamada o reunión.  <br/> |
|Red de audio clasificada llamada deficiente  <br/> |Sesión  <br/> |Se encontraron problemas de calidad de red (como pérdida de paquetes, vibración, degradación NMOS, RTT o relación de ocultación). Para obtener más información sobre las condiciones que se usan para clasificar las llamadas incorrectas, vea esta [entrada de blog de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|El dispositivo no funciona  <br/> |Dispositivo  <br/> | Un dispositivo no funciona correctamente. Las relaciones de dispositivo no funcionan: <br/>  DeviceRenderNotFunctioningEventRatio >= 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0,005 <br/> |
   
## <a name="related-topics"></a>Temas relacionados
[Configurar el Análisis de llamadas](set-up-call-analytics.md)

[Análisis de llamadas y Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
