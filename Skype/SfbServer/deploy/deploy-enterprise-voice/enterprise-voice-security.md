---
title: Requisitos previos de configuración y seguridad para Enterprise Voice en Skype para Business Server
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
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Resumen: Obtenga información sobre los requisitos previos de configuración y seguridad para Enterprise Voice en Skype para Business Server.'
ms.openlocfilehash: 522252119dd6e3699dc93e0191d50a3c09c023dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212484"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="41b02-103">Requisitos previos de configuración y seguridad para Enterprise Voice en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="41b02-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="41b02-104">**Resumen:** Obtenga información acerca de los requisitos previos de configuración y seguridad para Enterprise Voice en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="41b02-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="41b02-105">Antes de implementar Enterprise Voice, compruebe que su infraestructura cumple la siguiente seguridad, configuración de usuario y los requisitos previos de hardware específico del escenario.</span><span class="sxs-lookup"><span data-stu-id="41b02-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="41b02-106">Derechos administrativos e infraestructura de certificados</span><span class="sxs-lookup"><span data-stu-id="41b02-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="41b02-107">Antes de implementar, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41b02-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="41b02-108">Los administradores que implementen Enterprise Voice deben ser miembros del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="41b02-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="41b02-109">Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:</span><span class="sxs-lookup"><span data-stu-id="41b02-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="41b02-110">**CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="41b02-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="41b02-p101">**CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Telefonía IP empresarial para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.</span><span class="sxs-lookup"><span data-stu-id="41b02-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="41b02-113">**CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="41b02-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="41b02-114">Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="41b02-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41b02-115">Para obtener información detallada sobre los requisitos de certificado en Skype para Business Server, vea [requisitos de entorno para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41b02-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="41b02-116">Configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="41b02-116">User configuration</span></span>

<span data-ttu-id="41b02-117">Si instala el servidor de mediación con cada grupo de servidores Front-End o servidor Standard Edition durante la implementación de Front-End, la configuración de usuario necesarios para Enterprise Voice se configuraron automáticamente durante la instalación de los archivos para esas funciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="41b02-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="41b02-118">Si va a implementar recién la carga de trabajo de Enterprise Voice en este momento, antes de comenzar el proceso de implementación, designar un número de teléfono principal de cada usuario que va a habilitar para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="41b02-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="41b02-119">En tanto que administrador, es responsable de asegurarse de que este número sea único.</span><span class="sxs-lookup"><span data-stu-id="41b02-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="41b02-120">Antes de la implementación, todos los principales de teléfono se deben normalizar los números (el formato correcto) y copiado en propiedad de **URI de línea** de cada usuario mediante Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="41b02-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41b02-121">Si desea ver ejemplos de números de teléfono principales necesarios en una implementación de Telefonía IP empresarial, consulte [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="41b02-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="41b02-122">Pasos siguientes: Instalar archivos o configurar la conectividad RTC</span><span class="sxs-lookup"><span data-stu-id="41b02-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="41b02-123">Después de comprobar el software y los requisitos previos para Enterprise Voice puede:</span><span class="sxs-lookup"><span data-stu-id="41b02-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="41b02-124">Instalar al servidor de mediación, tal y como se describe en [implementar un servidor de mediación en el generador de Skype para Business Server](deploy-a-mediation-server.md), pero sólo si desea implementar un servidor de mediación o grupo de servidores independiente, ya que los servidores de mediación se instalan como parte de Front-End proceso de implementación de Standard Edition server cuando combinado o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="41b02-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="41b02-125">O bien, puede empezar a configurar opciones para enrutar las llamadas para los usuarios de Enterprise Voice, tal como se describe en [Configurar troncos en Skype para Business Server](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="41b02-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

