---
title: Pruebas de recuperación ante desastres en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Realizar una recuperación del sistema de un servidor del grupo de servidores de Skype empresarial para probar el proceso de recuperación ante desastres documentado
ms.openlocfilehash: d65f8bfa512a3954728e09d659b571335d32a379
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279217"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="34877-103">Pruebas de recuperación ante desastres en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="34877-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="34877-104">Realice una recuperación del sistema de un servidor del grupo de servidores de Skype empresarial para probar el proceso de recuperación ante desastres documentado.</span><span class="sxs-lookup"><span data-stu-id="34877-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="34877-105">Esta prueba simulará un error de hardware completo para un servidor y le ayudará a garantizar que los recursos, los planes y los datos estén disponibles para la recuperación.</span><span class="sxs-lookup"><span data-stu-id="34877-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="34877-106">Trate de variar cada mes el objeto de esta simulación, de modo que su organización vaya poniendo a prueba distintos servidores u otros elementos.</span><span class="sxs-lookup"><span data-stu-id="34877-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="34877-p102">Tenga en cuenta que el programa mediante el cual las organizaciones realizan pruebas de recuperación ante desastres puede variar. Es muy importante no ignorar o descuidar estas pruebas.</span><span class="sxs-lookup"><span data-stu-id="34877-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="34877-109">Exporte la topología, las directivas y los parámetros de configuración de Skype empresarial Server a un archivo.</span><span class="sxs-lookup"><span data-stu-id="34877-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="34877-110">Entre otras cosas, este archivo podrá usarse para restaurar esta información en el Almacén de administración central después de una actualización, un error de hardware o cualquier otro problema que resulte en la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="34877-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="34877-111">Importe la topología, las directivas y las opciones de configuración de Skype empresarial Server en el almacén de administración central o en el equipo local, tal y como se muestra en los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="34877-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="34877-112">Para hacer una copia de seguridad de los datos de producción:</span><span class="sxs-lookup"><span data-stu-id="34877-112">To back up production data:</span></span>

- <span data-ttu-id="34877-113">Haga una copia de seguridad de las bases de datos RTC y LCSLog con el proceso de copia de seguridad estándar de SQL Server para volcar la base de datos en un dispositivo de volcado de archivo o cinta.</span><span class="sxs-lookup"><span data-stu-id="34877-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="34877-114">Use una aplicación de terceros para realizar en un archivo o cinta una copia de seguridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="34877-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="34877-115">Use el cmdlet Export-CsUserData para crear una exportación XML de toda la base de datos RTC.</span><span class="sxs-lookup"><span data-stu-id="34877-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="34877-116">Use la copia de seguridad del sistema de archivos o la copia de seguridad de terceros para realizar copias de seguridad de contenido y registros de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="34877-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="34877-117">Use la herramienta de línea de comandos Export-CsConfiguration para realizar copias de seguridad de la configuración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="34877-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="34877-118">El primer paso en el procedimiento de conmutación por error incluye el traslado forzoso de los usuarios desde el grupo de producción al grupo de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="34877-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="34877-119">Se trata de un traslado forzoso porque el grupo de producción no estará disponible para aceptar la reubicación de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="34877-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="34877-120">El proceso para mover usuarios de Skype empresarial Server es en realidad un cambio en un atributo en el objeto de cuenta de usuario, además de una actualización de registro en la base de datos de SQL de RTC.</span><span class="sxs-lookup"><span data-stu-id="34877-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="34877-121">Estos datos se pueden restaurar desde el dispositivo de volcado de la copia de seguridad original desde el servidor SQL de producción mediante el proceso de restauración estándar de SQL Server o mediante una herramienta de copia de seguridad y restauración de terceros.</span><span class="sxs-lookup"><span data-stu-id="34877-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="34877-122">Una vez que se hayan restaurado estos datos, los usuarios podrán conectarse al grupo de recuperación de desastres y funcionar de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="34877-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="34877-123">Para permitir que los usuarios se conecten al grupo de recuperación de desastres, será necesario un cambio de registro DNS.</span><span class="sxs-lookup"><span data-stu-id="34877-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="34877-124">Los clientes hará referencia al grupo de producción de Skype empresarial mediante la configuración automática y los registros SRV de DNS de:</span><span class="sxs-lookup"><span data-stu-id="34877-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="34877-125">SRV: _ SIP. _ TLS. \<domain>/CNAME: SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="34877-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="34877-126">CNAME: SIP. \<domain>/CVC-Pool-1. \<domain></span><span class="sxs-lookup"><span data-stu-id="34877-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="34877-127">Para facilitar la conmutación por error, este registro CNAME debe actualizarse para que haga referencia al FQDN DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="34877-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="34877-128">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="34877-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="34877-129">/DROCSPool. \<domain></span><span class="sxs-lookup"><span data-stu-id="34877-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="34877-130">SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="34877-130">Sip.\<domain></span></span>
- <span data-ttu-id="34877-131">AV.\<domain></span><span class="sxs-lookup"><span data-stu-id="34877-131">AV.\<domain></span></span>
- <span data-ttu-id="34877-132">WebConf. \<domain></span><span class="sxs-lookup"><span data-stu-id="34877-132">webconf.\<domain></span></span>
