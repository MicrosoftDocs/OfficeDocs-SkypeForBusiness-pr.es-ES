---
title: Preparar Active Directory
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de Skype para Business Server, debe preparar el esquema, bosque y dominios que se va a hospedar servidores y usuarios de los servicios de dominio de Active Directory. El Skype para el Asistente para la implementación de Business Server le guiará a través de los pasos necesarios para preparar Active Directory, comenzando con el esquema y, a continuación, en la preparación del bosque. Después de confirmar que la replicación de Active Directory es correcta, a continuación, preparar cada dominio que se va a hospedar los usuarios o servidores.
ms.openlocfilehash: 04e4baaaf5209c966fe9bfc350313f7e3cd25d22
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245184"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="24910-105">Preparar Active Directory</span><span class="sxs-lookup"><span data-stu-id="24910-105">Prepare Active Directory</span></span>

<span data-ttu-id="24910-106">Para comenzar la instalación de Skype para Business Server, debe preparar el esquema, bosque y dominios que se va a hospedar servidores y usuarios de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="24910-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="24910-107">El Skype para el Asistente para la implementación de Business Server le guiará a través de los pasos necesarios para preparar Active Directory, comenzando con el esquema y, a continuación, en la preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="24910-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="24910-108">Después de confirmar que la replicación de Active Directory es correcta, a continuación, preparar cada dominio que se va a hospedar los usuarios o servidores.</span><span class="sxs-lookup"><span data-stu-id="24910-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24910-p103">Para preparar el esquema correctamente, debe iniciar sesión como miembro de los grupos Administradores de esquema y Administradores de organización. Para preparar el bosque, debe iniciar sesión como miembro del grupo Administradores de organización o como administrador en el dominio raíz del bosque. Para la preparación del dominio, debe iniciar sesión como miembro del grupo Admins. del dominio.</span><span class="sxs-lookup"><span data-stu-id="24910-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="24910-112">Para obtener información detallada sobre las topologías compatibles de Active Directory, vea [Compatibilidad con Active Directory](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) en la documentación de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="24910-112">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="24910-113">Para obtener información detallada sobre la preparación de Active Directory, vea [Información general de dominio de servicios de preparación de Active Directory](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="24910-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


