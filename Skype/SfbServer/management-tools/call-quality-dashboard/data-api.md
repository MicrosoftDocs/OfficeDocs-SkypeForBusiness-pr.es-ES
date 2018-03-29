---
title: API de datos de llamada Quality Dashboard (CQD) en Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumen: Conozca la Rata API para panel de calidad de la llamada. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 038324064177c110c0736092985e9da1b330ea8b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a>API de datos de llamada Quality Dashboard (CQD) en Skype para Business Server 2015
 
**Resumen:** Conozca la Rata API para panel de calidad de la llamada. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La API de datos proporciona acceso mediante programación para llamar al panel de calidad para Skype para Business Server 2015.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de datos para el panel de calidad de la llamada

La API de datos ofrece una interfaz de consulta al cubo QoE. La API de datos es una API de REST para trabajar con una base de datos multidimensional que proporciona métricas de calidad agregados basados en los filtros y las dimensiones especificadas.
  
Las operaciones de resto se incluyen en la tabla siguiente.
  

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener el cubo](get-cube.md) <br/> |Obtener la lista de medidas y dimensiones disponibles.  <br/> |
|[Los miembros de dimensión](get-dimension-members.md) <br/> |Operación de obtención de miembros de dimensión, devuelve la lista de miembros de una dimensión específica. También proporcionan la capacidad para filtrar la lista de miembros y obtener un subconjunto, para reducir el costo de la transferencia de alambre.  <br/> |
|[Ejecutar consulta](run-query.md) <br/> |Ejecutar consulta operación proporciona la capacidad de ejecutar una consulta en el cubo basándose en los filtros, las medidas y dimensiones especificadas y devolver los datos de nuevo.  <br/> |
|[Borrar caché](clear-cache.md) <br/> |Operación de caché borrado elimina la caché en el servidor para consultas y datos. Esto restablecerá la caché y le facilitaremos datos nuevos de cubo QoE posteriormente para las nuevas solicitudes.  <br/> |
|[Obtener Log integración](get-integration-log.md) <br/> |Obtener Log integración operación devuelve una lista de entradas del registro que describe las actividades en el cubo de la calidad de procesamiento.  <br/> |
|[Obtener los últimos datos de integración](get-last-integration-data.md) <br/> |Obtener los últimos datos de integración del cubo.  <br/> |
   
 **Recursos compartidos (CORS) admite API de datos de origen cruzado**
  
API de datos admiten el uso compartido de recursos entre origen (CORS). CORS es una característica HTTP que permite a una aplicación web que ejecuta en un dominio tener acceso a recursos de otro dominio. Los exploradores Web implementan una restricción de seguridad que se conoce como directiva de mismo origen [Política del mismo origen](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impide que una página web de llamar a las API en un dominio diferente. CORS proporciona una forma segura para permitir un dominio (el dominio de origen) llamar a las API de otro dominio. Vea la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.
  
 **Habilitación de CORS para datos de API**
  
 El siguiente es un extracto del archivo web.config de datos API, que muestra dos dominios enumerados en la configuración de la aplicación corsTrustedOrigin. Todas las solicitudes realizadas por las secuencias de comandos cargados desde estos servidores son de confianza por la API de datos.
  
Recuerde incluir el protocolo exacto, el nombre de host y el puerto (si existe). No para poner cualquier diagonal carácter (/) al final. Pueden especificarse varias entradas separando con comas.
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>

```


