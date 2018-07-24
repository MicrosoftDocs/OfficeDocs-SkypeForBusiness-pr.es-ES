---
title: Introducción a la implementación para el sistema de sala de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: Obtenga información acerca de cómo implementar del sistema de la sala de Skype, una reunión de solución de sala formado por integrada de hardware y software que está optimizado para unirse a Skype para reuniones de negocios.
ms.openlocfilehash: a985a209c63d6d0262db42fb07f78133960444ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020475"
---
# <a name="deployment-planning-for-skype-room-system-in-skype-for-business"></a>Planes de implementación de sistema de sala de Skype en Skype para la empresa
 
Obtenga información acerca de cómo implementar del sistema de la sala de Skype, una reunión de solución de sala formado por integrada de hardware y software que está optimizado para unirse a Skype para reuniones de negocios.
  
> [!NOTE]
> Para los propósitos de este contenido, Skype para la empresa para sistema de sala inteligentes, RL Crestron, y Polycom CX8000 se hará referencia a como sistema de sala de Skype. 

> [!NOTE]
> Sistemas de salón de Skype v2 es un producto diferente con dependencias diferentes y procedimientos de implementación. Para obtener información sobre los sistemas de la sala de Skype v2, vea [planeación de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md).
  
 Sistema de sala de Skype es un Skype para cliente de comunicaciones unificadas de negocio que se ha optimizado para Skype para reuniones de negocios en salas de conferencias físico.
  
El cliente del sistema de salas de Skype se desarrolló desde el Skype para cliente empresarial mediante el uso de la Skype para SDK de negocio. El Skype para clientes empresariales se ejecuta en segundo plano en el modo de la interfaz de usuario se suprimieron parcial. El Skype para clientes empresariales controla la Galería de vídeo y régimen de contenido en la pantalla en la parte frontal de la sala. El cliente del sistema de salas de Skype proporciona una experiencia de consola en la pantalla de sobremesa para controlar las reuniones. Sistema de sala de Skype proporciona: 
  
- Una experiencia de unión a reuniones en un solo toque
    
- Configuración automática para galería de vídeo de varias vistas 
    
- Pizarra táctil en la pantalla de la parte frontal de la sala 
    
- Integración con el calendario para acceder a las reuniones programadas
    
- Compartir e intercambiar contenido 
    
Este documento le guía a través del aprovisionamiento del sistema de la sala de Skype en Skype para Business Server y Exchange Server. Consulte también la Guía de instalación del sistema de sala de Skype proporcionada por el administrador, que le guiará en el proceso de configuración del dispositivo PC y dispositivos en la sala de reuniones. 
  
## <a name="prerequisites"></a>Requisitos previos

A continuación es los requisitos de sistema de la sala de Skype: 
  
- Una cuenta de buzón de recursos de Exchange para facilitar la programación del calendario para las salas de reuniones con el servicio Detección automática habilitado en Exchange Server (versión 2013 preferida).
    
- Un Skype para la cuenta del sistema de sala de Skype habilitado para el negocio en un Skype para grupo de servidores de empresarial (Enterprise o Standard Edition).
    
- Un dispositivo de cliente de sistema de salas de Skype PC con todo el software necesario instalado. El equipo debe ejecutar el sistema operativo Windows 7 Embedded Standard. Los asociados de OEM proporcionarán este hardware junto con todos los dispositivos (pantallas, cámaras, micrófonos y altavoces).
    
- Si decide participar en el dispositivo del sistema de salas de Skype PC a un dominio de servicios de dominio de Active Directory (AD DS), debe especificar la configuración de directiva de grupo que no interfiera con el sistema de sala de Skype. Como alternativa, puede dejar este equipo en el grupo de trabajo. 
    
- Derechos de usuario adecuados para ejecutar los cmdlets en este documento. Los cmdlets CsMeetingRoom se modelan tomando como base el cmdlet CsUser. Por lo tanto, todos los roles de controles de acceso basados en roles (RBAC) requeridos para ejecutar cmdlet CsUser también se aplican a los cmdlets CsMeetingRoom. 
    
## <a name="supported-topologies"></a>Topologías compatibles

En la siguiente tabla indica la interoperabilidad del cliente del sistema de salas de Skype entre las diversas implementaciones de Skype para topologías empresariales y de Exchange, ya sea local o en la nube: 
  

|**Topología**|**AD**|**Skype Empresarial**|**Exchange**|
|:-----|:-----|:-----|:-----|
|Implementación local  <br/> |Implementación local  <br/> |Implementación local  <br/> |Implementación local  <br/> |
|Office 365 varios inquilinos (O365MT)  <br/> |En línea  <br/> |En línea  <br/> |En línea  <br/> |
|Office 365 Dedicated  <br/> (Póngase en contacto con su proveedor de servicios)  <br/> |Implementación local  <br/> |En línea  <br/> |En línea  <br/> |
|Híbrido (dominio dividido)  <br/> No compatible  <br/> |Implementación local  <br/> Implementación local  <br/> Implementación local  <br/> |Implementación local  <br/> En línea  <br/> En línea  <br/> |En línea  <br/> En línea  <br/> Implementación local  <br/> |
   
Las versiones anteriores a Lync Server 2013 son compatibles parcialmente. En estos escenarios, sistema de sala de Skype pueden participar en Skype para conferencias de empresa (aquellos que están programados por los usuarios hospedados en Lync Server 2010) como las conferencias son "públicas", lo que significa que las conferencias no están personalizadas para el acceso restringido. 
  
Sistema de sala de Skype no pueden hospedarse en una versión de Lync server anteriores a Lync Server 2013. Cuando no se puede conectar un sistema de sala de Skype a Exchange para recuperar la configuración de calendario--por ejemplo, cuando no hay ningún buzón de Exchange configurado para la cuenta del sistema de salas de Skype o no se puede tener acceso a Exchange--Reunirse ahora y conferencia ad hoc funcionará, pero unirse un reunión programada no lo harán. 
  
En la siguiente tabla indica la compatibilidad de cliente del sistema de salas de Skype con versiones de Exchange Server: 
  

|**Exchange**|**Implementación local**|**En línea**|**Híbrido**|
|:-----|:-----|:-----|:-----|
|Exchange 2010  <br/> |Sí (un solo bosque)  <br/> |N/D  <br/> |N/D  <br/> |
|Exchange 2013  <br/> |Sí (compatibilidad con varios bosques disponible para Exchange 2013 CU6 y versiones posteriores)  <br/> |Sí  <br/> |Sí  <br/> |
|Exchange 2016  <br/> |Sí (múltiples bosques soporte disponible)  <br/> |Sí  <br/> |Sí  <br/> |
   

