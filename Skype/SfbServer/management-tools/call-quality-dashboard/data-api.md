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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumen: obtenga información sobre la API de datos para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 2497b978944ec860d7188560ecaf72091df3f626
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586922"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de datos para panel de calidad de llamadas (CQD) en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre la API de datos para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La API de datos proporciona acceso mediante programación al Panel de calidad de llamadas para Skype Empresarial Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de datos para panel de calidad de llamadas

La API de datos ofrece una interfaz de consulta al cubo de QoE. La API de datos es una API de REST para trabajar con una base de datos multidimensional que proporciona métricas de QoE agregadas en función de las dimensiones y filtros especificados.
  
Las operaciones rest se incluyen en la tabla siguiente.
  

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener cubo](get-cube.md) <br/> |Obtener la lista de dimensiones y medidas disponibles.  <br/> |
|[Obtener miembros de dimensión](get-dimension-members.md) <br/> |La operación Obtener miembros de dimensión devuelve la lista de miembros de una dimensión específica. También permite filtrar la lista de miembros y obtener un subconjunto para reducir el costo de transferencia bancaria.  <br/> |
|[Ejecutar consulta](run-query.md) <br/> |La operación Ejecutar consulta permite ejecutar una consulta en el cubo en función de las dimensiones, medidas y filtros especificados y devolver los datos.  <br/> |
|[Borrar caché](clear-cache.md) <br/> |La operación Borrar caché elimina la memoria caché del servidor para consultas y datos. Esto restablecerá la memoria caché y, posteriormente, se obtienen datos nuevos de QoE Cube para las nuevas solicitudes.  <br/> |
|[Obtener integración de registro](get-integration-log.md) <br/> |La operación Obtener registro de integración devuelve una lista de entradas de registro que describen las actividades del procesamiento del cubo qoE.  <br/> |
|[Obtener últimos datos de integración](get-last-integration-data.md) <br/> |Obtener los últimos datos de integración del cubo.  <br/> |
   
 **Compatibilidad con uso compartido de recursos entre orígenes (CORS) para la API de datos**
  
La API de datos admite el uso compartido de recursos entre orígenes (CORS). CORS es una característica HTTP que permite a una aplicación web que se ejecuta en un dominio tener acceso a los recursos de otro dominio. Los exploradores web implementan [](https://www.w3.org/Security/wiki/Same_Origin_Policy) una restricción de seguridad conocida como directiva del mismo origen que impide que una página web llame a API en un dominio diferente. CORS proporciona una forma segura de permitir que un dominio (el dominio de origen) llame a las API en otro dominio. Consulte la [especificación CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.
  
 **Habilitar CORS para api de datos**
  
 A continuación se muestra un fragmento de api de web.config datos, que muestra dos dominios enumerados en la configuración de la aplicación corsTrustedOrigin. Todas las solicitudes realizadas por los scripts cargados desde estos servidores son de confianza para la API de datos.
  
Recuerde incluir el protocolo exacto, el nombre de host y el puerto (si lo hubiera). No ponga ningún carácter de barra diagonal hacia delante (/) al final. Se pueden especificar varias entradas separando con comas.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


