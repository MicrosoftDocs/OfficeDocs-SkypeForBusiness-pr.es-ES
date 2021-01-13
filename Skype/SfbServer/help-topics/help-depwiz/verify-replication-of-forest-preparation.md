---
title: Comprobar replicación de la preparación del bosque
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Para confirmar que la replicación del catálogo global y la creación de objetos durante la preparación del bosque se han realizado correctamente, siga estos pasos:'
ms.openlocfilehash: 010cf3fbadf8e07b4ccb80c33c34057024dde896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800560"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="4b3c6-103">Comprobar replicación de la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="4b3c6-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="4b3c6-104">Para confirmar que la replicación del catálogo global y la creación de objetos durante la preparación del bosque se han realizado correctamente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b3c6-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="4b3c6-105">En un controlador de dominio (preferiblemente en un sitio remoto desde otros controladores de dominio) del bosque en el que se ejecutó la preparación del bosque, abra  **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4b3c6-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="4b3c6-106">En  **Usuarios y equipos de Active Directory**, expanda el nombre de dominio del bosque o un dominio secundario.</span><span class="sxs-lookup"><span data-stu-id="4b3c6-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="4b3c6-107">Haga clic **en el** contenedor Usuarios del panel izquierdo y busque el grupo universal CsAdministrator en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="4b3c6-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="4b3c6-108">Si CsAdministrator (entre otros ocho nuevos grupos universales que comienzan con Cs) está presente, la replicación de la preparación del bosque se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b3c6-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="4b3c6-p102">Si el grupo o los grupos aún no están presentes, puede forzar la replicación o esperar 15 minutos y actualizar el panel derecho. Cuando los grupos están presentes, la replicación se ha completado.</span><span class="sxs-lookup"><span data-stu-id="4b3c6-p102">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane. When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="4b3c6-111">Si desea revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para la implementación, en el directorio de usuarios del usuario de Servicios de dominio de Active Directory que realizó el paso.</span><span class="sxs-lookup"><span data-stu-id="4b3c6-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="4b3c6-112">Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="4b3c6-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

