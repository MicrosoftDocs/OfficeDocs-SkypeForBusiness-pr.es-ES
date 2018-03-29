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
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="285cc-103">Requisitos previos de seguridad y configuración para telefonía IP empresarial en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="285cc-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="285cc-104">**Resumen:** Conozca los requisitos previos de configuración y seguridad para Telefonía IP empresarial en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="285cc-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="285cc-105">Antes de implementar la Telefonía IP empresarial, compruebe que la infraestructura cumpla la siguiente seguridad, configuración de usuario y los requisitos previos de hardware específicos de la situación.</span><span class="sxs-lookup"><span data-stu-id="285cc-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="285cc-106">Derechos administrativos e infraestructura de certificados</span><span class="sxs-lookup"><span data-stu-id="285cc-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="285cc-107">Antes de implementar, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="285cc-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="285cc-108">Implementación de Telefonía IP empresarial de administradores deben ser miembros del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="285cc-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="285cc-109">Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:</span><span class="sxs-lookup"><span data-stu-id="285cc-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="285cc-110">**CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="285cc-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="285cc-p101">**CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Telefonía IP empresarial para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.</span><span class="sxs-lookup"><span data-stu-id="285cc-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="285cc-113">**CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="285cc-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="285cc-114">Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="285cc-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="285cc-115">Para obtener más información sobre los requisitos de certificado de Skype para Business Server, consulte [los requisitos ambientales para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="285cc-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="285cc-116">Configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="285cc-116">User configuration</span></span>

<span data-ttu-id="285cc-117">Si coloca el servidor de mediación con cada grupo de servidores Front-End o servidor Standard Edition durante la implementación de Front-End, configuración de usuario necesaria para Telefonía IP empresarial se configura automáticamente durante la instalación de los archivos de dichos roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="285cc-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="285cc-118">Si recién va a distribuir la carga de trabajo de la Telefonía IP empresarial en este momento, antes de comenzar el proceso de implementación, designar un número de teléfono principal para cada usuario que se va a habilitar para la Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="285cc-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="285cc-119">En tanto que administrador, es responsable de asegurarse de que este número sea único.</span><span class="sxs-lookup"><span data-stu-id="285cc-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="285cc-120">Antes de la implementación, todas las principal teléfono números deben normalizarse (el formato correcto) y copia en propiedad de **URI de la línea** de cada usuario mediante Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="285cc-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="285cc-121">Si desea ver ejemplos de números de teléfono principales necesarios en una implementación de Telefonía IP empresarial, consulte [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="285cc-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="285cc-122">Pasos siguientes: Instalar archivos o configurar la conectividad RTC</span><span class="sxs-lookup"><span data-stu-id="285cc-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="285cc-123">Después de comprobar el software y los requisitos previos del entorno para Telefonía IP empresarial puede:</span><span class="sxs-lookup"><span data-stu-id="285cc-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="285cc-124">Instalar al servidor de mediación, tal como se describe en [implementar un servidor de mediación en el generador de topología en Skype para Business Server 2015](deploy-a-mediation-server.md), pero sólo si va a implementar un servidor de mediación de independiente o grupo porque los servidores de mediación se instalan como parte de la parte delantera Grupo de servidores o el proceso de implementación de Standard Edition server cuando ubicados.</span><span class="sxs-lookup"><span data-stu-id="285cc-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="285cc-125">O bien, puede empezar a configurar opciones para dirigir las llamadas de los usuarios de Telefonía IP empresarial, como se describe en [configurar los troncos en Skype para Business Server 2015](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="285cc-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server 2015](configure-trunks.md).</span></span>
    

