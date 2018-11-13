---
title: Skype para soluciones híbridas de negocio
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/18/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Una explicación de las soluciones híbridas disponibles en Skype para Business Server 2019.
ms.openlocfilehash: 2909f524d1b9984fe01700a89d1bf6dc1b70f100
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295372"
---
NOTA: LOS SIGUIENTES SE COPIAN DESDE EL 2015 Y ESTÁ EN CURSO. Contenido de marcador de posición en curso adicionales puede encontrarse [debajo](#placeholder-topic-for-hybrid-solutions).


# <a name="skype-for-business-hybrid-solutions"></a>Skype para soluciones híbridas de negocio

Obtenga información acerca de cómo planear un Skype para implementación híbrida de negocio. 
  
En este tema se presentan distintas configuraciones híbridas que pueden ayudarlo a determinar qué configuración es la mejor para su empresa. Luego, puede leer más sobre la configuración que le interese, siguiendo los vínculos de este tema. Este artículo contiene las siguientes secciones:
  
- [Configuraciones híbridas de Skype Empresarial](hybrid-solutions.md#BKMK_HybridConfigurations)
    
- [Agregar Skype para profesionales en línea en la existente local Skype para el entorno empresarial](hybrid-solutions.md#BKMK_HybridConnectivity)
    
- [Permite aprovechar sistema telefónico en Office 365 (en la nube PBX)](hybrid-solutions.md#BKMK_CloudPBX)
    
- [Integración con Exchange y SharePoint](hybrid-solutions.md#BKMK_IntegratewExchangeSharePoint)
    
- [Tareas para planificar y configurar un entorno híbrido](hybrid-solutions.md#BKMK_Tasks)
    
- [Para más información](hybrid-solutions.md#BKMK_MoreInfo)
    
## <a name="skype-for-business-hybrid-configurations"></a>Configuraciones híbridas de Skype Empresarial
<a name="BKMK_HybridConfigurations"> </a>

Skype para la empresa es compatible con varias configuraciones híbridas. Puede agregar Skype para profesionales en línea en la existente local Skype para el entorno empresarial, integrar su Skype para la implementación de empresa con Exchange Online y SharePoint Online y aprovechar las ventajas del sistema de teléfono en Office 365 (en la nube PBX) — de Microsoft tecnología para habilitar el control de llamadas y las capacidades de conmutación (PBX) en la nube de Office 365 con Skype para profesionales en línea. 
  
Con un Skype para implementación híbrida de negocio, combinar un Skype para suscripción empresarial en línea con su Skype local para la oferta de negocio. Puede empezar a crear habilidades de administración de software como servicio en su organización y mover su Skype para los usuarios empresariales a la nube a su propio ritmo. Los usuarios que están hospedados en la nube pueden aprovechar sistema telefónico en Office 365 conservando la conectividad pública red de telefónica conmutada (RTC) de local.
  
Con un Skype para la configuración híbrida de negocio, tenga en cuenta lo siguiente:
  
- Algunos usuarios podrían estar alojados localmente y algunos en línea, pero todos ellos comparten el mismo dominio de Protocolo de inicio de sesión (SIP), como contoso.com.
    
- Puede migrar los usuarios de Skype para la empresa local a Skype para profesionales en línea con el tiempo, en la programación.
    
- Puede realizar una integración con otras aplicaciones de Microsoft Office 365, incluidas Exchange Online y SharePoint Online.
    
- Puede realizar una integración con Exchange y SharePoint.
    
- Puede aprovechar Difusión de reunión de Skype.
    
- Puede aprovechar la función de conferencia RTC.
    
## <a name="add-skype-for-business-online-into-your-existing-on-premises-skype-for-business-environment"></a>Agregar Skype para profesionales en línea en la existente local Skype para el entorno empresarial
<a name="BKMK_HybridConnectivity"> </a>

Conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea significa que los usuarios de un dominio, como contoso.com, se reparten entre el uso de Skype para Business Server local y Skype para profesionales en línea. Algunos usuarios del dominio están alojados en forma local, mientras que otros están en línea. Puede configurar la implementación local para la implementación híbrida con Skype para profesionales en línea y utilizar sincronización de Active Directory para mantener su local y en línea a los usuarios sincronizados. 
  
En el siguiente diagrama se muestra cómo se puede agregar Skype para profesionales en línea en su Skype local existente para el entorno empresarial, lo que le permite mover los usuarios a la nube a su propio ritmo:
  
![Configuración híbrida de Skype Empresarial](../../sfbserver/media/4580f2c8-7008-4c6e-826c-020d0f2d1636.png)
  
Para obtener más información, vea [Planear la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea o los equipos](plan-hybrid-connectivity.md) y [Configure la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](configure-hybrid-connectivity.md).
  
## <a name="take-advantage-of-phone-system-in-office-365-cloud-pbx"></a>Permite aprovechar sistema telefónico en Office 365 (en la nube PBX)
<a name="BKMK_CloudPBX"> </a>

 Sistema de teléfono en Office 365 (en la nube PBX) es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de conmutación (PBX) en la nube de Office 365 con Skype para profesionales en línea. Sistema telefónico en Office 365 le permite reemplazar el sistema PBX existente con un conjunto de características de entrega de Office 365 y estrechamente integrados en la experiencia de productividad de nube de Microsoft.
  
Además de dos del sistema de teléfono en las ofertas de Office 365 híbrida, Microsoft ofrece el sistema telefónico en Office 365 con el Plan para llamar a: una servicio de llamada de RTC: para una solución totalmente la en nube que no requiere una implementación de servidor local. Para decidir si el sistema de teléfono en Office 365 con el Plan para llamar a podría ser la solución adecuada para su organización, vea el [Sistema telefónico en soluciones de Office 365](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings).
  
Hay dos sistema telefónico en las ofertas de Office 365 híbrida: 
  
- [Sistema telefónico en Office 365 con conectividad local proporcionada por su Skype para la implementación de Business Server](hybrid-solutions.md#BKMK_Server)
    
- [Sistema telefónico en Office 365 con conectividad local proporcionada por Skype para Business Server en la nube conector Edition](hybrid-solutions.md#BKMK_CCE)
    
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-your-skype-for-business-server-deployment"></a>Sistema telefónico en Office 365 con conectividad local proporcionada por su Skype para la implementación de Business Server
<a name="BKMK_Server"> </a>

Esta configuración consta de un Skype para la implementación local de Business Server modificado para entornos híbridos RTC. Los usuarios de su organización que están hospedados en la nube pueden recibir servicios de PBX de la nube de Microsoft, pero se proporciona conectividad RTC a través de Enterprise Voice en su Skype local para la implementación de Business Server. 
  
![PBX en la nube con implementación de Skype Empresarial Server](../../sfbserver/media/d4136bbc-b01e-469c-bf94-90ba59c61cda.png)
  
Esta es la mejor configuración si: 
  
- Su sistema PBX no ofrece características únicas que necesita conservar.
    
- Llamar al Plan, el servicio de llamada de RTC de Office 365, no está disponible en su región.
    
- Tiene una existente de Lync o Skype para la implementación de Business Server.
    
Para obtener más información, vea [Planear el sistema de teléfono en Office 365 con conectividad RTC en Skype para Business Server local](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md) y [Habilitar usuarios para el sistema telefónico en Office 365 con conectividad de RTC local en Skype para Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system.md).
  
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-skype-for-business-server-cloud-connector-edition"></a>Sistema telefónico en Office 365 con conectividad local proporcionada por Skype para Business Server en la nube conector Edition
<a name="BKMK_CCE"> </a>

Esta configuración consta de un conjunto de máquinas virtuales empaquetadas que implementan la conectividad con RTC local. Mediante la implementación de un mínimo Skype para la topología de servidor empresarial en un entorno virtualizado, los usuarios de su organización que están hospedados en la nube pueden recibir servicios de PBX de la nube de Microsoft, pero se proporciona conectividad RTC a través de la voz local existente infraestructura. 
  
![CloudPBXCloudConnectorEdition](../../sfbserver/media/7a6ee221-bfe1-422b-ac44-6446db6b766c.png)
  
Esta es la mejor configuración si:
  
- Su sistema PBX no ofrece características únicas que necesita conservar.
    
- Llamar al Plan, el servicio de llamada de RTC de Office 365, no está disponible en su región.
    
- No es necesario un Lync existente o Skype para la implementación de Business Server.
    
Para obtener más información, consulte [Plan de Skype para Business Edition de conector en la nube](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="integrate-with-exchange-and-sharepoint"></a>Integración con Exchange y SharePoint
<a name="BKMK_IntegratewExchangeSharePoint"> </a>

Un Skype para configuración híbrida de empresarial permite integrarse con otras aplicaciones de Microsoft Office 365, incluido Exchange Online y SharePoint Online.
  
### <a name="skype-for-business-server-with-exchange-online-and-sharepoint-online"></a>Skype Empresarial Server con Exchange Online y SharePoint Online

Se puede integrar Skype para Business Server con Exchange Online y SharePoint Online, tal como se muestra en el siguiente diagrama:
  
![Skype Empresarial Server con Exchange Online y SharePoint Online](../../sfbserver/media/9f456ed2-8777-4a20-a519-c87dfc56b7f5.png)
  
Integración de Skype para Business Server con Exchange Online y SharePoint Online tiene varias ventajas. Puede:
  
- Usar el conjunto completo de características de Skype para Business Server.
    
- Aprovechar su equipamiento telefónico local existente, como PBX.
    
- Usar Exchange Online para correo electrónico, lo que aligera la carga de los servidores de correo electrónico y el almacenamiento locales.
    
- Usar SharePoint Online para colaboración, lo que aligera la carga del mantenimiento de servidores de SharePoint locales.
    
- Usar Skype para la empresa, Exchange y SharePoint había integrado características, incluidos mensajería unificada (UM) en Office 365.
    
Para más información, vea [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
### <a name="exchange-server-with-skype-for-business-online"></a>Exchange Server con Skype Empresarial Online

Exchange Server se puede integrar con Skype para profesionales en línea tal como se muestra en el siguiente diagrama:
  
![Integrar Exchange con Skype Empresarial Online](../../sfbserver/media/e8ca44ad-f47c-46a3-9cef-8fe7deafd615.png)
  
Integración de Exchange Server con Skype para profesionales en línea tiene las siguientes ventajas:
  
- Aprovechar la infraestructura de Exchange existente.
    
- Usar Skype para empresarial en línea para las funciones de presencia, mensajería instantánea y conferencias. 
    
Para más información, vea [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
## <a name="tasks-for-planning-and-configuring-a-hybrid-environment"></a>Tareas para planificar y configurar un entorno híbrido
<a name="BKMK_Tasks"> </a>

Skype para la empresa proporciona un amplio conjunto de capacidades de independientemente de cómo crear su implementación. La arquitectura que elija determinará qué responsabilidades de TI serán suyas y cuáles tendrá que pagarle a Microsoft para que admita a través de su suscripción. Independientemente de la arquitectura que elija para su organización, existen cinco responsabilidades principales que siempre serán suyas:
  
- **Red y conectividad** - Asegúrese de capacidad de la red y la disponibilidad a través de firewalls, servidores proxy, las puertas de enlace y a través de vínculos WAN mediante la realización de una evaluación de la red o por contratantes con un socio para realizar la evaluación.
    
- **Gobierno de datos &amp; la administración de derechos** - clasificar los datos confidenciales y garantizar que está protegida y supervisar siempre que se encuentra almacenada y mientras está en tránsito.
    
- **Los extremos de cliente** - establecer, medir y exigir la aplicación de estándares de seguridad modernos en dispositivos que se usan para tener acceso a sus datos y activos.
    
- **Cuenta &amp; acceder a administración de** - establecer un perfil de actividad de la cuenta "normal" y mostrar una alerta en la actividad inusual.
    
- **Identidad**: use credenciales protegidas por hardware o autenticación multifactor (MFA) para todas las identidades. 
    
Además de las tareas de arquitectura que realice para el entorno local, tendrá que:
  
- Planear y diseñar requisitos de administración de identidades, incluida la integración de identidades locales con Office 365.
    
- Garantizar la capacidad y disponibilidad de la red.
    
- Adquirir certificados SSL de terceros para brindar seguridad empresarial para las ofertas de servicios de Office 365.
    
- Decidir si desea conectarse a Office 365 con el protocolo de Internet versión 6 (IPv6).
    
- Determinar cuánto integración de características con local y versiones en línea de Skype para la empresa, Exchange y SharePoint se desea obtener. 
    
- Determinar qué servidor proxy se usará para las solicitudes de Office 365.
    
También tendrá que realizar el seguimiento para profesionales de TI tareas para implementar su Skype para entorno híbrido de negocio:
  
- Asegúrese de que tener un inquilino de Microsoft Office 365 con Skype para profesionales Online habilitado.
    
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
    
- [Identidad de nube de Microsoft para arquitectos de empresa](https://docs.microsoft.com/en-us/office365/enterprise/microsoft-cloud-it-architecture-resources#identity)
    
- [Preparar la organización para Office 365 Enterprise](https://aka.ms/O365EntPrep)
    
- [Planear la conectividad híbrida entre Skype para Business Server y Skype en línea de negocio o los equipos](plan-hybrid-connectivity.md)
    
- [Configurar la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](configure-hybrid-connectivity.md)
    
- [Sistema telefónico en soluciones de Office 365](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings)
    
- [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
Si desea descargar una versión en póster de este tema, vaya a:
  
- [Modelos arquitectónicos de Skype Empresarial (pdf)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)
    
- [Modelos arquitectónicos de Skype Empresarial (Visio)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)
    

### <a name="placeholder-topic-for-hybrid-solutions"></a>TEMA DE MARCADOR DE POSICIÓN PARA SOLUCIONES HÍBRIDAS 

EN CURSO...


Es posible que también conozca el término "voz híbrida". Hace referencia a los troncos de voz locales que suministra funciones a los usuarios alojados en la nube. La voz híbrida proporciona migración a la nube a la vez que conserva la configuración de voz local. Si ya cuenta con una implementación de Skype Empresarial Server, el primer paso para habilitar la voz híbrida consiste en configurar un entorno de dominios divididos. 
  
Por ejemplo, supongamos que su compañía tiene un campo móvil grandes organización que requiere PBX mínima voz pero extensa teléfono inteligente que se utilice. Podría elegir transferir a estos usuarios a la nube para beneficiarse del Sistema telefónico de Office 365 (PBX en la nube) de Microsoft. Si su compañía tiene también un centro de llamadas de gran tamaño local que requiere el software de avanzada, complejo centro de contacto como parte de su PBX local, es posible que elija dejar estos usuarios local. Los usuarios que están alojados en línea y en local tienen conectividad RTC a través de su implementación local.
  
En el siguiente diagrama se muestra una implementación de voz híbrida de Skype Empresarial:
  
![Dominio dividido de SfB con PBX en la nube](../../sfbserver/media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)
  
Para obtener más información acerca de cómo configurar una solución híbrida de voz con su Skype para la implementación de servidor empresarial, vea [Planear el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md). 
  
También puede configurar las implementaciones híbridas para la integración con Exchange y SharePoint local o con aplicaciones de Microsoft Office 365, incluido Exchange Online y SharePoint Online. También puede configurar una solución de voz híbrida que no requiera una implementación completa de Skype Empresarial Server mediante Cloud Connector Edition. Para obtener más información acerca de todos los Skype para soluciones híbridas de negocio y planear la migración a la nube, vea [Skype para soluciones híbridas de negocio](hybrid-solutions.md).


## <a name="exchange-co-existence"></a>Coexistencia de Exchange
<a name="BKMK_Exchange"> </a>

Para admitir la coexistencia con Exchange, tenga lo siguiente en cuenta:
  
- El procedimiento recomendado consiste en mover el buzón del usuario a Exchange Online antes de pasar página principal Skype del usuario para la empresa.
    
- Los usuarios con buzones de correo de Exchange son compatibles con las siguientes limitaciones conocidas:
    
  - Inicio de sesión de cliente: los usuarios pueden necesitar iniciar sesión dos veces durante el inicio de sesión de cliente de SfB.
    
  - Historial de conversaciones de lado servidor, archivado, almacén de contactos unificados, fotografías HighRes requiere Exchange 2013 o posterior, y debe habilitar el servidor de OAuth para la comunicación entre el servidor. Para obtener más información, vea [Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones asociadas en Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/jj204817.aspx).
    
Para obtener información detallada sobre la coexistencia con Exchange Server, incluidos los criterios y las limitaciones de la compatibilidad en distintas combinaciones de implementaciones locales y en línea, vea [Compatibilidad con la característica](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) en [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).



**TERMINOLOGÍA**

unidad organizativa aquí encontrará más información acerca de la configuración de Active Directory en las secciones siguientes. Sin embargo, primero hay que ver un resumen de la terminología y los acrónimos que se usan en los diagramas siguientes, así como en muchos de los temas sobre conectividad híbrida:
  
- RTC: red telefónica conmutada
    
- PBX: sistema telefónico de central de conmutación
    
- Sistema telefónico: oferta de sistema telefónico de PBX en la nube de Microsoft
    
- Tronco - línea de telefonía que conecta la PBX a la RTC: un tronco podría usar el protocolo de inicio de sesión (SIP) — A voz a través del protocolo de Internet (VoIP), o la tecnología más antigua de multiplexación por división de tiempo (TDM) 
    
- SBC: controlador de borde de sesión. Dispositivo que sirve como firewall y enrutador en redes telefónicas. Por ejemplo, proporciona seguridad, conectividad, interoperabilidad y calidad de servicios. 
    
- Puerta de enlace RTC: un dispositivo que actúa como enrutador en redes telefónicas, capaz de hacer la mayoría de las cosas que hace un SBC, excepto la seguridad y el cruce de NAT.
    
El siguiente diagrama muestra una Skype para la configuración híbrida de negocio "dominio dividido". Los usuarios A y los usuarios B se alojan en línea pero los usuarios locales pueden detectarlos; los usuarios C y D se alojan en local, pero los usuarios en línea los pueden detectar.
  

