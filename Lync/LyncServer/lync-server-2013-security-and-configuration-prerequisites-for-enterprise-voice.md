---
title: Requisitos previos de seguridad y configuración para telefonía IP empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="aba54-102">Requisitos previos de seguridad y configuración de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aba54-102">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aba54-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="aba54-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="aba54-104">Compruebe que su infraestructura cumple con los requisitos previos de hardware, configuración de usuario y seguridad específicos de escenarios.</span><span class="sxs-lookup"><span data-stu-id="aba54-104">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="aba54-105">Derechos de administración e infraestructura de certificados</span><span class="sxs-lookup"><span data-stu-id="aba54-105">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="aba54-106">Asegúrese de que su entorno está configurado con los siguientes grupos de usuarios administrativos e infraestructura de certificados para usar durante el proceso de implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="aba54-106">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="aba54-107">Los administradores que implementen la telefonía IP empresarial deben ser miembros del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="aba54-107">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="aba54-108">Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:</span><span class="sxs-lookup"><span data-stu-id="aba54-108">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="aba54-109">**CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="aba54-109">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="aba54-p101">**CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Telefonía IP empresarial para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.</span><span class="sxs-lookup"><span data-stu-id="aba54-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="aba54-112">**CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="aba54-112">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="aba54-113">La delegación permite que más administradores participen en la implementación de Lync Server sin tener que abrir un acceso innecesario a los recursos.</span><span class="sxs-lookup"><span data-stu-id="aba54-113">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="aba54-114">Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="aba54-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="aba54-115">Para obtener más información sobre los requisitos de certificado de Lync Server, consulte <A href="lync-server-2013-certificate-infrastructure-requirements.md">requisitos de infraestructura de certificados para Lync server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="aba54-115">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="aba54-116">Configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="aba54-116">User Configuration</span></span>

<span data-ttu-id="aba54-117">Si ha colocado el servidor de mediación con cada grupo de servidores front-end o servidor Standard Edition durante la implementación front end, la configuración de usuario necesaria para la telefonía IP empresarial se configuró automáticamente durante la instalación de los archivos de esos roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="aba54-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="aba54-118">Si ha implementado recientemente la carga de trabajo de telefonía IP empresarial en este momento, antes de comenzar el proceso de implementación, designe un número de teléfono principal para cada usuario que tenga previsto habilitar para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="aba54-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="aba54-119">En tanto que administrador, es responsable de asegurarse de que este número sea único.</span><span class="sxs-lookup"><span data-stu-id="aba54-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="aba54-120">Antes de la implementación, todos los números de teléfono principales deben normalizarse (formateados correctamente) y copiarse en la propiedad del **identificador URI** de cada usuario mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aba54-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="aba54-121">Para obtener ejemplos de números de teléfono primarios necesarios para la implementación de telefonía IP empresarial, consulte la sección de <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planes de marcado y reglas de normalización en Lync server 2013</A> , sección de <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planes de marcado y reglas de normalización en Lync Server 2013</A> en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="aba54-121">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="aba54-122">Pasos siguientes: instalar archivos o configurar conectividad RTC</span><span class="sxs-lookup"><span data-stu-id="aba54-122">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="aba54-123">Después de verificar el software y los requisitos previos del entorno de telefonía IP empresarial, puede usar el siguiente contenido para:</span><span class="sxs-lookup"><span data-stu-id="aba54-123">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="aba54-124">Instale el servidor de mediación, como se describe en [instalar los archivos de Media Server en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), pero solo si desea implementar un servidor de mediación o un grupo de mediación independiente cuando se colocan en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="aba54-124">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="aba54-125">También puede empezar a configurar las opciones para enrutar llamadas para usuarios de Enterprise Voice, como se describe en [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="aba54-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

