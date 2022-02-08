---
title: API de repositorio para panel de calidad de llamadas (CQD) en Skype Empresarial Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumen: obtenga información sobre la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 19d1f456afdf9f72721d1a246b206ad4f7259f14
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386578"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de repositorio para panel de calidad de llamadas (CQD) en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La API de repositorio proporciona acceso mediante programación al Panel de calidad de llamadas para Skype Empresarial Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API de repositorio para panel de calidad de llamadas

La API de repositorio ofrece una interfaz de acceso a datos a la base de datos del repositorio. El repositorio permite que el contenido se organice en una estructura de árbol o gráfico de modo que los usuarios puedan agruparlos de la manera que tienen sentido para los usuarios. El repositorio admite dos tipos generales de usuarios: el usuario del sistema, que es un usuario integrado que representa el repositorio, y los usuarios normales que representan a los usuarios autorizados del repositorio.
  
La API de repositorio consta de tres servicios generales: 
  
- [Servicio de usuario para CQD](user-service.md) : para obtener acceso a usuarios.
    
- [Servicio de elementos para panel de calidad de llamadas (CQD):](item-service.md) para obtener acceso a los elementos y el contenido almacenado en elementos.
    
- [Servicio Configuración usuario para panel de calidad de llamadas (CQD):](user-settings-service.md) para obtener acceso a los usuarios Configuración.
    
El Panel de calidad de llamadas usa la API de repositorio para administrar la siguiente información: 
  
- **Usuario** : representación de los usuarios que tienen acceso al repositorio.
    
- **Informe** : contiene una lista de consultas, almacenadas como contenido en elementos del repositorio.
    
- **Consulta** : se usa para recuperar datos de la API de datos, almacenados como contenido en elementos del repositorio.
    
- **Configuración de** usuario: describe un comportamiento de aplicación opcional para el usuario.
    
  **Compatibilidad con uso compartido de recursos entre orígenes (CORS) para la API de repositorio**
  
La API de repositorio admite el uso compartido de recursos entre orígenes (CORS). CORS es una característica HTTP que permite a una aplicación web que se ejecuta en un dominio tener acceso a los recursos de otro dominio. Los exploradores web implementan una restricción de [](https://www.w3.org/Security/wiki/Same_Origin_Policy) seguridad conocida como directiva del mismo origen que impide que una página web llame a API en un dominio diferente. CORS proporciona una forma segura de permitir que un dominio (el dominio de origen) llame a las API en otro dominio. Consulte la [especificación CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.
  
 **Habilitar CORS para api de repositorio**
  
 A continuación se muestra un fragmento de api de repositorio web.config, que muestra dos dominios enumerados en la configuración de la aplicación corsTrustedOrigin. Todas las solicitudes realizadas por los scripts cargados desde estos servidores son de confianza para la API de repositorio.
  
Recuerde incluir el protocolo exacto, el nombre de host y el puerto (si lo hubiera). No ponga ningún carácter de barra diagonal hacia delante (/) al final. Se pueden especificar varias entradas separando con comas.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


