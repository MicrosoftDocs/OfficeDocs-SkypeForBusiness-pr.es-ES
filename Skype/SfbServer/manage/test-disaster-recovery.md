---
title: Pruebas de recuperación ante desastres en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Realizar una recuperación del sistema para un servidor de grupo de Skype Empresarial Server para probar el proceso de recuperación ante desastres documentado
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832820"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="72b6a-103">Pruebas de recuperación ante desastres en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="72b6a-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="72b6a-104">Realice una recuperación del sistema para un servidor de grupo de Skype Empresarial Server para probar el proceso de recuperación ante desastres documentado.</span><span class="sxs-lookup"><span data-stu-id="72b6a-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="72b6a-105">Esta prueba simulará un error de hardware completo para un servidor y le ayudará a garantizar que los recursos, los planes y los datos están disponibles para la recuperación.</span><span class="sxs-lookup"><span data-stu-id="72b6a-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="72b6a-106">Intente girar el foco de la prueba cada mes para que su organización pruebe el error de un servidor diferente u otro equipo cada vez.</span><span class="sxs-lookup"><span data-stu-id="72b6a-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="72b6a-107">Tenga en cuenta que la programación según la cual las organizaciones realizan pruebas de recuperación ante desastres variará.</span><span class="sxs-lookup"><span data-stu-id="72b6a-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="72b6a-108">Es muy importante que las pruebas de recuperación ante desastres no se ignoren ni se ignoren.</span><span class="sxs-lookup"><span data-stu-id="72b6a-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="72b6a-109">Exporte la topología, las directivas y las opciones de configuración de Skype Empresarial Server a un archivo.</span><span class="sxs-lookup"><span data-stu-id="72b6a-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="72b6a-110">Entre otras cosas, este archivo puede usarse para restaurar esta información en el almacén de administración central después de una actualización, un error de hardware o algún otro problema que haya provocado la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="72b6a-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="72b6a-111">Importe la topología, las directivas y las opciones de configuración de Skype Empresarial Server al almacén de administración central o al equipo local, como se muestra en los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="72b6a-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="72b6a-112">Para hacer una copia de seguridad de los datos de producción:</span><span class="sxs-lookup"><span data-stu-id="72b6a-112">To back up production data:</span></span>

- <span data-ttu-id="72b6a-113">Realice una copia de seguridad de las bases de datos RTC y LCSLog mediante el proceso de copia de seguridad estándar de SQL Server para volcar la base de datos en un archivo o dispositivo de volcado de cinta.</span><span class="sxs-lookup"><span data-stu-id="72b6a-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="72b6a-114">Use la aplicación de copia de seguridad de terceros para realizar una copia de seguridad de los datos en un archivo o en cinta.</span><span class="sxs-lookup"><span data-stu-id="72b6a-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="72b6a-115">Use el cmdlet Export-CsUserData para crear una exportación XML de toda la base de datos RTC.</span><span class="sxs-lookup"><span data-stu-id="72b6a-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="72b6a-116">Use la copia de seguridad del sistema de archivos o la copia de seguridad de terceros para hacer una copia de seguridad del contenido de reuniones y los registros de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="72b6a-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="72b6a-117">Use la Export-CsConfiguration de línea de comandos para hacer una copia de seguridad de la configuración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="72b6a-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="72b6a-118">El primer paso del procedimiento de conmutación por error incluye un movimiento forzado de usuarios del grupo de producción al grupo de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="72b6a-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="72b6a-119">Esto será un traslado forzado porque el grupo de producción no estará disponible para aceptar la reubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="72b6a-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="72b6a-120">El proceso de usuario de movimiento de Skype Empresarial Server es efectivamente un cambio en un atributo en el objeto de cuenta de usuario además de una actualización de registros en la base de datos de SQL RTC.</span><span class="sxs-lookup"><span data-stu-id="72b6a-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="72b6a-121">Estos datos se pueden restaurar desde el dispositivo de volcado de copia de seguridad original desde el SQL Server de producción mediante el proceso de restauración estándar de SQL Server o mediante una utilidad de copia de seguridad y restauración de terceros.</span><span class="sxs-lookup"><span data-stu-id="72b6a-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="72b6a-122">Después de restaurar estos datos, los usuarios pueden conectarse de forma eficaz al grupo de recuperación ante desastres y funcionar como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="72b6a-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="72b6a-123">Para permitir que los usuarios se conecten al grupo de recuperación ante desastres, se requiere un cambio en el registro DNS.</span><span class="sxs-lookup"><span data-stu-id="72b6a-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="72b6a-124">Los clientes harán referencia al grupo de producción de Skype Empresarial mediante la configuración automática y los registros SRV de DNS de:</span><span class="sxs-lookup"><span data-stu-id="72b6a-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="72b6a-125">SRV: _sip._tls.\<domain></span><span class="sxs-lookup"><span data-stu-id="72b6a-125">SRV: _sip._tls.\<domain></span></span> <span data-ttu-id="72b6a-126">/CNAME: SIP.\<domain></span><span class="sxs-lookup"><span data-stu-id="72b6a-126">/CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="72b6a-127">CNAME: SIP.\<domain></span><span class="sxs-lookup"><span data-stu-id="72b6a-127">CNAME: SIP.\<domain></span></span> <span data-ttu-id="72b6a-128">/cvc-pool-1.\<domain></span><span class="sxs-lookup"><span data-stu-id="72b6a-128">/cvc-pool-1.\<domain></span></span>

<span data-ttu-id="72b6a-129">Para facilitar la conmutación por error, este registro CNAME debe actualizarse para hacer referencia al FQDN de DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="72b6a-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="72b6a-130">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="72b6a-130">CNAME: SIP.<domain></span></span> <span data-ttu-id="72b6a-131">/DROCSPool.\<domain></span><span class="sxs-lookup"><span data-stu-id="72b6a-131">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="72b6a-132">Sip.\<domain></span><span class="sxs-lookup"><span data-stu-id="72b6a-132">Sip.\<domain></span></span>
- <span data-ttu-id="72b6a-133">Av.\<domain></span><span class="sxs-lookup"><span data-stu-id="72b6a-133">AV.\<domain></span></span>
- <span data-ttu-id="72b6a-134">webconf.\<domain></span><span class="sxs-lookup"><span data-stu-id="72b6a-134">webconf.\<domain></span></span>
