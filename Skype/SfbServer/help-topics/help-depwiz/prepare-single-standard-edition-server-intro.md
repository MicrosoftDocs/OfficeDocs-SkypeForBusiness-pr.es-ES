---
title: Preparar un servidor único de Standard Edition (introducción)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Para iniciar la instalación de un servidor De Skype Empresarial Server 2015 Standard Edition que contendrán el almacén de administración central y otros servicios que seleccione, debe iniciar sesión como miembro del grupo administradores locales en el servidor que se convertirá en el servidor Standard Edition. En la página de preparación de un solo servidor Standard Edition se detallan los requisitos para la instalación inicial. El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.
ms.openlocfilehash: 0523645350c6d6f2c0e42237b944f29193e06555
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829790"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="e89e9-105">Preparar un servidor único de Standard Edition (introducción)</span><span class="sxs-lookup"><span data-stu-id="e89e9-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="e89e9-106">Para iniciar la instalación de un servidor De Skype Empresarial Server 2015 Standard Edition que contendrán el almacén de administración central y otros servicios que seleccione, debe iniciar sesión como miembro del grupo administradores locales en el servidor que se convertirá en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e89e9-106">To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="e89e9-107">En la página de **preparación de un solo servidor Standard Edition** se detallan los requisitos para la instalación inicial.</span><span class="sxs-lookup"><span data-stu-id="e89e9-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="e89e9-108">El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.</span><span class="sxs-lookup"><span data-stu-id="e89e9-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="e89e9-109">El objetivo de esta tarea específica es configurar un servidor Standard Edition como primer servidor de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="e89e9-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="e89e9-110">Esta tarea instala el almacén de administración central, que es SQL Server Express, en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e89e9-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="e89e9-111">Si ya tiene implementado otro servidor Standard Edition u otro grupo de servidores front-end, debe hacer clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="e89e9-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e89e9-112">Después de completar esta tarea, instalará topology Builder (si aún no la ha instalado) y configurará el documento de topología.</span><span class="sxs-lookup"><span data-stu-id="e89e9-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="e89e9-113">No podrá publicar el documento de topología hasta que tenga un almacén de administración central disponible, que se implementa completando la tarea descrita en este tema.</span><span class="sxs-lookup"><span data-stu-id="e89e9-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

