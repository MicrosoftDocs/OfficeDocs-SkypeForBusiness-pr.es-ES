---
title: Requisitos previos de seguridad y configuración para Telefonía IP empresarial en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Summary: Learn about the security and configuration prerequisites for Telefonía IP empresarial in Skype Empresarial Server.'
ms.openlocfilehash: 48cb415208008441f306dd0384c494149f65c4e4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778920"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Requisitos previos de seguridad y configuración para Telefonía IP empresarial en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre los requisitos previos de seguridad y configuración para Telefonía IP empresarial en Skype Empresarial Server.
  
Antes de implementar Telefonía IP empresarial, compruebe que la infraestructura cumple los siguientes requisitos previos de seguridad, configuración de usuario y hardware específicos del escenario. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Derechos administrativos e infraestructura de certificados

Antes de implementar, compruebe lo siguiente:
  
- Los administradores que implementen Enterprise Voice deben ser miembros del grupo RTCUniversalServerAdmins.
    
- Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:
    
  - **CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.
    
  - **CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Enterprise Voice para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.
    
  - **CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.
    
- Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.
    
    > [!NOTE]
    > Para obtener más información sobre los requisitos de certificado en Skype Empresarial Server, vea Requisitos del entorno [para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o Requisitos de servidor [para Skype Empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md). 
  
## <a name="user-configuration"></a>Configuración del usuario

Si collocó el servidor de mediación con cada grupo de servidores front-end o servidor Standard Edition durante la implementación front-end, las opciones de usuario necesarias para Telefonía IP empresarial se configuraron automáticamente durante la instalación de los archivos para esos roles de servidor.
  
En caso de que esté implementando la carga de trabajo de Enterprise Voice por primera vez, antes de iniciar el proceso, designe un número de teléfono principal por cada usuario para el que tenga previsto habilitar Enterprise Voice. En tanto que administrador, es responsable de asegurarse de que este número sea único. Antes de la implementación, todos los números de teléfono principales deben normalizarse (con el formato correcto) y copiarse en la propiedad **URI** de línea de cada usuario mediante Skype Empresarial Server Panel de control.
  
> [!NOTE]
> Para obtener ejemplos de números de teléfono principales necesarios para Telefonía IP empresarial implementación, vea [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Pasos siguientes: Instalar archivos o configurar la conectividad de RTC

Después de comprobar los requisitos previos de software y Telefonía IP empresarial puede:
  
- Instale el servidor de mediación, tal como se describe en Implementar un servidor de mediación en el Generador de topologías en [Skype Empresarial Server](deploy-a-mediation-server.md), pero solo si desea implementar un servidor de mediación independiente o un grupo de servidores porque los servidores de mediación se instalan como parte del grupo de servidores front-end o del proceso de implementación de un servidor Standard Edition cuando se instalan.
    
- O bien, comience a configurar las opciones para enrutar llamadas Telefonía IP empresarial usuarios, como se describe en [Configurar troncos en Skype Empresarial Server](configure-trunks.md).
    

