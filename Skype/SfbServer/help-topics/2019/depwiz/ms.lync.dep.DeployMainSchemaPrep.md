---
title: Preparar esquema
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Para preparar el esquema de los servicios de dominio de Active Directory, ejecute el paso Preparar el esquema en el Skype para el Asistente para la implementación de servidor de negocio. Haga clic en Ejecutar para comenzar la preparación del esquema.
ms.openlocfilehash: 5cc9f4136d86408296a95c8bad0ffdbd13185d8d
ms.sourcegitcommit: ddedcfe6efd4d8adec794a70c904468a45fbdeb4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2018
ms.locfileid: "22601965"
---
# <a name="prepare-schema"></a><span data-ttu-id="48635-104">Preparar esquema</span><span class="sxs-lookup"><span data-stu-id="48635-104">Prepare Schema</span></span>
 
<span data-ttu-id="48635-105">Para preparar el esquema de los servicios de dominio de Active Directory, ejecute el paso Preparar el esquema en el Skype para el Asistente para la implementación de servidor de negocio.</span><span class="sxs-lookup"><span data-stu-id="48635-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="48635-106">Haga clic en **Ejecutar** para comenzar la preparación del esquema.</span><span class="sxs-lookup"><span data-stu-id="48635-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="48635-107">El paso Preparar el esquema lee el esquema proporcionado en archivos de definición en el \Program Files\Skype para Active directory de 2019\Deployment\Setup Business Server en el sistema que se está ejecutando el Asistente para la implementación en.</span><span class="sxs-lookup"><span data-stu-id="48635-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="48635-108">Estos archivos también están disponibles en el directorio \Support\Schema del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="48635-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="48635-109">El paso Preparar esquema ampliará el esquema e informará sobre el estado del proceso.</span><span class="sxs-lookup"><span data-stu-id="48635-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="48635-110">Además, avisará cuando el proceso haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="48635-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="48635-111">En la pantalla de resumen se podrán ver los registros del proceso.</span><span class="sxs-lookup"><span data-stu-id="48635-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="48635-112">Examine los registros para asegurarse de que la preparación se haya completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="48635-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="48635-113">Para ampliar el esquema, debe iniciar sesión en el dominio como miembro de los grupos Administradores de esquema y Administradores de organización.</span><span class="sxs-lookup"><span data-stu-id="48635-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="48635-114">Se agregan las clases y atributos para extender el esquema de los servicios de dominio de Active Directory para admitir Skype para server Business Server, servicio y objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="48635-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="48635-115">Antes de ampliar el esquema, se recomienda realizar una copia de seguridad del estado del sistema del controlador de dominio que tiene la función maestra de esquema.</span><span class="sxs-lookup"><span data-stu-id="48635-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="48635-116">La ampliación del esquema es una acción que no puede deshacerse.</span><span class="sxs-lookup"><span data-stu-id="48635-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="48635-117">Debe hacer lo posible para limitar el impacto potencial de una ampliación de esquema incorrecta y para asegurarse de que la ampliación de esquema sea correcta.</span><span class="sxs-lookup"><span data-stu-id="48635-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="48635-118">Esto es especialmente crítico en caso de pérdida de comunicación o de cualquier otro error en el servidor.</span><span class="sxs-lookup"><span data-stu-id="48635-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="48635-119">Debe realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="48635-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="48635-120">Para realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory:</span><span class="sxs-lookup"><span data-stu-id="48635-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="48635-121">Desconecte de la red el controlador de dominio que tiene el rol maestro de esquema.</span><span class="sxs-lookup"><span data-stu-id="48635-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="48635-122">Efectúe una copia de seguridad de estado del sistema del controlador de dominio que tiene el rol maestro de esquema.</span><span class="sxs-lookup"><span data-stu-id="48635-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="48635-123">Amplíe el esquema.</span><span class="sxs-lookup"><span data-stu-id="48635-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="48635-124">Si la ampliación del esquema es correcta, vuelva a conectar el controlador de dominio a la red y compruebe que la replicación esté activa y en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="48635-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="48635-125">En el evento poco probable de un error de extensión de esquema, restaure el estado de sistemas del controlador de dominio y Active Directory mediante el uso de la copia de seguridad de estado del sistema que realizó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="48635-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="48635-126">Si necesita revisar los archivos de registro que se crean mediante la Skype para el Asistente para la implementación de servidor de negocio, puede encontrar los archivos en el equipo donde se ejecutó el Asistente para la implementación, en el directorio de usuarios del usuario de Active Directory que se ejecutó el paso.</span><span class="sxs-lookup"><span data-stu-id="48635-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="48635-127">Por ejemplo, si el usuario iniciado sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="48635-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

