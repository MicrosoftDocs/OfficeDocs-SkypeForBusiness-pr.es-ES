---
title: Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Use los detalles de Análisis de llamadas por usuario sobre dispositivos, redes y conectividad para solucionar problemas de usuario con las llamadas y reuniones de Microsoft Teams.
ms.openlocfilehash: c83ecbad418dc471f1db2c9c71b88fa621fe4a11
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397101"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas

En este artículo se explica cómo usar Análisis de llamadas para solucionar problemas de calidad deficiente de las llamadas o reuniones de Microsoft Teams para usuarios individuales si tiene el rol de ingeniero de administrador de Teams, de soporte técnico de comunicaciones de Teams o de soporte técnico de comunicaciones de Teams.

## <a name="call-analytics-permissions"></a>Permisos de Análisis de llamadas

En este artículo se supone que ya ha configurado Análisis de llamadas. Si no lo ha hecho, lea [Configurar análisis de llamadas para Teams](set-up-call-analytics.md).

## <a name="introduction-to-call-analytics"></a>Introducción a Análisis de llamadas

Análisis de llamadas muestra información detallada sobre las llamadas y reuniones de Teams para cada usuario de su cuenta de Office 365. Incluye información sobre los dispositivos, las redes, la conectividad y la calidad de las llamadas (cualquiera de estos puede ser un factor de mala calidad en las llamadas o las reuniones). Si carga información de compilaciones, sitios e inquilinos, esta información también se mostrará para cada llamada y reunión. Use Análisis de llamadas para ayudarle a averiguar por qué un usuario tuvo una experiencia de llamada o reunión deficiente.

Análisis de llamadas muestra cada etapa de una llamada o reunión , por ejemplo, de un participante a un segundo participante. Mediante el análisis de estos detalles, un administrador de Teams puede aislar áreas problemáticas e identificar la causa raíz de la mala calidad.

Como administrador de Teams, obtendrá acceso total a todos los datos de Análisis de llamadas de cada usuario. Además, puede asignar roles de Azure Active Directory para dar soporte al personal. Para obtener más información sobre estos roles, lea [Conceder permiso al personal de soporte técnico y soporte técnico](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff). No se pierda [¿Qué hace cada rol de soporte técnico de Teams?](#what-does-each-teams-support-role-do) a continuación.

## <a name="where-to-find-per-user-call-analytics"></a>Dónde buscar análisis de llamadas por usuario

Para ver toda la información y los datos de las llamadas de un usuario, vaya al [Centro de administración de Teams](https://admin.teams.microsoft.com). En **Usuarios**, seleccione un usuario y abra la pestaña **Reuniones & Llamadas** en la página de perfil del usuario. Aquí encontrará todas las llamadas y reuniones de ese usuario durante los últimos 30 días.

![Captura de pantalla de todos los datos de usuario de análisis.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Para obtener información adicional sobre una sesión determinada, incluyendo estadísticas detalladas de medios y redes, haga clic en una sesión para ver los detalles.

![Captura de pantalla de datos de sesión de usuario de análisis de llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

En este vídeo se muestran los pasos para ver las reuniones y la información de llamadas de un usuario.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53x2e?autoplay=false]

## <a name="what-does-each-teams-support-role-do"></a>¿Qué hace cada rol de soporte técnico de Teams?

El **especialista en soporte técnico de comunicaciones de Teams** (soporte técnico de nivel 1) se encarga de los problemas básicos de calidad de las llamadas. No investigan los problemas relacionados con las reuniones. En su lugar, recopilan información relacionada y después se convierten en ingenieros de soporte técnico de comunicaciones de Teams.

El **ingeniero de soporte** técnico de comunicaciones de Teams (soporte técnico de nivel 2) ve información en registros de llamadas detallados que están ocultos al especialista de soporte técnico de comunicaciones de Teams. En la tabla siguiente se muestra la información disponible para cada rol de soporte técnico de comunicación de Teams.

La tabla siguiente indica qué información por usuario está disponible para cada rol de soporte técnico de comunicaciones.

|Actividad|Información|¿Cuáles son las comunicaciones?<br>*el especialista de* soporte técnico ve|¿Cuáles son las comunicaciones?<br>*el ingeniero de* soporte técnico ve|
|---|---|---|---|
|**Llamadas**|Nombre del autor de la llamada|Solo el nombre del usuario para el que el agente ha buscado.|Nombre de usuario.|
||Nombre del destinatario|Se muestra como Usuario interno o Usuario externo.|Nombre del destinatario.|
||Número de teléfono del autor de la llamada|Todo el número de teléfono, excepto los últimos tres dígitos, se ofusca con símbolos de asterisco. Por ejemplo, 15552823\*\*\*.|Todo el número de teléfono, excepto los últimos tres dígitos, se ofusca con símbolos de asterisco. Por ejemplo, 15552823\*\*\*.|
||Número de teléfono del destinatario|Todo el número de teléfono, excepto los últimos tres dígitos, se ofusca con símbolos de asterisco. Por ejemplo, 15552823\*\*\*.|Todo el número de teléfono, excepto los últimos tres dígitos, se ofusca con símbolos de asterisco. Por ejemplo, 15552823\*\*\*.|
||**Detalles de** \> la llamada **Pestaña Avanzadas**|Información no mostrada.|Se muestran todos los detalles, como los nombres de los dispositivos, la dirección IP, la asignación de subred y mucho más.|
||**Detalles de** \> la llamada **Avanzada** \> **Pestaña Depurar**|Información no mostrada.|Se muestran todos los detalles, como sufijo DNS y SSID.|
|**Reuniones**|Nombres de los participantes|Solo el nombre del usuario para el que el agente ha buscado. Otros participantes identificados como Usuario interno o Usuario externo.|Se muestran todos los nombres.|
||Recuento de participantes|Número de participantes.|Número de participantes.|
||Detalles de la sesión|Los detalles de la sesión se muestran con excepciones. Solo se muestra el nombre del usuario para el que ha buscado el agente. Otros participantes identificados como Usuario interno o Usuario externo. Los últimos tres dígitos del número de teléfono se ofuscaron con símbolos de asterisco.|Se muestran los detalles de la sesión. Se muestran los nombres de usuario y los detalles de la sesión. Los últimos tres dígitos del número de teléfono se ofuscaron con símbolos de asterisco.|
||||

> [!NOTE]
> La información contenida en la sección 'Otros' de la pestaña Avanzadas y en la pestaña Depuración contiene datos de diagnóstico de telemetría y servicio destinados a ayudar a los ingenieros de soporte técnico de Microsoft. Sin el contexto de los datos adicionales disponibles para los ingenieros de soporte técnico, puede parecer redundantes, inexactos o confusos. Aunque la ponemos a disposición de los usuarios avanzados que buscan otro nivel de detalle en la solución de problemas de llamadas, no recomendamos realizar juicios basados en estos datos sin soporte técnico de Microsoft.

## <a name="troubleshoot-user-call-quality-problems"></a>Solucionar problemas de calidad de llamadas de usuario

1. Abra el Centro de administración de Teams (<https://admin.teams.microsoft.com>) e inicie sesión con el soporte técnico de comunicaciones de Teams o las credenciales de administrador de Teams.

2. En el **panel**, en **Búsqueda de usuarios**, empiece a escribir el nombre o la dirección SIP del usuario cuyas llamadas quiera solucionar o seleccione **Ver usuarios** para ver una lista de usuarios.

3. Seleccione el usuario de la lista.

4. Selecciona **Historial de llamadas** y, a continuación, selecciona la llamada o reunión que quieres solucionar.

5. Selecciona la pestaña **Avanzadas** y, a continuación, busca elementos amarillos y rojos que indiquen mala calidad de la llamada o problemas de conexión.

   En los detalles de la sesión de cada llamada o reunión, los problemas menores aparecen en amarillo. Si algo es amarillo, está fuera del rango normal y puede estar contribuyendo al problema, pero es poco probable que sea la principal causa del problema. Si algo está en rojo, es un problema importante y es probable que sea la causa principal de la mala calidad de la llamada para esta sesión.

En raras ocasiones, no se reciben datos de calidad de la experiencia para las sesiones de audio. A menudo esto es causado por una llamada caída o cuando la conexión con el cliente termina. Cuando esto ocurre, la clasificación de la sesión **no está disponible**.

En las sesiones de audio que sí tienen datos de Calidad de experiencia (QoE), en la tabla siguiente se describen los principales problemas que califican a una sesión como **mala**.

|Problema|Área|Descripción|
|---|---|---|
|Configuración de llamadas|Sesión|El código de error Ms-diag 20-29 indica que no se pudo realizar la configuración de la llamada. El usuario no pudo unirse a la llamada o a la reunión.|
|Llamadas de red de audio clasificadas como malas|Sesión|Se encontraron problemas de calidad de red (como pérdida de paquetes, vibración, degradación de NMOS, RTT o relación oculta).|
|El dispositivo no funciona|Dispositivo|Un dispositivo no funciona correctamente. Las relaciones de no funcionamiento del dispositivo son: <p> DeviceRenderNotFunctioningEventRatio >= 0,005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0.005|
||||

## <a name="related-topics"></a>Temas relacionados

[Configurar análisis de llamadas por usuario](set-up-call-analytics.md)
