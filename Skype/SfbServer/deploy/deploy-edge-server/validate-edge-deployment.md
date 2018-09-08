---
title: Validar la implementación perimetral en Skype para Business Server
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumen: Obtenga información sobre cómo comprobar que la implementación de servidor perimetral o grupo de servidores perimetrales está funcionando en Skype para Business Server.'
ms.openlocfilehash: 267a02407a66614d0c78592da073307979136e39
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883551"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="a89b9-103">Validar la implementación perimetral en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="a89b9-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="a89b9-104">**Resumen:** Obtenga información sobre cómo comprobar que la implementación de servidor perimetral o grupo de servidores perimetrales está funcionando en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="a89b9-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="a89b9-105">Una vez que haya implementado el servidor perimetral o grupo de servidores perimetrales, necesita saber si funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="a89b9-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="a89b9-106">A continuación presentamos un par de cosas que pueden ayudar a con el entorno perimetral está conectado para confirmar a los servidores internos y los usuarios externos pueden conectarse a su Skype para entorno Business Server a través de su borde.</span><span class="sxs-lookup"><span data-stu-id="a89b9-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="a89b9-107">Comprobar la conectividad entre los servidores internos y los servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="a89b9-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="a89b9-108">Mientras se realiza la validación de conectividad automáticamente en el servidor perimetral o grupo de servidores perimetrales cuando se instalan los servidores perimetrales, puede confirmarlo aún usted mismo con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a89b9-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="a89b9-109">Ejecute el cmdlet Get-CsManagementStoreReplicationStatus en el servidor interno que tiene la Administración Central de almacenar o cualquier equipo del dominio unidas en qué Skype para los componentes principales de servidor empresarial (OcsCore.msi) se instalan.</span><span class="sxs-lookup"><span data-stu-id="a89b9-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="a89b9-p103">El resultado inicial de ejecutar este comando puede ofrecer un estado False, en lugar de True, para replicación. Si eso ocurre ejecute el cmdlet Invoke-CsManagementStoreReplication. Dele algo de tiempo para completar la replicación y después ejecute el cmdlet Get-CsManagementStoreReplicationStatus de nuevo.</span><span class="sxs-lookup"><span data-stu-id="a89b9-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="a89b9-113">Comprobar la conectividad de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="a89b9-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="a89b9-114">Hemos desarrollado una gran herramienta para confirmar la configuración del servidor perimetral y la capacidad de conectarse, enviar y recibir los mensajes correctos para los escenarios de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a89b9-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="a89b9-115">Es el [sitio de Anaylzer de conectividad remota](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="a89b9-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="a89b9-116">Se trata de un sitio que administra y mantiene el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a89b9-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="a89b9-117">Para usar esta herramienta, vaya al sitio web y siga las instrucciones para elegir el escenario correcto para usted.</span><span class="sxs-lookup"><span data-stu-id="a89b9-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="a89b9-118">Aspectos que se deben tener en cuenta al probar la conectividad de los usuarios externos</span><span class="sxs-lookup"><span data-stu-id="a89b9-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="a89b9-119">Las pruebas para el acceso de usuarios externos tienen que incluir cada tipo de usuario interno que admite la organización, que podría incluir alguno de los elementos siguientes o todos ellos:</span><span class="sxs-lookup"><span data-stu-id="a89b9-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="a89b9-120">Usuarios de al menos un dominio federado (le recomendamos probarlas todas).</span><span class="sxs-lookup"><span data-stu-id="a89b9-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="a89b9-121">Usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="a89b9-121">Anonymous users.</span></span>
    
- <span data-ttu-id="a89b9-122">Usuarios de la organización que se registran en Skype para la empresa de forma remota, pero no se usen una VPN.</span><span class="sxs-lookup"><span data-stu-id="a89b9-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="a89b9-123">Estas pruebas determinará si el servidor perimetral es:</span><span class="sxs-lookup"><span data-stu-id="a89b9-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="a89b9-124">Escucha en los puertos necesarios a través de un cliente de telnet de fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="a89b9-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="a89b9-125">Por ejemplo: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="a89b9-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="a89b9-126">Debe realizar las pruebas anteriores en los puertos que se está utilizando en el servidor perimetral o grupo de servidores perimetrales, dependiendo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="a89b9-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="a89b9-127">Logre una resolución de DNS externa precisa.</span><span class="sxs-lookup"><span data-stu-id="a89b9-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="a89b9-128">Desde fuera de la red, haga ping a cada uno de los FQDN externos de su servidor perimetral o grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="a89b9-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="a89b9-129">Incluso si se produce un error en el comando ping, verá las direcciones IP, que puede comparar las direcciones IP que haya asignado previamente.</span><span class="sxs-lookup"><span data-stu-id="a89b9-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

