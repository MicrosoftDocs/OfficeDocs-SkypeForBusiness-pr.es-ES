---
title: API del depósito para el panel de calidad de la llamada (CQD) en Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumen: Aprender sobre la API del depósito para el panel de calidad de la llamada. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 0f84e3967bd4f78f8852dbcfed8ce5d59cbe4e8c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a>API del depósito para el panel de calidad de la llamada (CQD) en Skype para Business Server 2015
 
**Resumen:** Obtenga información acerca de la API del depósito para el panel de calidad de la llamada. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La API de repositorio proporciona acceso mediante programación para llamar al panel de calidad para Skype para Business Server 2015.
  
## <a name="repository-api-for-call-quality-dashboard"></a>Panel de calidad de la llamada de API del depósito

API del depósito ofrece una interfaz de acceso a datos a la base de datos de repositorio. El repositorio permite el contenido organizado en una estructura de árbol o gráfico tal que los usuarios pueden agrupar en las formas que tienen sentido para los usuarios. El repositorio es compatible con dos tipos generales de usuarios: usuario del sistema, que es un usuario integradas que representa el repositorio y los usuarios normales que representan a los usuarios autorizados del repositorio.
  
API del depósito está formado por tres servicios generales: 
  
- [Servicio de usuario para CQD](user-service.md) - para tener acceso a los usuarios.
    
- [Servicio de elementos para el panel de calidad llamar (CQD)](item-service.md) : para obtener acceso a elementos y el contenido que se almacena en los elementos.
    
- [Servicio de configuración de usuario para el panel de calidad llamar (CQD)](user-settings-service.md) - para el acceso a la configuración de usuario.
    
Panel de calidad llamada utiliza API de repositorio para gestionar la siguiente información: 
  
- **Usuario** : representación de los usuarios que tienen acceso al repositorio.
    
- **Informe** - contiene una lista de consultas, que se almacena como un contenido en elementos del repositorio.
    
- **Consulta** - utilizado para recuperar datos de la API de datos, almacenados como un contenido en elementos del repositorio
    
- **Configuración de usuario** - describe un comportamiento de aplicación opcional para el usuario.
    
 **Recursos compartidos (CORS) soporte para la API del depósito de origen cruzado**
  
API del depósito es compatible con el uso compartido de recursos entre origen (CORS). CORS es una característica HTTP que permite a una aplicación web que ejecuta en un dominio tener acceso a recursos de otro dominio. Los exploradores Web implementan una restricción de seguridad que se conoce como directiva de mismo origen [Política del mismo origen](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impide que una página web de llamar a las API en un dominio diferente. CORS proporciona una forma segura para permitir un dominio (el dominio de origen) llamar a las API de otro dominio. Vea la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.
  
 **Habilitación de CORS de la API del depósito**
  
 El siguiente es un extracto del archivo web.config de API de repositorio, que muestra dos dominios enumerados en la configuración de la aplicación corsTrustedOrigin. Todas las solicitudes realizadas por las secuencias de comandos cargados desde estos servidores son de confianza por la API del depósito.
  
Recuerde incluir el protocolo exacto, el nombre de host y el puerto (si existe). No para poner cualquier diagonal carácter (/) al final. Pueden especificarse varias entradas separando con comas.
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>

```


