---
title: Requisitos previos de seguridad y configuración para telefonía IP empresarial en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Resumen: Obtenga información sobre los requisitos previos de configuración y seguridad para Enterprise Voice en Skype para Business Server 2015.'
ms.openlocfilehash: 2ece3aaa99c1e81afd9241e8d435ac0ab3328893
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server-2015"></a>Requisitos previos de seguridad y configuración para telefonía IP empresarial en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información acerca de los requisitos previos de configuración y seguridad para Enterprise Voice en Skype para Business Server 2015.
  
Antes de implementar Enterprise Voice, compruebe que su infraestructura cumple la siguiente seguridad, configuración de usuario y los requisitos previos de hardware específico del escenario. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Derechos administrativos e infraestructura de certificados

Antes de implementar, compruebe lo siguiente:
  
- Los administradores que implementen Enterprise Voice deben ser miembros del grupo RTCUniversalServerAdmins.
    
- Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:
    
  - **CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.
    
  - **CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Telefonía IP empresarial para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.
    
  - **CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.
    
- Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.
    
    > [!NOTE]
    > Para obtener información detallada sobre los requisitos de certificado en Skype para Business Server, vea [requisitos de entorno para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). 
  
## <a name="user-configuration"></a>Configuración de usuario

Si instala el servidor de mediación con cada grupo de servidores Front-End o servidor Standard Edition durante la implementación de Front-End, la configuración de usuario necesarios para Enterprise Voice se configuraron automáticamente durante la instalación de los archivos para esas funciones de servidor.
  
Si va a implementar recién la carga de trabajo de Enterprise Voice en este momento, antes de comenzar el proceso de implementación, designar un número de teléfono principal de cada usuario que va a habilitar para Enterprise Voice. En tanto que administrador, es responsable de asegurarse de que este número sea único. Antes de la implementación, todos los principales de teléfono se deben normalizar los números (el formato correcto) y copiado en propiedad de **URI de línea** de cada usuario mediante Skype para el Panel de Control de servidor empresarial.
  
> [!NOTE]
> Si desea ver ejemplos de números de teléfono principales necesarios en una implementación de Telefonía IP empresarial, consulte [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Pasos siguientes: Instalar archivos o configurar la conectividad RTC

Después de comprobar el software y los requisitos previos para Enterprise Voice puede:
  
- Instalar al servidor de mediación, tal y como se describe en [implementar un servidor de mediación en el generador de Skype para Business Server 2015](deploy-a-mediation-server.md), pero solo si desea implementar un servidor de mediación o grupo de servidores independiente, ya que los servidores de mediación se instalan como parte de la parte delantera Finalizar el proceso de implementación de Standard Edition server cuando combinado o grupo de servidores.
    
- O bien, puede empezar a configurar opciones para enrutar las llamadas para los usuarios de Enterprise Voice, tal como se describe en [Configurar troncos en Skype para Business Server 2015](configure-trunks.md).
    

