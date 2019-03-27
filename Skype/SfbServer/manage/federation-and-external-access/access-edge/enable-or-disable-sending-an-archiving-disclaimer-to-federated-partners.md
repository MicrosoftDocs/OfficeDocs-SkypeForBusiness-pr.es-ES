---
title: Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 859b4e295a90fd44ce69efe4af7daa63ddc8812c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885322"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="8c607-102">Habilitar o deshabilitar el envío de una renuncia de archivado a los socios federados en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8c607-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="8c607-103">En el momento en que implementan los servidores perimetrales y habilitado la federación para su organización, debe ha especificado si se envían automáticamente la renuncia de archivado a los socios federados.</span><span class="sxs-lookup"><span data-stu-id="8c607-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="8c607-104">Si archiva las comunicaciones externas, debe habilitar el envío de una renuncia de archivado.</span><span class="sxs-lookup"><span data-stu-id="8c607-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="8c607-105">Use el procedimiento de este tema para cambiar dicha configuración.</span><span class="sxs-lookup"><span data-stu-id="8c607-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="8c607-106">El siguiente procedimiento se supone que ya ha habilitado la federación para su organización.</span><span class="sxs-lookup"><span data-stu-id="8c607-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="8c607-107">Para obtener información detallada acerca de cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8c607-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="8c607-108">Para habilitar o deshabilitar el envío de una renuncia de archivado a los socios federados</span><span class="sxs-lookup"><span data-stu-id="8c607-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="8c607-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8c607-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8c607-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8c607-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8c607-111">En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**, haga clic en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="8c607-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="8c607-112">En la ficha **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="8c607-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="8c607-113">En **Editar configuración perimetral de acceso**, en **Habilitar las comunicaciones con los usuarios federados**, active o desactive la casilla de verificación **Enviar declinación de responsabilidades a los socios federados de archivado** para habilitar o deshabilitar el envío automáticamente el archivado declinación de responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="8c607-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="8c607-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8c607-114">Click **Commit**.</span></span>

<span data-ttu-id="8c607-115">Para habilitar los usuarios federados puedan colaborar con los usuarios de su Skype para la implementación de Business Server, debe haber configurado también al menos una directiva de acceso externo para admitir el acceso de usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="8c607-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="8c607-116">Para obtener información detallada acerca de cómo controlar el acceso de dominios federados concretos, vea [Configurar compatibilidad para dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="8c607-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8c607-117">Habilitar o deshabilitar la renuncia de archivado mediante el uso de cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c607-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="8c607-118">El uso de la renuncia de archivado se puede administrar mediante el uso de Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="8c607-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="8c607-119">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c607-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="8c607-120">Para habilitar la renuncia de archivado</span><span class="sxs-lookup"><span data-stu-id="8c607-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="8c607-121">Para habilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="8c607-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="8c607-122">Para deshabilitar la renuncia de archivado</span><span class="sxs-lookup"><span data-stu-id="8c607-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="8c607-123">Para deshabilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="8c607-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


