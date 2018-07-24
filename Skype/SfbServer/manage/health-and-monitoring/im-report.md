---
title: Informe de mensajería instantánea de punto a punto en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 'Resumen: Información sobre el informe de mensajería instantánea de punto a punto en Skype para Business Server.'
ms.openlocfilehash: e7e65e11d6a8710c4a37fc3afe0a983d5ce9b14d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968617"
---
# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a>Informe de mensajería instantánea de punto a punto en Skype para Business Server
 
**Resumen:** Obtenga información sobre el informe de mensajería instantánea de punto a punto en Skype para Business Server.
  
El informe de mensajería instantánea punto a punto ofrece información de tendencias sobre las sesiones de mensajería instantánea (MI) punto a punto, desglosadas por grupo de servidores y por tipo de autenticación. El informe puede mostrar la cantidad total de sesiones mantenidas durante el período de tiempo especificado (por ejemplo, día a día u hora a hora) o bien, puede mostrar la cantidad total de mensajes instantáneos enviados durante ese período de tiempo.
  
## <a name="accessing-the-peer-to-peer-im-report"></a>Obtener acceso al informe de mensajería instantánea de punto a punto

Puede obtener acceso el informe de mensajería instantánea de punto a punto sólo por abrir el [informe de resumen de actividad punto a punto en Skype para Business Server](peer-to-peer-activity-summary-report.md) y, a continuación, haciendo clic en cualquiera de las métricas siguientes:
  
- Total de sesiones de mensajería instantánea de punto a punto
    
- Total de mensajes instantáneos de punto a punto
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Aprovechar al máximo el informe de mensajería instantánea de punto a punto

De manera predeterminada, el informe de mensajería instantánea de punto a punto le muestra el recuento de mensajes por hora (o día, en función de su configuración). Pero, también puede elegir ver el día por sesiones por hora. Para ello, haga clic en **Mostrar u ocultar parámetros** en la esquina superior derecha de la ventana Informes y, luego, haga clic en **Recuento de sesiones** en la lista **Informe por**.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de mensajería instantánea punto a punto.
  
**Filtros del informe de mensajería instantánea punto a punto**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio 07/07/2015 y una fecha de finalización 28/02/2015, se mostrarán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
|**Informe por** <br/> | Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes: <br/>  Recuento de sesiones <br/>  Recuento de mensajes <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Métricas para la mensajería instantánea punto a punto por grupo

En la tabla siguiente, se muestra la información proporcionada en el informe de mensajería instantánea punto a punto.
  
**Métricas para la mensajería instantánea punto a punto por grupo**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Grupo de servidores** <br/> |No  <br/> |Nombre del grupo de registrador o servidor perimetral.  <br/> |
|**Fecha y hora** <br/> |No  <br/> |Fecha y hora en las que tuvo lugar la sesión.  <br/> |
|**Total** <br/> |No  <br/> |Cantidad total de sesiones o recuento total de mensajes.  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Métricas para la mensajería instantánea punto a punto por tipo de autenticación

En la tabla siguiente, se muestra la información proporcionada en el informe de mensajería instantánea punto a punto para cada tipo de autenticación utilizado por los participantes de una sesión punto a punto.
  
**Métricas para la mensajería instantánea punto a punto por tipo de autenticación**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Tipo de autenticación** <br/> |No  <br/> | Tipo de autenticación utilizado por los participantes de la sesión. Los valores suelen ser los siguientes: <br/>  Enterprise <br/>  Federated <br/>  PIC <br/> |
|**Fecha y hora** <br/> |No  <br/> |Fecha y hora en las que tuvo lugar la sesión.  <br/> |
|**Total** <br/> |No  <br/> |Cantidad total de sesiones o recuento total de mensajes.  <br/> |
   

