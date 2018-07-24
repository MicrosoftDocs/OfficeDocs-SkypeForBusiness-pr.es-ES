---
title: Solicitar, instalar o asignar certificados
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
ROBOTS: NOINDEX, NOFOLLOW
description: 'Paso 3: Solicitar, instalar o asignar certificados inicia al Asistente para certificados cuando haga clic en ejecutar. Los certificados que se configuran mediante el asistente se basan en la definición de la Skype para la topología de servidores de negocios que esté configurada y publicado por el generador de topología para el almacén de Administración Central. Para ejecutar correctamente el Asistente para certificados para una entidad de certificación en línea (CA) en su organización, debe iniciar sesión en el equipo como un usuario que sea miembro del grupo Administradores local del equipo. También debe ser un usuario autenticado de dominio en el dominio donde existen el equipo y la entidad de certificación. El Asistente para certificados ofrecen la posibilidad de especificar credenciales alternativas para el acceso de entidad emisora de certificados de su organización.'
ms.openlocfilehash: cf61a6e2c065ea01e18ae5935c3b4e0e49d9ea36
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966218"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="9f52c-107">Solicitar, instalar o asignar certificados</span><span class="sxs-lookup"><span data-stu-id="9f52c-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="9f52c-108">**Paso 3: solicitar, instalar o asignar certificados** se inicia el Asistente para certificados al hacer clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="9f52c-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="9f52c-109">Los certificados que se configuran mediante el asistente se basan en la definición de la Skype para la topología de servidores de negocios que esté configurada y publicado por el generador de topología para el almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="9f52c-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="9f52c-110">Para ejecutar correctamente el Asistente para certificados para una entidad de certificación en línea (CA) en su organización, debe iniciar sesión en el equipo como un usuario que sea miembro del grupo Administradores local del equipo.</span><span class="sxs-lookup"><span data-stu-id="9f52c-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="9f52c-111">También debe ser un usuario autenticado de dominio en el dominio donde existen el equipo y la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="9f52c-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="9f52c-112">El Asistente para certificados ofrecen la posibilidad de especificar credenciales alternativas para el acceso de entidad emisora de certificados de su organización.</span><span class="sxs-lookup"><span data-stu-id="9f52c-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f52c-p103">El Asistente para certificaciones también es válido para solicitar y procesar solicitudes de certificados sin conexión que se envían a una entidad de certificación pública o a otra infraestructura de clave pública sin conexión. Para generar una solicitud sin conexión, aparte de las que se necesitan para iniciar sesión en el equipo, no existen pertenencias a grupos específicos. Para procesar la respuesta de la entidad de certificación pública y asignar el certificado al equipo y al rol, debe iniciar sesión como miembro del grupo de administradores locales u otro equivalente.</span><span class="sxs-lookup"><span data-stu-id="9f52c-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

