---
title: Administrar directivas de PIN para conferencias de acceso telefónico local en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Resumen: Aprenda a administrar directivas de PIN para conferencias de acceso telefónico local en Skype empresarial Server.'
ms.openlocfilehash: a8db6fc0398d2f577afe54ab2289c3122adcb197
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280358"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="368e4-103">Administrar directivas de PIN para conferencias de acceso telefónico local en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="368e4-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="368e4-104">**Resumen:** Aprenda a administrar directivas de PIN para conferencias de acceso telefónico local en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="368e4-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="368e4-105">Los usuarios de Skype empresarial Server que tienen credenciales de servicios de dominio de Active Directory (AD DS) en su organización pueden unirse a conferencias de acceso telefónico local como usuarios autenticados mediante un número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="368e4-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="368e4-106">La directiva de PIN define las reglas de funcionamiento de los PIN de conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="368e4-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="368e4-p102">Si desea usar la misma directiva de PIN para toda la organización, puede usar la directiva de PIN global y modificarla según sea necesario. La directiva de PIN global define las reglas de los PIN para conferencias de acceso telefónico local en el nivel de bosque. Puede modificar la directiva de PIN global, pero no se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="368e4-p102">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. The global PIN policy defines the rules for dial-in conferencing PINs at the forest level. You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="368e4-110">Puede crear una nueva directiva de PIN si desea aplicar una directiva específica a un sitio a un grupo de usuarios determinado.</span><span class="sxs-lookup"><span data-stu-id="368e4-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="368e4-111">Las directivas de PIN se aplican a usuarios que van del ámbito más limitado al ámbito más extenso.</span><span class="sxs-lookup"><span data-stu-id="368e4-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="368e4-112">Si asigna una directiva de PIN de usuario a un usuario, esa configuración tendrá preferencia.</span><span class="sxs-lookup"><span data-stu-id="368e4-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="368e4-113">Si no asigna una directiva de usuario, se aplica la directiva de PIN de sitio, si existe.</span><span class="sxs-lookup"><span data-stu-id="368e4-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="368e4-114">Si no se aplica ni la directiva de usuario ni la de sitio, la directiva de PIN global proporcionará la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="368e4-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="368e4-115">Ver información sobre las directivas de PIN</span><span class="sxs-lookup"><span data-stu-id="368e4-115">View information about PIN policies</span></span>

<span data-ttu-id="368e4-116">Puede ver información sobre las directivas de PIN con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="368e4-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="368e4-117">Ver información sobre directivas de PIN con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="368e4-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="368e4-118">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .</span><span class="sxs-lookup"><span data-stu-id="368e4-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="368e4-119">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="368e4-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="368e4-120">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="368e4-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="368e4-121">En la página **Directiva de PIN**, haga clic en la directiva de PIN que desee modificar, haga clic en **Editar** y luego en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="368e4-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="368e4-122">Ver información sobre directivas de PIN mediante el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="368e4-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="368e4-123">Para ver información sobre las directivas de PIN, use el cmdlet **Get-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="368e4-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="368e4-124">Por ejemplo, el siguiente comando devuelve información sobre una sola directiva de PIN con el valor de Identity site:Redmond:</span><span class="sxs-lookup"><span data-stu-id="368e4-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="368e4-125">Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, vea [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="368e4-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="368e4-126">Modificar la directiva de PIN global</span><span class="sxs-lookup"><span data-stu-id="368e4-126">Modify the global PIN policy</span></span>

<span data-ttu-id="368e4-127">Puede modificar la Directiva de PIN global mediante el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="368e4-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="368e4-128">Modificar la Directiva de PIN de conferencias de acceso telefónico local global mediante el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="368e4-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="368e4-129">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .</span><span class="sxs-lookup"><span data-stu-id="368e4-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="368e4-130">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="368e4-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="368e4-131">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="368e4-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="368e4-132">En la página **Directiva de PIN**, haga clic en **Global**, en **Editar** y después en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="368e4-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="368e4-p105">En **Editar directiva de PIN**, en **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que desea permitir. La longitud mínima predeterminada es de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="368e4-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="368e4-p106">Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla   **Especificar número máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="368e4-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="368e4-138">Si ha seleccionado la casilla **Especificar número máximo de intentos de inicio de sesión**, en **Número máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.</span><span class="sxs-lookup"><span data-stu-id="368e4-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="368e4-p107">Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="368e4-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="368e4-142">Si activa la casilla **Habilitar expiración de PIN**, en **El PIN expira tras (días)**, escriba o seleccione el número de días después de los cuales expira el PIN.</span><span class="sxs-lookup"><span data-stu-id="368e4-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="368e4-p108">En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar el PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.</span><span class="sxs-lookup"><span data-stu-id="368e4-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="368e4-p109">Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.</span><span class="sxs-lookup"><span data-stu-id="368e4-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="368e4-148">Por motivos de seguridad, Microsoft recomienda que no se permitan patrones comunes.</span><span class="sxs-lookup"><span data-stu-id="368e4-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="368e4-149">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="368e4-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="368e4-150">Modificar la Directiva de PIN de conferencias de acceso telefónico local global mediante el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="368e4-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="368e4-151">Para modificar la directiva de PIN global de conferencias de acceso telefónico local, use el cmdlet **Set-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="368e4-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="368e4-p110">El siguiente comando cambia el valor de la propiedad MinPasswordLength de todas las directivas de PIN configuradas para su uso en la organización. Para ello, el comando llama primero al cmdlet **Get-CsPinPolicy** sin ningún parámetro, para recuperar una recopilación de todas las directivas de PIN existentes. Después, la recopilación se canaliza al cmdlet **Set-CsPinPolicy**, que modifica el valor de la propiedad MinPasswordLength de todas las directivas de la colección:</span><span class="sxs-lookup"><span data-stu-id="368e4-p110">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization. To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies. That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="368e4-155">Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, consulte [set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="368e4-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="368e4-156">Crear una directiva de PIN de usuario o sitio</span><span class="sxs-lookup"><span data-stu-id="368e4-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="368e4-157">Puede crear una directiva de PIN de sitio o usuario mediante el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="368e4-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="368e4-158">Crear una directiva de PIN de sitio o usuario con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="368e4-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="368e4-159">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .</span><span class="sxs-lookup"><span data-stu-id="368e4-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="368e4-160">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="368e4-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="368e4-161">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="368e4-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="368e4-162">En la página **Directiva de PIN**, haga clic en **Nueva** y, a continuación, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="368e4-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="368e4-p111">Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Nueva directiva de PIN**, en   **Nombre**, escriba un nombre descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="368e4-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="368e4-p112">Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista de sitios, haga clic en el sitio que desee y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="368e4-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="368e4-168">En el campo **Descripción**, escriba una descripción de la directiva de PIN.</span><span class="sxs-lookup"><span data-stu-id="368e4-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="368e4-p113">En el campo **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que desee permitir. La longitud mínima predeterminada es de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="368e4-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="368e4-p114">Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla   **Especificar número máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="368e4-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="368e4-174">Si ha seleccionado la casilla **Especificar número máximo de intentos de inicio de sesión**, en **Número máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.</span><span class="sxs-lookup"><span data-stu-id="368e4-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="368e4-p115">Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="368e4-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="368e4-178">Si activa la casilla **Habilitar expiración de PIN**, en **El PIN expira tras (días)**, escriba o seleccione el número de días después de los cuales expira el PIN.</span><span class="sxs-lookup"><span data-stu-id="368e4-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="368e4-p116">En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar el PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.</span><span class="sxs-lookup"><span data-stu-id="368e4-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="368e4-p117">Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.</span><span class="sxs-lookup"><span data-stu-id="368e4-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="368e4-184">Por motivos de seguridad, Microsoft recomienda que no se permitan patrones comunes.</span><span class="sxs-lookup"><span data-stu-id="368e4-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="368e4-185">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="368e4-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="368e4-186">Crear una directiva de PIN de sitio o usuario con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="368e4-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="368e4-187">Para crear una directiva de PIN de usuario o sitio, use el cmdlet **New-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="368e4-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="368e4-p118">El siguiente comando crea una directiva de PIN con el parámetro Identity site:Redmond. Este comando solo incluye un parámetro opcional, MinPasswordLength, que se usa para establecer la propiedad MinPasswordLength en 7. El resto de propiedades de la directiva se configurarán con los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="368e4-p118">The following command creates a new PIN policy with the Identity site:Redmond. This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7. All the remaining policy properties will be configured using the default values.</span></span>
  
```
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="368e4-191">Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, consulte [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="368e4-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="368e4-192">Modificar una directiva de PIN de usuario o sitio</span><span class="sxs-lookup"><span data-stu-id="368e4-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="368e4-193">Puede modificar una directiva de PIN de sitio o usuario mediante el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="368e4-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="368e4-194">Modificar una directiva de PIN de usuario o de sitio con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="368e4-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="368e4-195">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .</span><span class="sxs-lookup"><span data-stu-id="368e4-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="368e4-196">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="368e4-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="368e4-197">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="368e4-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="368e4-198">En la página **Directiva de PIN**, haga clic en la directiva de PIN que desee modificar, haga clic en **Editar** y después en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="368e4-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="368e4-199">En **Editar directiva de PIN**, modifique cualquier configuración de directivas (salvo el nombre de la directiva, que no se puede modificar).</span><span class="sxs-lookup"><span data-stu-id="368e4-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="368e4-200">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="368e4-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="368e4-201">Modificar una directiva de PIN de usuario o de sitio con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="368e4-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="368e4-202">Para modificar la directiva de PIN de conferencias de acceso telefónico local, use el cmdlet **Set-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="368e4-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="368e4-p119">El siguiente comando modifica la directiva de PIN asignada al sitio de Redmond. En este caso, el comando cambia el valor de la propiedad MinPasswordLength a 10; esto significa que los nuevos PIN necesitan contener al menos 10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="368e4-p119">The following command modifies the PIN policy assigned to the Redmond site. In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="368e4-205">Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, consulte [set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="368e4-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="368e4-206">Eliminar una directiva de PIN de usuario o sitio</span><span class="sxs-lookup"><span data-stu-id="368e4-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="368e4-207">Puede eliminar una directiva de PIN de sitio o usuario mediante el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="368e4-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="368e4-208">Eliminar una directiva de PIN de usuario o de sitio con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="368e4-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="368e4-209">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .</span><span class="sxs-lookup"><span data-stu-id="368e4-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="368e4-210">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="368e4-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="368e4-211">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="368e4-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="368e4-212">En la página **Directiva de PIN**, haga clic en la directiva de PIN que desee modificar, haga clic en **Editar** y después en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="368e4-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="368e4-213">Eliminar una directiva de PIN de usuario o de sitio con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="368e4-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="368e4-214">Para eliminar una directiva de PIN de usuario o sitio, use el cmdlet **Remove-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="368e4-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="368e4-p120">El siguiente comando quita todas las directivas de PIN que se han configurado en el ámbito de sitio. Para ello, use el cmdlet **Get-CsPinPolicy** junto con el parámetro Filter, para devolver una colección con todas las directivas cuyo parámetro Identity comienza por los caracteres "site:". Luego, esta colección se canaliza al cmdlet **Remove-CsPinPolicy**, que elimina las distintas directivas de la colección:</span><span class="sxs-lookup"><span data-stu-id="368e4-p120">The following command removes all the PIN policies that have been configured at the site scope. To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:". This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="368e4-218">Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, consulte [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="368e4-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

