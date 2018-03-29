---
title: Informe de detalles de conferencia en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Resumen: Conozca el informe de detalle de la conferencia usado en Skype para Business Server 2015.'
ms.openlocfilehash: 4c55b2f339aa3d591f01d73d0f60d8fbc0bb483f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conference-detail-report-in-skype-for-business-server-2015"></a>Informe de detalles de conferencia en Skype Empresarial Server 2015
 
**Resumen:** Obtener información sobre el informe de detalle de la conferencia usado en Skype para Business Server 2015.
  
El Informe de detalles de conferencia proporciona información detallada sobre todos los usuarios que participaron en una conferencia. Por ejemplo, puede ver información como la fecha y hora en que un usuario se conectó a la conferencia, la fecha y hora en la que el usuario se desconectó de la conferencia y el agente del usuario del extremo que se utilizó para conectar a ese usuario a la conferencia. También puede ver información sobre el rol del usuario en cada conferencia (por ejemplo, moderador o asistente). Quizás lo más importante, puede ver rápidamente qué usuarios se conectan satisfactoriamente y finalizan la conferencia y qué usuarios no pudieron conectarse satisfactoriamente ni finalizar la conferencia.
  
## <a name="accessing-the-conference-detail-report"></a>Acceso al Informe de detalles de conferencia

Es posible obtener acceso al Informe de detalles de conferencia a partir de los siguientes informes:
  
- El [Informe de Control de admisión llamar en Skype para Business Server 2015](call-admission-control-report.md) (haciendo clic en la métrica de detalle para una conferencia)
    
- El [Informe de lista de error en Skype para Business Server 2015](failure-list-report.md) (haciendo clic en la métrica de conferencia)
    
- El [Informe de actividad de usuario en Skype para Business Server 2015](user-activity-report.md) (haciendo clic en la métrica de conferencia URI)
    
Desde el informe de detalle de la conferencia puede tener acceso el [Informe de diagnóstico en Skype para el año 2015 de Server Business](diagnostic-report.md) pulsando la métrica del informe de diagnóstico (detalles).
  
## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el Informe de detalles de conferencia.
  
## <a name="metrics"></a>Métricas

La siguiente tabla muestra la información brindada en la sección Información de conferencia del Informe de detalles de conferencia.
  
**Métricas de la información de conferencia**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**URI de conferencia** <br/> |URI asignado a la conferencia. Por ejemplo:  <br/> SIP:kmyer@litwareinc.com;GRUU;OPAQUE=App:conf:Focus:ID:drg2y8v4  <br/> |
|**FQDN del grupo de servidores** <br/> |Nombre de dominio completo del grupo de registrador o servidor perimetral involucrado en una sesión.  <br/> |
|**Hora de inicio** <br/> |Fecha y hora en que comenzó la conferencia.  <br/> |
|**Organizador** <br/> |Dirección SIP del usuario que organizó la conferencia  <br/> |
|**Hora de finalización** <br/> |Fecha y hora en que la conferencia finalizó.  <br/> |
   
La siguiente tabla muestra la información brindada en la sección Participación de conferencia del Informe de detalles de conferencia.
  
**Métricas de participación de conferencia**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**Usuario** <br/> |Dirección SIP del usuario que participó en la conferencia.  <br/> |
|**Rol** <br/> |Rol (por ejemplo, Moderador) que ocupó el participante de la conferencia.  <br/> |
|**Conectividad** <br/> |Conectividad de red (normalmente Desde conexión interna o Desde conexión externa) del participante.  <br/> |
|**Hora de conexión** <br/> |Fecha y hora en que el participante se unió a la conferencia.  <br/> |
|**Hora de desconexión** <br/> |Fecha y hora en que el participante abandonó la conferencia.  <br/> |
|**Agente de usuario** <br/> |Identificador para el software utilizado por extremo del participante.  <br/> |
|**Informes de diagnósticos** <br/> |Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.  <br/> |
   
En la siguiente tabla se enumera la información proporcionada en la sección de las modalidades de conferencia del informe Detalle de conferencia.
  
**Métricas de las modalidades de conferencia**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**Usuario** <br/> |Dirección SIP del usuario que participó en la conferencia.  <br/> |
|**Hora de conexión** <br/> |Fecha y hora en que el participante se unió a la conferencia.  <br/> |
|**Hora de desconexión** <br/> |Fecha y hora en que un participante abandonó la conferencia.  <br/> |
|**URI del servidor de conferencia** <br/> |URI para el servidor de conferencia utilizado en la conferencia.  <br/> |
|**Informes de diagnósticos** <br/> |Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.  <br/> |
   

