---
title: Características clave de seguridad en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype Empresarial Server incluye varias características de seguridad, como la autenticación de servidor a servidor, el control de acceso basado en roles y el almacenamiento centralizado de datos de configuración.
ms.openlocfilehash: 1163216f2aeb369576f51af53180297f8028813e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832180"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Características clave de seguridad en Skype Empresarial Server
 
Skype Empresarial Server incluye varias características de seguridad, como la autenticación de servidor a servidor, el control de acceso basado en roles y el almacenamiento centralizado de datos de configuración. 
  
En este artículo se proporciona información general de alto nivel sobre la seguridad de Skype Empresarial Server. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Características clave de seguridad en Skype Empresarial Server

La seguridad es un tema muy amplio. La seguridad llega a todas las características de Skype Empresarial Server, así como a bases de datos, servicios y hardware que forma un ecosistema de Skype Empresarial Server. En este artículo se describen algunas de las características de Skype Empresarial Server en particular diseñadas para la seguridad.
  
### <a name="planning-and-design-tools"></a>Herramientas de planeación y diseño

Skype Empresarial Server proporciona dos herramientas para facilitar la planeación y el diseño y para reducir la posibilidad de configurar de forma errónea componentes de Skype Empresarial Server. 
  
- **La Herramienta de planeación de** topología automatiza gran parte del proceso de diseño de la topología. Puede exportar los resultados de la Herramienta de planeación al Generador de topologías, que es la herramienta necesaria para instalar cada servidor que ejecute Skype Empresarial Server.
    
- **Topology Builder** almacena toda la información de configuración en el almacén de administración central.
    
Para obtener más información sobre estas herramientas, consulte Herramientas de administración [de Skype Empresarial Server.](../../management-tools/management-tools.md)
  
### <a name="central-management-store"></a>Almacén de administración central

En Skype Empresarial Server, los datos de configuración sobre servidores y servicios forman parte del almacén de administración central. El almacén de administración central proporciona un almacenamiento sólido y esquematizado de los datos necesarios para definir, configurar, mantener, administrar, describir y operar una implementación de Skype Empresarial Server. También valida los datos para garantizar la coherencia de la configuración. Todos los cambios en estos datos de configuración se suceden en el almacén de administración central, lo que elimina los problemas de "no sincronización". 
  
Las copias de solo lectura de los datos se replican a todos los servidores de la topología, incluidos los servidores perimetrales. La replicación se administra por medio de un servicio que, de manera predeterminada, se ejecuta en el contexto del servicio de red limitando los derechos y permisos a los de un simple usuario del equipo. 
  
### <a name="server-to-server-authentication"></a>Autenticación de servidor a servidor

En Skype Empresarial Server, la autenticación se puede configurar entre servidores mediante el protocolo Open Authorization (OAuth). Por ejemplo, puede configurar Skype Empresarial Server para que se autentique con un servidor que Microsoft Exchange Server 2016. Con el protocolo OAuth, Skype Empresarial Server y el Microsoft Exchange Server pueden confiar entre sí. Esto proporciona la capacidad de integrar los productos de forma fluida. Para obtener más información, consulte Administrar la autenticación de servidor [a servidor (OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md)y las aplicaciones de socio en Skype Empresarial Server.
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell basada en web e interfaz de administración basada en web

Skype Empresarial Server proporciona una interfaz de administración eficaz, integrada en la Windows PowerShell de línea de comandos. Incluye cmdlets para administración de seguridad, y las características de seguridad de Windows PowerShell se habilitan de manera predeterminada de manera que los usuarios no puedan ejecutar scripts fácilmente o sin saberlo. Esto significa que los valores predeterminados de software se configuran automáticamente de manera que ayuden a maximizar la seguridad y a reducir las vías de ataque. Para obtener más información Windows PowerShell de administración en Skype Empresarial Server, consulte Shell de administración [de Skype Empresarial Server.](../../manage/management-shell.md) 
  
### <a name="role-based-access-control-rbac"></a>Control de acceso basado en roles (RBAC)

Skype Empresarial Server proporciona control de acceso basado en roles (RBAC) para permitirle delegar tareas administrativas a la vez que mantiene altos estándares de seguridad. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben los derechos administrativos que requiere su trabajo. Skype Empresarial Server proporciona la capacidad de crear un nuevo rol y también la capacidad de modificar un rol existente. 
  
## <a name="network-address-translation-nat"></a>Traducción de direcciones de red (NAT)

Skype Empresarial Server no admite el uso de traducción de direcciones de red (NAT) en la interfaz interna del servidor perimetral, pero sí admite la colocación de la interfaz externa del servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V detrás de un enrutador o firewall que realice la traducción de direcciones de red (NAT) para topologías de servidor perimetral consolidadas únicas y a escala. Varios servidores perimetrales detrás de un equilibrador de carga de hardware no pueden usar NAT. Si varios servidores perimetrales usan NAT en sus interfaces externas, se requiere el equilibrio de carga del Sistema de nombres de dominio (DNS). A su vez, el uso del equilibrio de carga de DNS permite reducir el número de direcciones IP públicas por servidor perimetral en un grupo de servidores perimetrales. Para obtener más información, [consulte escenarios de servidor perimetral en Skype Empresarial Server.](../../plan-your-deployment/edge-server-deployments/scenarios.md)
  
> [!NOTE]
> Si se federa con empresas que tienen una implementación de Microsoft Office Communications Server 2007 y necesita usar audio y vídeo entre la empresa y la empresa federada, los requisitos de puerto serán los de la versión anterior de los servidores perimetrales implementados. Por ejemplo, los intervalos de puertos necesarios para esas versiones anteriores deben abrirse para ambas empresas hasta que el socio federado actualice sus servidores perimetrales a Skype Empresarial Server. En ese momento, los requisitos en materia de puertos se podrán revisar y reducir de acuerdo con la nueva configuración. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Certificados simplificados para servidores perimetrales

El asistente para implementación puede rellenar automáticamente los nombres de sujetos (SN) y los nombres alternativos de sujetos (SAN) para reducir la probabilidad de incluir entradas innecesarias y potencialmente no seguras.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo de vida de desarrollo de seguridad (SDL) de informática de confianza

Skype Empresarial Server está diseñado y desarrollado de acuerdo con el ciclo de vida de desarrollo de seguridad (SDL) de [Microsoft Trustworthy Computing.](https://go.microsoft.com/fwlink/p/?linkid=68761)
  
- **Confiable por diseño** El primer paso para crear un sistema de comunicaciones unificadas más seguro fue diseñar modelos de amenazas y probar cada característica tal como se diseñó. Además, Microsoft realiza pruebas fuera del comportamiento diseñado para encontrar vulnerabilidades de seguridad resultantes del comportamiento inesperado del producto. Se integraron varias mejoras relacionadas con la seguridad en los procesos y procedimientos de codificación. Las herramientas en tiempo de compilación detectaron la saturación del búfer y otras posibles amenazas para la seguridad antes de que se comprobase el código en el producto final. Naturalmente, es imposible que al diseñar se tengan en cuenta todas las amenazas desconocidas en materia de seguridad. Ningún sistema puede garantizar una total seguridad. Sin embargo, dado que el desarrollo de productos adoptó principios de diseño seguro desde el principio, Skype Empresarial Server incorpora tecnologías de seguridad estándar del sector como parte fundamental de su arquitectura.
    
- **Confiable de forma predeterminada** De forma predeterminada, las comunicaciones de red en Skype Empresarial Server están cifradas. Dado que todos los servidores usan certificados y autenticación Kerberos, TLS, Protocolo de transporte Real-Time seguro (SRTP) y otras técnicas de cifrado estándar del sector, incluido el cifrado estándar de cifrado avanzado (AES) de 128 bits, prácticamente todos los datos de Skype Empresarial Server están protegidos en la red. Además, el control de acceso basado en roles permite implementar servidores que ejecutan Skype Empresarial Server para que cada rol de servidor ejecute solo los servicios y solo tenga los permisos relacionados con esos servicios que sean adecuados para el rol de servidor.
    
- **Confiable por implementación** Toda la documentación de Skype Empresarial Server incluye procedimientos recomendados y recomendaciones para ayudarle a determinar y configurar los niveles de seguridad óptimos para su implementación y evaluar los riesgos de seguridad de activar opciones no predeterminadas.
    

