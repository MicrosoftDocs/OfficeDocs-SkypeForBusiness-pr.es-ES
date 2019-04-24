---
title: Recuperación ante desastres pruebas en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Realizar una recuperación del sistema para que un Skype para servidor de grupo de servidores de Business Server probar el proceso de recuperación ante desastres documentado
ms.openlocfilehash: 876470f0e4193f02efe0a2094be80f7bdf891fdd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214739"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="cc5e8-103">Recuperación ante desastres pruebas en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="cc5e8-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="cc5e8-104">Realizar una recuperación del sistema para que un Skype para servidor de grupo de servidores de Business Server probar el proceso de recuperación ante desastres documentado.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="cc5e8-105">Esta prueba para simular un error de hardware completo para un solo servidor y le ayudará a garantizar que los recursos, los planes y los datos están disponibles para la recuperación.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="cc5e8-106">Trate de variar cada mes el objeto de esta simulación, de modo que su organización vaya poniendo a prueba distintos servidores u otros elementos.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="cc5e8-p102">Tenga en cuenta que el programa mediante el cual las organizaciones realizan pruebas de recuperación ante desastres puede variar. Es muy importante no ignorar o descuidar estas pruebas.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="cc5e8-109">Exportar su Skype para la topología, las directivas y opciones de configuración de Business Server a un archivo.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="cc5e8-110">Entre otras cosas, este archivo podrá usarse para restaurar esta información en el Almacén de administración central después de una actualización, un error de hardware o cualquier otro problema que resulte en la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="cc5e8-111">Importar su Skype para la topología de servidor empresarial, directivas y opciones de configuración en el almacén de Administración Central o en el equipo local, tal como se muestra en los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="cc5e8-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="cc5e8-112">Para realizar una copia de seguridad de los datos de producción:</span><span class="sxs-lookup"><span data-stu-id="cc5e8-112">To back up production data:</span></span>

- <span data-ttu-id="cc5e8-113">Copia de seguridad de las bases de datos RTC y LCSLog mediante el estándar SQL Server de copia de seguridad proceso a fin de volcado de la base de datos a un dispositivo de volcado de archivo o una cinta.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="cc5e8-114">Use una aplicación de terceros para realizar en un archivo o cinta una copia de seguridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="cc5e8-115">Use el cmdlet Export-CsUserData para crear una exportación XML de toda la base de datos RTC.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="cc5e8-116">Usar la copia de seguridad de archivos del sistema o una copia de seguridad de terceros para realizar una copia de seguridad de registros de contenido y cumplimiento de normas de la reunión.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="cc5e8-117">Use la herramienta de línea de comandos de Export-CsConfiguration para hacer una copia de seguridad de Skype para la configuración de Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="cc5e8-118">El primer paso en el procedimiento de conmutación por error incluye el traslado forzoso de los usuarios desde el grupo de producción al grupo de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="cc5e8-119">Se trata de un traslado forzoso porque el grupo de producción no estará disponible para aceptar la reubicación de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="cc5e8-120">El Skype para el proceso de usuario de movimiento de Business Server es realmente un cambio en un atributo en el objeto de cuenta de usuario además de una actualización de registro en la base de datos de SQL de RTC.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="cc5e8-121">Estos datos pueden restaurarse desde el dispositivo de volcado de copia de seguridad original de la producción SQL Server utilizando el proceso de restauración de SQL Server standard, o un tercero copia de seguridad y restauración utilidad.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="cc5e8-122">Una vez se hayan restaurado los datos, los usuarios eficazmente pueden conectarse al grupo de servidores de recuperación ante desastres y funcionan como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="cc5e8-123">Para habilitar a los usuarios conectarse al grupo de servidores de recuperación ante desastres, se necesitarán un cambio de registro de DNS.</span><span class="sxs-lookup"><span data-stu-id="cc5e8-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="cc5e8-124">La producción Skype para grupo de negocio se indicará por los clientes mediante la configuración automática y los registros DNS SRV:</span><span class="sxs-lookup"><span data-stu-id="cc5e8-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="cc5e8-125">SRV: _sip._tls. \<domain> /CNAME: SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="cc5e8-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="cc5e8-126">CNAME: SIP. \<domain> /cvc-pool-1. \<domain></span><span class="sxs-lookup"><span data-stu-id="cc5e8-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="cc5e8-127">Para facilitar la conmutación por error, este registro CNAME debe actualizarse para que haga referencia al FQDN DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="cc5e8-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="cc5e8-128">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="cc5e8-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="cc5e8-129">/ DROCSPool. \<domain></span><span class="sxs-lookup"><span data-stu-id="cc5e8-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="cc5e8-130">SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="cc5e8-130">Sip.\<domain></span></span>
- <span data-ttu-id="cc5e8-131">AV.\<domain></span><span class="sxs-lookup"><span data-stu-id="cc5e8-131">AV.\<domain></span></span>
- <span data-ttu-id="cc5e8-132">webconf. \<domain></span><span class="sxs-lookup"><span data-stu-id="cc5e8-132">webconf.\<domain></span></span>
