---
title: Requisitos previos de seguridad y configuración Telefonía IP empresarial en Skype Empresarial Server
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
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Resumen: obtenga información sobre los requisitos previos de seguridad y configuración Telefonía IP empresarial en Skype Empresarial Server.'
ms.openlocfilehash: 77efbf231f83c6d3c31254c9ab742de7e2b226e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830850"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="eefb6-103">Requisitos previos de seguridad y configuración Telefonía IP empresarial en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="eefb6-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="eefb6-104">**Resumen:** Obtenga información sobre los requisitos previos de seguridad y configuración Telefonía IP empresarial en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eefb6-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="eefb6-105">Antes de implementar Telefonía IP empresarial, compruebe que la infraestructura cumple los siguientes requisitos previos de seguridad, configuración de usuario y hardware específico del escenario.</span><span class="sxs-lookup"><span data-stu-id="eefb6-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="eefb6-106">Derechos administrativos e infraestructura de certificados</span><span class="sxs-lookup"><span data-stu-id="eefb6-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="eefb6-107">Antes de implementar, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eefb6-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="eefb6-108">Los administradores que implementen Enterprise Voice deben ser miembros del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="eefb6-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="eefb6-109">Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:</span><span class="sxs-lookup"><span data-stu-id="eefb6-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="eefb6-110">**CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="eefb6-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="eefb6-p101">**CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Enterprise Voice para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.</span><span class="sxs-lookup"><span data-stu-id="eefb6-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="eefb6-113">**CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="eefb6-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="eefb6-114">Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="eefb6-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eefb6-115">Para obtener más información sobre los requisitos de certificado en Skype Empresarial Server, consulte Requisitos del entorno para [Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o Requisitos de servidor para [Skype Empresarial Server 2019.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="eefb6-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="eefb6-116">Configuración del usuario</span><span class="sxs-lookup"><span data-stu-id="eefb6-116">User configuration</span></span>

<span data-ttu-id="eefb6-117">Si configuró el servidor de mediación con cada grupo de servidores front-end o servidor Standard Edition durante la implementación front-end, la configuración de usuario necesaria para Telefonía IP empresarial se configuró automáticamente durante la instalación de los archivos para esos roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="eefb6-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="eefb6-118">En caso de que esté implementando la carga de trabajo de Enterprise Voice por primera vez, antes de iniciar el proceso, designe un número de teléfono principal por cada usuario para el que tenga previsto habilitar Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="eefb6-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="eefb6-119">En tanto que administrador, es responsable de asegurarse de que este número sea único.</span><span class="sxs-lookup"><span data-stu-id="eefb6-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="eefb6-120">Antes de la implementación, todos los números de teléfono principales deben normalizarse (con el formato correcto) y copiarse en la propiedad **uri** de línea de cada usuario mediante el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eefb6-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eefb6-121">Para obtener ejemplos de números de teléfono principales necesarios para Telefonía IP empresarial implementación, consulte [Reglas de normalización de ejemplo.](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)</span><span class="sxs-lookup"><span data-stu-id="eefb6-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="eefb6-122">Pasos siguientes: Instalar archivos o configurar la conectividad con RTC</span><span class="sxs-lookup"><span data-stu-id="eefb6-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="eefb6-123">Después de comprobar los requisitos previos de software y Telefonía IP empresarial entorno, puede:</span><span class="sxs-lookup"><span data-stu-id="eefb6-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="eefb6-124">Instale el servidor de mediación, como se describe en Implementar un servidor de mediación en el Generador de topologías en Skype Empresarial [Server,](deploy-a-mediation-server.md)pero solo si desea implementar un servidor de mediación independiente o un grupo de servidores porque los servidores de mediación se instalan como parte del proceso de implementación del servidor Standard Edition o del grupo de servidores front-end cuando se instalan.</span><span class="sxs-lookup"><span data-stu-id="eefb6-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="eefb6-125">O bien, comience a configurar las opciones para enrutar las llamadas Telefonía IP empresarial usuarios, como se describe en [Configurar troncos en Skype Empresarial Server.](configure-trunks.md)</span><span class="sxs-lookup"><span data-stu-id="eefb6-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

