---
title: Implementar servicios de emergencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Implemente E9-1-1 en Skype Empresarial Server Telefonía IP empresarial. Incluye requisitos previos y lista de comprobación del proceso de implementación.
ms.openlocfilehash: 8aed5b6462ecf9d5d9fecfb0ffdc5573ca4f2352
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812530"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Implementar servicios de emergencia en Skype Empresarial Server
 
Implemente E9-1-1 en Skype Empresarial Server Telefonía IP empresarial. Incluye requisitos previos y lista de comprobación del proceso de implementación.
  
9-1-1 mejorado (E9-1-1) es una característica de notificación de emergencia que asocia el número de teléfono de la persona que llama con una dirección postal o postal. Con esta información, el punto de respuesta de seguridad pública (PSAP) puede enviar inmediatamente los servicios de emergencia al autor de la llamada en dificultades.
  
Para admitir E9-1-1, Skype Empresarial Server debe poder asociar correctamente una ubicación con un cliente y asegurarse de que esta información se usa para enrutar la llamada de emergencia al PSAP más cercano.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Requisitos previos para implementar E9-1-1

Antes de implementar E9-1-1, ya debe haber implementado los servidores internos de Skype Empresarial Server, incluido un almacén de administración central, un grupo de servidores front-end o un servidor Standard Edition. También debe implementar uno o más servidores de mediación, ya sea independiente o junto con servidores front-end. Además, una implementación de E9-1-1 requiere un tronco SIP con un proveedor de servicios de E9-1-1 certificado una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) para la Red telefónica conmutada (RTC).
  
## <a name="deployment-process"></a>Proceso de implementación

En la tabla siguiente se proporciona información general del proceso de implementación de E9-1-1.
  
|**Fase**|**Pasos**|**Roles**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Realizar configuraciones de tronco, rutas y usos de voz  <br/> |1. Cree un nuevo registro de uso de RTC. Se trata del mismo nombre que se ha usado para el parámetro **Uso de RTC** en la directiva de ubicación. <br/> 2. Cree o asigne una ruta de voz al registro de uso de RTC creado en el paso anterior y, a continuación, apunte el atributo de puerta de enlace al tronco SIP E9-1-1 o a la puerta de enlace ELIN.  <br/> 3. Para un proveedor de servicios E9-1-1 de tronco SIP, establezca el tronco que controlará las llamadas E9-1-1 a través del SIP para pasar datos PIDF-LO mediante el cmdlet **Set-CsTrunkConfiguration -EnablePIDFLOSupport.** <br/> 4. Opcionalmente, para un proveedor de servicios E9-1-1 de tronco SIP, cree o asigne una ruta RTC local para las llamadas que no sean manejadas por el tronco SIP del proveedor de servicios E9-1-1. Esta ruta se usará si la conexión al proveedor de servicios E9-1-1 no está disponible. Si lo admite el proveedor de servicios E9-1-1, asigne una regla de configuración de tronco a la puerta de enlace que convierte la cadena de marcado 911 en el número de llamada directa a la extensión (DID) del Centro de respuesta a llamadas de emergencia nacional y/o regional.  <br/> |CSVoiceAdmin  <br/> |[Configurar una ruta de voz E9-1-1 en Skype Empresarial Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Crear directivas de ubicación y asignarlas a usuarios y subredes  <br/> |1. Revise la directiva de ubicación global.  <br/> 2. Crear una directiva de ubicación con un ámbito de nivel de usuario; o bien, si la organización tiene más de un sitio con diferentes usos de emergencia, cree una directiva de ubicación con un ámbito de nivel de red.  <br/> 3. Asignar la directiva de ubicación a sitios de red.  <br/> 4. Agregue las subredes adecuadas al sitio de red.  <br/> 5. (Opcional) Asignar la directiva de ubicación a directivas de usuario.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (excepto para crear directivas de ubicación)  <br/> |[Crear directivas de ubicación en Skype Empresarial Server](create-location-policies.md) <br/> [Agregar una directiva de ubicación a un sitio de red en Skype Empresarial Server](add-a-location-policy-to-a-network-site.md) <br/> [Asociar una subred a un sitio de red](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configurar la base de datos de ubicación  <br/> |1. Rellene la base de datos con una asignación de elementos de red a ubicaciones.  <br/> 2. Para puertas de enlace ELIN, agregue los ELIN a la \<CompanyName\> columna.  <br/> 3. Configure la conexión con el proveedor de servicios E9-1-1 para validar direcciones.  <br/> 4. Valide las direcciones con el proveedor de servicios E9-1-1.  <br/> 5. Publicar la base de datos actualizada.  <br/> 6. Para puertas de enlace ELIN, cargue los ELIN en la base de datos de identificación automática de ubicación (ALI) del operador RTC.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurar la base de datos de ubicación en Skype Empresarial Server](configure-the-location-database.md) <br/> |
|Configurar características avanzadas (opcional)  <br/> |1. Configure la dirección URL de la aplicación SNMP.  <br/> 2. Configure la dirección URL para la ubicación del servicio de información de ubicación secundaria.  <br/> |CSVoiceAdmin  <br/> |[Configurar una aplicación SNMP en Skype Empresarial Server](configure-an-snmp-application.md) <br/> [Configurar un servicio secundario de información de ubicación en Skype Empresarial Server](secondary-location-information-service.md) <br/> |
   

