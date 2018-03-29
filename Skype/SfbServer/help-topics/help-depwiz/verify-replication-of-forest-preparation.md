---
title: Comprobar la replicación de la preparación del bosque
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Para confirmar que la replicación del catálogo Global y la creación de objetos durante la preparación del bosque ha sido correcta, haga lo siguiente:'
ms.openlocfilehash: cfb993a9a80bf4b37e76712a58aa6c1fb0c270c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="da0e5-103">Comprobar la replicación de la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="da0e5-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="da0e5-104">Para confirmar que la replicación del catálogo Global y la creación de objetos durante la preparación del bosque ha sido correcta, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da0e5-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="da0e5-105">En un controlador de dominio (preferentemente en un sitio remoto desde otros controladores de dominio) en el bosque donde se ejecutó la preparación del bosque, abra **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="da0e5-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="da0e5-106">En **Usuarios y equipos de Active Directory**, expanda el nombre de dominio del bosque o un dominio secundario.</span><span class="sxs-lookup"><span data-stu-id="da0e5-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="da0e5-107">Haga clic en el contenedor **usuarios** en el panel de la izquierda y busque el grupo Universal CsAdministrator en el panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="da0e5-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="da0e5-108">Si está presente CsAdministrator (entre ocho otros nuevos grupos universales que comienzan con Cs), la replicación de la preparación del bosque ha tenido éxito.</span><span class="sxs-lookup"><span data-stu-id="da0e5-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="da0e5-109">Si el grupo aún no está presente, puede forzar la replicación o espere 15 minutos y actualizar el panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="da0e5-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="da0e5-110">Cuando los grupos están presentes, la replicación se ha completado.</span><span class="sxs-lookup"><span data-stu-id="da0e5-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="da0e5-111">Si desea revisar los archivos de registro creados por el Skype para el Asistente para implementación de Business Server, puede encontrarlas en el equipo donde se ejecuta el Asistente de implementación, en el directorio de usuarios de usuario de servicios de dominio de Active Directory que ejecutó el paso.</span><span class="sxs-lookup"><span data-stu-id="da0e5-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="da0e5-112">Por ejemplo, si el usuario ha iniciado sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="da0e5-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

