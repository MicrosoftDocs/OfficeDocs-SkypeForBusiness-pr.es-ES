---
title: Requisitos previos de seguridad y configuración para telefonía IP empresarial en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Resumen: Conozca los requisitos previos de configuración y seguridad para Telefonía IP empresarial en Skype para Business Server 2015.'
ms.openlocfilehash: 400af6d42026007315e30a7706e9730901f90708
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server-2015"></a>Requisitos previos de seguridad y configuración para telefonía IP empresarial en Skype Empresarial Server 2015
 
**Resumen:** Conozca los requisitos previos de configuración y seguridad para Telefonía IP empresarial en Skype para Business Server 2015.
  
Antes de implementar la Telefonía IP empresarial, compruebe que la infraestructura cumpla la siguiente seguridad, configuración de usuario y los requisitos previos de hardware específicos de la situación. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Derechos administrativos e infraestructura de certificados

Antes de implementar, compruebe lo siguiente:
  
- Implementación de Telefonía IP empresarial de administradores deben ser miembros del grupo RTCUniversalServerAdmins.
    
- Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:
    
  - **CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.
    
  - **CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Telefonía IP empresarial para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.
    
  - **CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.
    
- Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.
    
    > [!NOTE]
    > Para obtener más información sobre los requisitos de certificado de Skype para Business Server, consulte [los requisitos ambientales para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). 
  
## <a name="user-configuration"></a>Configuración de usuario

Si coloca el servidor de mediación con cada grupo de servidores Front-End o servidor Standard Edition durante la implementación de Front-End, configuración de usuario necesaria para Telefonía IP empresarial se configura automáticamente durante la instalación de los archivos de dichos roles de servidor.
  
Si recién va a distribuir la carga de trabajo de la Telefonía IP empresarial en este momento, antes de comenzar el proceso de implementación, designar un número de teléfono principal para cada usuario que se va a habilitar para la Telefonía IP empresarial. En tanto que administrador, es responsable de asegurarse de que este número sea único. Antes de la implementación, todas las principal teléfono números deben normalizarse (el formato correcto) y copia en propiedad de **URI de la línea** de cada usuario mediante Skype para Panel de Control de servidor empresarial.
  
> [!NOTE]
> Si desea ver ejemplos de números de teléfono principales necesarios en una implementación de Telefonía IP empresarial, consulte [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Pasos siguientes: Instalar archivos o configurar la conectividad RTC

Después de comprobar el software y los requisitos previos del entorno para Telefonía IP empresarial puede:
  
- Instalar al servidor de mediación, tal como se describe en [implementar un servidor de mediación en el generador de topología en Skype para Business Server 2015](deploy-a-mediation-server.md), pero sólo si va a implementar un servidor de mediación de independiente o grupo porque los servidores de mediación se instalan como parte de la parte delantera Grupo de servidores o el proceso de implementación de Standard Edition server cuando ubicados.
    
- O bien, puede empezar a configurar opciones para dirigir las llamadas de los usuarios de Telefonía IP empresarial, como se describe en [configurar los troncos en Skype para Business Server 2015](configure-trunks.md).
    

