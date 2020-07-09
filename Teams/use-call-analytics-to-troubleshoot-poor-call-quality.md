---
title: Usar análisis de llamadas para solucionar problemas de baja calidad de las llamadas
ms.author: lolaj
author: LolaJacobsen
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
description: 'Usar detalles de análisis de llamadas por usuario: detalles sobre dispositivos, redes y conectividad para solucionar problemas de los usuarios con las llamadas y las reuniones de Microsoft Teams.'
ms.openlocfilehash: fa923a133ac6a56edcbc6f6445d2859692adf351
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085326"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar análisis de llamadas para solucionar problemas de baja calidad de las llamadas

En este artículo se explica cómo usar el análisis de llamadas para solucionar problemas de llamadas o reuniones deficientes de Microsoft Teams para usuarios individuales si es un administrador de equipos o un especialista o Ingeniero de soporte de comunicaciones entre equipos.


  
## <a name="call-analytics-permissions"></a>Permisos de análisis de llamadas

En este artículo se presupone que ya ha configurado el análisis de llamadas. Si no lo ha hecho, lea [configurar análisis de llamadas para Teams](set-up-call-analytics.md).

## <a name="introduction-to-call-analytics"></a>Introducción a análisis de llamadas

El análisis de llamadas muestra información detallada sobre las llamadas de Teams y las reuniones de cada usuario de su cuenta de Office 365. Incluye información sobre dispositivos, redes, conectividad y calidad de las llamadas (cualquiera de estas puede ser un factor importante en la calidad de la llamada o la calidad de la reunión). Si carga la información sobre el edificio, el sitio y el inquilino, esta información también se mostrará para cada llamada y reunión. Use análisis de llamadas para ayudarle a averiguar por qué un usuario tuvo una experiencia o una reunión deficientes.

El análisis de llamadas le muestra cada uno de los tramos de una llamada o reunión, por ejemplo, de un participante a un segundo participante. Al analizar estos detalles, un administrador de equipos puede aislar las áreas problemáticas e identificar la causa de la mala calidad.
   
Como administrador de equipos, obtiene acceso total a todos los datos de análisis de llamadas para cada usuario. Además, puede asignar roles de Azure Active Directory al personal de soporte técnico. Para obtener más información sobre estos roles, lea [conceder permiso para el personal de soporte técnico y para el servicio de asistencia](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff). No se pierda [lo que hace cada equipo la función de soporte técnico?](#what-does-each-teams-support-role-do) a continuación.

## <a name="where-to-find-per-user-call-analytics"></a>Dónde encontrar análisis de llamadas por usuario

Para ver toda la información de las llamadas y los datos de un usuario, vaya al [centro de administración de Teams](https://admin.teams.microsoft.com). En **usuarios**, seleccione un usuario y, a continuación, abra la pestaña **historial de llamadas** en la página de perfil del usuario. Aquí encontrarás todas las llamadas y reuniones de ese usuario durante los últimos 30 días.

![Captura de pantalla de todos los datos de usuario de análisis](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Para obtener información adicional sobre una sesión determinada, incluidos medios detallados y estadísticas de redes, haga clic en una sesión para ver los detalles.

![Captura de pantalla de datos de sesión de usuario de análisis de llamadas](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a>¿Qué hace cada equipo la función de soporte técnico?

El **especialista en soporte técnico de comunicaciones** (soporte técnico de nivel 1) controla los problemas básicos de la calidad de la llamada. No investiguen los problemas de las reuniones. En su lugar, recopilan información relacionada y, a continuación, se comunican con un ingeniero de soporte de comunicaciones. 

El **Ingeniero de soporte técnico de comunicaciones de Teams** (soporte técnico de nivel 2) ve información en registros de llamadas detallados que están ocultos para el especialista de soporte de comunicaciones de Teams. En la tabla siguiente se muestra la información disponible para cada rol de soporte técnico de comunicaciones de Teams.

En la tabla siguiente se indica qué información para cada usuario está disponible para cada rol de soporte técnico de comunicaciones.

|**Actividad**|**Informaciones**|Qué ve el **especialista** de soporte de comunicaciones|Lo que ve el **Ingeniero** de soporte técnico de comunicaciones|
|:-----|:-----|:-----|:-----|
|**Llamadas** <br/> |Nombre de la persona que llama  <br/> |Solo el nombre del usuario para el que buscó el agente.  <br/> |Nombre de usuario.  <br/> |
||Nombre del destinatario  <br/> |Muestra como usuario interno o usuario externo.  <br/> |Nombre del destinatario.  <br/> |
||Número de teléfono del autor de la llamada  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, se ofuscan con símbolos de asterisco. Por ejemplo, 15552823 * * *.  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, se ofuscan con símbolos de asterisco. Por ejemplo, 15552823 * * *.  <br/> |
||Número de teléfono del destinatario  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, se ofuscan con símbolos de asterisco. Por ejemplo, 15552823 * * *.  <br/> |Los números de teléfono completos, excepto los últimos tres dígitos, se ofuscan con símbolos de asterisco. Por ejemplo, 15552823 * * *.  <br/> |
||Detalles de la **llamada**  >  Pestaña **avanzadas** <br/> |La información no se muestra.  <br/> |Se muestran todos los detalles, como los nombres de los dispositivos, la dirección IP, la asignación de subred, etc.  <br/> |
||Detalles de la **llamada**  >  **Avanzada**  >  Pestaña **depurar** <br/> |La información no se muestra.  <br/> |Se muestran todos los detalles, como el sufijo DNS y SSID.  <br/> |
|**Reuniones** <br/> |Nombres de los participantes  <br/> |Solo el nombre del usuario para el que buscó el agente. Otros participantes identificados como usuario interno o usuario externo.  <br/> |Se muestran todos los nombres.  <br/> |
||Recuento de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalles de la sesión  <br/> |Detalles de la sesión que se muestran con excepciones. Solo se muestra el nombre del usuario para el que se ha buscado el agente. Otros participantes identificados como usuario interno o usuario externo. Los últimos tres dígitos de número de teléfono que se han ofuscado con símbolos de asterisco.  <br/> |Detalles de la sesión mostrados. Nombres de usuario y detalles de la sesión mostrados. Los últimos tres dígitos de número de teléfono que se han ofuscado con símbolos de asterisco.  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a>Solucionar problemas de calidad de llamadas de usuario 

1. Abra el centro de administración de Teams ( https://admin.teams.microsoft.com) e inicie sesión con las credenciales de administrador de Teams support o Teams de Teams).

2. En el **Panel**, en **búsqueda de usuario**, comience a escribir el nombre o la dirección SIP del usuario cuyas llamadas desea solucionar, o bien seleccione **Ver usuarios** para ver una lista de usuarios.

3. Seleccione el usuario de la lista.

4. Seleccione **historial de llamadas**y, a continuación, seleccione la llamada o la reunión que desea solucionar.
    
5. Seleccione la pestaña **avanzado** y, a continuación, busque los elementos amarillos y rojos que indican una mala calidad de la llamada o problemas de conexión.
    
    En los detalles de la sesión de cada llamada o reunión, los problemas secundarios aparecen en amarillo. Si algo es amarillo, está fuera del rango normal y puede estar contribuyendo al problema, pero probablemente no sea la causa principal del problema. Si algo está rojo, es un problema importante y es probable que sea la causa principal de la mala calidad de la llamada para esta sesión. 
      
En raras ocasiones, no se reciben datos sobre la calidad de la experiencia de las sesiones de audio. A menudo, esto se debe a una llamada interrumpida o a la finalización de la conexión con el cliente. Cuando esto sucede, la clasificación de la sesión **no está disponible**.
  
En el caso de las sesiones de audio que tienen los datos de calidad de la experiencia (QoE), en la tabla siguiente se describen problemas importantes que califican una sesión como **mala**.
  
|**Problema**|**Área**|**Descripción**|
|:-----|:-----|:-----|
|Configuración de llamadas  <br/> |Sesión  <br/> |El código de error MS-Diag 20-29 indica que se produjo un error en la configuración de la llamada. El usuario no pudo unirse a la llamada o reunión.  <br/> |
|Red de audio clasificada llamada deficiente  <br/> |Sesión  <br/> |Se encontraron problemas de calidad de red (como pérdida de paquetes, vibración, degradación NMOS, RTT o relación de ocultación).  <br/> |
|El dispositivo no funciona  <br/> |Dispositivo  <br/> | Un dispositivo no funciona correctamente. Las relaciones de dispositivo no funcionan: <br/>  DeviceRenderNotFunctioningEventRatio >= 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0,005 <br/> |
   

## <a name="related-topics"></a>Temas relacionados

[Configurar análisis de llamadas por usuario](set-up-call-analytics.md)



  
 
