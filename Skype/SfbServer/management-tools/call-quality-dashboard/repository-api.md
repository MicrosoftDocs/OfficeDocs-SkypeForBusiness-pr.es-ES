---
title: API de repositorio para el panel de calidad de llamadas (CQD) en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumen: Obtenga información sobre la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 283ef7544435c3954898b2d5ae9e5f5b38762f3c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888789"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de repositorio para el panel de calidad de llamadas (CQD) en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La API de Repository proporciona acceso mediante programación para el panel de calidad de llamadas de Skype empresarial Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API de repositorio para panel de calidad de llamadas

La API de repositorio ofrece una interfaz de acceso a datos para la base de datos del repositorio. El repositorio permite que el contenido se organice en una estructura de árbol o gráfico, de modo que los usuarios puedan agruparlos de la manera que tengan sentido para los usuarios. El repositorio admite dos tipos de usuarios generales: usuario del sistema, que es un usuario integrado que representa el repositorio y usuarios habituales que representan a los usuarios autorizados del repositorio.
  
La API del repositorio consta de tres servicios generales: 
  
- [Servicio de usuario de CQD](user-service.md) : para acceder a los usuarios.
    
- [Servicio de artículos para el panel de calidad de llamadas (CQD)](item-service.md) : para obtener acceso a los elementos y el contenido almacenado en los elementos.
    
- [Servicio de configuración de usuario del panel de calidad de llamadas (CQD)](user-settings-service.md) : para acceder a la configuración de usuario.
    
El panel de calidad de llamadas usa la API de repositorio para administrar la siguiente información: 
  
- Representación del **usuario** de los usuarios que tienen acceso al repositorio.
    
- **Informe** : contiene una lista de consultas, almacenadas como contenido en elementos del repositorio.
    
- **Consulta** : se usa para recuperar datos de la API de datos, almacenados como contenido en elementos del repositorio.
    
- **Configuración de usuario** : describe un comportamiento de la aplicación opcional para el usuario.
    
  **Compatibilidad con el uso compartido de recursos entre orígenes (CORS) para la API del repositorio**
  
La API de repositorio es compatible con el uso compartido de recursos cruzados (CORS). CORS es una característica HTTP que permite que una aplicación web que se ejecuta en un dominio tenga acceso a los recursos de otro dominio. Los exploradores Web implementan una restricción de seguridad conocida como una directiva de mismo origen de la [Directiva](https://www.w3.org/Security/wiki/Same_Origin_Policy) de mismo origen que impide que una página web llame a las API de otro dominio. CORS ofrece una manera segura de permitir que un dominio (el dominio de origen) llame a las API de otro dominio. Consulta la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.
  
 **Habilitar CORS para la API del repositorio**
  
 A continuación se muestra un extracto de la API del depósito Web. config, que muestra dos dominios que aparecen en la configuración de la aplicación corsTrustedOrigin. Todas las solicitudes realizadas por los scripts cargados desde estos servidores son de confianza para la API del repositorio.
  
Recuerde incluir el protocolo, el nombre de host y el puerto exactos (si corresponde). No coloque ningún carácter de barra diagonal (/) al final. Se pueden especificar varias entradas separándolas con comas.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


