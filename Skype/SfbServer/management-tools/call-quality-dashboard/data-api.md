---
title: Data API for Call Quality Dashboard (CQD) en Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumen: obtenga información sobre data API para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 3204398dcf667f785f1efe71cc4d6dc5478ce54d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675742"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Data API for Call Quality Dashboard (CQD) en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre data API para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
Data API proporciona acceso mediante programación para el panel de calidad de llamadas para Skype Empresarial Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>Data API for Call Quality Dashboard

Data API ofrece una interfaz de consulta al cubo QoE. Data API es una API REST para trabajar con una base de datos multidimensional que proporciona métricas de QoE agregadas basadas en dimensiones y filtros especificados.
  
Las operaciones REST se incluyen en la tabla siguiente.
  

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener cubo](get-cube.md) <br/> |Obtenga la lista de dimensiones y medidas disponibles.  <br/> |
|[Obtener miembros de dimensión](get-dimension-members.md) <br/> |La operación Obtener miembros de dimensión devuelve la lista de miembros de una dimensión específica. También ofrece la capacidad de filtrar la lista de miembros y obtener un subconjunto para reducir el costo de transferencia bancaria.  <br/> |
|[Ejecutar consulta](run-query.md) <br/> |La operación Ejecutar consulta proporciona la capacidad de ejecutar una consulta en el cubo en función de las dimensiones, medidas y filtros especificados y devolver los datos.  <br/> |
|[Borrar caché](clear-cache.md) <br/> |La operación Borrar caché elimina la memoria caché en el servidor para consultas y datos. Esto restablecerá la memoria caché y se obtendrán datos nuevos del cubo QoE posteriormente para las nuevas solicitudes.  <br/> |
|[Obtener integración de registro](get-integration-log.md) <br/> |La operación Obtener registro de integración devuelve una lista de entradas de registro que describen las actividades del procesamiento del cubo qoE.  <br/> |
|[Obtener últimos datos de integración](get-last-integration-data.md) <br/> |Obtenga los últimos datos de integración del cubo.  <br/> |
   
 **Compatibilidad con el uso compartido de recursos entre orígenes (CORS) para Data API**
  
Data API admite el uso compartido de recursos entre orígenes (CORS). CORS es una característica HTTP que permite que una aplicación web que se ejecuta en un dominio acceda a los recursos de otro dominio. Los exploradores web implementan una restricción de seguridad conocida como directiva [de](https://www.w3.org/Security/wiki/Same_Origin_Policy) mismo origen del mismo origen que impide que una página web llame a las API en un dominio diferente. CORS proporciona una manera segura de permitir que un dominio (el dominio de origen) llame a las API de otro dominio. Consulte la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.
  
 **Habilitación de CORS para Data API**
  
 A continuación se muestra un extracto de web.config de Data API que muestra dos dominios enumerados en la configuración de la aplicación corsTrustedOrigin. Data API confía en todas las solicitudes realizadas por los scripts cargados desde estos servidores.
  
No olvide incluir el protocolo exacto, el nombre de host y el puerto (si existe). No coloque ningún carácter de barra diagonal (/) al final. Se pueden especificar varias entradas separando con comas.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
...  </appSettings>
</configuration>
```


