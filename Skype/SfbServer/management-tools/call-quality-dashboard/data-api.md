---
title: API de datos para el panel de calidad de llamada (CQD) en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumen: Obtenga información sobre la API de Rata para el panel de calidad de llamada. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 0af168c46e8b2732d5c967550391ab52459ddf95
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531760"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de datos para el panel de calidad de llamada (CQD) en Skype para Business Server
 
**Resumen:** Obtenga información acerca de la API de Rata para el panel de calidad de llamada. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La API de datos proporciona acceso mediante programación para llamar al panel de calidad de Skype para Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de datos para el panel de calidad de llamada

La API de datos ofrece una interfaz de consulta para el cubo de QoE. La API de datos es una API de REST para trabajar con la base de datos multidimensional que proporciona agregadas métricas de QoE en función de los filtros y las dimensiones especificadas.
  
Las operaciones de REST se incluyen en la siguiente tabla.
  

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener el cubo](get-cube.md) <br/> |Obtener la lista de dimensiones disponibles y las medidas.  <br/> |
|[Obtener a miembros de dimensión](get-dimension-members.md) <br/> |Operación de obtención de miembros de dimensión, devuelve la lista de miembros de una dimensión específica. También proporcionan la capacidad de filtrar la lista de miembros y obtener un subconjunto, para reducir el costo de transferencia de cable.  <br/> |
|[Ejecutar la consulta](run-query.md) <br/> |Ejecutar consulta operación proporciona la capacidad de ejecutar una consulta en el cubo en función de los filtros, las medidas y dimensiones especificadas y volver atrás los datos.  <br/> |
|[Borrar caché](clear-cache.md) <br/> |Operación de caché borrado elimina la memoria caché en el servidor de consultas y los datos. Esto restablecerá la memoria caché y se va a obtener datos actualizados desde QoE cubo más adelante para nuevas solicitudes.  <br/> |
|[Obtener Log integración](get-integration-log.md) <br/> |Obtenga la operación devuelve una lista de entradas de registro que describe las actividades en el cubo de QoE de procesamiento de registro de integración.  <br/> |
|[Obtener los últimos datos de integración](get-last-integration-data.md) <br/> |Obtenga los últimos datos de integración del cubo.  <br/> |
   
 **Recursos de origen cruzado (CORS) compatibilidad con API de datos de uso compartido**
  
API de datos admite el uso compartido de recursos de origen cruzado (CORS). CORS es una característica HTTP que permite a una aplicación web que se ejecuta en un dominio tener acceso a recursos en otro dominio. Los exploradores Web implementan una restricción de seguridad que se conoce como directiva del mismo origen de [Directiva del mismo origen](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impide que una página web de llamar a las API en un dominio diferente. CORS proporciona una forma segura para permitir que un dominio (el dominio de origen) para llamar a las API en otro dominio. Vea la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener información detallada en CORS.
  
 **Habilitar CORS para la API de datos**
  
 El siguiente es un fragmento del archivo web.config de API de datos, que muestra dos dominios incluidos en la configuración de la aplicación corsTrustedOrigin. Todas las solicitudes realizadas por los scripts que se cargan desde estos servidores son de confianza mediante la API de datos.
  
No olvide incluir el protocolo exacta, el nombre de host y el puerto (si hay alguno). No para colocar cualquiera diagonal carácter (/) al final. Pueden especificarse varias entradas, separe con comas.
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


