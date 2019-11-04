---
title: API de datos para el panel de calidad de llamadas (CQD) en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumen: Obtenga información sobre la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 016cc1be9f5cd5506f8ee7d8ddbe2765e0015ffd
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "36571924"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de datos para el panel de calidad de llamadas (CQD) en Skype empresarial Server
 
**Resumen:** Más información sobre la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La API de datos proporciona acceso mediante programación para el panel de calidad de llamadas de Skype empresarial Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de datos para el panel de calidad de llamadas

La API de datos ofrece una interfaz de consulta al cubo de QoE. La API de datos es una API de REST para trabajar con bases de datos multidimensionales que proporcionan métricas de QoE agregadas basadas en las dimensiones y filtros especificados.
  
Las operaciones de REST se incluyen en la tabla siguiente.
  

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener cubo](get-cube.md) <br/> |Obtener la lista de dimensiones y medidas disponibles.  <br/> |
|[Obtener miembros de dimensión](get-dimension-members.md) <br/> |Operación de obtención de miembros de dimensión devuelve la lista de miembros de una dimensión específica. También ofrece la posibilidad de filtrar la lista de miembros y obtener un subconjunto, para reducir el coste de la transferencia bancaria.  <br/> |
|[Ejecutar consulta](run-query.md) <br/> |Ejecutar la operación de consulta proporciona la capacidad de ejecutar una consulta en el cubo basándose en las dimensiones, medidas y filtros especificados y devolver los datos.  <br/> |
|[Borrar caché](clear-cache.md) <br/> |Operación de borrar caché elimina la caché del servidor de consultas y datos. Esto restablecerá la memoria caché y recibirá datos nuevos de la actualización del cubo de QoE después para solicitudes nuevas.  <br/> |
|[Obtener integración de registro](get-integration-log.md) <br/> |La operación obtener registro de integración devuelve una lista de entradas de registro que describen las actividades en el procesamiento del cubo QoE.  <br/> |
|[Obtener últimos datos de integración](get-last-integration-data.md) <br/> |Obtenga los últimos datos de integración del cubo.  <br/> |
   
 **Compatibilidad con el uso compartido de recursos entre orígenes (CORS) para la API de datos**
  
La API de datos admite el uso compartido de recursos de origen cruzado (CORS). CORS es una característica HTTP que permite que una aplicación web que se ejecuta en un dominio tenga acceso a los recursos de otro dominio. Los exploradores Web implementan una restricción de seguridad conocida como una directiva de mismo origen de la [Directiva](https://www.w3.org/Security/wiki/Same_Origin_Policy) de mismo origen que impide que una página web llame a las API de otro dominio. CORS ofrece una manera segura de permitir que un dominio (el dominio de origen) llame a las API de otro dominio. Consulta la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.
  
 **Habilitar CORS para la API de datos**
  
 A continuación se muestra un extracto de la API de datos Web. config, que muestra dos dominios que aparecen en la configuración de la aplicación de corsTrustedOrigin. Todas las solicitudes realizadas por los scripts cargados desde estos servidores son de confianza para la API de datos.
  
Recuerde incluir el protocolo, el nombre de host y el puerto exactos (si corresponde). No coloque ningún carácter de barra diagonal (/) al final. Se pueden especificar varias entradas separándolas con comas.
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


