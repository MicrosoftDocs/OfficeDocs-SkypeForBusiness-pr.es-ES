---
title: Probar conferencias de acceso telefónico local en Skype Empresarial Server
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
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Summary: Learn how to test dial-in conferencing in Skype for Business Server.'
ms.openlocfilehash: be1cf5bba5a5bec2076f78880343582be19eda70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096736"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="f1488-103">Probar conferencias de acceso telefónico local en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f1488-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="f1488-104">**Resumen:** Obtenga información sobre cómo probar las conferencias de acceso telefónico local en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f1488-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="f1488-105">Para realizar una comprobación final de la configuración de conferencia de acceso telefónico local, busque planes de marcado que tengan una región de conferencia de acceso telefónico local que no sea usada por ningún número de acceso, así como números de acceso que no tengan asignada ninguna región de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="f1488-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="f1488-106">También debe comprobar que la página web Configuración de conferencia de acceso telefónico local y los números de acceso telefónico local funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="f1488-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="f1488-107">Buscar planes de marcado con una región de conferencia de acceso telefónico local que no se usa con un número de acceso</span><span class="sxs-lookup"><span data-stu-id="f1488-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="f1488-108">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f1488-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="f1488-109">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f1488-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f1488-110">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="f1488-110">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="f1488-111">Este cmdlet devuelve todos los planes de marcado que tienen una región de conferencia de acceso telefónico local que no es usada por ningún número de acceso.</span><span class="sxs-lookup"><span data-stu-id="f1488-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="f1488-112">Para obtener más información, [vea Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f1488-112">For more information, see [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="f1488-113">Buscar números de acceso sin regiones asignadas</span><span class="sxs-lookup"><span data-stu-id="f1488-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="f1488-114">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f1488-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="f1488-115">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f1488-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f1488-116">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="f1488-116">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="f1488-117">Este cmdlet devuelve todos los números de acceso de conferencia de acceso telefónico local que no están asociados a ninguna región.</span><span class="sxs-lookup"><span data-stu-id="f1488-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="f1488-118">Para obtener más información, [vea Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f1488-118">For more information, see [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="f1488-119">Página web de prueba y números de acceso</span><span class="sxs-lookup"><span data-stu-id="f1488-119">Test webpage and access numbers</span></span>

<span data-ttu-id="f1488-120">Para comprobar que la página web Configuración de la conferencia de acceso telefónico local y los números de acceso telefónico local funcionan correctamente, debe realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f1488-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="f1488-121">Pruebe la página web Configuración de la conferencia de acceso telefónico local iniciando sesión en la dirección URL sencilla.</span><span class="sxs-lookup"><span data-stu-id="f1488-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="f1488-p102">Pruebe que los números de acceso telefónico local funcionan correctamente para un grupo de servidores específico ejecutando el script que se ofrece más adelante en este tema. Este script simula llamadas a números de acceso. Para usar este script necesita la dirección SIP y las credenciales de un cliente de comunicaciones unificadas (UC) que se hospede en el grupo de servidores específico.</span><span class="sxs-lookup"><span data-stu-id="f1488-p102">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="f1488-125">Para probar números de acceso para un grupo de servidores específico</span><span class="sxs-lookup"><span data-stu-id="f1488-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="f1488-126">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f1488-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="f1488-127">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f1488-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f1488-128">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="f1488-128">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="f1488-129">El informe resultante indica si hay errores, junto con la información de diagnóstico específica.</span><span class="sxs-lookup"><span data-stu-id="f1488-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="f1488-130">La marca -Verbose proporciona información más detallada sobre cuántos números de acceso se encontraron y detalles sobre ellos.</span><span class="sxs-lookup"><span data-stu-id="f1488-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="f1488-131">Para obtener más información, [vea Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f1488-131">For more information, see [Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
