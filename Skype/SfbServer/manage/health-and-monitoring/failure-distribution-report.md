---
title: Informe de distribución de errores en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
description: 'Resumen: Obtenga información sobre el informe de distribución de errores en Skype empresarial Server.'
ms.openlocfilehash: d9e7d2ac0ff10743c69bee665be3878ac9009933
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305699"
---
# <a name="failure-distribution-report-in-skype-for-business-server"></a>Informe de distribución de errores en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre el informe de distribución de errores en Skype empresarial Server.
  
El Informe de distribución de errores clasifica las sesiones con error en las categorías siguientes:
  
- Principales motivos de diagnóstico
    
- Principales modalidades
    
- Principales grupos de servidores
    
- Principales fuentes
    
- Principales componentes
    
- Principales remitentes
    
- Principales destinatarios
    
- Agentes de usuarios de origen principales
    
Puede usar estas categorías para determinar dónde se está produciendo exactamente el problema y, en determinados casos, por qué se está produciendo el problema. Por ejemplo, supongamos que ha registrado 242 sesiones de audio/vídeo con error en un día determinado. El Informe de distribución de errores puede mostrar que 237 de dichas sesiones con error tuvieron lugar en el grupo de Dublín. Esto supone un buen punto de partida para el seguimiento y el diagnóstico de las causas de dichos errores. Si hace clic en el grupo de Dublín en la categoría **Grupos principales**, verá un Informe de distribución de errores solo para dicho grupo. Desde ahí, podrá comenzar a analizar las razones por las que el grupo de Dublín tenía tantos problemas.
  
## <a name="viewing-the-failure-distribution-report"></a>Visualización del Informe de distribución de errores

Puede tener acceso al Informe de distribución de errores desde cualquiera de los informes siguientes haciendo clic en la métrica **Volumen de errores esperados** o **Volumen de errores inesperados**:
  
- [Informe de errores principales en Skype empresarial Server](top-failures-report.md)
    
- [Informe de diagnóstico de conferencia en Skype empresarial Server](conference-diagnostic-report.md)
    
- [Informe de diagnóstico de actividad de punto a punto en Skype empresarial Server](peer-to-peer-activity-diagnostic-report.md)
    
En el informe de distribución de errores, puede hacer clic en cualquiera de las siguientes métricas para ver el [Informe de la lista de errores en Skype empresarial Server](failure-list-report.md):
  
- Principales motivos del diagnóstico (sesiones)
    
- Principales modalidades (sesiones)
    
- Principales grupos de servidores (sesiones)
    
- Principales orígenes (sesiones)
    
- Principales componentes (sesiones)
    
- Principales remitentes (sesiones)
    
- Principales destinatarios (sesiones)
    
- Principales agentes de remitente (sesiones)
    
## <a name="using-the-failure-distribution-report"></a>Uso del Informe de distribución de errores

Dependiendo del tamaño de su monitor y de la resolución de la pantalla, es posible que algunos de los datos del Informe de distribución de errores aparezcan truncados. Esto se produce, sobre todo, en métricas como, por ejemplo, las de los agentes de usuarios que tienen etiquetas muy largas. Por ejemplo, es posible que un agente de usuario con el nombre "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" solo se muestre de forma parcial en la pantalla: 
  
UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...
  
Afortunadamente, basta con mantener el mouse sobre el valor truncado para ver la etiqueta completa.
  
Una métrica interesante que puede filtrar con el Informe de distribución de errores es la del Id. de diagnóstico. Si se muestra el mismo Id. de diagnóstico en otros informes, podrá filtrar dicho Id. de diagnóstico en el Informe de distribución de errores y obtener una vista detallada del lugar exacto y la frecuencia con la que se ha informado de dicho Id. en la sesión con errores.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de distribución de errores le permite filtrar por tipo de actividad (sesión de punto a punto o sesión de conferencias) o por el Id. de diagnóstico que contenía cada sesión con errores.
  
La siguiente tabla muestra los filtros que puede utilizar con el informe de resumen de conferencia.
  
**Filtros de informes de distribución de errores**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Grupo de servidores** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todos]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.<br/> |
|**Tipo de actividad** <br/> | Tipo de actividad para filtrar. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Punto a punto <br/>  Una conferencia <br/> |
|**Categoría de sesión** <br/> | Indica si la actividad correspondiente se desarrolló correctamente o causó errores. Seleccione una de las siguientes opciones: <br/>  [Todas] <br/>  Correcto <br/>  Error esperado <br/>  Error inesperado <br/>  Un "error esperado" es aquel que se prevé que vaya a producirse. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen. Un "error inesperado" es aquel que se produce en un sistema que está aparentemente en buen estado. Por ejemplo, una llamada no tendría que finalizarse si el autor de la llamada está en espera. De ser así, tal cosa se identificaría como un error inesperado. <br/> |
|**Id. de diagnóstico** <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.  <br/> |
   
## <a name="metrics-for-top-diagnostic-reasons"></a>Métricas para motivos del diagnóstico destacados

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en el Id. de diagnóstico que aparece con mayor frecuencia.
  
**Métricas para motivos del diagnóstico destacados**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Clasificación** <br/> |No  <br/> |Clasificación relativa de sesiones con errores basándose en los Id. de diagnóstico. El Id. de diagnóstico es un identificador único (con el formato de un encabezado de diagnóstico MS) adjunto a un mensaje SIP que suele proporcionar información útil para resolver errores.  <br/> |
|**Principales motivos de diagnóstico** <br/> |No  <br/> |Id. de diagnóstico generado en una sesión.  <br/> |
|**Sesiones** <br/> |No  <br/> |Cantidad total de sesiones con errores en las que generó el Id. de diagnóstico especificado.  <br/> |
   
## <a name="metrics-for-top-modalities"></a>Métricas para modalidades destacadas

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en las modalidades de sesiones que experimentaron más errores.
  
**Métricas para modalidades destacadas**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Clasificación** <br/> |No  <br/> |Clasificación relativa de sesiones con errores basándose en los tipos de sesiones (por ejemplo, una conferencia de audio o vídeo o una sesión de transferencia de archivos de punto a punto).  <br/> |
|**Principales modalidades** <br/> |No  <br/> |Tipo de sesión.  <br/> |
|**Sesiones** <br/> |No  <br/> |Cantidad total de sesiones con errores en las que aparece la modalidad especificada.  <br/> |
   
## <a name="metrics-for-top-pools"></a>Métricas para grupos destacados

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los grupos de servidores que experimentaron más errores.
  
**Métricas para grupos destacados**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Clasificación** <br/> |No  <br/> |Clasificación relativa de las sesiones erróneas basadas en el grupo de registradores o el servidor perimetral donde se realizó la sesión.  <br/> |
|**Principales grupos de servidores** <br/> |No  <br/> |Nombre del grupo de registradores o del servidor perimetral.  <br/> |
|**Sesiones** <br/> |No  <br/> |Número total de sesiones erróneas por grupo de registradores o servidor perimetral.  <br/> |
   
## <a name="metrics-for-top-sources"></a>Métricas para fuentes destacadas

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los equipos que experimentaron más errores.
  
**Métricas para fuentes destacadas**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Clasificación** <br/> |No  <br/> |Clasificación relativa de sesiones con errores por equipo.  <br/> |
|**Principales fuentes** <br/> |No  <br/> |Nombre del equipo que participó en la sesión con errores.  <br/> |
|**Sesiones** <br/> |No  <br/> |Cantidad total de sesiones con errores por equipo.  <br/> |
   
## <a name="metrics-for-top-components"></a>Métricas para componentes destacados

En la siguiente tabla se enumera la información proporcionada en el informe de distribución de errores a partir de los componentes que experimentaron más errores.
  
**Métricas para componentes destacados**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Clasificación** <br/> |No  <br/> |Clasificación relativa de las sesiones fallidas basadas en el componente (por ejemplo, ExumRouting, GroupChat o MediationServer).  <br/> |
|**Principales componentes** <br/> |No  <br/> |Nombre del componente que participó en la sesión con errores.  <br/> |
|**Sesiones** <br/> |No  <br/> |Cantidad total de sesiones con errores por componente.  <br/> |
   
## <a name="metrics-for-top-from-users"></a>Métricas para usuarios destacados

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los usuarios que experimentaron más errores al intentar llamar a otra persona (denominados remitentes).
  
**Métricas para usuarios destacados**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Clasificación** <br/> |No  <br/> |Clasificación relativa de sesiones con errores basándose en el usuario invitado a unirse a la sesión.  <br/> |
|**Principales remitentes** <br/> |No  <br/> |Dirección SIP del usuario invitado a unirse a la sesión.  <br/> |
|**Sesiones** <br/> |No  <br/> |Cantidad total de sesiones con error por usuario.  <br/> |
   
## <a name="metrics-for-top-to-users"></a>Métricas para principales destinatarios

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los usuarios que experimentaron más errores cuando otro usuario intentó llamarlos (denominados destinatarios).
  
|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Clasificación** <br/> |No  <br/> |Clasificación relativa de sesiones con errores basándose en el usuario que inició la sesión.  <br/> |
|**Principales destinatarios** <br/> |No  <br/> |Dirección SIP del usuario que inició la sesión.  <br/> |
|**Sesiones** <br/> |No  <br/> |Cantidad total de sesiones con error por usuario.  <br/> |
   
## <a name="metrics-for-top-user-agents"></a>Métricas para agentes de usuario destacados

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en el software extremo que experimentó más errores.
  
**Métricas para agentes de usuario destacados**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Clasificación** <br/> |No  <br/> |Clasificación relativa de sesiones con errores basándose en el agente de usuario (software) que participa en la sesión. Por ejemplo: RTCC/4.0.0.0 Enrutamiento de entrada/4.0.0.0.  <br/> |
|**Principales agentes de usuario** <br/> |No  <br/> |Nombre del agente de usuario que participó en la sesión con errores.  <br/> |
|**Sesiones** <br/> |No  <br/> |Cantidad total de sesiones con errores por agente de usuario.  <br/> |
   

