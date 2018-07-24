---
title: Informe de lista de errores en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Resumen: Información sobre el informe de lista de errores en Skype para Business Server.'
ms.openlocfilehash: 3d40d7d73b6a4cb63e3885736a9a32f8b64ed989
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992636"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Informe de lista de errores en Skype para Business Server 
 
**Resumen:** Obtenga información sobre el informe de lista de errores en Skype para Business Server.
  
El informe de lista de errores proporciona información sobre los usuarios que participaron de una sesión punto a punto o de conferencia con errores. Esta información incluye el URI del usuario que experimentó el problema, además del código de respuesta SIP y el identificador de diagnóstico asociado al error.
  
## <a name="accessing-the-failure-list-report"></a>Obtener acceso al informe de lista de errores

El informe de lista de errores se tiene acceso haciendo clic en cualquiera de las siguientes métricas en el [Informe de distribución de errores en Skype para Business Server](failure-distribution-report.md):
  
- Principales motivos del diagnóstico (sesiones)
    
- Principales modalidades (sesiones)
    
- Principales grupos de servidores (sesiones)
    
- Principales orígenes (sesiones)
    
- Principales componentes (sesiones)
    
- Principales remitentes (sesiones)
    
- Principales destinatarios (sesiones)
    
- Principales agentes de remitente (sesiones)
    
Desde el informe de lista de errores, puede acceder al [informe de detalles de la sesión de punto a punto en Skype para Business Server](peer-to-peer-session-detail-report.md) haciendo clic en la métrica de todos los detalles de la sesión de una sesión de punto a punto. También puede tener acceso al informe de detalles de conferencia si hace clic en la métrica Conferencia para una conferencia.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Aprovechar al máximo el informe de lista de errores

En el informe de lista de errores, puede ver una descripción de cada código de respuesta o cada identificador de diagnóstico. Para ello, simplemente mantenga el mouse sobre ese valor. Por ejemplo, si coloca el mouse sobre el identificador de diagnóstico 7025, verá un mensaje similar al siguiente como información sobre herramientas:
  
Error interno del servidor al crear medios para el usuario.
  
Es importante tener en cuenta que el informe de lista de errores no ofrece una manera directa de recuperar una lista de todos los usuarios que participaron de al menos una sesión con errores, ni tampoco permite determinar qué usuarios participaron con más frecuencia en sesiones con errores. (En primer lugar, el informe de lista de errores no tiene capacidad de filtrado). Sin embargo, si exporta los datos y, a continuación, se convierta en un archivo de valores separados por comas, se puede usar Windows PowerShell para encontrar las respuestas a preguntas como las. Por ejemplo, supongamos que guarda los datos en un archivo .CSV con el nombre C:\Data\Failure_List.csv. De acuerdo con los datos guardados en ese archivo, este comando muestra todos los usuarios que participaron de al menos una sesión con errores: 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Ese comando devolverá una lista similar a esta:
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

Estos dos comandos ofrecen información sobre el número total de sesiones con errores de las que participó cada usuario:
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Se devolverán datos similares a estos:
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el informe de lista de errores.
  
## <a name="metrics"></a>Métricas

En la siguiente tabla se detalla la información proporcionada en el informe de lista de errores para cada llamada con errores.
  
**Métricas del informe de lista de errores**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Hora de notificación** <br/> |No  <br/> |Fecha y hora en que se registró el informe.  <br/> |
|**Solicitud** <br/> |No  <br/> |Tipo de solicitud SIP que presentó errores. Por ejemplo, INVITE o BYE.  <br/> |
|**Código de respuesta** <br/> |No  <br/> |Código de respuesta SIP enviado cuando se produjo un error en la conferencia.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.  <br/> |
|**Tiempo coste de conexión (ms)** <br/> |No  <br/> |Cantidad de tiempo (en milisegundos) que necesitó el usuario para unirse a la conferencia.  <br/> |
|**Remitente** <br/> |No  <br/> |Dirección SIP del usuario que inició la llamada.  <br/> |
|**Agente de remitente** <br/> |No  <br/> |Software usado por el extremo del usuario que inició la llamada.  <br/> |
|**Destinatario** <br/> |No  <br/> |Dirección SIP del usuario que recibió la llamada.  <br/> |
   

