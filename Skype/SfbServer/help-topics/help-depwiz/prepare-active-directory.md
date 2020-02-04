---
title: Preparar Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Para comenzar la instalación de Skype empresarial Server 2015, debe preparar el esquema, el bosque y los dominios de los servicios de dominio de Active Directory que alojarán los servidores y los usuarios. El Asistente de implementación de Skype empresarial Server le guiará a través de los pasos necesarios para preparar Active Directory, empezando con el esquema y luego en la preparación del bosque. Después de confirmar que la replicación de Active Directory se realiza correctamente, prepare todos los dominios que hospedarán usuarios o servidores.
ms.openlocfilehash: a184e67b7cb87eca95556495ab32f4ded97aaf14
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700765"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="93008-105">Preparar Active Directory</span><span class="sxs-lookup"><span data-stu-id="93008-105">Prepare Active Directory</span></span>

<span data-ttu-id="93008-106">Para comenzar la instalación de Skype empresarial Server 2015, debe preparar el esquema, el bosque y los dominios de los servicios de dominio de Active Directory que alojarán los servidores y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="93008-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="93008-107">El Asistente de implementación de Skype empresarial Server le guiará a través de los pasos necesarios para preparar Active Directory, empezando con el esquema y luego en la preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="93008-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="93008-108">Después de confirmar que la replicación de Active Directory se realiza correctamente, prepare todos los dominios que hospedarán usuarios o servidores.</span><span class="sxs-lookup"><span data-stu-id="93008-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93008-p103">Para preparar el esquema correctamente, debe iniciar sesión como miembro de los grupos Administradores de esquema y Administradores de organización. Para preparar el bosque, debe iniciar sesión como miembro del grupo Administradores de organización o como administrador en el dominio raíz del bosque. Para la preparación del dominio, debe iniciar sesión como miembro del grupo Admins. del dominio.</span><span class="sxs-lookup"><span data-stu-id="93008-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="93008-p104">Para obtener información detallada sobre las topologías de Active Directory admitidas, consulte [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) en la documentación sobre compatibilidad. Para obtener información detallada sobre la preparación de Active Directory, consulte [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="93008-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


