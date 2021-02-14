---
title: Usar análisis de llamadas para solucionar problemas de calidad de llamada deficiente
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
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
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Use los detalles de análisis de llamadas por usuario acerca de los dispositivos, las redes y la conectividad para solucionar problemas de usuario con las llamadas y reuniones de Microsoft Teams.
ms.openlocfilehash: 8bee41e79f2610adcb9a1fed3f895c728526f5ea
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583629"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar análisis de llamadas para solucionar problemas de calidad de llamada deficiente

En este artículo se explica cómo usar el análisis de llamadas para solucionar problemas de la mala calidad de las llamadas o reuniones de Microsoft Teams para usuarios individuales si es administrador de Teams o un ingeniero o especialista en soporte de comunicaciones de Teams.


  
## <a name="call-analytics-permissions"></a>Permisos de Análisis de llamadas

En este artículo se presupone que ya ha configurado el análisis de llamadas. Si no lo ha hecho, lea [Configurar análisis de llamadas para Teams.](set-up-call-analytics.md)

## <a name="introduction-to-call-analytics"></a>Introducción al análisis de llamadas

El análisis de llamadas muestra información detallada sobre las llamadas y reuniones de Teams para cada usuario de su cuenta de Office 365. Incluye información sobre los dispositivos, las redes, la conectividad y la calidad de la llamada (cualquiera de estos puede ser un factor en la mala calidad de las llamadas o reuniones). Si carga información de edificio, sitio e inquilino, esta información también se mostrará para cada llamada y reunión. Use el análisis de llamadas para averiguar por qué un usuario tuvo una experiencia deficiente de llamada o reunión.

El análisis de llamadas muestra cada etapa de una llamada o reunión (por ejemplo, de un participante a un segundo participante). Al analizar estos detalles, un administrador de Teams puede aislar las áreas de problemas e identificar la causa principal de la mala calidad.
   
Como administrador de Teams, tiene acceso total a todos los datos de análisis de llamadas de cada usuario. Además, puede asignar roles de Azure Active Directory al personal de soporte técnico. Para obtener más información sobre estos roles, lea [Conceder permiso para el soporte técnico y el personal del departamento de soporte técnico.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) ¿Qué hace cada rol de [soporte técnico de Teams?](#what-does-each-teams-support-role-do) a continuación.

## <a name="where-to-find-per-user-call-analytics"></a>Dónde buscar análisis de llamadas por usuario

Para ver toda la información y los datos de llamadas de un usuario, vaya al Centro [de administración de Teams.](https://admin.teams.microsoft.com) En **Usuarios,** seleccione un usuario y, a continuación, abra la pestaña Historial **de** llamadas en la página de perfil del usuario. Aquí encontrará todas las llamadas y reuniones de ese usuario durante los últimos 30 días.

![Captura de pantalla de todos los datos de usuario de análisis](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Para obtener información adicional sobre una sesión determinada, incluidas estadísticas detalladas de medios y redes, haga clic en una sesión para ver los detalles.

![Captura de pantalla de datos de sesión de usuario de análisis de llamadas](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a>¿Qué hace cada rol de soporte técnico de Teams?

La especialista **de soporte de comunicaciones** de Teams (soporte técnico de nivel 1) se encarga de los problemas básicos de calidad de las llamadas. No se investigan los problemas relacionados con las reuniones. En su lugar, recopilan información relacionada y luego se escalan a un ingeniero de soporte técnico de comunicaciones. 

El **ingeniero de soporte de comunicaciones** de Teams (soporte técnico de nivel 2) ve información en registros de llamadas detallados que están ocultos para el especialista de soporte de comunicaciones de Teams. En la tabla siguiente se muestra la información disponible para cada rol de soporte técnico de comunicación de Teams.

En la tabla siguiente se indica qué información por usuario está disponible para cada rol de soporte técnico de comunicaciones.

|**Actividad**|**Información**|Lo que ve el especialista de soporte **de** comunicaciones|Lo que ve el ingeniero de **soporte técnico de** comunicaciones|
|:-----|:-----|:-----|:-----|
|**Llamadas** <br/> |Nombre del autor de la llamada  <br/> |Solo el nombre del usuario al que ha buscado el agente.  <br/> |Nombre de usuario.  <br/> |
||Nombre del destinatario  <br/> |Se muestra como usuario interno o usuario externo.  <br/> |Nombre del destinatario.  <br/> |
||Número de teléfono del autor de la llamada  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, están ofuscados con símbolos de asterisco. Por ejemplo, 15552823***.  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, están ofuscados con símbolos de asterisco. Por ejemplo, 15552823***.  <br/> |
||Número de teléfono del destinatario  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, están ofuscados con símbolos de asterisco. Por ejemplo, 15552823***.  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, están ofuscados con símbolos de asterisco. Por ejemplo, 15552823***.  <br/> |
||**Detalles de la llamada**  >  **Pestaña** Avanzadas <br/> |No se muestra la información.  <br/> |Se muestran todos los detalles, como los nombres de dispositivo, la dirección IP, la asignación de subred y mucho más.  <br/> |
||**Detalles de la llamada**  >  **Avanzado**  >  **Pestaña De depuración** <br/> |No se muestra la información.  <br/> |Se muestran todos los detalles, como el sufijo DNS y el SSID.  <br/> |
|**Reuniones** <br/> |Nombres de los participantes  <br/> |Solo el nombre del usuario al que ha buscado el agente. Otros participantes identificados como Usuario interno o Usuario externo.  <br/> |Se muestran todos los nombres.  <br/> |
||Recuento de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalles de la sesión  <br/> |Detalles de la sesión que se muestran con excepciones. Solo se muestra el nombre del usuario al que el agente ha buscado. Otros participantes identificados como Usuario interno o Usuario externo. Los últimos tres dígitos del número de teléfono están ofuscados con símbolos de asterisco.  <br/> |Se muestran los detalles de la sesión. Se muestran los nombres de usuario y los detalles de la sesión. Los últimos tres dígitos del número de teléfono están ofuscados con símbolos de asterisco.  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a>Solucionar problemas de calidad de llamadas de usuario 

1. Abra el Centro de administración de Teams (e inicie sesión con sus credenciales de soporte técnico de comunicaciones de https://admin.teams.microsoft.com) Teams o de administrador de Teams).

2. En el **panel,** en Búsqueda del **usuario,** comience a escribir el nombre o  la dirección SIP del usuario cuyas llamadas desea solucionar, o seleccione Ver usuarios para ver una lista de usuarios.

3. Seleccione el usuario de la lista.

4. Seleccione **el historial de** llamadas y, a continuación, seleccione la llamada o la reunión a la que desea solucionar los problemas.
    
5. Seleccione la **pestaña Avanzadas** y, a continuación, busque elementos amarillos y rojos que indiquen una mala calidad de llamada o problemas de conexión.
    
    En los detalles de la sesión de cada llamada o reunión, los problemas menores aparecen en amarillo. Si algo es amarillo, está fuera del rango normal y puede estar contribuyendo al problema, pero es poco probable que sea la principal causa del problema. Si algo es rojo, es un problema importante y es probable que sea la causa principal de la mala calidad de llamada en esta sesión. 
      
En raras ocasiones, los datos de calidad de la experiencia no se reciben para las sesiones de audio. Esto suele deberse a una llamada que se ha anulado o a que finaliza la conexión con el cliente. Cuando esto ocurre, la clasificación de la sesión **no está disponible.**
  
Para las sesiones de audio que tienen datos de calidad de la experiencia (QoE), en la tabla siguiente se describen los principales problemas que pueden calificar una sesión como **mala.**
  
|**Problema**|**Área**|**Descripción**|
|:-----|:-----|:-----|
|Configuración de llamadas  <br/> |Sesión  <br/> |El código de error Ms-diag 20-29 indica que se produjo un error en la configuración de la llamada. El usuario no pudo unirse a la llamada o a la reunión.  <br/> |
|Llamada mala clasificada como mala en la red de audio  <br/> |Sesión  <br/> |Se han detectado problemas de calidad de red (como pérdida de paquetes, vibración, degradación NMOS, RTT o relación oculta).  <br/> |
|Dispositivo que no funciona  <br/> |Dispositivo  <br/> | Un dispositivo no funciona correctamente. Las relaciones de dispositivos no funcionales son: <br/>  DeviceNotFunctioningEventRatio >= 0,005 <br/>  Device CaptureNotFunctioningEventRatio >= 0,005 <br/> |
   

## <a name="related-topics"></a>Temas relacionados

[Configurar el análisis de llamadas por usuario](set-up-call-analytics.md)



  
 
