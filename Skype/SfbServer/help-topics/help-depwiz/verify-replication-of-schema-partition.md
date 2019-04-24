---
title: Comprobar la replicación de la partición del esquema
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Para comprobar que la ampliación del esquema se han replicado correctamente en su bosque de los servicios de dominio de Active Directory, haga lo siguiente:'
ms.openlocfilehash: 38d5983623c837e931274deef7581dd1567fc492
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234862"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="27b64-103">Comprobar la replicación de la partición del esquema</span><span class="sxs-lookup"><span data-stu-id="27b64-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="27b64-104">Para comprobar que la ampliación del esquema se han replicado correctamente en su bosque de los servicios de dominio de Active Directory, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27b64-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="27b64-105">Inicie sesión en su bosque de los servicios de dominio de Active Directory, donde se han aplicado las extensiones del esquema como un miembro del grupo Administradores de organización en un controlador de dominio (que no sea el controlador de dominio que contiene la función de maestro de esquema).</span><span class="sxs-lookup"><span data-stu-id="27b64-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="27b64-106">Abrir Editar ADSI: Haga clic en **Inicio**, haga clic en **Herramientas administrativas**y, a continuación, haga clic en **Edición de ADSI**.</span><span class="sxs-lookup"><span data-stu-id="27b64-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="27b64-107">Como alternativa, haga clic en **Inicio**, a continuación, haga clic en **Ejecutar**, escriba **adsiedit.msc** para iniciar el Editor ADSI.</span><span class="sxs-lookup"><span data-stu-id="27b64-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="27b64-108">En el árbol de Microsoft Management Console (MMC), si aún no está seleccionado, haga clic en el Editor ADSI.</span><span class="sxs-lookup"><span data-stu-id="27b64-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="27b64-109">En el menú **Acción**, haga clic en **Conectar con**.</span><span class="sxs-lookup"><span data-stu-id="27b64-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="27b64-110">En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27b64-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="27b64-111">En el contenedor de esquema, busque CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="27b64-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="27b64-112">Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema correctamente se ha actualizado y replicado.</span><span class="sxs-lookup"><span data-stu-id="27b64-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="27b64-113">Si este objeto no existe o si los valores de los atributos **rangeUpper** y **rangeLower** no son como especificado, a continuación, el esquema no se ha modificado o no se ha replicado.</span><span class="sxs-lookup"><span data-stu-id="27b64-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="27b64-114">Si la verificación de la replicación del esquema no mostrar aún una replicación correcta, espere aproximadamente 15 minutos y, a continuación, compruebe de nuevo.</span><span class="sxs-lookup"><span data-stu-id="27b64-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="27b64-115">Replicación de Active Directory se basa en un modelo de coherencia no estricta y puede producirse algunos latencia de replicación, en función de un número de factores que influyen en el servidor y la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="27b64-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

