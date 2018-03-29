---
title: Comprobar la replicación de la partición de esquema
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Para comprobar que se han replicado correctamente la extensión del esquema en el bosque de servicios de dominio de Active Directory, haga lo siguiente:'
ms.openlocfilehash: a5628e369ffc796affe9984cef8ecb1ba044ec8a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="3bf1f-103">Comprobar la replicación de la partición de esquema</span><span class="sxs-lookup"><span data-stu-id="3bf1f-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="3bf1f-104">Para comprobar que se han replicado correctamente la extensión del esquema en el bosque de servicios de dominio de Active Directory, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3bf1f-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="3bf1f-105">Inicie sesión en un controlador de dominio (que no sea controlador de dominio que desempeña la función de maestro de esquema) en el bosque de servicios de dominio de Active Directory, donde se aplicaron las extensiones de esquema como miembro del grupo Administradores de organización.</span><span class="sxs-lookup"><span data-stu-id="3bf1f-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="3bf1f-106">Abrir Editar ADSI: Haga clic en **Inicio**, haga clic en **Herramientas administrativas**y, a continuación, haga clic en **Edición de ADSI**.</span><span class="sxs-lookup"><span data-stu-id="3bf1f-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3bf1f-107">O bien, haga clic en **Inicio**, haga clic en **Ejecutar**, escriba **adsiedit.msc** para iniciar ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="3bf1f-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="3bf1f-108">En el árbol de la consola de Microsoft Management Console (MMC), si no está ya seleccionada, haga clic en edición de ADSI.</span><span class="sxs-lookup"><span data-stu-id="3bf1f-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="3bf1f-109">En el menú **Acción**, haga clic en **Conectar con**.</span><span class="sxs-lookup"><span data-stu-id="3bf1f-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="3bf1f-110">En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3bf1f-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="3bf1f-111">Bajo el contenedor del esquema, busque CN = ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="3bf1f-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="3bf1f-112">Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema correctamente se actualiza y replica.</span><span class="sxs-lookup"><span data-stu-id="3bf1f-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="3bf1f-113">Si este objeto no existe o si los valores de los atributos **rangeUpper** y **rangeLower** no se especifica, a continuación, el esquema no se modificó o no se ha replicado.</span><span class="sxs-lookup"><span data-stu-id="3bf1f-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3bf1f-114">Si la verificación de la replicación del esquema no muestra todavía una replicación correcta, espere aproximadamente 15 minutos y compruébelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="3bf1f-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="3bf1f-115">Replicación de Active Directory se basa en un modelo de coherencia no estricta y cierta latencia de replicación puede producirse, basándose en una serie de factores en el servidor y la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="3bf1f-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

