---
title: Características de seguridad clave de Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype para Business Server incluye varias características de seguridad, incluida la autenticación de servidor a servidor, el control de acceso basado en roles y el almacenamiento centralizado de datos de configuración.
ms.openlocfilehash: 5a0a82800be8158b6d54e4e01e7609d3e6b3714d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213609"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Características de seguridad clave de Skype para Business Server
 
Skype para Business Server incluye varias características de seguridad, incluida la autenticación de servidor a servidor, el control de acceso basado en roles y el almacenamiento centralizado de datos de configuración. 
  
En este artículo se proporciona una introducción de alto nivel de Skype para seguridad Business Server. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Características de seguridad clave de Skype para Business Server

La seguridad es un tema muy amplio. Seguridad llega a través de todas las características de Skype para Business Server, así como las bases de datos, servicios y hardware que componen un Skype para ecosistema de Business Server. En este artículo se describe algunas de las características de Skype para Business Server en particular que están diseñados para la seguridad.
  
### <a name="planning-and-design-tools"></a>Herramientas de planeación y diseño

Skype para Business Server proporciona dos herramientas para facilitar la planificación y diseño y para reducir la posibilidad de configurar mal Skype para los componentes de Business Server. 
  
- **Herramienta de planeación de topología** automatiza gran parte del proceso de diseño de topología. Puede exportar los resultados de la herramienta de planeación a Topology Builder, que es la herramienta que se requiere para instalar a cada servidor que ejecuta Skype para Business Server.
    
- El **Generador de topologías** almacena toda la información de configuración en el almacén de administración central.
    
Para obtener información detallada acerca de estas herramientas, vea [Skype para herramientas de administración de servidor empresarial](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Almacén de administración central

En Skype para Business Server, datos de configuración acerca de los servidores y servicios están parte del almacén de Administración Central. El almacén de Administración Central proporciona un almacenamiento robusto y esquematizado de los datos necesarios para definir, configurar, mantener, administrar, se describen y operar una Skype para la implementación de Business Server. También comprueba los datos para asegurarse de que la configuración es coherente. Todos los cambios realizados a estos datos de configuración se producen en el almacén de Administración Central, lo que elimina los problemas de "desincronización". 
  
Las copias de solo lectura de los datos se replican en todos los servidores de la topología, incluyendo los servidores perimetrales y las aplicaciones de sucursal con funciones de supervivencia. Un servicio que se ejecuta de forma predeterminada en el contexto del servicio de red es el encargado de administrar la replicación, de modo que los permisos y derechos se reducen a los de un simple usuario del equipo. 
  
### <a name="server-to-server-authentication"></a>Autenticación de servidor a servidor

En Skype para Business Server, se puede configurar la autenticación entre servidores mediante el protocolo Open Authorization (OAuth). Por ejemplo, puede configurar Skype para Business Server realizar la autenticación con un servidor que ejecuta Microsoft Exchange Server 2016. Mediante el protocolo OAuth, la Skype para Business Server y Microsoft Exchange Server puede confíen entre sí. Esto proporciona la posibilidad de integrar los productos de forma sencilla. Para obtener información detallada, vea [Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones asociadas en Skype para Business Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Administración basada en Windows PowerShell e interfaz de administración basada en web

Skype para Business Server proporciona una interfaz de administración eficaces, integrada en la interfaz de línea de comandos de Windows PowerShell. Incluye cmdlets para administración de seguridad, y las características de seguridad de Windows PowerShell se habilitan de manera predeterminada de manera que los usuarios no puedan ejecutar scripts fácilmente o sin saberlo. Esto significa que los valores predeterminados de software se configuran automáticamente de manera que ayuden a maximizar la seguridad y a reducir las vías de ataque. Para obtener información detallada sobre la compatibilidad de administración de Windows PowerShell en Skype para Business Server, vea [Skype para Shell de administración de servidor empresarial](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Control de acceso basado en roles (RBAC)

Skype para Business Server proporciona control de acceso basado en roles (RBAC) que le permite delegar tareas administrativas a la vez mantener altos estándares de seguridad. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben los derechos administrativos que requiere su trabajo. Skype para Business Server proporciona la capacidad para crear un nuevo rol y también la posibilidad de modificar un rol existente. 
  
## <a name="network-address-translation-nat"></a>Traducción de direcciones de red (NAT)

Skype para Business Server no admite el uso de traducción de direcciones de red (NAT) en la interfaz interna del servidor perimetral, pero es compatible con la colocación de la interfaz externa del servicio de servidor perimetral de acceso, servicio perimetral de conferencia Web y A / servicio perimetral A/v detrás de un enrutador o servidor de seguridad que realiza la traducción de direcciones de red (NAT) para escaladas y únicas había consolidada topologías de servidor perimetral. Si hay varios servidores perimetrales tras un equilibrador de carga de hardware, no se podrá utilizar NAT. Si hay varios servidores perimetrales que utilizan NAT en sus interfaces externas, se necesitará aplicar equilibrio de carga de sistema de nombres de dominio (DNS). El equilibrio de carga de DNS permite, al mismo tiempo, reducir el número de direcciones IP públicas por servidor perimetral en grupo de servidores perimetrales. Para obtener más información, vea [escenarios de servidor perimetral de Skype para Business Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Si su empresa se federa con otra que tenga una implementación de Microsoft Office Communications Server 2007 y necesita utilizar audio/vídeo entre su empresa y la empresa federada, los requisitos de los puertos serán los correspondientes a la versión antigua de servidores perimetrales que se haya implementado. Por ejemplo, los intervalos de puertos necesarios para las más antiguas versiones deben estar abiertas para ambas empresas hasta que el socio federado actualiza sus servidores perimetrales a Skype para Business Server. En ese momento, los requisitos en materia de puertos se podrán revisar y reducir de acuerdo con la nueva configuración. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Certificados simplificados para servidores perimetrales

El asistente para implementación puede rellenar automáticamente los nombres de sujetos (SN) y los nombres alternativos de sujetos (SAN) para reducir la probabilidad de incluir entradas innecesarias y potencialmente no seguras.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo de vida de desarrollo de seguridad (SDL) de Trustworthy Computing

Skype para Business Server está diseñado y desarrollado conforme al [Microsoft Trustworthy Computing Security Development Lifecycle](https://go.microsoft.com/fwlink/p/?linkid=68761) (computación confiable).
  
- **Confiable por diseño** El primer paso en la creación de un sistema de comunicaciones unificadas más seguro fue para diseñar modelos de amenaza y probar cada característica que se había diseñado. Además, Microsoft realiza pruebas fuera el comportamiento diseñado con el fin de encontrar vulnerabilidades de seguridad resultante de comportamiento del producto inesperado. Se incorporaron muchas mejoras relacionadas con la seguridad, tanto al proceso como a las prácticas de codificación. Las herramientas de tiempo de compilación detectan excesos de almacenaje y otras amenazas de seguridad antes de que el código se incorpore al producto final. Obviamente, es imposible realizar diseños contra amenazas de seguridad desconocidas. Ningún sistema puede garantizar la seguridad total. Sin embargo, debido a que el desarrollo de productos adoptaron principios de diseño seguro desde el principio, Skype para Business Server incorpora las tecnologías de seguridad estándar del sector como una parte fundamental de su arquitectura.
    
- **Confiable de forma predeterminada** De forma predeterminada, se cifran las comunicaciones de red en Skype para Business Server. Debido a que todos los servidores usan certificados y la autenticación Kerberos, TLS, el protocolo seguro de transporte en tiempo real (SRTP) y otras técnicas de cifrado estándar del sector, incluido el cifrado estándar de cifrado avanzado (AES) de 128 bits, prácticamente todos los Skype para Datos del servidor empresarial está protegidos en la red. Además, el control de acceso basado en roles hace posible implementar servidores que ejecuten Skype para Business Server para que cada función de servidor ejecuta únicamente los servicios y sólo tiene los permisos relacionados con estos servicios, que son adecuados para el rol de servidor.
    
- **Confiable por desarrollo** Todos los Skype para la documentación de Business Server incluye procedimientos recomendados y recomendaciones que le ayudarán a determinar y configurar los niveles de seguridad óptima para la implementación y evaluar los riesgos de seguridad de activación de las opciones que no sean predeterminadas.
    

