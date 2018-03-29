---
title: Informe de lista de errores en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Resumen: Conozca el informe de lista de fallo en Skype para Business Server 2015.'
ms.openlocfilehash: ef5b11f92997e6919de0fd9056acdeebddc898d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="failure-list-report-in-skype-for-business-server-2015"></a>Informe de lista de errores en Skype Empresarial Server 2015
 
**Resumen:** Obtener información sobre el informe de lista de fallo en Skype para Business Server 2015.
  
El informe de lista de errores proporciona información sobre los usuarios que participaron de una sesión punto a punto o de conferencia con errores. Esta información incluye el URI del usuario que experimentó el problema, además del código de respuesta SIP y el identificador de diagnóstico asociado al error.
  
## <a name="accessing-the-failure-list-report"></a>Obtener acceso al informe de lista de errores

El informe de lista de error se tiene acceso haciendo clic en cualquiera de las siguientes métricas en el [Informe de distribución falla en Skype para Business Server 2015](failure-distribution-report.md):
  
- Principales motivos del diagnóstico (sesiones)
    
- Principales modalidades (sesiones)
    
- Principales grupos de servidores (sesiones)
    
- Principales orígenes (sesiones)
    
- Principales componentes (sesiones)
    
- Principales remitentes (sesiones)
    
- Principales destinatarios (sesiones)
    
- Principales agentes de remitente (sesiones)
    
Desde el informe de error de lista puede tener acceso el [informe de detalle de la sesión de Peer-to-Peer en Skype para Business Server 2015](peer-to-peer-session-detail-report.md) pulsando la métrica de detalle de sesión para una sesión de peer-to-peer. También puede tener acceso al informe de detalles de conferencia si hace clic en la métrica Conferencia para una conferencia.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Aprovechar al máximo el informe de lista de errores

En el informe de lista de errores, puede ver una descripción de cada código de respuesta o cada identificador de diagnóstico. Para ello, simplemente mantenga el mouse sobre ese valor. Por ejemplo, si coloca el mouse sobre el identificador de diagnóstico 7025, verá un mensaje similar al siguiente como información sobre herramientas:
  
Error interno del servidor al crear medios para el usuario.
  
Es importante tener en cuenta que el informe de lista de errores no ofrece una manera directa de recuperar una lista de todos los usuarios que participaron de al menos una sesión con errores, ni tampoco permite determinar qué usuarios participaron con más frecuencia en sesiones con errores. (Por ejemplo, el informe de lista de errores no tiene capacidad de filtrado.) Sin embargo, si exporta los datos y luego convertirla en un archivo de valores separados por comas, puede utilizar Windows PowerShell para encontrar las respuestas a preguntas como las. Por ejemplo, supongamos que guarda los datos en un archivo .CSV con el nombre C:\Data\Failure_List.csv. De acuerdo con los datos guardados en ese archivo, este comando muestra todos los usuarios que participaron de al menos una sesión con errores: 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Ese comando devolverá una lista similar a esta:
  
```
From user
----
Pilar.Ackerman@litwareinc.com
Henrik.Jensen@litwareinc.com
Gilead.Amosnino@litwareinc.com
David.Ahs@litwareinc.com
Ken.Myer@litwareinc.com
```

Estos dos comandos ofrecen información sobre el número total de sesiones con errores de las que participó cada usuario:
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Se devolverán datos similares a estos:
  
```
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
```

## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el informe de lista de errores.
  
## <a name="metrics"></a>Métricas

En la siguiente tabla se detalla la información proporcionada en el informe de lista de errores para cada llamada con errores.
  
**Métricas de informe de lista de errores**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Hora de notificación** <br/> |No  <br/> |Fecha y hora en que se registró el informe.  <br/> |
|**Solicitud** <br/> |No  <br/> |Tipo de solicitud SIP que presentó errores. Por ejemplo, INVITE o BYE.  <br/> |
|**Código de respuesta** <br/> |No  <br/> |Código de respuesta SIP enviado cuando se produjo un error en la conferencia.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.  <br/> |
|**Tiempo coste de conexión (ms)** <br/> |No  <br/> |Cantidad de tiempo (en milisegundos) que necesitó el usuario para unirse a la conferencia.  <br/> |
|**Remitente** <br/> |No  <br/> |Dirección SIP del usuario que inició la llamada.  <br/> |
|**Agente de remitente** <br/> |No  <br/> |Software usado por el extremo del usuario que inició la llamada.  <br/> |
|**Destinatario** <br/> |No  <br/> |Dirección SIP del usuario que recibió la llamada.  <br/> |
   

