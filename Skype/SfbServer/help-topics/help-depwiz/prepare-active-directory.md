---
title: Preparar Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Para comenzar la instalación de Skype para Business Server 2015, debe preparar el esquema, bosque y dominios que se va a hospedar servidores y usuarios de los servicios de dominio de Active Directory. El Skype para el Asistente para la implementación de Business Server le guiará a través de los pasos necesarios para preparar Active Directory, comenzando con el esquema y, a continuación, en la preparación del bosque. Después de confirmar que la replicación de Active Directory es correcta, a continuación, preparar cada dominio que se va a hospedar los usuarios o servidores.
ms.openlocfilehash: 4961292a87cc31ef37afd0cb0ea49753c9fae715
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33918728"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="9c442-105">Preparar Active Directory</span><span class="sxs-lookup"><span data-stu-id="9c442-105">Prepare Active Directory</span></span>

<span data-ttu-id="9c442-106">Para comenzar la instalación de Skype para Business Server 2015, debe preparar el esquema, bosque y dominios que se va a hospedar servidores y usuarios de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9c442-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="9c442-107">El Skype para el Asistente para la implementación de Business Server le guiará a través de los pasos necesarios para preparar Active Directory, comenzando con el esquema y, a continuación, en la preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="9c442-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="9c442-108">Después de confirmar que la replicación de Active Directory es correcta, a continuación, preparar cada dominio que se va a hospedar los usuarios o servidores.</span><span class="sxs-lookup"><span data-stu-id="9c442-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c442-p103">Para preparar el esquema correctamente, debe iniciar sesión como miembro de los grupos Administradores de esquema y Administradores de organización. Para preparar el bosque, debe iniciar sesión como miembro del grupo Administradores de organización o como administrador en el dominio raíz del bosque. Para la preparación del dominio, debe iniciar sesión como miembro del grupo Admins. del dominio.</span><span class="sxs-lookup"><span data-stu-id="9c442-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="9c442-p104">Para obtener información detallada sobre las topologías de Active Directory admitidas, consulte [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) en la documentación sobre compatibilidad. Para obtener información detallada sobre la preparación de Active Directory, consulte [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="9c442-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


