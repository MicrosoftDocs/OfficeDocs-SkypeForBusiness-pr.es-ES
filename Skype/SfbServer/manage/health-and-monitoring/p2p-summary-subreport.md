---
title: Informe integrado de Resumen de P2P en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Resumen: Obtenga información sobre el subinforme Resumen de P2P en Skype empresarial Server.'
ms.openlocfilehash: 31e17aaff8d449c49a7c51d3dba484e7fab48d55
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817799"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>Informe integrado de Resumen de P2P en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre el subinforme Resumen de P2P en Skype empresarial Server.
  
El Subinforme de resumen de P2P ofrecer una vista general de todas las sesiones de comunicación de punto a punto que han presentado error.
  
## <a name="filters"></a>Filtros

Los filtros ofrecen el medio para devolver un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. La tabla siguiente muestra los filtros que se pueden utilizar con el Subinforme de resumen de P2P.
  
**Filtros del Subinforme de resumen de P2P**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Grupo de servidores** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todos]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información recogida en el Subinforme de resumen de P2P.
  
**Métricas del Subinforme de resumen de P2P**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Total de sesiones** <br/> |No  <br/> |Cantidad total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.  <br/> |
|**Porcentaje de errores** <br/> |No  <br/> |Porcentaje de las sesiones punto a punto con errores.  <br/> |
|**Sesiones por modalidad** <br/> |No  <br/> |Cantidad total de sesiones agrupadas por modalidad (por ejemplo, mensajería instantánea).  <br/> |
|**Porcentaje de errores por modalidad** <br/> |No  <br/> |Cantidad total de sesiones con error agrupadas por modalidad (por ejemplo, mensajería instantánea).  <br/> |
   

