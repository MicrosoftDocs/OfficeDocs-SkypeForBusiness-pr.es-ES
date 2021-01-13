---
title: Informe de detalles de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Resumen: obtenga información sobre el informe de detalles de conferencias usado en Skype Empresarial Server.'
ms.openlocfilehash: 245691fcb304a872942be4d5a9aabe8183b4db14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816910"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>Informe de detalles de conferencia en Skype Empresarial Server

**Resumen:** Obtenga información sobre el informe de detalles de conferencia usado en Skype Empresarial Server.

El Informe de detalles de conferencia proporciona información detallada sobre todos los usuarios que participaron en una conferencia. Por ejemplo, puede ver información como la fecha y hora en que un usuario se conectó a la conferencia, la fecha y hora en la que el usuario se desconectó de la conferencia y el agente del usuario del extremo que se utilizó para conectar a ese usuario a la conferencia. También puede ver información sobre el rol del usuario en cada conferencia (por ejemplo, moderador o asistente). Quizás lo más importante, puede ver rápidamente qué usuarios se conectan satisfactoriamente y finalizan la conferencia y qué usuarios no pudieron conectarse satisfactoriamente ni finalizar la conferencia.

## <a name="accessing-the-conference-detail-report"></a>Acceso al Informe de detalles de conferencia

Es posible acceder al Informe de detalles de conferencia a partir de los siguientes informes:

- El [Call Admission Control Report](call-admission-control-report.md) (haciendo clic en la métrica Detalle de una conferencia)

- El [Failure List Report](failure-list-report.md) (haciendo clic en la métrica Conferencia)

- El [User Activity Report](call-diagnostic-reports-per-user.md) (haciendo clic en la métrica URI de conferencia)

Desde el Informe de detalles de conferencia, puede acceder al [Diagnostic Report](diagnostic-report.md) haciendo clic en la métrica Informe de diagnósticos (Detalle).

## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el Informe de detalles de conferencia.

## <a name="metrics"></a>Métricas

La siguiente tabla muestra la información brindada en la sección Información de conferencia del Informe de detalles de conferencia.

**Métricas de Información de conferencia**


| **Nombre**                 | **Descripción**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **URI de conferencia** <br/> | URI asignado a la conferencia. Por ejemplo:  <br/> sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4  <br/> |
| **FQDN del grupo de servidores** <br/>      | Nombre de dominio completo del grupo de registrador o servidor perimetral involucrado en una sesión.  <br/>                             |
| **Hora de inicio** <br/>     | Fecha y hora en que comenzó la conferencia.  <br/>                                                                          |
| **Organizador** <br/>      | Dirección SIP del usuario que organizó la conferencia  <br/>                                                               |
| **Hora de finalización** <br/>       | Fecha y hora en que finalizó la conferencia.  <br/>                                                                            |

La siguiente tabla muestra la información brindada en la sección Participación de conferencia del Informe de detalles de conferencia.

**Métricas de Participación de conferencia**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**Usuario** <br/> |Dirección SIP del usuario que participó en la conferencia.  <br/> |
|**Rol** <br/> |Rol (por ejemplo, Moderador) que ocupó el participante de la conferencia.  <br/> |
|**Conectividad** <br/> |Conectividad de red (normalmente Desde conexión interna o Desde conexión externa) del participante.  <br/> |
|**Hora de conexión** <br/> |Fecha y hora en que el participante se unió a la conferencia.  <br/> |
|**Hora de desconexión** <br/> |Fecha y hora en que el participante abandonó la conferencia.  <br/> |
|**Agente de usuario** <br/> |Identificador del software usado por el punto de conexión del participante.  <br/> |
|**Informes de diagnósticos** <br/> |Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.  <br/> |

En la tabla siguiente se muestra la información proporcionada en la sección Modalidades de conferencia del Informe de detalles de conferencia.

**Métricas de Modalidades de conferencia**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**Usuario** <br/> |Dirección SIP del usuario que participó en la conferencia.  <br/> |
|**Hora de conexión** <br/> |Fecha y hora en que el participante se unió a la conferencia.  <br/> |
|**Hora de desconexión** <br/> |Fecha y hora en que un participante abandonó la conferencia.  <br/> |
|**URI del servidor de conferencia** <br/> |URI para el servidor de conferencia utilizado en la conferencia.  <br/> |
|**Informes de diagnósticos** <br/> |Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.  <br/> |


