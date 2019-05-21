---
title: Requisitos previos de seguridad y configuración de telefonía IP empresarial en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Resumen: Obtenga información sobre los requisitos previos de seguridad y configuración de telefonía IP empresarial en Skype empresarial Server.'
ms.openlocfilehash: b3fced9ecac9020da9601c2ab6831769b34ae00a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294161"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="2ff8b-103">Requisitos previos de seguridad y configuración de telefonía IP empresarial en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2ff8b-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="2ff8b-104">**Resumen:** Obtenga más información sobre la seguridad y la configuración de los requisitos previos de telefonía IP empresarial en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="2ff8b-105">Antes de implementar la telefonía IP empresarial, compruebe que su infraestructura cumpla con los requisitos previos de hardware, configuración de usuario y seguridad específicos de escenarios.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="2ff8b-106">Derechos administrativos e infraestructura de certificados</span><span class="sxs-lookup"><span data-stu-id="2ff8b-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="2ff8b-107">Antes de implementar, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ff8b-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="2ff8b-108">Los administradores que implementen la telefonía IP empresarial deben ser miembros del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="2ff8b-109">Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:</span><span class="sxs-lookup"><span data-stu-id="2ff8b-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="2ff8b-110">**CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="2ff8b-p101">**CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Telefonía IP empresarial para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="2ff8b-113">**CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="2ff8b-114">Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2ff8b-115">Para obtener más información sobre los requisitos de certificado de Skype empresarial Server, consulte [requisitos ambientales para Skype empresarial server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos de servidor para skype empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ff8b-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="2ff8b-116">Configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="2ff8b-116">User configuration</span></span>

<span data-ttu-id="2ff8b-117">Si ha colocado el servidor de mediación con cada grupo de servidores front-end o servidor Standard Edition durante la implementación front end, la configuración de usuario necesaria para la telefonía IP empresarial se configuró automáticamente durante la instalación de los archivos de esos roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="2ff8b-118">Si ha implementado recientemente la carga de trabajo de telefonía IP empresarial en este momento, antes de comenzar el proceso de implementación, designe un número de teléfono principal para cada usuario que tenga previsto habilitar para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="2ff8b-119">En tanto que administrador, es responsable de asegurarse de que este número sea único.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="2ff8b-120">Antes de la implementación, todos los números de teléfono principales deben normalizarse (formateados correctamente) y copiarse en la propiedad del URI de la **línea** de cada usuario con el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ff8b-121">Si desea ver ejemplos de números de teléfono principales necesarios en una implementación de Telefonía IP empresarial, consulte [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="2ff8b-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="2ff8b-122">Pasos siguientes: Instalar archivos o configurar la conectividad RTC</span><span class="sxs-lookup"><span data-stu-id="2ff8b-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="2ff8b-123">Después de verificar el software y los requisitos previos del entorno de telefonía IP empresarial, puede:</span><span class="sxs-lookup"><span data-stu-id="2ff8b-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="2ff8b-124">Instale el servidor de mediación, como se describe en [implementar un servidor de mediación en el generador de topologías de Skype empresarial Server](deploy-a-mediation-server.md), pero solo si desea implementar un servidor de mediación o un grupo de mediación independiente, ya que los servidores de mediación están instalados como parte del front-end el proceso de implementación del grupo o del servidor Standard Edition cuando se colocaba.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="2ff8b-125">También puede empezar a configurar las opciones para enrutar llamadas para usuarios de Enterprise Voice, como se describe en [configurar los troncos de Skype empresarial Server](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="2ff8b-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

