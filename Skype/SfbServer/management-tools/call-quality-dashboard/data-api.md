---
title: API de datos para panel de calidad de llamadas (CQD) en Skype Empresarial Server
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
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumen: obtenga información sobre la API de datos para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832700"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de datos para panel de calidad de llamadas (CQD) en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre la API de datos para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La API de datos proporciona acceso mediante programación para el Panel de calidad de llamadas para Skype Empresarial Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de datos para panel de calidad de llamadas

La API de datos ofrece una interfaz de consulta para el cubo QoE. La API de datos es una API de REST para trabajar con una base de datos multidimensional que proporciona métricas de QoE agregadas basadas en filtros y dimensiones especificadas.
  
Las operaciones rest se incluyen en la tabla siguiente.
  

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener cubo](get-cube.md) <br/> |Obtiene la lista de dimensiones y medidas disponibles.  <br/> |
|[Obtener miembros de dimensión](get-dimension-members.md) <br/> |La operación Obtener miembros de dimensión devuelve la lista de miembros de una dimensión específica. También permite filtrar la lista de miembros y obtener un subconjunto para reducir el costo de transferencia bancaria.  <br/> |
|[Ejecutar consulta](run-query.md) <br/> |La operación Ejecutar consulta permite ejecutar una consulta en el cubo en función de las dimensiones, medidas y filtros especificados y devolver los datos.  <br/> |
|[Borrar caché](clear-cache.md) <br/> |La operación Borrar caché elimina la memoria caché del servidor para consultas y datos. Esto restablecerá la memoria caché y se recibirán datos nuevos del cubo QoE posteriormente para las nuevas solicitudes.  <br/> |
|[Obtener integración de registro](get-integration-log.md) <br/> |La operación Obtener registro de integración devuelve una lista de entradas de registro que describen las actividades en el procesamiento del cubo QoE.  <br/> |
|[Obtener últimos datos de integración](get-last-integration-data.md) <br/> |Obtenga los últimos datos de integración del cubo.  <br/> |
   
 **Compatibilidad con uso compartido de recursos entre orígenes (CORS) para API de datos**
  
La API de datos admite el uso compartido de recursos entre orígenes (CORS). CORS es una característica HTTP que permite que una aplicación web que se ejecuta en un dominio obtenga acceso a los recursos de otro dominio. Los exploradores web implementan [](https://www.w3.org/Security/wiki/Same_Origin_Policy) una restricción de seguridad conocida como directiva de mismo origen que impide que una página web llame a las API de un dominio diferente. CORS proporciona una forma segura de permitir que un dominio (el dominio de origen) llame a las API de otro dominio. Consulta la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.
  
 **Habilitar CORS para la API de datos**
  
 A continuación se muestra un extracto de la API de web.config, que muestra dos dominios enumerados en la configuración de la aplicación corsTrustedOrigin. Todas las solicitudes realizadas por los scripts cargados desde estos servidores son de confianza para la API de datos.
  
Recuerde incluir el protocolo, el nombre de host y el puerto exactos (si los hay). No coloque ningún carácter de barra diagonal (/) al final. Se pueden especificar varias entradas separándose con comas.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


