---
title: Comprobar la replicación de la partición del esquema
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Para comprobar que la extensión de esquema se ha replicado correctamente en el bosque de los servicios de dominio de Active Directory, haga lo siguiente:'
ms.openlocfilehash: 0b90f61849e66e78c49d7d00783133198bab6b54
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687323"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="835f4-103">Comprobar la replicación de la partición del esquema</span><span class="sxs-lookup"><span data-stu-id="835f4-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="835f4-104">Para comprobar que la extensión de esquema se ha replicado correctamente en el bosque de los servicios de dominio de Active Directory, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="835f4-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="835f4-105">Inicie sesión en un controlador de dominio (que no sea el controlador de dominio que desempeña la función de maestro de esquema) en el bosque de los servicios de dominio de Active Directory, donde las extensiones de esquema se han aplicado como miembro del grupo administradores de empresa.</span><span class="sxs-lookup"><span data-stu-id="835f4-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="835f4-106">Abra ADSI Edit: haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **ADSI Edit**.</span><span class="sxs-lookup"><span data-stu-id="835f4-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="835f4-107">Como alternativa, haga clic en **Inicio**y, a continuación, en **Ejecutar**, escriba **ADSIEdit. msc** para iniciar ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="835f4-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="835f4-108">En el árbol de Microsoft Management Console (MMC), si aún no está seleccionado, haga clic en ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="835f4-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="835f4-109">En el menú **Acción**, haga clic en **Conectar con**.</span><span class="sxs-lookup"><span data-stu-id="835f4-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="835f4-110">En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="835f4-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="835f4-111">En el contenedor de esquema, busque CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="835f4-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="835f4-112">Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se ha actualizado y replicado correctamente.</span><span class="sxs-lookup"><span data-stu-id="835f4-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="835f4-113">Si este objeto no existe o si los valores de los atributos **rangeUpper** y **rangeLower** no son los especificados, el esquema no se modificó o no se ha replicado.</span><span class="sxs-lookup"><span data-stu-id="835f4-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="835f4-114">Si la comprobación de la replicación del esquema aún no muestra una replicación correcta, espere aproximadamente 15 minutos y, a continuación, vuelva a comprobarlo.</span><span class="sxs-lookup"><span data-stu-id="835f4-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="835f4-115">La replicación de Active Directory se basa en un modelo de coherencia separada y puede producirse cierta latencia de replicación, en función de una serie de factores en el servidor y en la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="835f4-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

