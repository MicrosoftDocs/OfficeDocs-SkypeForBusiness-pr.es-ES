---
title: Subinforme de resumen de P2P en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Resumen: Conozca el subinforme Resumen P2P en Skype para Business Server 2015.'
ms.openlocfilehash: db610f21eda9b4decd01facf55f69699c48aa9f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="p2p-summary-subreport-in-skype-for-business-server-2015"></a>Subinforme de resumen de P2P en Skype Empresarial Server 2015
 
**Resumen:** Conozca el subinforme Resumen P2P en Skype para Business Server 2015.
  
El Subinforme de resumen de P2P ofrecer una vista general de todas las sesiones de comunicación de punto a punto que han presentado error.
  
## <a name="filters"></a>Filtros

Los filtros ofrecen el medio para devolver un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. La tabla siguiente muestra los filtros que se pueden utilizar con el Subinforme de resumen de P2P.
  
**Filtros de informe secundario de resumen de P2P**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Grupo de servidores** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todos]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información recogida en el Subinforme de resumen de P2P.
  
**Métricas de subinforme Resumen de P2P**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Total de sesiones** <br/> |No  <br/> |Cantidad total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.  <br/> |
|**Porcentaje de errores** <br/> |No  <br/> |Porcentaje de las sesiones punto a punto con errores.  <br/> |
|**Sesiones por modalidad** <br/> |No  <br/> |Cantidad total de sesiones agrupadas por modalidad (por ejemplo, mensajería instantánea).  <br/> |
|**Porcentaje de errores por modalidad** <br/> |No  <br/> |Cantidad total de sesiones con error agrupadas por modalidad (por ejemplo, mensajería instantánea).  <br/> |
   

