---
title: API de repositorio para panel de calidad de llamadas (CQD) en Skype Empresarial Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumen: obtenga información sobre la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803130"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de repositorio para panel de calidad de llamadas (CQD) en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La API de repositorio proporciona acceso mediante programación para el Panel de calidad de llamadas para Skype Empresarial Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API de repositorio para panel de calidad de llamadas

La API de repositorio ofrece una interfaz de acceso a datos a la base de datos del repositorio. El repositorio permite que el contenido se organice en una estructura de gráfico o árbol, de modo que los usuarios puedan agruparlos de la manera que tienen sentido para los usuarios. El repositorio admite dos tipos generales de usuarios: usuario del sistema, que es un usuario integrado que representa el repositorio, y usuarios normales que representan a los usuarios autorizados del repositorio.
  
La API de repositorio consta de tres servicios generales: 
  
- [Servicio de usuario para CQD:](user-service.md) para obtener acceso a usuarios.
    
- Servicio de elementos para el Panel de calidad de [llamadas (CQD):](item-service.md) para obtener acceso a elementos y el contenido almacenado en elementos.
    
- [Servicio de configuración de usuario para el Panel de calidad de llamadas (CQD):](user-settings-service.md) para obtener acceso a La configuración del usuario.
    
El Panel de calidad de llamadas usa la API de repositorio para administrar la siguiente información: 
  
- **Usuario:** representación de los usuarios que tienen acceso al repositorio.
    
- **Informe:** contiene una lista de consultas, almacenadas como contenido en elementos del repositorio.
    
- **Consulta:** se usa para recuperar datos de la API de datos, almacenados como contenido en elementos del repositorio.
    
- **Configuración de** usuario: describe un comportamiento opcional de la aplicación para el usuario.
    
  **Compatibilidad con el uso compartido de recursos entre orígenes (CORS) para la API de repositorio**
  
La API de repositorio admite el uso compartido de recursos entre orígenes (CORS). CORS es una característica HTTP que permite que una aplicación web que se ejecuta en un dominio obtenga acceso a los recursos de otro dominio. Los exploradores web implementan [](https://www.w3.org/Security/wiki/Same_Origin_Policy) una restricción de seguridad conocida como directiva de mismo origen que impide que una página web llame a las API de un dominio diferente. CORS proporciona una forma segura de permitir que un dominio (el dominio de origen) llame a las API de otro dominio. Consulta la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.
  
 **Habilitar CORS para la API de repositorio**
  
 A continuación se muestra un extracto de la API de repositorio web.config que muestra dos dominios enumerados en la configuración de la aplicación corsTrustedOrigin. Todas las solicitudes realizadas por los scripts cargados desde estos servidores son de confianza para la API de repositorio.
  
Recuerde incluir el protocolo, el nombre de host y el puerto exactos (si los hay). No coloque ningún carácter de barra diagonal (/) al final. Se pueden especificar varias entradas separándose con comas.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


