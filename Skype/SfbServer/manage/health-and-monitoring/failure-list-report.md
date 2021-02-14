---
title: Informe de lista de errores en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Resumen: obtenga información sobre el informe de lista de errores en Skype Empresarial Server.'
ms.openlocfilehash: 48654ee827f0d7efcb50bcccc4e1d2f3fdb5422e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816850"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Informe de lista de errores en Skype Empresarial Server 
 
**Resumen:** Obtenga información sobre el informe de lista de errores en Skype Empresarial Server.
  
El informe de lista de errores proporciona información sobre los participantes individuales que participaron en una sesión punto a punto o de conferencia con errores. Esta información incluye el URI del usuario que experimentó el problema, así como el código de respuesta SIP y el id. de diagnóstico asociado al error.
  
## <a name="accessing-the-failure-list-report"></a>Acceso al informe de lista de errores

Para obtener acceso al informe de lista de errores, haga clic en cualquiera de las métricas siguientes en el informe de distribución de errores [de Skype Empresarial Server:](failure-distribution-report.md)
  
- Motivos del diagnóstico principales (sesiones)
    
- Modalidades principales (sesiones)
    
- Grupos principales (sesiones)
    
- Fuentes principales (sesiones)
    
- Componentes principales (sesiones)
    
- Usuarios de origen principales (sesiones)
    
- Usuarios de destino principales (sesiones)
    
- Agentes de usuarios de origen principales (sesiones)
    
Desde el informe de lista de errores puede obtener acceso al informe de detalles de sesiones punto a punto en [Skype Empresarial Server](peer-to-peer-session-detail-report.md) haciendo clic en la métrica de detalles de sesión de una sesión punto a punto. También puede obtener acceso al Informe de detalles de conferencia haciendo clic en la métrica Conferencia de una conferencia.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Aprovechar al máximo el informe de lista de errores

En el informe de lista de errores, puede ver una descripción para cada código de respuesta o cada identificador de diagnóstico simplemente manteniendo el mouse sobre ese valor. Por ejemplo, si mantienes el mouse sobre el Id. de diagnóstico 7025, verás lo siguiente en una información sobre herramientas:
  
Error interno del servidor al crear medios para el usuario.
  
Es importante tener en cuenta que el informe de lista de errores no proporciona una forma sencilla de recuperar directamente una lista de todos los usuarios que participaron en al menos una sesión con errores, ni proporciona una forma de determinar qué usuarios participaron con más frecuencia en una sesión con errores. (Por un lado, el informe de lista de errores no tiene capacidades de filtrado). Sin embargo, si exporta los datos y los convierte en un archivo de valores separados por comas, puede usar Windows PowerShell para encontrar las respuestas a preguntas como estas. Por ejemplo, supongamos que guarda los datos en un archivo . Archivo CSV denominado C:\Data\Failure_List.csv. En función de los datos guardados en ese archivo, este comando enumera todos los usuarios que participaron en al menos una sesión con errores: 
  
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

Ninguno. No puede filtrar el informe de lista de errores.
  
## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información proporcionada en el informe de lista de errores para cada llamada con errores.
  
**Métricas del informe de lista de errores**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Hora notificada** <br/> |No  <br/> |Fecha y hora en que se registró el informe.  <br/> |
|**Solicitud** <br/> |No  <br/> |Tipo de solicitud SIP con error. Por ejemplo, INVITE o BYE.  <br/> |
|**Código de respuesta** <br/> |No  <br/> |Código de respuesta SIP enviado cuando la conferencia ha fallado.  <br/> |
|**Id. de diagnóstico** <br/> |No  <br/> |Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.  <br/> |
|**Tiempo de costo de unión (ms)** <br/> |No  <br/> |Cantidad de tiempo (en milisegundos) necesario para que el usuario se una a la conferencia.  <br/> |
|**Remitente** <br/> |No  <br/> |Dirección SIP del usuario que inició la llamada.  <br/> |
|**Agente de remitente** <br/> |No  <br/> |Software usado por el punto de conexión del usuario que inició la llamada.  <br/> |
|**Destinatario** <br/> |No  <br/> |Dirección SIP del usuario al que se ha llamado.  <br/> |
   

