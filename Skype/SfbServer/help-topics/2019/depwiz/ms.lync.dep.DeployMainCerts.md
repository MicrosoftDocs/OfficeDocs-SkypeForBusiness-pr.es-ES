---
title: Solicitar, instalar o asignar certificados
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
ROBOTS: NOINDEX, NOFOLLOW
description: 'Paso 3: Solicitar, instalar o asignar certificados inicia el Asistente para certificados al hacer clic en Ejecutar. Los certificados que se configuran a través del asistente se basan en la definición de la topología de Skype Empresarial Server que el Generador de topologías configura y publica en el almacén de administración central. Para ejecutar correctamente el Asistente para certificados para una entidad de certificación (CA) en línea de su organización, debe iniciar sesión en el equipo como un usuario que sea miembro del grupo de administradores locales del equipo. También debe ser un usuario de dominio autenticado en el dominio donde existen el equipo y la CA. El asistente para certificados proporciona la capacidad de especificar credenciales alternativas para obtener acceso a la CA de su organización.'
ms.openlocfilehash: ec611ee92e26923da45602055771b85fb8cc9a55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825020"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="b70c0-107">Solicitar, instalar o asignar certificados</span><span class="sxs-lookup"><span data-stu-id="b70c0-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="b70c0-108">**Paso 3: Solicitar, instalar o** asignar certificados inicia el Asistente para certificados al hacer clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b70c0-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="b70c0-109">Los certificados que se configuran a través del asistente se basan en la definición de la topología de Skype Empresarial Server que el Generador de topologías configura y publica en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="b70c0-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="b70c0-110">Para ejecutar correctamente el Asistente para certificados para una entidad de certificación (CA) en línea de su organización, debe iniciar sesión en el equipo como un usuario que sea miembro del grupo de administradores locales del equipo.</span><span class="sxs-lookup"><span data-stu-id="b70c0-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="b70c0-111">También debe ser un usuario de dominio autenticado en el dominio donde existen el equipo y la CA.</span><span class="sxs-lookup"><span data-stu-id="b70c0-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="b70c0-112">El asistente para certificados proporciona la capacidad de especificar credenciales alternativas para obtener acceso a la CA de su organización.</span><span class="sxs-lookup"><span data-stu-id="b70c0-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b70c0-p103">El Asistente para certificaciones también es válido para solicitar y procesar solicitudes de certificados sin conexión que se envían a una entidad de certificación pública o a otra infraestructura de clave pública sin conexión. Para generar una solicitud sin conexión, aparte de las que se necesitan para iniciar sesión en el equipo, no existen pertenencias a grupos específicos. Para procesar la respuesta de la entidad de certificación pública y asignar el certificado al equipo y al rol, debe iniciar sesión como miembro del grupo de administradores locales u otro equivalente.</span><span class="sxs-lookup"><span data-stu-id="b70c0-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

