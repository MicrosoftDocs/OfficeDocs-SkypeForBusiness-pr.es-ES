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
f1keywords:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
ms.custom:
- Reporting
description: Use Analytics llamada obtener información detallada sobre los dispositivos, redes y la conectividad para solucionar problemas de usuario con Microsoft Teams y Skype para reuniones y llamadas de trabajo.
ms.openlocfilehash: b020ae52b9cb7906484c6a0a5403e626ebab68a8
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494240"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas

Análisis de llamada le ayudará a solucionar los problemas de conexión o llamada con Microsoft Teams y Skype para la empresa. Análisis de la llamada, muestran información detallada acerca de los dispositivos, redes y conectividad para las llamadas y las reuniones de cada usuario en su cuenta de Office 365. Si crear, del sitio y de inquilinos se ha agregado información para análisis de llamadas, también se mostrarán para cada llamada y la sesión. Información disponible a través de análisis de llamadas puede ayudar a averiguar por qué un usuario tuvo una llamada deficiente o experiencia de reunión. 
  
## <a name="call-analytics-permissions"></a>Permisos de análisis de llamada

Como la administración, obtener acceso completo a todas las características de análisis de llamadas. Además, puede asignar funciones de Azure Active Directory para el personal de soporte técnico. Asignar la función de especialista de soporte de comunicaciones de los equipos a los usuarios que deben tener una vista limitada del análisis de llamadas. Asigne la función de ingeniero de soporte de comunicaciones de los equipos a los usuarios que necesitan tener acceso a la funcionalidad completa de análisis de llamadas. Ambos niveles de permisos impiden el acceso al resto del centro de administración de Microsoft Teams.

Especialistas en soporte técnico de comunicaciones controlan problemas básicos de calidad de la llamada. No investigar los problemas con las reuniones. En su lugar, puedan recopilan información relacionada y, a continuación, pasar a un ingeniero de soporte técnico de comunicaciones. Los ingenieros de soporte técnico de comunicaciones vea información en el registro de llamadas detallada que está oculta de communications especialistas en soporte técnico. En la siguiente tabla se proporciona una introducción a información disponible a ingenieros de soporte técnico comunicaciones y especialistas en soporte técnico de comunicaciones al usar análisis de llamadas.

El nivel de permisos que se le han asignado determina qué tipo de información tiene acceso a llamar análisis de:
  
- **Los equipos de servicio de administrador o administrador de comunicaciones de los equipos**: tener acceso a toda la información en análisis de llamadas y en el centro de administración de Microsoft Teams.
    
- **Especialista en soporte de comunicaciones de los equipos**: vea un conjunto limitado de datos de análisis de llamadas. Puede solucionar problemas de las llamadas, pero podrá entregar problemas con las reuniones a un ingeniero de soporte de comunicaciones de los equipos. No tiene acceso al resto del centro de administración de Microsoft Teams.
    
- **Ingeniero de soporte de los equipos de comunicaciones**: vea todos los datos disponibles en análisis de llamadas y puede ayudar a solucionar los problemas con las llamadas y las reuniones. No tiene acceso al resto del centro de administración de Microsoft Teams.
    
> [!NOTE]
> La función de especialista en soporte técnico de communications es equivalente a soporte técnico de nivel 1 y la función de ingeniero de soporte técnico de comunicaciones es equivalente a soporte técnico de nivel 2.

Para obtener más información acerca de las funciones de administración de equipos, vea [roles de administrador de equipos de uso de Microsoft para administrar los equipos](using-admin-roles.md). Para obtener una comparación detallada de la compatibilidad con las comunicaciones de los equipos especialista y las comunicaciones de los equipos admite ingeniero de roles, vea [Configurar el análisis de llamadas](set-up-call-analytics.md#set-call-analytics-permissions) 
  
Si necesita ayuda con los permisos, vea sus equipos y Skype para administración empresarial.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Solucionar los problemas de calidad de llamada mediante el análisis de llamadas

1. Inicie sesión con su compatibilidad con las comunicaciones de los equipos o credenciales de administrador de equipos.

2. En el explorador web, vaya a *https://admin.teams.microsoft.com*.
    
3. En el **panel**, en la **Búsqueda de usuarios**, empiece a escribir el nombre o la dirección sip del usuario cuyas llamadas desea solucionar problemas o seleccione **Ver los usuarios** para ver una lista de los usuarios.
    
    ![Captura de pantalla del cuadro de búsqueda de usuarios del análisis de llamadas en el centro de administración de Microsoft Teams.](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. Seleccione el usuario en la lista.

5. Seleccione **historial de llamadas**y, a continuación, seleccione la llamada o reunión que va a solucionar problemas.
    
    ![Captura de pantalla muestra la página de historial de llamadas para un usuario.](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. Seleccione la ficha **Opciones avanzadas** y, a continuación, busque elementos de amarillos y rojos que indican problemas de calidad o conexión llamada deficiente.
    
    En los detalles de la sesión para cada llamada o una reunión, problemas secundarias aparecen en amarillo. (Por ejemplo, en la siguiente captura de pantalla, los valores están en amarillo para vibración Media, la vibración de Max y la frecuencia de pérdida de paquetes promedio.) Si algo es el amarillo, está fuera del intervalo normal y puede contribuir al problema, pero es poco probable que sea la causa principal del problema. Si algo es rojo, es un problema importante, y es probable que es la causa principal de la calidad de llamadas deficientes para esta sesión. 
    
    ![Captura de pantalla muestra la ficha Avanzadas del historial de llamadas de un usuario ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
En algunos casos poco frecuentes, no se recibió calidad de experiencia de datos para las sesiones de audioconferencias. A menudo esto está causado por la llamada quitando y la conexión con el cliente de terminación. Cuando esto ocurre, la clasificación de la sesión no está **disponible**.
  
Para las sesiones de audioconferencias que tienen la calidad de los datos de la experiencia (QoE), en la siguiente tabla se describe los problemas principales que calificar una sesión como **deficiente**.
  
|**Problema**|**Área**|**Descripción**|
|:-----|:-----|:-----|
|Programa de instalación de la llamada  <br/> |Sesión  <br/> |El código de error de que MS-diag 20-29 indica el error en la configuración de la llamada. El usuario no puede unirse a la llamada o reunión.  <br/> |
|Red audio clasificados llamada deficiente  <br/> |Sesión  <br/> |Se encontraron problemas de calidad de red (por ejemplo, la pérdida de paquetes, vibración, degradación de NMOS, RTT o relación oculta). Para obtener más información acerca de las condiciones que se usan para clasificar las llamadas deficientes, vea esta [entrada de blog de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Dispositivo no funciona  <br/> |Dispositivo  <br/> | Un dispositivo no está funcionando correctamente. Dispositivo no funciona proporciones es: <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## <a name="related-topics"></a>Temas relacionados
[Configurar el Análisis de llamadas](set-up-call-analytics.md)

[Análisis de llamadas y Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
