---
title: Implementar servicios de emergencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Implementar E9-1-1 en Skype empresarial Server Enterprise Voice. Incluye los requisitos previos y una lista de comprobación del proceso de implementación.
ms.openlocfilehash: 61aefd76d848305334372c2b7c7f4214f87b6570
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767563"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Implementar servicios de emergencia en Skype empresarial Server
 
Implementar E9-1-1 en Skype empresarial Server Enterprise Voice. Incluye los requisitos previos y una lista de comprobación del proceso de implementación.
  
Enhanced 9-1-1 (E9-1-1) es una función de notificación de emergencia que asocia el número de teléfono de la persona que llama con una dirección de la ciudad o de la calle. Con esta información, el PSAP (punto de respuesta de seguridad pública) puede enviar servicios de emergencia de forma inmediata a la persona que llama y tiene dificultades.
  
Para admitir E9-1-1, Skype empresarial Server debe poder asociar correctamente una ubicación con un cliente y asegurarse de que esta información se use para enrutar la llamada de emergencia a la PSAP más cercana.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Requisitos previos para implementar E9-1-1

Antes de implementar E9-1-1, ya debe haber implementado sus servidores internos de Skype empresarial Server, incluido un almacén de administración central, un grupo de servidores front-end o un servidor Standard Edition. También debe implementar uno o varios servidores de mediación, ya sean independientes o colocados con servidores de aplicaciones para el usuario. Además, una implementación de E9-1-1 requiere un tronco SIP con un proveedor de servicios E9-1-1 certificado o una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a la red telefónica conmutada (RTC).
  
## <a name="deployment-process"></a>Proceso de implementación

En la tabla siguiente se proporciona información general del proceso de implementación de E9-1-1.
  
|**Fase**|**Pasos**|**Roles**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Realizar configuraciones de tronco, rutas y usos de voz  <br/> |1. cree un nuevo registro de uso de RTC. Se trata del mismo nombre que se ha usado para el parámetro **Uso de RTC** en la directiva de ubicación. <br/> 2. cree o asigne una ruta de voz al registro de uso de RTC creado en el paso anterior y, a continuación, apunte el atributo de puerta de enlace al E9-1-1 SIP trunk or ELIN Gateway.  <br/> 3. para un proveedor de servicios E9-1-1 de SIP, establezca el tronco que controlará E9-1-1 llamadas a través de SIP para que pasen los datos de PIDF-o mediante el cmdlet **set-CsTrunkConfiguration-EnablePIDFLOSupport** . <br/> 4. opcionalmente, para un proveedor de servicios de tronco de E9-1-1 de SIP, cree o asigne una ruta RTC local para las llamadas que no se controlan mediante el protocolo de enlace SIP del proveedor de servicios E9-1-1. Esta ruta se usará si la conexión al proveedor de servicios E9-1-1 no está disponible. Si lo admite el proveedor de servicios E9-1-1, asigne una regla de configuración de tronco a la puerta de enlace que convierte la cadena de marcado 911 en el número de llamada directa a la extensión (DID) del Centro de respuesta a llamadas de emergencia nacional y/o regional.  <br/> |CSVoiceAdmin  <br/> |[Configurar una ruta de voz E9-1-1 en Skype empresarial Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Crear directivas de ubicación y asignarlas a usuarios y subredes  <br/> |1. Revise la política de ubicación global.  <br/> 2. crear una directiva de ubicación con un ámbito de nivel de usuario; o bien, si la organización tiene más de un sitio con diferentes usos de emergencia, cree una directiva de ubicación con un ámbito de nivel de red.  <br/> 3. asignar la Directiva de ubicación a los sitios de red.  <br/> 4. Agregue las subredes apropiadas al sitio de red.  <br/> 5. (opcional) asigne la Directiva de ubicación a directivas de usuario.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (excepto para crear directivas de ubicación)  <br/> |[Crear directivas de ubicación en Skype empresarial Server](create-location-policies.md) <br/> [Agregar una directiva de ubicación a un sitio de red en Skype empresarial Server](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configurar la base de datos de ubicaciones  <br/> |1. Rellene la base de datos con una asignación de elementos de red a ubicaciones.  <br/> 2. para las puertas de enlace ELIN, agregue la ELINs \<a\> la columna CompanyName.  <br/> 3. configurar la conexión con el proveedor de servicios de E9-1-1 para validar direcciones.  <br/> 4. valide las direcciones con el proveedor de servicios E9-1-1.  <br/> 5. publicar la base de datos actualizada.  <br/> 6. para las puertas de enlace ELIN, cargue la ELINs a la base de datos de identificación de ubicación automática (ALI) del operador PSTN.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurar la base de datos de ubicación en Skype empresarial Server](configure-the-location-database.md) <br/> |
|Configurar características avanzadas (opcional)  <br/> |1. configurar la dirección URL de la aplicación SNMP.  <br/> 2. configurar la dirección URL para la ubicación del servicio de información de ubicación secundaria.  <br/> |CSVoiceAdmin  <br/> |[Configurar una aplicación SNMP en Skype empresarial Server](configure-an-snmp-application.md) <br/> [Configurar un servicio de información de ubicación secundaria en Skype empresarial Server](secondary-location-information-service.md) <br/> |
   

