---
title: Implementar el Sistema de salas de Skype en Skype Empresarial Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: Obtenga información acerca de cómo implementar el sistema de sala de Skype, una reunión solución de sala compuesta de integrada de hardware y software que está optimizado para unirse a Skype para reuniones de negocios.
ms.openlocfilehash: 11cbae1cdbdd0585a2ea67625179ee7862309723
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-system-in-skype-for-business-server"></a>Implementar el Sistema de salas de Skype en Skype Empresarial Server
 
Obtenga información acerca de cómo implementar el sistema de sala de Skype, una reunión solución de sala compuesta de integrada de hardware y software que está optimizado para unirse a Skype para reuniones de negocios.
  
> [!NOTE]
> Para los propósitos de este contenido, Skype para el negocio para el sistema de sala inteligente, RL Crestron, y Polycom CX8000 se denominará sistema de sala de Skype. 
  
 Sistema de sala de Skype es un Skype para cliente de comunicaciones unificadas de negocio que ha sido optimizado para Skype para reuniones de negocios en salas de conferencias física.
  
El cliente del sistema de sala de Skype se desarrolló desde el Skype para Business client utilizando el Skype para SDK de negocio. El Skype para Business client se ejecuta en segundo plano en el modo UI suprimido parcial. El Skype para Business client controla la Galería de vídeos y la fase contenido en la pantalla en la parte delantera de la sala. El cliente del sistema de sala de Skype proporciona una experiencia de consola en la pantalla de sobremesa para controlar las reuniones. Sistema de sala de Skype proporciona: 
  
- Una experiencia de unión a reuniones en un solo toque
    
- Configuración automática para galería de vídeo de varias vistas 
    
- Pizarra táctil en la pantalla de la parte frontal de la sala 
    
- Integración con el calendario para acceder a las reuniones programadas
    
- Compartir e intercambiar contenido 
    
Este documento le guiará en el proceso de aprovisionamiento del sistema de sala de Skype en Skype para Business Server y Exchange Server. Consulte también la Guía de instalación de sistema de sala de Skype proporcionado por el administrador, que le guiará en el proceso de configuración del dispositivo PC y dispositivos en la sala de reuniones. 
  
## <a name="prerequisites"></a>Requisitos previos

Los siguientes son los requisitos de sistema de sala de Skype: 
  
- Una cuenta de buzón de recursos de Exchange para facilitar la programación del calendario para las salas de reuniones con el servicio Detección automática habilitado en Exchange Server (versión 2013 preferida).
    
- Un Skype para la cuenta de sistema habilitado para negocios de sala de Skype en un Skype para el grupo de servidores de empresa (Enterprise o Standard Edition).
    
- Un dispositivo de cliente de sistema de sala de Skype PC con todo el software necesario instalado. El equipo debe ejecutar el sistema operativo Windows 7 Embedded Standard. Los asociados de OEM proporcionarán este hardware junto con todos los dispositivos (pantallas, cámaras, micrófonos y altavoces).
    
- Si decide unir el dispositivo de sistema de sala de Skype PC a un dominio de servicios de dominio de Active Directory (AD DS), debe especificar la configuración de directiva de grupo que no interfiera con el sistema del sitio de Skype. Como alternativa, puede dejar este equipo en el grupo de trabajo. 
    
- Derechos de usuario adecuados para ejecutar los cmdlets en este documento. Los cmdlets CsMeetingRoom se modelan tomando como base el cmdlet CsUser. Por lo tanto, todos los roles de controles de acceso basados en roles (RBAC) requeridos para ejecutar cmdlet CsUser también se aplican a los cmdlets CsMeetingRoom. 
    
## <a name="supported-topologies"></a>Topologías compatibles

La tabla siguiente indica la interoperabilidad del sistema de sala de Skype de cliente entre varias implementaciones de Skype para topologías de Exchange y de negocios, en locales o en la nube: 
  

|**Topología**|**AD**|**Skype Empresarial**|**Exchange**|
|:-----|:-----|:-----|:-----|
|Implementación local  <br/> |Implementación local  <br/> |Implementación local  <br/> |Implementación local  <br/> |
|Office 365 multiempresa (O365MT)  <br/> |En línea  <br/> |En línea  <br/> |En línea  <br/> |
|Office 365 Dedicated  <br/> (Póngase en contacto con su proveedor de servicios)  <br/> |Implementación local  <br/> |En línea  <br/> |En línea  <br/> |
|Híbrido (dominio dividido)  <br/> No compatible  <br/> |Implementación local  <br/> Implementación local  <br/> Implementación local  <br/> |Implementación local  <br/> En línea  <br/> En línea  <br/> |En línea  <br/> En línea  <br/> Implementación local  <br/> |
   
Las versiones anteriores a Lync Server 2013 son compatibles parcialmente. En estos casos, el sistema del sitio de Skype pueden participar en Skype para conferencias de empresa (los que programan los usuarios alojados en Lync Server 2010) como las conferencias son "públicas", lo que significa que las conferencias no están personalizados para el acceso restringido. 
  
Sistema de sala de Skype no puede ser alojado en una versión de Lync server anteriores a Lync Server 2013. Cuando un sistema de sala de Skype no puede conectarse a Exchange para recuperar la configuración del calendario, por ejemplo, cuando no hay ningún buzón de Exchange configurado para la cuenta de sistema del sitio de Skype o no se puede tener acceso a Exchange--Reunirse ahora y conferencia ad hoc funcionará, pero va a unir una reunión programada no lo hará. 
  
En la siguiente tabla indica la compatibilidad de cliente de sistema de sala de Skype con versiones de Exchange Server: 
  

|**Exchange**|**En las instalaciones**|**En línea**|**Híbrido**|
|:-----|:-----|:-----|:-----|
|Exchange 2010  <br/> |Sí (un solo bosque)  <br/> |N/D  <br/> |N/D  <br/> |
|Exchange 2013  <br/> |Sí (compatibilidad con varios bosques disponible para Exchange 2013 CU6 y versiones posteriores)  <br/> |Sí  <br/> |Sí  <br/> |
|Exchange 2016  <br/> |Sí (múltiples bosques soporte disponible)  <br/> |Sí  <br/> |Sí  <br/> |
   

