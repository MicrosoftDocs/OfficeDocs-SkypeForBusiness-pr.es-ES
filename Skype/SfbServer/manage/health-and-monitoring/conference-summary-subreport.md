---
title: Subinforme de resumen de conferencia en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
description: 'Resumen: Conozca el subinforme Resumen de conferencia en Skype para Business Server 2015.'
ms.openlocfilehash: 39c71ebfa5798d861a9b8afd8865486dba033c1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conference-summary-subreport-in-skype-for-business-server-2015"></a>Subinforme de resumen de conferencia en Skype Empresarial Server 2015
 
**Resumen:** Conozca el subinforme Resumen de conferencia en Skype para Business Server 2015.
  
El Subinforme de resumen de conferencia proporciona información general de sesiones de conferencia fallidas. Estas sesiones fallidas se dividen además por tipo de sesión: sesiones de foco y sesiones MCU.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el Subinforme de resumen de conferencia.
  
**Filtros de informe secundario de resumen de conferencia**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Grupo de servidores** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todos]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
   
## <a name="metrics"></a>Métricas

La siguiente tabla contiene la información que recoge el Subinforme de resumen de conferencia.
  
**Métricas de informe secundario de resumen de conferencia**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Total de conferencias** <br/> |No  <br/> |Cantidad total de conferencias que ha tenido lugar.  <br/> |
|**Total de sesiones de conferencias** <br/> |No  <br/> |Cantidad total de sesiones de conferencia. Una única conferencia puede tener varias sesiones; por ejemplo, una conferencia podría incluir tanto una sesión de foco como una sesión MCU.  <br/> |
|**Porcentaje de errores de sesión generales** <br/> |No  <br/> |Porcentaje de todas las conferencias fallidas.  <br/> |
|**Sesiones de foco** <br/> |No  <br/> |Cantidad total de sesiones de foco.  <br/> |
|**Porcentaje de errores de foco** <br/> |No  <br/> |Porcentaje de sesiones de foco fallidas.  <br/> |
|Sesiones MCU  <br/> |No  <br/> |Cantidad total de sesiones MCU.  <br/> |
|**Porcentaje de errores de MCU** <br/> |No  <br/> |Porcentaje de sesiones MCU fallidas.  <br/> |
|**Sesiones MCU por modalidad** <br/> |No  <br/> |Cantidad total de sesiones MCU, agrupadas por modalidad (por ejemplo, conferencia de mensajería instantánea).  <br/> |
|**Porcentaje de errores por modalidad** <br/> |No  <br/> |Porcentaje de sesiones MCU fallidas, agrupadas por modalidad (por ejemplo, conferencia de mensajería instantánea).  <br/> |
   

