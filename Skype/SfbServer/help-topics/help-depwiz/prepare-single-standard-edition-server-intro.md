---
title: Preparar un servidor único de Standard Edition (introducción)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Para comenzar la instalación de un Skype para servidor 2015 Business Server Standard Edition que contendrá el almacén de Administración Central y otros servicios colocadas que seleccione, debe iniciar sesión como miembro del grupo de administradores local en el servidor que será se convierten en el servidor Standard Edition. La página de preparar estándar single Server Edition detalla los requisitos para la instalación inicial. El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.
ms.openlocfilehash: 9c43f3bc4574d35577b483cf1ca0748f78f3d04a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="d696f-105">Preparar un servidor único de Standard Edition (introducción)</span><span class="sxs-lookup"><span data-stu-id="d696f-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="d696f-106">Para comenzar la instalación de un Skype para servidor 2015 Business Server Standard Edition que contendrá el almacén de Administración Central y otros servicios colocadas que seleccione, debe iniciar sesión como miembro del grupo de administradores local en el servidor que será se convierten en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d696f-106">To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="d696f-107">En la página de **preparación de un solo servidor Standard Edition** se detallan los requisitos para la instalación inicial.</span><span class="sxs-lookup"><span data-stu-id="d696f-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="d696f-108">El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.</span><span class="sxs-lookup"><span data-stu-id="d696f-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="d696f-109">El objetivo de esta tarea específica es configurar un servidor Standard Edition como primer servidor de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="d696f-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="d696f-110">Esta tarea instala el almacén de Administración Central, que es SQL Server Express, en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d696f-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="d696f-111">Si ya tiene implementado otro servidor Standard Edition u otro grupo de servidores front-end, debe hacer clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="d696f-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d696f-112">Después de completar esta tarea, instalará al generador de topología (si no se ha instalado ya) y configurar el documento de la topología.</span><span class="sxs-lookup"><span data-stu-id="d696f-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="d696f-113">No podrá publicar el documento de topología hasta que tenga un almacén de administración central disponible, que se implementa completando la tarea descrita en este tema.</span><span class="sxs-lookup"><span data-stu-id="d696f-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

