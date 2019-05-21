---
title: Características de seguridad clave de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype empresarial Server incluye varias características de seguridad, entre las que se incluyen la autenticación de servidor a servidor, el control de acceso basado en roles y el almacenamiento centralizado de los datos de configuración.
ms.openlocfilehash: cd86d1ac404cd2fe487f6f9369cc73df0d72c52f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296892"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Características de seguridad clave de Skype empresarial Server
 
Skype empresarial Server incluye varias características de seguridad, entre las que se incluyen la autenticación de servidor a servidor, el control de acceso basado en roles y el almacenamiento centralizado de los datos de configuración. 
  
Este artículo ofrece información general de alto nivel sobre la seguridad de Skype empresarial Server. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Características de seguridad clave de Skype empresarial Server

La seguridad es un tema muy amplio. La seguridad llega a todas las características de Skype empresarial Server, así como a las bases de datos, los servicios y el hardware que componen un ecosistema de Skype empresarial Server. En este artículo, se describen algunas de las características de Skype empresarial Server en particular, diseñadas para la seguridad.
  
### <a name="planning-and-design-tools"></a>Herramientas de planeación y diseño

Skype empresarial Server proporciona dos herramientas para facilitar la planificación y el diseño, y para reducir la posibilidad de que se configuren componentes de Skype empresarial. 
  
- La herramienta de planeación de la **topología** automatiza gran parte del proceso de diseño de la topología. Puede exportar los resultados de la herramienta de planeación a Topology Builder, que es la herramienta necesaria para instalar cada servidor que ejecute Skype empresarial Server.
    
- El **Generador de topologías** almacena toda la información de configuración en el almacén de administración central.
    
Para obtener más información sobre estas herramientas, consulte [herramientas de administración de Skype empresarial Server](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Almacén de administración central

En Skype empresarial Server, los datos de configuración de los servidores y los servicios forman parte del almacén central de administración. El almacén central de administración proporciona un sólido almacenamiento schematized de los datos necesarios para definir, configurar, mantener, administrar, describir y ejecutar una implementación de Skype empresarial Server. También comprueba los datos para asegurarse de que la configuración es coherente. Todos los cambios en estos datos de configuración se producen en el almacén de administración central, eliminando problemas de "dessincronización". 
  
Las copias de solo lectura de los datos se replican en todos los servidores de la topología, incluyendo los servidores perimetrales y las aplicaciones de sucursal con funciones de supervivencia. Un servicio que se ejecuta de forma predeterminada en el contexto del servicio de red es el encargado de administrar la replicación, de modo que los permisos y derechos se reducen a los de un simple usuario del equipo. 
  
### <a name="server-to-server-authentication"></a>Autenticación de servidor a servidor

En Skype empresarial Server, la autenticación se puede configurar entre servidores mediante el protocolo de autorización abierta (OAuth). Por ejemplo, puede configurar Skype empresarial Server para autenticar con un servidor que ejecuta Microsoft Exchange Server 2016. Con el protocolo OAuth, Skype empresarial Server y Microsoft Exchange Server pueden confiar entre sí. Esto proporciona la posibilidad de integrar los productos de forma sencilla. Para obtener más información, vea [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Skype empresarial Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Administración basada en Windows PowerShell e interfaz de administración basada en web

Skype empresarial Server proporciona una eficaz interfaz de administración, creada en la interfaz de línea de comandos de Windows PowerShell. Incluye cmdlets para administración de seguridad, y las características de seguridad de Windows PowerShell se habilitan de manera predeterminada de manera que los usuarios no puedan ejecutar scripts fácilmente o sin saberlo. Esto significa que los valores predeterminados de software se configuran automáticamente de manera que ayuden a maximizar la seguridad y a reducir las vías de ataque. Para obtener más información sobre la compatibilidad de administración de Windows PowerShell en Skype empresarial Server, consulte [Shell de administración de Skype empresarial Server](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Control de acceso basado en roles (RBAC)

Skype empresarial Server proporciona control de acceso basado en roles (RBAC) para permitir delegar tareas administrativas a la vez que se mantienen estándares altos de seguridad. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben los derechos administrativos que requiere su trabajo. Skype empresarial Server proporciona la capacidad de crear un nuevo rol y también la capacidad de modificar un rol existente. 
  
## <a name="network-address-translation-nat"></a>Traducción de direcciones de red (NAT)

Skype empresarial Server no admite el uso de la traducción de direcciones de red (NAT) en la interfaz interna del servidor perimetral, pero admite la colocación de la interfaz externa del servicio perimetral de acceso, el servicio perimetral de conferencias web y el servicio perimetral A/V detrás de un enrutador o firewall que realice la traducción de direcciones de red (NAT) para topologías de servidores perimetrales individuales y a escala. Si hay varios servidores perimetrales tras un equilibrador de carga de hardware, no se podrá utilizar NAT. Si hay varios servidores perimetrales que utilizan NAT en sus interfaces externas, se necesitará aplicar equilibrio de carga de sistema de nombres de dominio (DNS). El equilibrio de carga de DNS permite, al mismo tiempo, reducir el número de direcciones IP públicas por servidor perimetral en grupo de servidores perimetrales. Para obtener más información, consulte [escenarios de servidores perimetrales en Skype empresarial Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Si su empresa se federa con otra que tenga una implementación de Microsoft Office Communications Server 2007 y necesita utilizar audio/vídeo entre su empresa y la empresa federada, los requisitos de los puertos serán los correspondientes a la versión antigua de servidores perimetrales que se haya implementado. Por ejemplo, los intervalos de puertos necesarios para esas versiones anteriores deben abrirse en ambas empresas hasta que el socio federado actualice sus servidores perimetrales a Skype empresarial Server. En ese momento, los requisitos en materia de puertos se podrán revisar y reducir de acuerdo con la nueva configuración. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Certificados simplificados para servidores perimetrales

El asistente para implementación puede rellenar automáticamente los nombres de sujetos (SN) y los nombres alternativos de sujetos (SAN) para reducir la probabilidad de incluir entradas innecesarias y potencialmente no seguras.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo de vida de desarrollo de seguridad (SDL) de Trustworthy Computing

Skype empresarial Server se ha diseñado y desarrollado en conformidad con el [ciclo de vida de desarrollo de seguridad de Microsoft Trustworthy Computing](https://go.microsoft.com/fwlink/p/?linkid=68761) (SDL).
  
- **Digno de confianza por diseño** El primer paso para crear un sistema de comunicaciones unificado más seguro era diseñar modelos de amenazas y probar cada característica tal como se diseñó. Además, Microsoft realiza pruebas fuera del comportamiento diseñado para encontrar vulnerabilidades de seguridad derivadas del comportamiento inesperado del producto. Se incorporaron muchas mejoras relacionadas con la seguridad, tanto al proceso como a las prácticas de codificación. Las herramientas de tiempo de compilación detectan excesos de almacenaje y otras amenazas de seguridad antes de que el código se incorpore al producto final. Obviamente, es imposible realizar diseños contra amenazas de seguridad desconocidas. Ningún sistema puede garantizar la seguridad total. Sin embargo, dado que el desarrollo del producto ha adoptado principios de diseño seguros desde el principio, Skype empresarial Server incorpora las tecnologías de seguridad estándar de la industria como parte fundamental de su arquitectura.
    
- **Fidedigno de forma predeterminada** De forma predeterminada, las comunicaciones de red de Skype empresarial Server están cifradas. Como todos los servidores usan certificados y autenticación Kerberos, TLS, protocolo seguro de transporte en tiempo real (SRTP) y otras técnicas de cifrado estándar de la industria, incluido el cifrado estándar de cifrado avanzado (AES) de 128, casi todos los usuarios de Skype para Los datos de Business Server están protegidos en la red. Además, el control de acceso basado en roles permite implementar servidores que ejecuten Skype empresarial Server para que cada rol de servidor solo ejecute los servicios y tenga solo los permisos relacionados con dichos servicios, que son adecuados para el rol de servidor.
    
- **Confianza por implementación** Toda la documentación de Skype empresarial Server incluye procedimientos recomendados y recomendaciones para ayudarle a determinar y configurar los niveles de seguridad óptimos para su implementación y evaluar los riesgos de seguridad de activar opciones no predeterminadas.
    

