---
title: Usar análisis de llamadas para solucionar problemas de mala calidad de llamada
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
description: Use detalles de análisis de llamadas por usuario sobre dispositivos, redes y conectividad para solucionar problemas de usuario con Microsoft Teams llamadas y reuniones.
ms.openlocfilehash: 4732cf68624b824a452455fc779b22ae7eb32d56
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760569"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Usar análisis de llamadas para solucionar problemas de mala calidad de llamada

Microsoft Teams En este artículo se explica cómo usar el análisis de llamadas para solucionar problemas de mala calidad de una llamada o reunión para usuarios individuales si es un administrador de Teams o un ingeniero de soporte técnico de Teams comunicaciones de Teams.

## <a name="call-analytics-permissions"></a>Permisos de Análisis de llamadas

En este artículo se presupone que ya ha configurado el análisis de llamadas. Si no lo ha hecho, lea Configurar [análisis de llamadas para Teams](set-up-call-analytics.md).

## <a name="introduction-to-call-analytics"></a>Introducción al análisis de llamadas

El análisis de llamadas muestra información detallada sobre Teams llamadas y reuniones para cada usuario de su Office 365 cuenta. Incluye información sobre dispositivos, redes, conectividad y calidad de llamadas (cualquiera de ellos puede ser un factor de mala calidad de las llamadas o reuniones). Si carga información de edificio, sitio e inquilino, esta información también se mostrará para cada llamada y reunión. Use el análisis de llamadas para ayudarle a averiguar por qué un usuario tuvo una mala experiencia de llamada o reunión.

El análisis de llamadas muestra cada tramo de una llamada o reunión, por ejemplo, de un participante a un segundo participante. Al analizar estos detalles, un administrador Teams puede aislar áreas problemáticas e identificar la causa raíz de mala calidad.

Como administrador Teams, obtiene acceso completo a todos los datos de análisis de llamadas para cada usuario. Además, puede asignar roles Azure Active Directory al personal de soporte técnico. Para obtener más información sobre estos roles, lea Conceder [permiso al personal de soporte técnico y soporte técnico.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) No se pierda ¿Qué hace cada Teams de soporte técnico? a [continuación.](#what-does-each-teams-support-role-do)

## <a name="where-to-find-per-user-call-analytics"></a>Dónde buscar análisis de llamadas por usuario

Para ver toda la información de llamada y los datos de un usuario, vaya al [centro de Teams de administración.](https://admin.teams.microsoft.com) En **Usuarios,** seleccione un usuario y, a continuación, abra la pestaña Reuniones **& llamadas** en la página de perfil del usuario. Aquí encontrará todas las llamadas y reuniones de ese usuario durante los últimos 30 días.

![Captura de pantalla de todos los datos de usuario de análisis](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Para obtener información adicional sobre una sesión determinada, incluidos los medios detallados y las estadísticas de redes, haga clic en una sesión para ver los detalles.

![Captura de pantalla de los datos de sesión de usuario de análisis de llamadas](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>¿Qué hace cada Teams de soporte técnico?

El **Teams de soporte técnico de comunicaciones** (soporte técnico de nivel 1) se encarga de los problemas básicos de calidad de las llamadas. No investigan problemas con las reuniones. En su lugar, recopilan información relacionada y luego se escalan a un ingeniero de soporte técnico de comunicaciones.

El **Teams** de soporte técnico de comunicaciones (soporte técnico de nivel 2) ve información en registros de llamadas detallados que están ocultos del Teams de soporte técnico de comunicaciones. En la tabla siguiente se muestra la información disponible para cada Teams de soporte técnico de comunicaciones.

En la tabla siguiente se indica qué información por usuario está disponible para cada rol de soporte técnico de comunicaciones.

|Actividad|Información|Qué comunicaciones<br>el *especialista en* soporte técnico ve|Qué comunicaciones<br>El *ingeniero de* soporte técnico ve|
|---|---|---|---|
|**Llamadas**|Nombre del autor de la llamada|Solo el nombre del usuario cuyo agente ha buscado.|Nombre de usuario.|
||Nombre del destinatario|Se muestra como usuario interno o usuario externo.|Nombre del destinatario.|
||Número de teléfono del autor de la llamada|Todo el número de teléfono excepto los últimos tres dígitos están ofuscados con símbolos de asterisco. Por ejemplo, 15552823 \* \* \* .|Todo el número de teléfono excepto los últimos tres dígitos están ofuscados con símbolos de asterisco. Por ejemplo, 15552823 \* \* \* .|
||Número de teléfono del destinatario|Todo el número de teléfono excepto los últimos tres dígitos están ofuscados con símbolos de asterisco. Por ejemplo, 15552823 \* \* \* .|Todo el número de teléfono excepto los últimos tres dígitos están ofuscados con símbolos de asterisco. Por ejemplo, 15552823 \* \* \* .|
||**Detalles de la llamada** \> **Pestaña** Avanzadas|Información no mostrada.|Se muestran todos los detalles, como nombres de dispositivo, dirección IP, asignación de subred y mucho más.|
||**Detalles de la llamada** \> **Avanzadas** \> **Pestaña Depurar**|Información no mostrada.|Se muestran todos los detalles, como sufijo DNS y SSID.|
|**Reuniones**|Nombres de participantes|Solo el nombre del usuario cuyo agente ha buscado. Otros participantes identificados como Usuario interno o Usuario externo.|Se muestran todos los nombres.|
||Recuento de participantes|Número de participantes.|Número de participantes.|
||Detalles de la sesión|Los detalles de la sesión se muestran con excepciones. Solo se muestra el nombre del usuario cuyo agente ha buscado. Otros participantes identificados como Usuario interno o Usuario externo. Los últimos tres dígitos del número de teléfono están ofuscados con símbolos de asterisco.|Se muestran los detalles de la sesión. Se muestran los nombres de usuario y los detalles de la sesión. Los últimos tres dígitos del número de teléfono están ofuscados con símbolos de asterisco.|
||||

## <a name="troubleshoot-user-call-quality-problems"></a>Solucionar problemas de calidad de llamadas de usuario

1. Abra el Teams de administración ( ) e inicie sesión con su Teams de comunicaciones o <https://admin.teams.microsoft.com> Teams de administrador.

2. En el **panel**, en **Búsqueda** de usuario, empiece a escribir el nombre o  la dirección SIP del usuario cuyas llamadas desea solucionar, o seleccione Ver usuarios para ver una lista de usuarios.

3. Seleccione el usuario de la lista.

4. Seleccione **Historial de llamadas** y, a continuación, seleccione la llamada o reunión que desea solucionar.

5. Seleccione la **pestaña** Avanzadas y, a continuación, busque elementos amarillos y rojos que indiquen problemas de conexión o calidad de llamada deficientes.

   En los detalles de la sesión para cada llamada o reunión, los problemas menores aparecen en amarillo. Si algo es amarillo, está fuera del rango normal y puede estar contribuyendo al problema, pero es poco probable que sea la causa principal del problema. Si algo es rojo, es un problema importante y es probable que sea la causa principal de la mala calidad de la llamada para esta sesión.

En raras ocasiones, los datos de calidad de la experiencia no se reciben para las sesiones de audio. A menudo, esto se debe a una llamada descartada o a la terminación de la conexión con el cliente. Cuando esto ocurre, la clasificación de la sesión **no está disponible.**

Para las sesiones de audio que tienen datos de calidad de la experiencia (QoE), en la tabla siguiente se describen los problemas principales que califican una sesión como **mala.**

|Problema|Área|Descripción|
|---|---|---|
|Configuración de llamadas|Sesión|El código de error Ms-diag 20-29 indica que no se pudo configurar la llamada. El usuario no pudo unirse a la llamada o reunión.|
|Llamada mala clasificada en red de audio|Sesión|Se encontraron problemas de calidad de red (como pérdida de paquetes, vibración, degradación de NMOS, RTT o relación oculta).|
|Dispositivo que no funciona|Dispositivo|Un dispositivo no funciona correctamente. Las relaciones entre dispositivos que no funcionan son: <p> DeviceRenderNotFunctioningEventRatio >= 0,005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0,005|
||||

## <a name="related-topics"></a>Temas relacionados

[Configurar análisis de llamadas por usuario](set-up-call-analytics.md)
