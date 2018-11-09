---
title: API del depósito para el panel de calidad de llamada (CQD) en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumen: Obtenga información sobre la API del depósito para el panel de calidad de llamada. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: de933063e5768b12af5ae8dc678ec7aa2da5f168
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035562"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API del depósito para el panel de calidad de llamada (CQD) en Skype para Business Server
 
**Resumen:** Obtenga información acerca de la API del depósito para el panel de calidad de llamada. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La API de repositorio proporciona acceso mediante programación para llamar al panel de calidad de Skype para Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API del depósito para el panel de calidad de llamada

API del depósito ofrece una interfaz de acceso a datos a la base de datos de repositorio. El repositorio permite que el contenido a organizarse en una estructura de árbol o gráfico de manera que los usuarios pueden agrupar en las formas que tienen sentido para los usuarios. El repositorio es compatible con dos tipos generales de los usuarios: el usuario del sistema, que es un usuario integrada que representa el repositorio y los usuarios habituales que representan a los usuarios autorizados del repositorio de.
  
API del depósito consta de tres servicios generales: 
  
- [Servicio de usuario para CQD](user-service.md) - para obtener acceso a los usuarios.
    
- [Elemento de servicio para el panel de calidad de llamadas (CQD)](item-service.md) : para obtener acceso a los elementos y el contenido almacenado en los elementos.
    
- [Servicio de configuración de usuario para el panel de calidad de llamadas (CQD)](user-settings-service.md) : para obtener acceso a la configuración del usuario.
    
Panel de calidad de llamada usa la API de repositorio para administrar la información siguiente: 
  
- **Usuario** : representación de los usuarios que tienen acceso al repositorio.
    
- **Informe** - contiene una lista de consultas, que se almacenan como un contenido en elementos del repositorio.
    
- **Consulta** - utilizada para recuperar datos de la API de datos, almacenados como un contenido en elementos del repositorio
    
- **Configuración de usuario** - describe un comportamiento de aplicación opcional para el usuario.
    
  **Recursos de origen cruzado (CORS) soporte para la API del depósito de uso compartido**
  
API del depósito es compatible con el uso compartido de recursos de origen cruzado (CORS). CORS es una característica HTTP que permite a una aplicación web que se ejecuta en un dominio tener acceso a recursos en otro dominio. Los exploradores Web implementan una restricción de seguridad que se conoce como directiva del mismo origen de [Directiva del mismo origen](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impide que una página web de llamar a las API en un dominio diferente. CORS proporciona una forma segura para permitir que un dominio (el dominio de origen) para llamar a las API en otro dominio. Vea la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener información detallada en CORS.
  
 **Habilitar CORS para la API de repositorio**
  
 El siguiente es un fragmento del archivo web.config de API de repositorio, que muestra dos dominios incluidos en la configuración de la aplicación corsTrustedOrigin. Todas las solicitudes realizadas por los scripts que se cargan desde estos servidores son de confianza mediante la API de repositorio.
  
No olvide incluir el protocolo exacta, el nombre de host y el puerto (si hay alguno). No para colocar cualquiera diagonal carácter (/) al final. Pueden especificarse varias entradas, separe con comas.
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


