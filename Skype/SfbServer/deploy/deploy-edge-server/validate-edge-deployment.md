---
title: Validar la implementación perimetral en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumen: obtenga información sobre cómo comprobar que la implementación del servidor perimetral o el grupo de servidores perimetrales funciona en Skype Empresarial Server.'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804360"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="167dd-103">Validar la implementación perimetral en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="167dd-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="167dd-104">**Resumen:** Obtenga información sobre cómo comprobar que la implementación del servidor perimetral o del grupo de servidores perimetrales funciona en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="167dd-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="167dd-105">Una vez que haya implementado el servidor perimetral o el grupo de servidores perimetrales, debe saber si funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="167dd-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="167dd-106">Estas son algunas de las cosas que pueden ayudar a confirmar que el entorno perimetral está conectado a los servidores internos y que los usuarios externos pueden conectarse a su entorno de Skype Empresarial Server a través de su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="167dd-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="167dd-107">Comprobar la conectividad entre los servidores internos y los servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="167dd-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="167dd-108">Aunque la validación de conectividad se realiza automáticamente en el servidor perimetral o en el grupo de servidores perimetrales cuando se instalan los servidores perimetrales, puede confirmarlo usted mismo con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="167dd-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="167dd-109">Ejecute el cmdlet Get-CsManagementStoreReplicationStatus en el servidor interno que tiene el almacén de administración central o en cualquier equipo unido al dominio en el que estén instalados los componentes principales de Skype Empresarial Server (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="167dd-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="167dd-110">El resultado inicial de ejecutar este comando puede dar un estado False, en lugar de True, para la replicación.</span><span class="sxs-lookup"><span data-stu-id="167dd-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="167dd-111">Si esto ocurre, ejecute el cmdlet Invoke-CsManagementStoreReplication.</span><span class="sxs-lookup"><span data-stu-id="167dd-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="167dd-112">Dele tiempo para completar la replicación y, a continuación, ejecute el cmdlet Get-CsManagementStoreReplicationStatus nuevo.</span><span class="sxs-lookup"><span data-stu-id="167dd-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="167dd-113">Comprobar la conectividad de los usuarios externos</span><span class="sxs-lookup"><span data-stu-id="167dd-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="167dd-114">Tenemos una excelente herramienta para confirmar la configuración del servidor perimetral y la capacidad de conectarse, enviar y recibir los mensajes correctos para escenarios de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="167dd-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="167dd-115">Es el sitio [Desatilizador de conectividad remota.](https://testconnectivity.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="167dd-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="167dd-116">Este es un sitio administrado y mantenido por el Soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="167dd-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="167dd-117">Para usar esta herramienta, vaya al sitio web y siga las instrucciones para elegir el escenario adecuado.</span><span class="sxs-lookup"><span data-stu-id="167dd-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="167dd-118">Aspectos que se deben tener en cuenta al probar la conectividad de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="167dd-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="167dd-119">Cualquier prueba para el acceso de usuarios externos debe incluir cada tipo de usuario interno compatible con la organización, que puede incluir cualquiera de los siguientes elementos o todos ellos:</span><span class="sxs-lookup"><span data-stu-id="167dd-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="167dd-120">Usuarios de al menos un dominio federado (recomendamos probarlos todos).</span><span class="sxs-lookup"><span data-stu-id="167dd-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="167dd-121">Usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="167dd-121">Anonymous users.</span></span>
    
- <span data-ttu-id="167dd-122">Usuarios de su organización que hayan iniciado sesión en Skype Empresarial de forma remota, pero que no estén usando VPN.</span><span class="sxs-lookup"><span data-stu-id="167dd-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="167dd-123">Estas pruebas determinarán si el servidor perimetral es:</span><span class="sxs-lookup"><span data-stu-id="167dd-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="167dd-124">Escuchar en los puertos necesarios mediante un cliente telnet desde fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="167dd-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="167dd-125">Por ejemplo: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="167dd-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="167dd-126">Debe realizar la prueba anterior en los puertos que use en el servidor perimetral o en el grupo de servidores perimetrales, en función de la implementación.</span><span class="sxs-lookup"><span data-stu-id="167dd-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="167dd-127">Realizar una resolución dns externa precisa.</span><span class="sxs-lookup"><span data-stu-id="167dd-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="167dd-128">Desde fuera de la red, haga ping a cada uno de los FQDN externos de su servidor perimetral o grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="167dd-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="167dd-129">Incluso si se produce un error en el ping, verá las direcciones IP, que puede comparar las direcciones IP que asignó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="167dd-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

