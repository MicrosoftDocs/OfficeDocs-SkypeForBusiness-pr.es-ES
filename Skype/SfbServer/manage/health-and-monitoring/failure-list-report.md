---
title: Informe de lista de errores en Skype Empresarial Server
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
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Summary: Learn about the Failure List Report in Skype Empresarial Server.'
ms.openlocfilehash: 37442d95c3a79bffbd79ebd74a793f5d3e1f3fb4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858297"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Informe de lista de errores en Skype Empresarial Server 
 
**Resumen:** Obtenga información sobre el informe de lista de errores en Skype Empresarial Server.
  
El informe de lista de errores proporciona información sobre los participantes individuales que participaron en una sesión de punto a punto o conferencia con errores. Esta información incluye el URI del usuario que experimentó el problema, así como el código de respuesta SIP y el identificador de diagnóstico asociado con el error.
  
## <a name="accessing-the-failure-list-report"></a>Acceso al informe de lista de errores

Para obtener acceso al informe de lista de errores, haga clic en cualquiera de las siguientes métricas del Informe de distribución de [errores Skype Empresarial Server](failure-distribution-report.md):
  
- Motivos del diagnóstico principales (sesiones)
    
- Modalidades principales (sesiones)
    
- Grupos principales (sesiones)
    
- Fuentes principales (sesiones)
    
- Componentes principales (sesiones)
    
- Usuarios de origen principales (sesiones)
    
- Usuarios de destino principales (sesiones)
    
- Agentes de usuarios de origen principales (sesiones)
    
En el Informe de lista de errores, puede obtener acceso al Informe de detalles de sesión punto a punto en [Skype Empresarial Server](peer-to-peer-session-detail-report.md) haciendo clic en la métrica Detalles de sesión de una sesión punto a punto. También puede obtener acceso al Informe de detalles de conferencia haciendo clic en la métrica de conferencia de una conferencia.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Hacer el mejor uso del informe de lista de errores

En el Informe de lista de errores, puede ver una descripción para cada código de respuesta o cada identificador de diagnóstico simplemente manteniendo el mouse sobre ese valor. Por ejemplo, si mantiene el mouse sobre el identificador de diagnóstico 7025, verá lo siguiente en una información sobre herramientas:
  
Error de servidor interno al crear medios para el usuario.
  
Es importante tener en cuenta que el informe de lista de errores no proporciona una forma sencilla de recuperar directamente una lista de todos los usuarios que participaron en al menos una sesión con errores, ni proporciona una forma de determinar qué usuarios participaron con más frecuencia en una sesión con errores. (Por un lado, el informe de lista de errores no tiene capacidades de filtrado). Sin embargo, si exporta los datos y, a continuación, los convierte en un archivo de valores separados por comas, puede usar Windows PowerShell para encontrar las respuestas a preguntas como esas. Por ejemplo, supongamos que guarda los datos en un archivo .CSV denominado C:\Data\Failure_List.csv. En función de los datos guardados en ese archivo, este comando enumera todos los usuarios que participaron en al menos una sesión con errores: 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Ese comando devolverá una lista similar a la siguiente:
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

Estos dos comandos informan del número total de sesiones con errores en las que participó cada usuario:
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Devolverá unos datos similares a estos:
  
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

Ninguna. No puede filtrar el informe de lista de errores.
  
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información proporcionada en el Informe de lista de errores para cada llamada con error.
  
**Métricas de informe de lista de errores**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Hora notificada** <br/> |No  <br/> |Fecha y hora en que se registró el informe.  <br/> |
|**Solicitud** <br/> |No  <br/> |Tipo de solicitud SIP que ha fallado. Por ejemplo, INVITE o BYE.  <br/> |
|**Código de respuesta** <br/> |No  <br/> |Código de respuesta SIP enviado cuando la conferencia ha fallado.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.  <br/> |
|**Tiempo de costo de unión (ms)** <br/> |No  <br/> |Cantidad de tiempo (en milisegundos) necesario para que el usuario se una a la conferencia.  <br/> |
|**Remitente** <br/> |No  <br/> |Dirección SIP del usuario que inició la llamada.  <br/> |
|**Agente de remitente** <br/> |No  <br/> |Software usado por el extremo del usuario que inició la llamada.  <br/> |
|**Destinatario** <br/> |No  <br/> |Dirección SIP del usuario al que se estaba llamado.  <br/> |
   

