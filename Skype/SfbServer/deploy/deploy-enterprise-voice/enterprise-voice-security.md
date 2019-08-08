---
title: Requisitos previos de seguridad y configuración de telefonía IP empresarial en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Resumen: Obtenga información sobre los requisitos previos de seguridad y configuración de telefonía IP empresarial en Skype empresarial Server.'
ms.openlocfilehash: 70acac97bd2a3554c0613f64bdbf93f64811a0b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240327"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Requisitos previos de seguridad y configuración de telefonía IP empresarial en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre la seguridad y la configuración de los requisitos previos de telefonía IP empresarial en Skype empresarial Server.
  
Antes de implementar la telefonía IP empresarial, compruebe que su infraestructura cumpla con los requisitos previos de hardware, configuración de usuario y seguridad específicos de escenarios. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Derechos administrativos e infraestructura de certificados

Antes de implementar, compruebe lo siguiente:
  
- Los administradores que implementen la telefonía IP empresarial deben ser miembros del grupo RTCUniversalServerAdmins.
    
- Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:
    
  - **CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.
    
  - **CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Telefonía IP empresarial para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.
    
  - **CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.
    
- Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.
    
    > [!NOTE]
    > Para obtener más información sobre los requisitos de certificado de Skype empresarial Server, consulte [requisitos ambientales para Skype empresarial server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos de servidor para skype empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md). 
  
## <a name="user-configuration"></a>Configuración de usuario

Si ha colocado el servidor de mediación con cada grupo de servidores front-end o servidor Standard Edition durante la implementación front end, la configuración de usuario necesaria para la telefonía IP empresarial se configuró automáticamente durante la instalación de los archivos de esos roles de servidor.
  
Si ha implementado recientemente la carga de trabajo de telefonía IP empresarial en este momento, antes de comenzar el proceso de implementación, designe un número de teléfono principal para cada usuario que tenga previsto habilitar para telefonía IP empresarial. En tanto que administrador, es responsable de asegurarse de que este número sea único. Antes de la implementación, todos los números de teléfono principales deben normalizarse (formateados correctamente) y copiarse en la propiedad del URI de la **línea** de cada usuario con el panel de control de Skype empresarial Server.
  
> [!NOTE]
> Si desea ver ejemplos de números de teléfono principales necesarios en una implementación de Telefonía IP empresarial, consulte [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Pasos siguientes: Instalar archivos o configurar la conectividad RTC

Después de verificar el software y los requisitos previos del entorno de telefonía IP empresarial, puede:
  
- Instale el servidor de mediación, como se describe en [implementar un servidor de mediación en el generador de topologías de Skype empresarial Server](deploy-a-mediation-server.md), pero solo si desea implementar un servidor de mediación o un grupo de mediación independiente, ya que los servidores de mediación están instalados como parte del front-end el proceso de implementación del grupo o del servidor Standard Edition cuando se colocaba.
    
- También puede empezar a configurar las opciones para enrutar llamadas para usuarios de Enterprise Voice, como se describe en [configurar los troncos de Skype empresarial Server](configure-trunks.md).
    

