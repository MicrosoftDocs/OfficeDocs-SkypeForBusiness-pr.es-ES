---
title: Implementar E9-1-1 en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Implementar E9-1-1 en Skype para Telefonía IP empresarial de Business Server. Incluye los requisitos previos y una lista de comprobación del proceso de implementación.
ms.openlocfilehash: 0994bb3b1c0cd5b4c4ce1dcc1c0a46b4e97b76b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-emergency-services-in-skype-for-business-server-2015"></a>Implementar E9-1-1 en Skype Empresarial Server 2015
 
Implementar E9-1-1 en Skype para Telefonía IP empresarial de Business Server. Incluye los requisitos previos y una lista de comprobación del proceso de implementación.
  
9-1-1 mejorado (E9-1-1) es una característica de notificación de emergencia que asocia el número de teléfono de la persona que llama a una ciudad o una dirección. Con esta información, el PSAP (punto de respuesta de seguridad pública) puede enviar servicios de emergencia de forma inmediata a la persona que llama y tiene dificultades.
  
Para admitir E9-1-1, Skype para Business Server debe ser capaz de asociar correctamente una ubicación con un cliente y asegúrese de que esta información se utiliza para enrutar la llamada de emergencia para el PSAP más cercano.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Requisitos previos para implementar E9-1-1

Antes de implementar E9-1-1, debe ya ha implementado su Skype para servidores internos Business Server incluyen un almacén de Administración Central, un grupo de servidores Front-End o un servidor Standard Edition. También debe implementar uno o más servidores de mediación, ya sea independiente o en combinación con servidores frontales. Además, una implementación de E9-1-1 requiere un tronco SIP con un proveedor de servicios E9-1-1 certificado o una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a la red telefónica conmutada (RTC).
  
## <a name="deployment-process"></a>Proceso de implementación

En la tabla siguiente se proporciona información general del proceso de implementación de E9-1-1.
  
|**Fase**|**Pasos**|**Funciones**|**Documentación sobre la implementación**|
|:-----|:-----|:-----|:-----|
|Realizar configuraciones de tronco, rutas y usos de voz  <br/> |1. crear un nuevo registro de uso de RTC. Se trata del mismo nombre que se ha usado para el parámetro **Uso de RTC** en la directiva de ubicación. <br/> 2. crear o asignar una ruta de voz para el registro de uso PSTN creado en el paso anterior y, a continuación, seleccione el atributo de puerta de enlace el tronco E9-1-1 SIP o puerta de enlace ELIN.  <br/> 3. para un proveedor de servicios SIP tronco E9-1-1, establezca el tronco que se pueden controlar las llamadas a E9-1-1 sobre el SIP para pasar datos PIDF-LO mediante el cmdlet **Set-CsTrunkConfiguration-EnablePIDFLOSupport** . <br/> 4. Si lo desea, para un proveedor de servicios SIP tronco E9-1-1, crear o asignar una ruta de RTC local para las llamadas que no son controladas por el tronco SIP del proveedor de servicios de E9-1-1. Esta ruta se usará si la conexión al proveedor de servicios E9-1-1 no está disponible. Si lo admite el proveedor de servicios E9-1-1, asigne una regla de configuración de tronco a la puerta de enlace que convierte la cadena de marcado 911 en el número de llamada directa a la extensión (DID) del Centro de respuesta a llamadas de emergencia nacional y/o regional.  <br/> |CSVoiceAdmin  <br/> |[Configurar una ruta de voz E9-1-1 en Skype para Business Server 2015](configure-an-e9-1-1-voice-route.md) <br/> |
|Crear directivas de ubicación y asignarlas a usuarios y subredes  <br/> |1. Revise la política de ubicación global.  <br/> 2. crear una política de ubicación con un ámbito de nivel de usuario; o bien, si la organización tiene más de un sitio con diferentes usos de emergencia, cree una directiva de ubicación con un ámbito de nivel de red.  <br/> 3. asigne la directiva de la ubicación a los sitios de red.  <br/> 4. agregar las subredes apropiadas para el sitio de red.  <br/> 5. (opcional) asignar la directiva de ubicación a las directivas de usuario.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (excepto para crear directivas de ubicación)  <br/> |[Crear políticas de ubicación de Skype para Business Server 2015](create-location-policies.md) <br/> [Agregar una directiva de ubicación en un sitio de red en Skype para Business Server 2015](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configurar la base de datos de ubicaciones  <br/> |1. llenar la base de datos con una asignación de elementos a ubicaciones de la red.  <br/> 2. para puertas de enlace ELIN, agregue el ELINs a la \<CompanyName\> columna.  <br/> 3. configurar la conexión con el proveedor de servicio E9-1-1 para validar direcciones.  <br/> 4. valida las direcciones con el proveedor del servicio E9-1-1.  <br/> 5. publicar la base de datos actualizada.  <br/> 6. para puertas de enlace ELIN, cargar la ELINs a base de datos de identificación de ubicación automática (ALI) de su operador de telefonía PSTN.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurar la base de datos de ubicación en Skype para Business Server 2015](configure-the-location-database.md) <br/> |
|Configurar características avanzadas (opcional)  <br/> |1. configurar la dirección URL de la aplicación SNMP.  <br/> 2. configurar la dirección URL de la ubicación del servicio de información de ubicación secundaria.  <br/> |CSVoiceAdmin  <br/> |[Configurar una aplicación SNMP en Skype para Business Server 2015](configure-an-snmp-application.md) <br/> [Configurar un servicio de información de ubicación secundario en Skype para Business Server 2015](secondary-location-information-service.md) <br/> |
   

