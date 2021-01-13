---
title: Comprobar la replicación de la partición del esquema
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Para comprobar que la extensión de esquema se haya replicado correctamente en el bosque de Servicios de dominio de Active Directory, haga lo siguiente:'
ms.openlocfilehash: db30087e6b996b70fe97e3249c1bf2eaa97a694c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800550"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="8fb59-103">Comprobar la replicación de la partición del esquema</span><span class="sxs-lookup"><span data-stu-id="8fb59-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="8fb59-104">Para comprobar que la extensión de esquema se haya replicado correctamente en el bosque de Servicios de dominio de Active Directory, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8fb59-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="8fb59-105">Inicie sesión en un controlador de dominio (que no sea el controlador de dominio que contiene el rol de maestro de esquema) en el bosque de Servicios de dominio de Active Directory, donde las extensiones de esquema se aplicaron como miembro del grupo Administradores de organización.</span><span class="sxs-lookup"><span data-stu-id="8fb59-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="8fb59-106">Abra el Editor ADSI: haga clic en **Inicio**, en **Herramientas administrativas** y en **Editor ADSI**.</span><span class="sxs-lookup"><span data-stu-id="8fb59-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8fb59-107">Si lo desea, haga clic en **Inicio**; a continuación, haga clic en **Ejecutar** y escriba **adsiedit.msc** para iniciar el Editor ADSI.</span><span class="sxs-lookup"><span data-stu-id="8fb59-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="8fb59-108">En el árbol de la consola MMC, haga clic en Editor ADSI si aún no está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8fb59-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="8fb59-109">En el menú **Acción**, haga clic en **Conectar con**.</span><span class="sxs-lookup"><span data-stu-id="8fb59-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="8fb59-110">En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8fb59-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="8fb59-p101">En el contenedor de esquema, busque CN=ms-RTC-SIP-SchemaVersion. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se ha actualizado y replicado correctamente. Si este objeto no existe o el valor de los atributos **rangeUpper** y **rangeLower** es distinto de lo que se ha especificado, el esquema no se ha modificado o no se ha replicado.</span><span class="sxs-lookup"><span data-stu-id="8fb59-p101">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion. If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated. If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8fb59-114">Si la comprobación de la replicación del esquema aún no muestra una replicación correcta, espere aproximadamente 15 minutos y vuelva a comprobarlo.</span><span class="sxs-lookup"><span data-stu-id="8fb59-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="8fb59-115">La replicación de Active Directory se basa en un modelo de coherencia flexible y puede producirse cierta latencia de replicación, en función de una serie de factores en el servidor y la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="8fb59-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

