---
title: Implementación de servicios de emergencia en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Implementar E9-1-1 en Skype para Business Server Enterprise Voice. Incluye los requisitos previos y una lista de comprobación del proceso de implementación.
ms.openlocfilehash: b24bdfdd40787c8be57b541f3a163e3c21f3012a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888650"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Implementación de servicios de emergencia en Skype para Business Server
 
Implementar E9-1-1 en Skype para Business Server Enterprise Voice. Incluye los requisitos previos y una lista de comprobación del proceso de implementación.
  
9-1-1 mejorado (E9-1-1) es una característica de notificación de emergencia que se asocia el número de teléfono de la persona que llama a una ciudad o una dirección postal. Con esta información, el PSAP (punto de respuesta de seguridad pública) puede enviar servicios de emergencia de forma inmediata a la persona que llama y tiene dificultades.
  
Para admitir E9-1-1, Skype para Business Server debe ser capaz de asociar correctamente una ubicación con un cliente y asegúrese de que esta información se usa para enrutar la llamada de emergencia al PSAP más cercano.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Requisitos previos para implementar E9-1-1

Antes de implementar E9-1-1, que debe haber implementado su Skype para los servidores internos Business Server, incluido un almacén de Administración Central, un grupo de servidores Front-End o un servidor Standard Edition. También debe implementar uno o varios servidores de mediación, puede ser independientes o combinados con servidores Front-End. Además, una implementación de E9-1-1 requiere un tronco SIP con un proveedor de servicios E9-1-1 certificado o una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a la red telefónica conmutada (RTC).
  
## <a name="deployment-process"></a>Proceso de implementación

En la tabla siguiente se proporciona información general del proceso de implementación de E9-1-1.
  
|**Fase**|**Pasos**|**Roles**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Realizar configuraciones de tronco, rutas y usos de voz  <br/> |1. crear un nuevo registro de uso de RTC. Se trata del mismo nombre que se ha usado para el parámetro **Uso de RTC** en la directiva de ubicación. <br/> 2. Cree o asigne una ruta de voz para el registro de uso de RTC creado en el paso anterior y, a continuación, elija el atributo de puerta de enlace el tronco SIP E9-1-1 o la puerta de enlace ELIN.  <br/> 3. para un proveedor de servicios E9-1-1 de tronco SIP, defina el tronco que va a gestionar las llamadas E9-1-1 sobre el SIP para transferir datos PIDF-mediante el cmdlet **Set-CsTrunkConfiguration-EnablePIDFLOSupport** . <br/> 4. de forma opcional, para un proveedor de servicios SIP tronco E9-1-1, cree o asigne una ruta de RTC local para las llamadas que no se controlan mediante el tronco SIP del proveedor de servicios E9-1-1. Esta ruta se usará si la conexión al proveedor de servicios E9-1-1 no está disponible. Si lo admite el proveedor de servicios E9-1-1, asigne una regla de configuración de tronco a la puerta de enlace que convierte la cadena de marcado 911 en el número de llamada directa a la extensión (DID) del Centro de respuesta a llamadas de emergencia nacional y/o regional.  <br/> |CSVoiceAdmin  <br/> |[Configurar una ruta de voz de E9-1-1 en Skype para Business Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Crear directivas de ubicación y asignarlas a usuarios y subredes  <br/> |1. Revise la directiva de ubicación global.  <br/> 2. crear una directiva de ubicación con un ámbito de nivel de usuario; o bien, si la organización tiene más de un sitio con diferentes usos de emergencia, cree una directiva de ubicación con un ámbito de nivel de red.  <br/> 3. asignar la directiva de ubicación a sitios de red.  <br/> 4. Agregue las subredes apropiadas al sitio de red.  <br/> 5. (opcional) asignar la directiva de ubicación a directivas de usuario.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (excepto para crear directivas de ubicación)  <br/> |[Crear directivas de ubicación en Skype para Business Server](create-location-policies.md) <br/> [Agregar una directiva de ubicación a un sitio de red en Skype para Business Server](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configurar la base de datos de ubicaciones  <br/> |1. rellenar la base de datos con una asignación de elementos de red a ubicaciones.  <br/> 2. para puertas de enlace ELIN, agregue los Elin a la \<CompanyName\> columna.  <br/> 3. configurar la conexión con el proveedor de servicios E9-1-1 para validar las direcciones.  <br/> 4. valide las direcciones con el proveedor de servicios E9-1-1.  <br/> 5. publicar la base de datos actualizada.  <br/> 6. para puertas de enlace ELIN, cargue los Elin en la base de datos de identificación de ubicación automática (ALI) de su operador de RTC.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configuración de la base de datos de ubicación en Skype para Business Server](configure-the-location-database.md) <br/> |
|Configurar características avanzadas (opcional)  <br/> |1. configurar la dirección URL de la aplicación SNMP.  <br/> 2. configurar la dirección URL de la ubicación del servicio de información de ubicación secundaria.  <br/> |CSVoiceAdmin  <br/> |[Configuración de una aplicación SNMP en Skype para Business Server](configure-an-snmp-application.md) <br/> [Configuración de un servicio de información de ubicación secundario en Skype para Business Server](secondary-location-information-service.md) <br/> |
   

