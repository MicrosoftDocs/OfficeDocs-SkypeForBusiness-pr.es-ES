---
title: Comprobar replicación de la preparación del bosque
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Para confirmar que la replicación del catálogo global y la creación de objetos durante la preparación del bosque se han realizado correctamente, haga lo siguiente:'
ms.openlocfilehash: 4f17b62fd0756019bab105df323215571557dce2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700655"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="e2852-103">Comprobar replicación de la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="e2852-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="e2852-104">Para confirmar que la replicación del catálogo global y la creación de objetos durante la preparación del bosque se han realizado correctamente, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e2852-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="e2852-105">En un controlador de dominio (preferentemente en un sitio remoto desde otros controladores de dominio) en el bosque donde se ejecutó la preparación del bosque, abra **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="e2852-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="e2852-106">En **Usuarios y equipos de Active Directory**, expanda el nombre de dominio del bosque o un dominio secundario.</span><span class="sxs-lookup"><span data-stu-id="e2852-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="e2852-107">Haga clic en el contenedor **usuarios** en el panel de la izquierda y busque el grupo universal CsAdministrator en el panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="e2852-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="e2852-108">Si CsAdministrator (entre otros ocho grupos universales nuevos que comienzan por CS) está presente, la replicación de la preparación del bosque se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e2852-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="e2852-109">Si los grupos aún no están presentes, puede forzar la replicación o esperar 15 minutos y actualizar el panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="e2852-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="e2852-110">Cuando los grupos están presentes, la replicación se ha completado.</span><span class="sxs-lookup"><span data-stu-id="e2852-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="e2852-111">Si desea revisar los archivos de registro creados por el Asistente para la implementación de Skype empresarial Server, puede encontrarlos en el equipo en el que se ejecutó el Asistente para la implementación, en el directorio usuarios del usuario de los servicios de dominio de Active Directory que ejecutó el paso.</span><span class="sxs-lookup"><span data-stu-id="e2852-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="e2852-112">Por ejemplo, si el usuario ha iniciado sesión como administrador del dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="e2852-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

