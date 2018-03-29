---
title: Validar la implementación perimetral en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumen: Conozca cómo comprobar que la implementación de servidor perimetral o grupo de servidores del servidor perimetral funciona en Skype para Business Server 2015.'
ms.openlocfilehash: 02f909310e6b491ae97e31b7013b1307c7688ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server-2015"></a><span data-ttu-id="814d8-103">Validar la implementación perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="814d8-103">Validate your Edge deployment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="814d8-104">**Resumen:** Obtenga información sobre cómo comprobar que la implementación de servidor perimetral o grupo de servidores del servidor perimetral funciona en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="814d8-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="814d8-105">Una vez que haya implementado el servidor perimetral o un grupo de servidores de servidor perimetral, necesitará saber si funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="814d8-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="814d8-106">Aquí hay un par de cosas que pueden ayudar a confirmar su entorno perimetral está conectado a los servidores internos y los usuarios externos pueden conectarse a su Skype para Business Server 2015 entorno a través de su borde.</span><span class="sxs-lookup"><span data-stu-id="814d8-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server 2015 environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="814d8-107">Comprobar la conectividad entre los servidores internos y los servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="814d8-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="814d8-108">Mientras se realiza la validación de conectividad automáticamente en el servidor perimetral o grupo de servidores de borde cuando se instalan los servidores perimetrales, puede confirmarlo todavía usted mismo con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="814d8-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="814d8-109">Ejecute el cmdlet Get-CsManagementStoreReplicationStatus en el servidor interno que tiene la Administración Central de almacén o cualquier equipo unido dominio en qué Skype para componentes de núcleo de Business Server 2015 (OcsCore.msi) se instalan.</span><span class="sxs-lookup"><span data-stu-id="814d8-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server 2015 Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="814d8-p103">El resultado inicial de ejecutar este comando puede ofrecer un estado False, en lugar de True, para replicación. Si eso ocurre ejecute el cmdlet Invoke-CsManagementStoreReplication. Dele algo de tiempo para completar la replicación y después ejecute el cmdlet Get-CsManagementStoreReplicationStatus de nuevo.</span><span class="sxs-lookup"><span data-stu-id="814d8-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="814d8-113">Comprobar la conectividad de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="814d8-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="814d8-114">Tenemos una gran herramienta para confirmar la configuración del servidor de borde y la capacidad de conectar, enviar y recibir los mensajes correctos para escenarios de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="814d8-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="814d8-115">Es el [sitio de Anaylzer de conectividad remota](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="814d8-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="814d8-116">Se trata de un sitio que administra y mantiene el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="814d8-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="814d8-117">Para usar esta herramienta, vaya al sitio web y siga las instrucciones para elegir el escenario correcto para usted.</span><span class="sxs-lookup"><span data-stu-id="814d8-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="814d8-118">Aspectos que se deben tener en cuenta al probar la conectividad de los usuarios externos</span><span class="sxs-lookup"><span data-stu-id="814d8-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="814d8-119">Las pruebas para el acceso de usuarios externos tienen que incluir cada tipo de usuario interno que admite la organización, que podría incluir alguno de los elementos siguientes o todos ellos:</span><span class="sxs-lookup"><span data-stu-id="814d8-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="814d8-120">Usuarios de al menos un dominio federado (le recomendamos probarlas todas).</span><span class="sxs-lookup"><span data-stu-id="814d8-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="814d8-121">Usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="814d8-121">Anonymous users.</span></span>
    
- <span data-ttu-id="814d8-122">Usuarios de la organización que se registran remotamente en Skype para el negocio, pero no mediante VPN.</span><span class="sxs-lookup"><span data-stu-id="814d8-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="814d8-123">Estas pruebas determinará si el servidor perimetral es:</span><span class="sxs-lookup"><span data-stu-id="814d8-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="814d8-124">Escucha en los puertos necesarios a través de un cliente de telnet de fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="814d8-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="814d8-125">Por ejemplo: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="814d8-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="814d8-126">Debe realizar la prueba anterior en los puertos que se utiliza en el servidor perimetral o grupo de servidores de borde, dependiendo de su implementación.</span><span class="sxs-lookup"><span data-stu-id="814d8-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="814d8-127">Logre una resolución de DNS externa precisa.</span><span class="sxs-lookup"><span data-stu-id="814d8-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="814d8-128">Desde fuera de la red, haga ping en cada uno de los FQDN externos del servidor perimetral o grupo de servidores de borde.</span><span class="sxs-lookup"><span data-stu-id="814d8-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="814d8-129">Incluso si falla el comando ping, verá las direcciones IP, que puede comparar las direcciones IP que haya asignado previamente.</span><span class="sxs-lookup"><span data-stu-id="814d8-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

