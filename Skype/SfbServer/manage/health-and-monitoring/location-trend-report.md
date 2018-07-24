---
title: Informe de tendencias de ubicación en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
description: 'Resumen: Información sobre el informe de tendencias de ubicación en Skype para Business Server.'
ms.openlocfilehash: 007bd549dbccffdbbe83ff4d96ebd09b83b7c5e3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973608"
---
# <a name="location-trend-report-in-skype-for-business-server"></a>Informe de tendencias de ubicación en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de tendencias de ubicación en Skype para Business Server.
  
El informe de tendencias de ubicación proporciona información sobre la tendencia de calidad de las llamadas de las ubicaciones de red.
  
## <a name="filters"></a>Filtros

Los filtros son un modo de recuperar un conjunto de datos más específico o de ver los datos devueltos de diferentes formas. Por ejemplo, el informe de tendencias de ubicación permite filtrar los datos devueltos por tipo de acceso (acceso interno o externo) o por tipo de conexión de red (cableada o inalámbrica). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día o semana.
  
En la siguiente tabla se muestran los filtros que se pueden usar con el informe de tendencias de ubicación. 
  
**Filtros del informe de tendencias de ubicación**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 01/01/2011 y una fecha de finalización del 28/02/2011, aparecerán los datos correspondientes a los días entre el 01/08/2011 a las 12:00 horas y el 01/09/2011 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
|**Tipo de acceso** <br/> | Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Interno <br/>  Externo <br/> |
|**Tipo de red** <br/> | Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Cableada <br/>  Inalámbrica <br/> |
|**VPN** <br/> | Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  VPN <br/>  Distinto de VPN <br/> |
   

