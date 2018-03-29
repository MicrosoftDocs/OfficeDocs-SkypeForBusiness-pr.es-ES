---
title: Skype para soluciones de negocio híbrido
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0b038686-ed36-4867-9653-14cc08c919cb
description: Para obtener información acerca de cómo planear un Skype para la implementación de empresa híbrido.
ms.openlocfilehash: c2ed5a488bae74e1756ca02b0b28e9770efe0160
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-hybrid-solutions"></a>Skype para soluciones de negocio híbrido
 
Para obtener información acerca de cómo planear un Skype para la implementación de empresa híbrido. 
  
En este tema se presentan distintas configuraciones híbridas que pueden ayudarlo a determinar qué configuración es la mejor para su empresa. Luego, puede leer más sobre la configuración que le interese, siguiendo los vínculos de este tema. Este artículo contiene las siguientes secciones:
  
- [Configuraciones híbridas de Skype Empresarial](skype-for-business-hybrid-solutions.md#BKMK_HybridConfigurations)
    
- [Agregar Skype para los negocios en línea en el actual local Skype para el entorno empresarial](skype-for-business-hybrid-solutions.md#BKMK_HybridConnectivity)
    
- [Aprovechar las ventajas del sistema de teléfono en Office 365 (nube PBX)](skype-for-business-hybrid-solutions.md#BKMK_CloudPBX)
    
- [Integración con Exchange y SharePoint](skype-for-business-hybrid-solutions.md#BKMK_IntegratewExchangeSharePoint)
    
- [Tareas para planificar y configurar un entorno híbrido](skype-for-business-hybrid-solutions.md#BKMK_Tasks)
    
- [Para más información](skype-for-business-hybrid-solutions.md#BKMK_MoreInfo)
    
## <a name="skype-for-business-hybrid-configurations"></a>Configuraciones híbridas de Skype Empresarial
<a name="BKMK_HybridConfigurations"> </a>

Skype para empresas es compatible con varias configuraciones de híbridos. Puede agregar Skype para los negocios en línea en el actual local Skype para el entorno empresarial, integrar su Skype para la implementación de empresa con Exchange Online y SharePoint Online y aprovechar las ventajas del sistema de teléfono en Office 365 (PBX nube), de Microsoft tecnología para habilitar capacidades de Private Branch Exchange (PBX) de la nube de Office 365 con Skype y control de llamadas para los negocios en línea. 
  
Con un Skype para la implementación de empresa híbrido, combinar un Skype para la suscripción de los negocios en línea con su Skype locales para la oferta del negocio. Puede empezar a crear habilidades de administración de software como servicio en su organización y mover su Skype para usuarios de negocio a la nube a su propio ritmo. Los usuarios que están alojados en la nube pueden aprovechar el sistema de teléfono en Office 365 sin perder la conectividad de la red pública de telefónica conmutada (PSTN) local.
  
Con un Skype para configuración híbrida de negocio, tenga en cuenta los siguiente:
  
- Algunos usuarios podrían estar alojados localmente y algunos en línea, pero todos ellos comparten el mismo dominio de Protocolo de inicio de sesión (SIP), como contoso.com.
    
- Puede migrar usuarios de Skype para empresas en instalaciones a Skype para los negocios en línea con el tiempo, en la programación.
    
- Puede realizar una integración con otras aplicaciones de Microsoft Office 365, incluidas Exchange Online y SharePoint Online.
    
- Puede realizar una integración con Exchange y SharePoint.
    
- Puede aprovechar Difusión de reunión de Skype.
    
- Puede aprovechar la función de conferencia RTC.
    
## <a name="add-skype-for-business-online-into-your-existing-on-premises-skype-for-business-environment"></a>Agregar Skype para los negocios en línea en el actual local Skype para el entorno empresarial
<a name="BKMK_HybridConnectivity"> </a>

Conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea significa que los usuarios de un dominio, como contoso.com, se dividen entre el uso de Skype para Business Server en locales y Skype para los negocios en línea. Algunos usuarios del dominio están alojados en forma local, mientras que otros están en línea. Puede configurar su implementación local para híbrido con Skype para los negocios en línea y utilizar sincronización de Active Directory para mantener su local y sincronizados de usuarios en línea. 
  
El diagrama siguiente muestra cómo puede agregar Skype para los negocios en línea en tu Skype local existente para el entorno empresarial, lo que permite mover los usuarios a la nube a su propio ritmo:
  
![Configuración híbrida de Skype Empresarial](../media/4580f2c8-7008-4c6e-826c-020d0f2d1636.png)
  
Para obtener más información, vea [Planear la conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea](plan-hybrid-connectivity.md) y [conectividad de implementación híbrida entre Skype para Business Server y Skype para los negocios en línea](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="take-advantage-of-phone-system-in-office-365-cloud-pbx"></a>Aprovechar las ventajas del sistema de teléfono en Office 365 (nube PBX)
<a name="BKMK_CloudPBX"> </a>

 Sistema de teléfono en Office 365 (nube PBX) es la tecnología de Microsoft para habilitar el control de llamadas y capacidades de Private Branch Exchange (PBX) de la nube de Office 365 con Skype para los negocios en línea. Sistema de teléfono en Office 365 permite reemplazar su sistema PBX existente con un conjunto de características de entrega de Office 365 y estrechamente integrados en la experiencia de productividad de nube de Microsoft.
  
Además del sistema de teléfono dos ofertas híbrido de Office 365, Microsoft ofrece el sistema telefónico en Office 365 con el Plan para llamar a: una llamada a servicio PSTN, para una solución todo-en la nube que no requiere una implementación de servidor local. Para decidir si el sistema de teléfono en Office 365 con el Plan de llamadas podría ser la solución adecuada para su organización, consulte el [Sistema de teléfono en soluciones de Office 365](plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings).
  
Existen dos sistema de teléfono en las ofertas de Office 365 híbrido: 
  
- [Sistema de teléfono en Office 365 con conectividad local proporcionada por su Skype para la implementación de Business Server](skype-for-business-hybrid-solutions.md#BKMK_Server)
    
- [Sistema de teléfono en Office 365 con conectividad local proporcionada por Skype para conector de nube Business Server Edition](skype-for-business-hybrid-solutions.md#BKMK_CCE)
    
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-your-skype-for-business-server-deployment"></a>Sistema de teléfono en Office 365 con conectividad local proporcionada por su Skype para la implementación de Business Server
<a name="BKMK_Server"> </a>

Esta configuración se compone de un Skype para la implementación local de Business Server modificado para híbrido PSTN. Los usuarios de su organización que están alojados en la nube pueden recibir servicios de PBX de la nube de Microsoft, pero implementación Business Server proporciona la conectividad PSTN a Telefonía IP empresarial en su locales Skype. 
  
![PBX en la nube con implementación de Skype Empresarial Server](../media/d4136bbc-b01e-469c-bf94-90ba59c61cda.png)
  
Esta es la mejor configuración si: 
  
- Su sistema PBX no ofrece características únicas que necesita conservar.
    
- Llamar a Plan, el servicio de llamadas PSTN de Office 365, no está disponible en su región.
    
- Tiene un Lync existente o Skype para la implementación de Business Server.
    
Para obtener más información, consulte [planificación del sistema de teléfono en Office 365 con conectividad PSTN en Skype para Business Server local](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md) y [Permitir a los usuarios para el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server](plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system.md).
  
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-skype-for-business-server-cloud-connector-edition"></a>Sistema de teléfono en Office 365 con conectividad local proporcionada por Skype para conector de nube Business Server Edition
<a name="BKMK_CCE"> </a>

Esta configuración consta de un conjunto de máquinas virtuales empaquetadas que implementan la conectividad con RTC local. Implementando un mínimo Skype para topología Business Server en un entorno virtualizado, los usuarios de su organización que están alojados en la nube pueden recibir servicios de PBX de la nube de Microsoft, pero se proporciona conectividad PSTN a través de la voz en instalaciones existentes infraestructura. 
  
![CloudPBXCloudConnectorEdition](../media/7a6ee221-bfe1-422b-ac44-6446db6b766c.png)
  
Esta es la mejor configuración si:
  
- Su sistema PBX no ofrece características únicas que necesita conservar.
    
- Llamar a Plan, el servicio de llamadas PSTN de Office 365, no está disponible en su región.
    
- No tienen un Lync existente o Skype para la implementación de Business Server.
    
Para obtener más información, consulte [Plan de Skype para conector de nube Business Edition](plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="integrate-with-exchange-and-sharepoint"></a>Integración con Exchange y SharePoint
<a name="BKMK_IntegratewExchangeSharePoint"> </a>

Un Skype para configuración híbrida de negocio le permite integrar con otras aplicaciones de Microsoft Office 365, incluido Exchange Online y SharePoint Online.
  
### <a name="skype-for-business-server-with-exchange-online-and-sharepoint-online"></a>Skype Empresarial Server con Exchange Online y SharePoint Online

Se puede integrar Skype para Business Server con Exchange Online y SharePoint Online, como se muestra en el siguiente diagrama:
  
![Skype Empresarial Server con Exchange Online y SharePoint Online](../media/9f456ed2-8777-4a20-a519-c87dfc56b7f5.png)
  
Integración de Skype para Business Server con Exchange Online y SharePoint Online tiene varias ventajas. Puede:
  
- Utilizar el conjunto completo de características de Skype para Business Server.
    
- Aprovechar su equipamiento telefónico local existente, como PBX.
    
- Usar Exchange Online para correo electrónico, lo que aligera la carga de los servidores de correo electrónico y el almacenamiento locales.
    
- Usar SharePoint Online para colaboración, lo que aligera la carga del mantenimiento de servidores de SharePoint locales.
    
- Usar Skype para negocios, Exchange y SharePoint había integrado características, incluida mensajería unificada (UM) en Office 365.
    
Para obtener más información, vea [Planear la integración de Skype para empresas y Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
### <a name="exchange-server-with-skype-for-business-online"></a>Exchange Server con Skype Empresarial Online

Exchange Server se puede integrar con Skype para los negocios en línea como se muestra en el siguiente diagrama:
  
![Integrar Exchange con Skype Empresarial Online](../media/e8ca44ad-f47c-46a3-9cef-8fe7deafd615.png)
  
Integración de Exchange Server con Skype para los negocios en línea tiene las siguientes ventajas:
  
- Aprovechar la infraestructura de Exchange existente.
    
- Usar Skype para los negocios en línea para las capacidades de presencia, mensajería instantánea y conferencias. 
    
Para obtener más información, vea [Planear la integración de Skype para empresas y Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
## <a name="tasks-for-planning-and-configuring-a-hybrid-environment"></a>Tareas para planificar y configurar un entorno híbrido
<a name="BKMK_Tasks"> </a>

Skype para empresas proporciona un completo conjunto de capacidades, independientemente de la forma de crear su implementación. La arquitectura que elija determinará qué responsabilidades de TI serán suyas y cuáles tendrá que pagarle a Microsoft para que admita a través de su suscripción. Independientemente de la arquitectura que elija para su organización, existen cinco responsabilidades principales que siempre serán suyas:
  
- **Red y conectividad** : asegurar la capacidad de la red y disponibilidad a través de firewalls, servidores proxy, las puertas de enlace y a través de vínculos WAN mediante la realización de una evaluación de la red o mediante la contratación de un compañero para hacer la evaluación.
    
- **Control de datos &amp; administración de derechos** - clasificar sus datos confidenciales y garantizar que está protegido y supervisado donde se almacena y mientras está en tránsito.
    
- **Extremos de cliente** - establecer, medir y hacer cumplir las normas de seguridad modernos en los dispositivos que se utilizan para tener acceso a sus datos y activos.
    
- **Cuenta &amp; acceder a administración de** - establecer un perfil de actividad de la cuenta "normal" y alerta en una actividad inusual.
    
- **Identidad**: use credenciales protegidas por hardware o autenticación multifactor (MFA) para todas las identidades. 
    
Además de las tareas de arquitectura que realice para el entorno local, tendrá que:
  
- Planear y diseñar requisitos de administración de identidades, incluida la integración de identidades locales con Office 365.
    
- Garantizar la capacidad y disponibilidad de la red.
    
- Adquirir certificados SSL de terceros para brindar seguridad empresarial para las ofertas de servicios de Office 365.
    
- Decidir si desea conectarse a Office 365 con el protocolo de Internet versión 6 (IPv6).
    
- Determinar cuánto integran con locales y versiones en línea de Skype para negocios, Exchange y SharePoint se desea obtener. 
    
- Determinar qué servidor proxy se usará para las solicitudes de Office 365.
    
También debe realizar las siguientes tareas de IT Pro para implementar su Skype para entornos híbridos de negocio:
  
- Asegúrese de que tiene un arrendatario Microsoft Office 365 con Skype para los negocios en línea habilitada.
    
- Implementar el plan de administración de identidades.  
    
- Planear e implementar registros y enrutamiento de DNS internos y externos.
    
- Configurar el proxy o firewall para los requisitos de URL y dirección IP de Office 365.
    
- Administrar cuentas de usuario y Skype para la configuración del negocio en línea. 
    
- Configurar el dispositivo de servidor proxy, si es necesario.  
    
- Configurar la integración de características entre versiones locales y en línea de Exchange Server y SharePoint.
    
## <a name="for-more-information"></a>Para más información
<a name="BKMK_MoreInfo"> </a>

Para obtener más información, consulte los recursos siguientes:
  
- [Recursos de arquitectura de TI de la nube de Microsoft](https://aka.ms/clouditarch)
    
- [Identidad de la nube de Microsoft para enterprise architects](https://aka.ms/cloudidarch)
    
- [Prepárese su organización para Enterprise de Office 365](https://aka.ms/O365EntPrep)
    
- [Planificar la conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online](plan-hybrid-connectivity.md)
    
- [Implementar conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)
    
- [Sistema de teléfono en soluciones de Office 365](plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings)
    
- [Planear la integración de Skype para empresas y Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
Si desea descargar una versión en póster de este tema, vaya a:
  
- [Skype para los modelos de arquitectura empresarial (pdf)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype for Business Architectural Models.pdf)
    
- [Skype para los modelos de arquitectura empresarial (Visio)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype for Business Architectural Models.vsd)
    

