---
title: Preparar esquema
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Para preparar el esquema para los Servicios de dominio de Active Directory, ejecute el paso Preparar esquema en el Asistente para la implementación de Skype Empresarial Server. Haga clic en Ejecutar para comenzar la preparación del esquema.
ms.openlocfilehash: b666cda29267c6f74eb034389f3f7967d7af99c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833780"
---
# <a name="prepare-schema"></a><span data-ttu-id="a102b-104">Preparar esquema</span><span class="sxs-lookup"><span data-stu-id="a102b-104">Prepare Schema</span></span>
 
<span data-ttu-id="a102b-105">Para preparar el esquema para los Servicios de dominio de Active Directory, ejecute el paso Preparar esquema en el Asistente para la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a102b-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="a102b-106">Haga clic en **Ejecutar** para comenzar la preparación del esquema.</span><span class="sxs-lookup"><span data-stu-id="a102b-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="a102b-107">El paso Preparar esquema lee los archivos de definición de esquema proporcionados en el directorio \Archivos de programa\Skype Empresarial Server 2019\Deployment\Setup del sistema en el que se ejecuta el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="a102b-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="a102b-108">Estos archivos también están disponibles en el directorio \Soporte\Esquema del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="a102b-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="a102b-109">El paso Preparar el esquema ampliará el esquema e informará sobre el estado del proceso.</span><span class="sxs-lookup"><span data-stu-id="a102b-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="a102b-110">Además, avisará cuando el proceso haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="a102b-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="a102b-111">En la pantalla de resumen se podrán ver los registros del proceso.</span><span class="sxs-lookup"><span data-stu-id="a102b-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="a102b-112">Examine los registros para asegurarse de que la preparación se haya completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a102b-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a102b-113">Para ampliar el esquema, debe iniciar sesión en el dominio como miembro de los grupos Administradores de esquema y Administradores de organización.</span><span class="sxs-lookup"><span data-stu-id="a102b-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="a102b-114">Se agregan clases y atributos para ampliar el esquema de Servicios de dominio de Active Directory para admitir objetos de servidor, servicio y usuario de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a102b-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="a102b-115">Antes de ampliar el esquema, se recomienda realizar una copia de seguridad del estado del sistema del controlador de dominio que tiene la función maestra de esquema.</span><span class="sxs-lookup"><span data-stu-id="a102b-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="a102b-116">La ampliación del esquema es una acción que no puede deshacerse.</span><span class="sxs-lookup"><span data-stu-id="a102b-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="a102b-117">Debe hacer lo posible para limitar el impacto potencial de una ampliación de esquema incorrecta y para asegurarse de que la ampliación de esquema sea correcta.</span><span class="sxs-lookup"><span data-stu-id="a102b-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="a102b-118">Esto es especialmente crítico en caso de pérdida de comunicación o de cualquier otro error en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a102b-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="a102b-119">Debe realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a102b-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="a102b-120">Para realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory:</span><span class="sxs-lookup"><span data-stu-id="a102b-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="a102b-121">Desconecte de la red el controlador de dominio que tiene el rol maestro de esquema.</span><span class="sxs-lookup"><span data-stu-id="a102b-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="a102b-122">Efectúe una copia de seguridad de estado del sistema del controlador de dominio que tiene el rol maestro de esquema.</span><span class="sxs-lookup"><span data-stu-id="a102b-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="a102b-123">Amplíe el esquema.</span><span class="sxs-lookup"><span data-stu-id="a102b-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="a102b-124">Si la ampliación del esquema es correcta, vuelva a conectar el controlador de dominio a la red y compruebe que la replicación esté activa y en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="a102b-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="a102b-125">En el caso poco probable de un error de extensión de esquema, restaure el estado del sistema del controlador de dominio y Active Directory mediante la copia de seguridad del estado del sistema que ha tomado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a102b-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a102b-126">Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrar los archivos en el equipo donde se ejecutó el Asistente para la implementación, en el directorio de usuarios del usuario de Active Directory que realizó el paso.</span><span class="sxs-lookup"><span data-stu-id="a102b-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="a102b-127">Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="a102b-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

