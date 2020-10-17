---
title: 'Lync Server 2013: configuración de notificaciones de inserción'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f68cafcfcc616bd6e467514704416f134de3665
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517497"
---
# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="39148-102">Configuración de notificaciones de inserción en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39148-102">Configuring for push notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39148-103">_**Última modificación del tema:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="39148-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="39148-104">Las notificaciones de inserción, en la forma de distintivos, iconos o alertas, se pueden enviar a un dispositivo móvil aunque la aplicación móvil se encuentre inactiva.</span><span class="sxs-lookup"><span data-stu-id="39148-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="39148-105">Las notificaciones de inserción notifican a un usuario eventos como correo de voz o invitaciones de mensajería instantánea nuevas o perdidas.</span><span class="sxs-lookup"><span data-stu-id="39148-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="39148-106">El servicio de movilidad de Lync Server 2013 envía las notificaciones al servicio de notificación de inserción de Lync Server basado en la nube que, a continuación, envía las notificaciones al servicio de notificaciones de inserción de Apple (para un dispositivo Apple que ejecuta el cliente móvil de Lync 2010) o a Microsoft Push Notification Service (MPNS) (para un dispositivo de Windows Phone que ejecuta Lync 2013 2010</span><span class="sxs-lookup"><span data-stu-id="39148-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="39148-107">Si usa Windows Phone con Lync 2010 Mobile o Lync 2013 Mobile Client, la notificación de inserción es una consideración importante.</span><span class="sxs-lookup"><span data-stu-id="39148-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="39148-108">Si usa Lync 2010 Mobile en dispositivos Apple, la notificación de inserción es una consideración importante.</span><span class="sxs-lookup"><span data-stu-id="39148-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="39148-109">Si usa Lync 2013 Mobile en dispositivos Apple, ya no necesitará notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="39148-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="39148-110">Configure su topología para admitir las notificaciones de inserción mediante el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="39148-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="39148-111">Si su entorno tiene un servidor perimetral de Lync Server 2010 o Lync Server 2013, debe agregar un nuevo proveedor de hospedaje, Microsoft Lync Online y, a continuación, configurar la Federación del proveedor de hospedaje entre su organización y Lync Online.</span><span class="sxs-lookup"><span data-stu-id="39148-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="39148-112">Si su entorno tiene un servidor perimetral de Office Communications Server 2007 R2, debe configurar la Federación SIP directa con push.lync.com.</span><span class="sxs-lookup"><span data-stu-id="39148-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39148-113">Push.lync.com es un dominio de Microsoft Office 365 para el servicio de notificación de inserción.</span><span class="sxs-lookup"><span data-stu-id="39148-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="39148-114">Para habilitar las notificaciones de inserción, debe ejecutar el cmdlet **Set-CsPushNotificationConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="39148-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="39148-115">De manera predeterminada, las notificaciones de inserción están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="39148-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="39148-116">Pruebe la configuración de federación y las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="39148-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="39148-117">Para configurar notificaciones de inserción con Lync Server 2013 o el servidor perimetral de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="39148-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="39148-118">Inicie sesión en un equipo en el que esté instalado shell de administración de Lync Server y Ocscore como miembro del grupo RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="39148-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="39148-119">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="39148-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="39148-120">Agregue un proveedor de hospedaje de Lync Server online.</span><span class="sxs-lookup"><span data-stu-id="39148-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="39148-121">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39148-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="39148-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39148-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39148-p104">No puede tener más de una relación de federación con un solo proveedor de hospedaje. Es decir, si ya ha configurado un proveedor de hospedaje que tiene una relación de federación con sipfed.online.lync.com, no agregue otro proveedor de hospedaje para él, aunque la identidad del proveedor de hospedaje no sea LyncOnline.</span><span class="sxs-lookup"><span data-stu-id="39148-p104">You cannot have more than one federation relationship with a single hosting provider. That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="39148-p105">Configure la federación del proveedor de hospedaje entre su organización y el servicio de notificación de inserción en Lync Online. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="39148-p105">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online. At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="39148-127">Para configurar notificaciones de inserción con el servidor perimetral de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="39148-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="39148-128">Inicie sesión en el servidor perimetral como miembro del grupo RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="39148-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="39148-129">Haga clic en **Iniciar**, en **Todos los programas**, en **Herramientas administrativas** y, a continuación, en **Administración del equipo**.</span><span class="sxs-lookup"><span data-stu-id="39148-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="39148-130">En el árbol de la consola, expanda **Servicios y aplicaciones**, haga clic con el botón secundario en **Microsoft Office Communications Server 2007 R2** y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="39148-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="39148-131">En la pestaña **Permitir**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="39148-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="39148-132">En el cuadro de diálogo **Agregar socio federado**, realice el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="39148-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="39148-133">En **Nombre de dominio del socio federado**, escriba **push.lync.com**.</span><span class="sxs-lookup"><span data-stu-id="39148-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="39148-134">En **Servidor perimetral de acceso al socio federado**, escriba **sipfed.online.lync.com**.</span><span class="sxs-lookup"><span data-stu-id="39148-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="39148-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39148-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="39148-136">Para habilitar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="39148-136">To enable push notifications</span></span>

1.  <span data-ttu-id="39148-137">Inicie sesión en un equipo en el que se instalen Shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="39148-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="39148-138">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="39148-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="39148-p106">Habilite las notificaciones de inserción. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="39148-p106">Enable push notifications. At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="39148-p107">Habilite la federación. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="39148-p107">Enable federation. At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="39148-143">Para probar la federación y las notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="39148-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="39148-144">Inicie sesión en un equipo en el que se instalen Shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="39148-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="39148-145">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="39148-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="39148-p108">Pruebe la configuración de la federación. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="39148-p108">Test the federation configuration. At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="39148-148">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39148-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="39148-p109">Pruebe las notificaciones de inserción. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="39148-p109">Test push notifications. At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="39148-151">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39148-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="39148-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="39148-152">See Also</span></span>


[<span data-ttu-id="39148-153">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="39148-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="39148-154">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="39148-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

