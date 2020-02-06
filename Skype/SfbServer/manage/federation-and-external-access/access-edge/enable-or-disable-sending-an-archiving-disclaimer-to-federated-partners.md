---
title: Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 889716377f89e2657adcd6e32c9077b8124e20c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818361"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="07926-102">Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="07926-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="07926-103">En el momento de implementar los servidores perimetrales y habilitar la Federación de su organización, debe haber especificado si se enviará automáticamente la renuncia de archivado a los socios federados.</span><span class="sxs-lookup"><span data-stu-id="07926-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="07926-104">Si archiva las comunicaciones externas, debe habilitar el envío de una renuncia de archivado.</span><span class="sxs-lookup"><span data-stu-id="07926-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="07926-105">Use el procedimiento de este tema para cambiar esa configuración.</span><span class="sxs-lookup"><span data-stu-id="07926-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="07926-106">En el procedimiento siguiente se supone que ya ha habilitado la Federación de su organización.</span><span class="sxs-lookup"><span data-stu-id="07926-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="07926-107">Para obtener más información sobre cómo habilitar la Federación, consulte [habilitar o deshabilitar el acceso de usuarios remotos](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="07926-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="07926-108">Para habilitar o deshabilitar el envío de una renuncia de archivado a socios federados</span><span class="sxs-lookup"><span data-stu-id="07926-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="07926-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="07926-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07926-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="07926-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="07926-111">En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**, haga clic en **configuración del borde de Access**.</span><span class="sxs-lookup"><span data-stu-id="07926-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="07926-112">En la ficha **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="07926-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="07926-113">En **Editar configuración del límite de acceso**, en **Habilitar la comunicación con usuarios federados**, Active o desactive la casilla **Enviar renuncia de archivado a socios federados** para habilitar o deshabilitar el envío automático de la renuncia de archivado.</span><span class="sxs-lookup"><span data-stu-id="07926-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="07926-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="07926-114">Click **Commit**.</span></span>

<span data-ttu-id="07926-115">Para permitir a los usuarios federados colaborar con los usuarios de su implementación de Skype empresarial Server, también debe haber configurado al menos una directiva de acceso externa para admitir el acceso de usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="07926-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="07926-116">Para obtener más información sobre cómo controlar el acceso a dominios federados específicos, consulte [configurar la compatibilidad de dominios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="07926-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="07926-117">Habilitar o deshabilitar la renuncia de archivado mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="07926-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="07926-118">El uso de la renuncia de archivado se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="07926-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="07926-119">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07926-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="07926-120">Para habilitar la renuncia de archivado</span><span class="sxs-lookup"><span data-stu-id="07926-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="07926-121">Para habilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="07926-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="07926-122">Para deshabilitar la renuncia de archivado</span><span class="sxs-lookup"><span data-stu-id="07926-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="07926-123">Para deshabilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="07926-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


