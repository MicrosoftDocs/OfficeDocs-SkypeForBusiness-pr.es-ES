---
title: Crear una nueva Directiva de PIN en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 'Resumen: cree una nueva Directiva de PIN en Skype empresarial Server.'
ms.openlocfilehash: 46464962ea53d81978f0d345d63e380a677b152f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818812"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="a3358-103">Crear una nueva Directiva de PIN en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a3358-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="a3358-104">**Resumen:** Crear una nueva Directiva de PIN en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a3358-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="a3358-105">Puede usar la página **Directiva de PIN** para proporcionar autenticación de número de identificación personal (PIN) a los usuarios que se conectan a Skype empresarial con teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="a3358-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="a3358-106">Para usar la autenticación de PIN, asegúrese de que la opción **Habilitar autenticación de PIN** esté seleccionada en la configuración del servicio web.</span><span class="sxs-lookup"><span data-stu-id="a3358-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="a3358-107">Siga estos pasos para crear una directiva de PIN de nivel de usuario o de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="a3358-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="a3358-108">Para crear una directiva de PIN de usuario o sitio</span><span class="sxs-lookup"><span data-stu-id="a3358-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="a3358-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .</span><span class="sxs-lookup"><span data-stu-id="a3358-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a3358-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a3358-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a3358-111">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="a3358-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="a3358-112">En la página **Directiva de PIN**, haga clic en **Nueva** y, a continuación, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3358-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="a3358-p102">Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Nueva directiva de PIN**, en   **Nombre**, escriba un nombre descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="a3358-p102">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="a3358-p103">Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista resultante de sitios, haga clic en el sitio de su interés y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3358-p103">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="a3358-118">En el campo **Descripción**, escriba una descripción de la directiva de PIN.</span><span class="sxs-lookup"><span data-stu-id="a3358-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="a3358-p104">En el campo **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que desee permitir. La longitud mínima predeterminada es de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="a3358-p104">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="a3358-p105">Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla   **Especificar número máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a3358-p105">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="a3358-124">Si ha seleccionado la casilla **Especificar número máximo de intentos de inicio de sesión**, en **Número máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.</span><span class="sxs-lookup"><span data-stu-id="a3358-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="a3358-p106">Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="a3358-p106">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="a3358-128">Si activa la casilla **Habilitar expiración de PIN**, en **El PIN expira tras (días)**, escriba o seleccione el número de días después de los cuales expira el PIN.</span><span class="sxs-lookup"><span data-stu-id="a3358-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="a3358-p107">En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar un PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.</span><span class="sxs-lookup"><span data-stu-id="a3358-p107">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="a3358-p108">Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, "1234" y "8888", active la casilla **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.</span><span class="sxs-lookup"><span data-stu-id="a3358-p108">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a3358-134">Se recomienda no permitir patrones comunes.</span><span class="sxs-lookup"><span data-stu-id="a3358-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="a3358-135">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a3358-135">Click **Commit**.</span></span>
    

