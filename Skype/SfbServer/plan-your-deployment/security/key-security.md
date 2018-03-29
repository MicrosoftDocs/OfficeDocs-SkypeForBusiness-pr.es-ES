---
title: Características de seguridad de clave de Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype para el año 2015 de Business Server incluye varias características de seguridad, como autenticación de servidor a servidor, control de acceso basado en funciones y almacenamiento centralizado de datos de configuración.
ms.openlocfilehash: 629444f4490022bb9f37f5c67f72f393345ec1a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="key-security-features-in-skype-for-business-server-2015"></a>Características de seguridad de clave de Skype Empresarial Server 2015
 
Skype para el año 2015 de Business Server incluye varias características de seguridad, como autenticación de servidor a servidor, control de acceso basado en funciones y almacenamiento centralizado de datos de configuración. 
  
Este artículo proporciona una introducción de alto nivel de Skype para seguridad Business Server 2015. 
  
## <a name="key-security-features-in-skype-for-business-server-2015"></a>Características de seguridad clave de Skype para Business Server 2015

La seguridad es un tema muy amplio. Seguridad abarca todas las características de Skype para Business Server 2015 así como las bases de datos, servicios y hardware que componen un Skype para el ecosistema de servidores empresariales. Este artículo describe algunas de las características de Skype para Business Server 2015 en particular que están diseñados para la seguridad.
  
### <a name="planning-and-design-tools"></a>Herramientas de planeación y diseño

Skype para Business Server 2015 proporciona dos herramientas para facilitar la planificación y diseño y para reducir la posibilidad de configurar mal Skype para los componentes de Business Server. 
  
- **Herramienta de planeación de topología** automatiza gran parte del proceso de diseño de topología. Puede exportar los resultados de la herramienta de planeación para el generador de topología, que es la herramienta que se necesita para instalar a cada servidor Skype para Business Server 2015.
    
- El **Generador de topologías** almacena toda la información de configuración en el almacén de administración central.
    
Para obtener más información acerca de estas herramientas, vea [Skype para herramientas de administración de Business Server 2015](../../management-tools/management-tools.md) y [planear su Skype para la implementación de Business Server 2015](../../plan-your-deployment/plan-your-deployment.md).
  
### <a name="central-management-store"></a>Almacén de administración central

En Skype para Business Server 2015, datos de configuración sobre los servidores y servicios están parte del almacén de Administración Central. El almacén de Administración Central proporciona un almacenamiento sólido y esquematizado de los datos necesarios para definir, configurar, mantener, administrar, describir y operar un Skype para la implementación de Business Server. También comprueba los datos para asegurarse de que la configuración es coherente. Todos los cambios en estos datos de configuración que se producen en el almacén de Administración Central, eliminando problemas de "fuera de sincronización". 
  
Las copias de solo lectura de los datos se replican en todos los servidores de la topología, incluyendo los servidores perimetrales y las aplicaciones de sucursal con funciones de supervivencia. Un servicio que se ejecuta de forma predeterminada en el contexto del servicio de red es el encargado de administrar la replicación, de modo que los permisos y derechos se reducen a los de un simple usuario del equipo. 
  
### <a name="server-to-server-authentication"></a>Autenticación de servidor a servidor

En Skype para Business Server 2015, puede configurarse la autenticación entre servidores mediante el protocolo de autorización abierta (OAuth). Por ejemplo, puede configurar Skype para Business Server 2015 autenticar con un servidor que está ejecutando Microsoft Exchange Server 2016. Mediante el protocolo OAuth, el Skype para Business Server y la de Microsoft Exchange Server puede confiar en ellos. Esto proporciona la posibilidad de integrar los productos de forma sencilla. Para obtener más información, vea [Administrar la autenticación de servidor a servidor (OAuth) y aplicaciones de los socios en Skype para Business Server 2015](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Administración basada en Windows PowerShell e interfaz de administración basada en web

Skype para Business Server 2015 proporciona una eficaz interfaz de administración, basada en la interfaz de línea de comandos de Windows PowerShell. Incluye cmdlets para administración de seguridad, y las características de seguridad de Windows PowerShell se habilitan de manera predeterminada de manera que los usuarios no puedan ejecutar scripts fácilmente o sin saberlo. Esto significa que los valores predeterminados de software se configuran automáticamente de manera que ayuden a maximizar la seguridad y a reducir las vías de ataque. Para obtener más información sobre la compatibilidad de administración de Windows PowerShell en Skype para Business Server 2015, vea [Skype para el Shell de administración de negocio servidor 2015](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Control de acceso basado en roles (RBAC)

Skype para Business Server 2015 proporciona control de acceso basado en roles (RBAC) que le permite delegar tareas administrativas manteniendo los altos estándares de seguridad. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben los derechos administrativos que requiere su trabajo. Skype para el año 2015 de Business Server proporciona la capacidad para crear un nuevo rol y también la capacidad de modificar un rol existente. 
  
## <a name="network-address-translation-nat"></a>Traducción de direcciones de red (NAT)

Skype para el año 2015 de Business Server no admite el uso de traducción de direcciones de red (NAT) en la interfaz interna del servidor perimetral, pero es compatible con la colocación de la interfaz externa del servicio de servidor perimetral de acceso, el servicio perimetral de conferencia Web y A / arista V servicio detrás de un enrutador o un firewall que realiza traducción de direcciones de red (NAT) para la escala y solo había consolidado topologías de servidor perimetral. Si hay varios servidores perimetrales tras un equilibrador de carga de hardware, no se podrá utilizar NAT. Si hay varios servidores perimetrales que utilizan NAT en sus interfaces externas, se necesitará aplicar equilibrio de carga de sistema de nombres de dominio (DNS). El equilibrio de carga de DNS permite, al mismo tiempo, reducir el número de direcciones IP públicas por servidor perimetral en grupo de servidores perimetrales. Para obtener más información, vea [escenarios de servidor perimetral en Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Si su empresa se federa con otra que tenga una implementación de Microsoft Office Communications Server 2007 y necesita utilizar audio/vídeo entre su empresa y la empresa federada, los requisitos de los puertos serán los correspondientes a la versión antigua de servidores perimetrales que se haya implementado. Por ejemplo, los intervalos de puertos necesarios para las más antiguas versiones deben estar abiertas para ambas empresas hasta que el socio federado actualiza sus servidores perimetrales a Skype para Business Server 2015. En ese momento, los requisitos en materia de puertos se podrán revisar y reducir de acuerdo con la nueva configuración. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Certificados simplificados para servidores perimetrales

El asistente para implementación puede rellenar automáticamente los nombres de sujetos (SN) y los nombres alternativos de sujetos (SAN) para reducir la probabilidad de incluir entradas innecesarias y potencialmente no seguras.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo de vida de desarrollo de seguridad (SDL) de Trustworthy Computing

Skype para Business Server 2015 diseñado y desarrollado en cumplimiento de [Microsoft Trustworthy Computing Security Development Lifecycle](https://go.microsoft.com/fwlink/p/?linkid=68761) (SDL).
  
- **Confianza por diseño** El primer paso en la creación de un sistema de comunicaciones unificadas más seguro fue diseñar modelos de amenazas y probar cada característica tal como se diseñó. Además, Microsoft realiza pruebas fuera el comportamiento diseñado con el fin de encontrar vulnerabilidades de seguridad resultantes de comportamiento inesperado del producto. Se han creado varias mejoras relacionadas con la seguridad en el proceso de codificación y prácticas. Herramientas en tiempo de compilación detectan saturaciones de búfer y otras posibles amenazas de seguridad antes que el código está desprotegido el producto final. Por supuesto, es imposible diseño contra todas las amenazas de seguridad desconocido. Ningún sistema puede garantizar una seguridad completa. Sin embargo, porque el desarrollo de productos adoptaron principios de diseño seguro desde el principio, Skype para Business Server 2015 incorpora tecnologías de seguridad estándar de la industria como una parte fundamental de su arquitectura.
    
- **Confianza de forma predeterminada** De forma predeterminada, se cifran las comunicaciones en Skype para Business Server 2015. Dado que todos los servidores utilizan autenticación Kerberos y certificados, TLS, protocolo seguro de transporte de en tiempo real (SRTP) y otras técnicas de cifrado estándar del sector, incluyendo cifrado estándar de cifrado avanzado (AES, Advanced Encryption Standard) de 128 bits, prácticamente todos los Skype para Datos de servidor de negocios está protegidos en la red. Además, control de acceso basado en roles permite implementar servidores ejecutan Skype para Business Server 2015 para cada función de servidor ejecuta sólo en los servicios y tiene sólo los permisos relacionados con dichos servicios, que son adecuados para la función del servidor.
    
- **Confianza con la implementación de** Skype todos para la documentación de Business Server 2015 incluye mejores prácticas y recomendaciones para ayudarle a determinar y configurar los niveles de seguridad óptima para su implementación y evaluar los riesgos de seguridad de activación de opciones no predeterminadas.
    

