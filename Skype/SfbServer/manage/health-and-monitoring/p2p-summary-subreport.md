---
title: Subinforme de resumen P2P en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Summary: Learn about the P2P Summary Subreport in Skype Empresarial Server.'
ms.openlocfilehash: e8296604626b143bb143ea2acbdf8e6875e1acf6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861327"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>Subinforme de resumen P2P en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el subinforme de resumen P2P en Skype Empresarial Server.
  
El Subinforme de resumen de P2P ofrecer una vista general de todas las sesiones de comunicación de punto a punto que han presentado error.
  
## <a name="filters"></a>Filtros

Los filtros ofrecen el medio para devolver un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. La tabla siguiente muestra los filtros que se pueden utilizar con el Subinforme de resumen de P2P.
  
**Filtros del Subinforme de resumen de P2P**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**To** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 1:00 PM  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Grupo** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todo]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información recogida en el Subinforme de resumen de P2P.
  
**Métricas del Subinforme de resumen de P2P**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Total de sesiones** <br/> |No  <br/> |Número total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.  <br/> |
|**Porcentaje de errores** <br/> |No  <br/> |Porcentaje de las sesiones punto a punto con errores.  <br/> |
|**Sesiones por modalidad** <br/> |No  <br/> |Número total de sesiones agrupadas por modalidad (por ejemplo, mensajería instantánea).  <br/> |
|**Porcentaje de errores por modalidad** <br/> |No  <br/> |Número total de sesiones con error agrupadas por modalidad (por ejemplo, mensajería instantánea).  <br/> |
   

