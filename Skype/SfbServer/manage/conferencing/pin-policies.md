---
title: Administrar directivas de PIN para conferencias de acceso telefónico local en Skype Empresarial Server
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
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Resumen: obtenga información sobre cómo administrar directivas de PIN para conferencias de acceso telefónico local en Skype Empresarial Server.'
ms.openlocfilehash: 34b006b54242c25fb9afcd3fc9fd6e6692e9cbd2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096756"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="89efb-103">Administrar directivas de PIN para conferencias de acceso telefónico local en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="89efb-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="89efb-104">**Resumen:** Obtenga información sobre cómo administrar directivas de PIN para conferencias de acceso telefónico local en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="89efb-105">Los usuarios de Skype Empresarial Server que tienen credenciales de Servicios de dominio de Active Directory (AD DS) en su organización pueden unirse a conferencias de acceso telefónico local como usuarios autenticados mediante un número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="89efb-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="89efb-106">La directiva de PIN define las reglas de funcionamiento de los PIN de conferencias de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="89efb-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="89efb-107">Si desea usar la misma directiva de PIN para toda la organización, puede usar la directiva de PIN global y modificarla según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="89efb-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="89efb-108">La directiva de PIN global define las reglas de los números de identificación personal para conferencias de acceso telefónico en el nivel de bosque.</span><span class="sxs-lookup"><span data-stu-id="89efb-108">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="89efb-109">Puede modificar la directiva de PIN global, pero no puede eliminarla.</span><span class="sxs-lookup"><span data-stu-id="89efb-109">You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="89efb-110">Puede crear una nueva directiva de PIN si desea aplicar una directiva específica a un sitio a un grupo de usuarios determinado.</span><span class="sxs-lookup"><span data-stu-id="89efb-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="89efb-111">Las directivas de PIN se aplican a usuarios que van del ámbito más limitado al ámbito más extenso.</span><span class="sxs-lookup"><span data-stu-id="89efb-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="89efb-112">Si asigna una directiva de PIN de usuario a un usuario, dicha configuración tendrá preferencia.</span><span class="sxs-lookup"><span data-stu-id="89efb-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="89efb-113">Si no asigna una directiva de usuario, se aplica la directiva de PIN de sitio, si existe.</span><span class="sxs-lookup"><span data-stu-id="89efb-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="89efb-114">Si no se aplica ni la directiva de usuario ni la de sitio, la directiva de PIN global proporcionará la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="89efb-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="89efb-115">Ver información sobre directivas de PIN</span><span class="sxs-lookup"><span data-stu-id="89efb-115">View information about PIN policies</span></span>

<span data-ttu-id="89efb-116">Puede ver información sobre las directivas de PIN mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="89efb-117">Ver información sobre directivas de PIN mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="89efb-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="89efb-118">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="89efb-119">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="89efb-120">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="89efb-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="89efb-121">En la **página Directiva de PIN,** haga clic en la directiva de PIN que desea ver, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles.**</span><span class="sxs-lookup"><span data-stu-id="89efb-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="89efb-122">Ver información sobre directivas de PIN mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="89efb-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="89efb-123">Para ver información sobre las directivas de PIN, use el cmdlet **Get-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="89efb-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="89efb-124">Por ejemplo, el siguiente comando devuelve información sobre una única directiva de PIN con el objeto Identity site:Redmond:</span><span class="sxs-lookup"><span data-stu-id="89efb-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="89efb-125">Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, [vea Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89efb-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="89efb-126">Modificar la directiva global de PIN</span><span class="sxs-lookup"><span data-stu-id="89efb-126">Modify the global PIN policy</span></span>

<span data-ttu-id="89efb-127">Puede modificar la directiva global de PIN mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="89efb-128">Modificar la directiva de PIN de conferencia de acceso telefónico local global mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="89efb-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="89efb-129">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="89efb-130">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="89efb-131">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="89efb-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="89efb-132">En la página **Directiva de PIN**, haga clic en **Global**, en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="89efb-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="89efb-p105">En **Editar directiva de PIN**, en **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que se va a admitir. La longitud mínima predeterminada es de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="89efb-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="89efb-p106">Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla **Especificar máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="89efb-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="89efb-138">Si activa la casilla **Especificar máximo de intentos de inicio de sesión** en **Máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.</span><span class="sxs-lookup"><span data-stu-id="89efb-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="89efb-p107">Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="89efb-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="89efb-142">Si activa la casilla **Habilitar expiración de PIN**, en **el PIN expira después de (días)**; escriba o seleccione el número de días después de los cuales expira el PIN.</span><span class="sxs-lookup"><span data-stu-id="89efb-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="89efb-p108">En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar el PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.</span><span class="sxs-lookup"><span data-stu-id="89efb-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="89efb-p109">Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla de verificación **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.</span><span class="sxs-lookup"><span data-stu-id="89efb-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="89efb-148">Por motivos de seguridad, Microsoft recomienda no permitir patrones comunes.</span><span class="sxs-lookup"><span data-stu-id="89efb-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="89efb-149">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="89efb-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="89efb-150">Modificar la directiva de PIN de conferencia de acceso telefónico local global mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="89efb-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="89efb-151">Para modificar la directiva de PIN de conferencia de acceso telefónico local global, use el cmdlet **Set-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="89efb-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="89efb-152">El siguiente comando cambia el valor de MinPasswordLength para todas las directivas de PIN configuradas para su uso en la organización.</span><span class="sxs-lookup"><span data-stu-id="89efb-152">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization.</span></span> <span data-ttu-id="89efb-153">Para ello, el comando primero llama al cmdlet **Get-CsPinPolicy** sin ningún parámetro para recuperar una colección de todas las directivas de PIN existentes.</span><span class="sxs-lookup"><span data-stu-id="89efb-153">To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies.</span></span> <span data-ttu-id="89efb-154">A continuación, esa colección se canalizó al cmdlet **Set-CsPinPolicy,** que modifica el valor de la propiedad MinPasswordLength para cada directiva de la colección:</span><span class="sxs-lookup"><span data-stu-id="89efb-154">That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="89efb-155">Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, vea [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89efb-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="89efb-156">Crear una directiva de PIN de usuario o sitio</span><span class="sxs-lookup"><span data-stu-id="89efb-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="89efb-157">Puede crear una directiva de PIN de usuario o sitio mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="89efb-158">Crear una directiva de PIN de usuario o sitio mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="89efb-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="89efb-159">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="89efb-160">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="89efb-161">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="89efb-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="89efb-162">En la página **Directiva de PIN**, haga clic en **Nueva** y, a continuación, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="89efb-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="89efb-p111">Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Nueva directiva de PIN**, en **Nombre**, escriba un nombre descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="89efb-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="89efb-p112">Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista de sitios, haga clic en el sitio que desee y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="89efb-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="89efb-168">En el campo **Descripción**, escriba una descripción de la directiva de PIN.</span><span class="sxs-lookup"><span data-stu-id="89efb-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="89efb-p113">En el campo **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que se va a admitir. La longitud mínima predeterminada es de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="89efb-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="89efb-p114">Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla **Especificar máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="89efb-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="89efb-174">Si activa la casilla **Especificar máximo de intentos de inicio de sesión** en **Máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.</span><span class="sxs-lookup"><span data-stu-id="89efb-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="89efb-p115">Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="89efb-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="89efb-178">Si activa la casilla **Habilitar expiración de PIN**, en **el PIN expira después de (días)**; escriba o seleccione el número de días después de los cuales expira el PIN.</span><span class="sxs-lookup"><span data-stu-id="89efb-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="89efb-p116">En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar el PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.</span><span class="sxs-lookup"><span data-stu-id="89efb-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="89efb-p117">Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla de verificación **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.</span><span class="sxs-lookup"><span data-stu-id="89efb-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="89efb-184">Por motivos de seguridad, Microsoft recomienda no permitir patrones comunes.</span><span class="sxs-lookup"><span data-stu-id="89efb-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="89efb-185">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="89efb-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="89efb-186">Crear una directiva de PIN de usuario o sitio mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="89efb-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="89efb-187">Para crear una directiva de PIN de usuario o sitio, use el cmdlet **New-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="89efb-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="89efb-188">El siguiente comando crea una nueva directiva de PIN con identity site:Redmond.</span><span class="sxs-lookup"><span data-stu-id="89efb-188">The following command creates a new PIN policy with the Identity site:Redmond.</span></span> <span data-ttu-id="89efb-189">Este comando incluye solo un parámetro opcional, MinPasswordLength, que se usa para establecer la propiedad MinPasswordLength en 7.</span><span class="sxs-lookup"><span data-stu-id="89efb-189">This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7.</span></span> <span data-ttu-id="89efb-190">El resto de propiedades de directiva se configurarán con los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="89efb-190">All the remaining policy properties will be configured using the default values.</span></span>
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="89efb-191">Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, [vea New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89efb-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="89efb-192">Modificar una directiva de PIN de usuario o sitio</span><span class="sxs-lookup"><span data-stu-id="89efb-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="89efb-193">Puede modificar una directiva de PIN de usuario o sitio mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="89efb-194">Modificar una directiva de PIN de usuario o sitio mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="89efb-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="89efb-195">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="89efb-196">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="89efb-197">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="89efb-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="89efb-198">En la página **Directiva de PIN**, haga clic en la directiva de PIN que desee modificar, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="89efb-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="89efb-199">En **Editar directiva de PIN**, modifique cualquier configuración de directivas (salvo el nombre de la directiva, que no se puede modificar).</span><span class="sxs-lookup"><span data-stu-id="89efb-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="89efb-200">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="89efb-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="89efb-201">Modificar una directiva de PIN de usuario o sitio mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="89efb-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="89efb-202">Para modificar la directiva de PIN de conferencia de acceso telefónico local, use el cmdlet **Set-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="89efb-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="89efb-203">El siguiente comando modifica la directiva de PIN asignada al sitio Redmond.</span><span class="sxs-lookup"><span data-stu-id="89efb-203">The following command modifies the PIN policy assigned to the Redmond site.</span></span> <span data-ttu-id="89efb-204">En este caso, el comando cambia el valor de la propiedad MinPasswordLength a 10; esto significa que los nuevos PIN tendrán que contener al menos 10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="89efb-204">In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="89efb-205">Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, vea [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89efb-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="89efb-206">Eliminar una directiva de PIN de usuario o sitio</span><span class="sxs-lookup"><span data-stu-id="89efb-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="89efb-207">Puede eliminar una directiva de PIN de usuario o sitio mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="89efb-208">Eliminar una directiva de PIN de usuario o sitio mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="89efb-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="89efb-209">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="89efb-210">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="89efb-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="89efb-211">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="89efb-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="89efb-212">En la **página Directiva de PIN,** haga clic en la directiva de PIN que desea cambiar, haga clic **en Editar** y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="89efb-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="89efb-213">Eliminar una directiva de PIN de usuario o sitio mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="89efb-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="89efb-214">Para eliminar una directiva de PIN de usuario o sitio, use el cmdlet **Remove-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="89efb-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="89efb-215">El siguiente comando quita todas las directivas de PIN que se han configurado en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="89efb-215">The following command removes all the PIN policies that have been configured at the site scope.</span></span> <span data-ttu-id="89efb-216">Para ello, use el cmdlet **Get-CsPinPolicy,** junto con el parámetro Filter, para devolver una colección de todas las directivas que tienen una identidad que comienza con los caracteres "site:".</span><span class="sxs-lookup"><span data-stu-id="89efb-216">To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:".</span></span> <span data-ttu-id="89efb-217">A continuación, esta colección se canalizó al cmdlet **Remove-CsPinPolicy,** que elimina cada directiva de la colección:</span><span class="sxs-lookup"><span data-stu-id="89efb-217">This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="89efb-218">Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, [vea Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89efb-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
