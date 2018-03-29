---
title: Aplicar una directiva de archivado a los usuarios de Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Resumen: Conozca cómo asignar una directiva de archivado para los usuarios de Skype para Business Server 2015.'
ms.openlocfilehash: fc9811aa57a1ba397dedce325f03ea2d77e4413b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a><span data-ttu-id="1c110-103">Aplicar una directiva de archivado a los usuarios de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c110-103">Apply an archiving policy to users in Skype for Business Server 2015</span></span>

<span data-ttu-id="1c110-104">**Resumen:** Obtenga información acerca de cómo asignar una directiva de archivado para los usuarios de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1c110-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1c110-105">Si ha creado uno o más de las directivas de usuario para el archivado de los usuarios alojados en Skype para Business Server 2015, puede implementar soporte de archiving para usuarios específicos mediante la aplicación de las políticas adecuadas para los usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="1c110-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server 2015, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="1c110-106">Por ejemplo, si crea una directiva para admitir el archivado de comunicaciones internas, puede aplicarlo al menos un usuario o grupo de usuarios para soportar archiving de Skype del usuario para las comunicaciones de negocios servidor 2015.</span><span class="sxs-lookup"><span data-stu-id="1c110-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server 2015 communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c110-107">Si habilita la integración de Microsoft Exchange para la implementación de Exchange en el mismo lugar mantenga control de directivas si el archivado está habilitado para los usuarios que están alojados en Exchange y han puesto a sus buzones en mantener en el lugar.</span><span class="sxs-lookup"><span data-stu-id="1c110-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="1c110-108">Para obtener más información, vea [planear para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md) y [Configurar la integración con almacenamiento de información de Exchange para Skype para Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="1c110-108">For details, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="1c110-109">Aplicar una directiva de usuario con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="1c110-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="1c110-110">Para aplicar una directiva de usuario con el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="1c110-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="1c110-111">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1c110-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="1c110-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="1c110-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="1c110-113">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="1c110-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="1c110-114">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="1c110-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1c110-115">En **Editar usuario de Lync Server** , bajo **Directiva de archivado**, seleccione la directiva de usuario de archivado que desee aplicar.</span><span class="sxs-lookup"><span data-stu-id="1c110-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1c110-116">La ** \<automática\> ** configuración aplica la configuración predeterminada de instalación del servidor.</span><span class="sxs-lookup"><span data-stu-id="1c110-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="1c110-117">El servidor aplica esta configuración automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1c110-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="1c110-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1c110-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="1c110-119">Aplicar una directiva de usuario mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c110-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="1c110-120">También puede aplicar una directiva de usuario mediante el cmdlet de Windows PowerShell **Grant CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="1c110-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1c110-121">El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="1c110-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="1c110-122">Este comando asigna el usuario por directiva RedmondArchivingPolicy a todos los usuarios de archivado que hayan cuentas alojados en el grupo registrador atl-cs-001.contoso.com. Para obtener más información acerca del parámetro de filtro utilizado en este comando, consulte la documentación del cmdlet [Get-Csusuario](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="1c110-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com. For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

```

<span data-ttu-id="1c110-p104">El siguiente comando quita cualquier directiva de archivado por usuario previamente asignada a Ken Myer. Una vez quitada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado con la directiva global (o, de existir, por la directiva de su sitio local). Las directivas de sitio tienen prioridad sobre las directivas globales.</span><span class="sxs-lookup"><span data-stu-id="1c110-p104">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="1c110-126">Para obtener más información, consulte la documentación de cmdlet de [Concesión CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="1c110-126">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

