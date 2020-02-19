---
title: 'Lync Server 2013: usar el portal web administrativo del sistema Lync Room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 759cae91575d3244d6860c6ec76fa664994d493e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="e6062-102">Usar el portal web administrativo del sistema Lync Room en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6062-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6062-103">_**Última modificación del tema:** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="e6062-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="e6062-104">Después de implementar LRS en el servidor, puede comprobar el estado de todos los salones LRS iniciando sesión en el portal web administrativo de LRS desde un explorador.</span><span class="sxs-lookup"><span data-stu-id="e6062-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="e6062-105">Iniciar sesión</span><span class="sxs-lookup"><span data-stu-id="e6062-105">Sign in</span></span>

1.  <span data-ttu-id="e6062-106">Vaya a la siguiente dirección URL:</span><span class="sxs-lookup"><span data-stu-id="e6062-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="e6062-107">https://\<fe-servidor\>/LRS</span><span class="sxs-lookup"><span data-stu-id="e6062-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="e6062-108">Escriba las credenciales de la cuenta LRSSupport o de una cuenta que se haya agregado al grupo de seguridad LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="e6062-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="e6062-109">![Pantalla de inicio de sesión del portal de administración del sistema Lync Room](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Pantalla de inicio de sesión del portal de administración del sistema Lync Room")</span><span class="sxs-lookup"><span data-stu-id="e6062-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="e6062-110">Página de resumen del portal web administrativo LRS</span><span class="sxs-lookup"><span data-stu-id="e6062-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="e6062-111">La página de Resumen proporciona la siguiente información para todos los salones de LRS implementados en el servidor:</span><span class="sxs-lookup"><span data-stu-id="e6062-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="e6062-112">**Etiquete**   el nombre personalizado que el administrador da al salón.</span><span class="sxs-lookup"><span data-stu-id="e6062-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="e6062-113">La etiqueta se puede establecer en el portal haciendo clic en el nombre del salón.</span><span class="sxs-lookup"><span data-stu-id="e6062-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="e6062-114">**Mantenimiento**   el estado de mantenimiento de la sala, que se deriva del estado de mantenimiento agregado de la sala, que se muestra en la sección estado de la página Configuración de la sala.</span><span class="sxs-lookup"><span data-stu-id="e6062-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="e6062-115">**Siguiente reunión**   la fecha y hora en que se programó la próxima reunión.</span><span class="sxs-lookup"><span data-stu-id="e6062-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="e6062-116">**Versión LRS, fabricante, modelo**   estos valores están preestablecidos en LRS.</span><span class="sxs-lookup"><span data-stu-id="e6062-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="e6062-117">Según el fabricante, estos campos podrían dejarse en blanco.</span><span class="sxs-lookup"><span data-stu-id="e6062-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="e6062-118">**Última actualización**   muestra la última vez que se actualizó la Página Web.</span><span class="sxs-lookup"><span data-stu-id="e6062-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="e6062-119">![Vista de resumen del portal de administración del sistema Lync Room](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Vista de resumen del portal de administración del sistema Lync Room")</span><span class="sxs-lookup"><span data-stu-id="e6062-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="e6062-120">Información de salón de LRS</span><span class="sxs-lookup"><span data-stu-id="e6062-120">LRS Room Information</span></span>

<span data-ttu-id="e6062-121">La sección de información de la sala del portal permite ver y configurar salones de LRS individuales.</span><span class="sxs-lookup"><span data-stu-id="e6062-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="e6062-122">Contiene cuatro secciones: configuración, detalles, solución de problemas y mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="e6062-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="e6062-123">Configuración</span><span class="sxs-lookup"><span data-stu-id="e6062-123">Settings</span></span>

<span data-ttu-id="e6062-124">En la sección configuración, puede establecer la contraseña, la etiqueta de salón y los niveles de volumen predeterminados para el salón.</span><span class="sxs-lookup"><span data-stu-id="e6062-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="e6062-125">Si configura estas opciones, los cambios solo se replican después de reiniciar la consola LRS.</span><span class="sxs-lookup"><span data-stu-id="e6062-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="e6062-126">Solo verá la configuración de actualizaciones del sistema para sistemas de salas de Lync que sean la versión 15,12 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="e6062-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="e6062-127">![Configuración del salón del portal de administración del sistema de Lync Room](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Configuración del salón del portal de administración del sistema de Lync Room")</span><span class="sxs-lookup"><span data-stu-id="e6062-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="e6062-128">Detalles</span><span class="sxs-lookup"><span data-stu-id="e6062-128">Details</span></span>

<span data-ttu-id="e6062-129">La sección de detalles proporciona un resumen de solo lectura de la configuración de la sala LRS, que incluye: la hora de la última actualización; próxima reunión; últimas actualizaciones, mantenimiento y calibración; configuración predeterminada de altavoces, micrófono y timbre; versi URI DE SIP; número de pantallas y detalles de cada pantalla; Estado y actividad.</span><span class="sxs-lookup"><span data-stu-id="e6062-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="e6062-130">![Vista detallada del portal de administración del sistema Lync Room](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Vista detallada del portal de administración del sistema Lync Room")</span><span class="sxs-lookup"><span data-stu-id="e6062-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="e6062-131">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="e6062-131">Troubleshooting</span></span>

<span data-ttu-id="e6062-132">La sección de solución de problemas se puede usar para recopilar registros de forma remota y guardarlos en una ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="e6062-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="e6062-133">También puede reiniciar la consola LRS (interfaz de usuario LRS) o reiniciar todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="e6062-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="e6062-134">Para recopilar registros, especifique una ruta de acceso a la carpeta en el formato especificado y asegúrese de que la carpeta tiene permisos de escritura en la cuenta del equipo LRS.</span><span class="sxs-lookup"><span data-stu-id="e6062-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="e6062-135">Si el tamaño del registro es demasiado grande, puede tardar hasta 5 minutos en finalizar la recopilación de registros.</span><span class="sxs-lookup"><span data-stu-id="e6062-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="e6062-136">La actualización de la página le dará el estado más reciente.</span><span class="sxs-lookup"><span data-stu-id="e6062-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="e6062-137">![Registro del salón del portal de administración del sistema Lync Room](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Registro del salón del portal de administración del sistema Lync Room")</span><span class="sxs-lookup"><span data-stu-id="e6062-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="e6062-138">Salud</span><span class="sxs-lookup"><span data-stu-id="e6062-138">Health</span></span>

<span data-ttu-id="e6062-139">La sección estado ofrece una indicación visual del estado de la conexión de Lync Server, el dispositivo de audio, el dispositivo de vídeo, el estado de resistencia y el dispositivo de pantalla.</span><span class="sxs-lookup"><span data-stu-id="e6062-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="e6062-140">![Portal de administración del sistema Lync Room Health Room](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Portal de administración del sistema Lync Room Health Room")</span><span class="sxs-lookup"><span data-stu-id="e6062-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="e6062-141">Notas adicionales sobre el portal web administrativo</span><span class="sxs-lookup"><span data-stu-id="e6062-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="e6062-142">Los cambios de configuración solo se aplican después de reiniciar el sistema LRS.</span><span class="sxs-lookup"><span data-stu-id="e6062-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="e6062-143">Si la contraseña de la cuenta LRSApp expira, no podrá ver el estado de las salas.</span><span class="sxs-lookup"><span data-stu-id="e6062-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="e6062-144">Configure la contraseña de la cuenta LRSAppuser para que nunca expire o asegúrese de actualizar la contraseña cuando esté próximo a expirar.</span><span class="sxs-lookup"><span data-stu-id="e6062-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="e6062-145">El portal web administrativo LRS solo es compatible con las implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="e6062-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="e6062-146">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="e6062-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="e6062-147">¿Por qué no puedo iniciar sesión en el portal web administrativo?</span><span class="sxs-lookup"><span data-stu-id="e6062-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="e6062-148">Al abrir https://localhost/lrs, podrás ver la página de inicio de sesión, pero, cuando escribas tus credenciales, no podrás iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="e6062-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="e6062-149">En este caso, debe abrir https://FQDNofFEserver/lrs para iniciar sesión en el portal web administrativo.</span><span class="sxs-lookup"><span data-stu-id="e6062-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="e6062-150">Si el equipo desde el que tiene acceso al portal web administrativo se encuentra en un grupo de trabajo, "http://" no funcionará.</span><span class="sxs-lookup"><span data-stu-id="e6062-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="e6062-151">Use "https" en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e6062-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="e6062-152">¿Por qué no puedo ver LRS en el portal web administrativo?</span><span class="sxs-lookup"><span data-stu-id="e6062-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="e6062-153">Asegúrese de que tiene cuentas LRS en su implementación y que se crean de acuerdo con las recomendaciones de implementación del portal web administrativo LRS.</span><span class="sxs-lookup"><span data-stu-id="e6062-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="e6062-154">Asegúrese de que las cuentas LRS se aprovisionan mediante enable-CsMeetingRoom, no enable-CsUser, en el servidor de Lync.</span><span class="sxs-lookup"><span data-stu-id="e6062-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="e6062-155">Si ha creado cuentas LRS y no puede ver las cuentas en el portal web administrativo, recopile los registros del servidor mediante la herramienta de registro de Lync Server con el componente **MeetingPortal** seleccionado y, a continuación, envíelos al contacto de soporte de LRS.</span><span class="sxs-lookup"><span data-stu-id="e6062-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="e6062-156">¿Por qué no puedo ver el estado de LRS en el portal web administrativo?</span><span class="sxs-lookup"><span data-stu-id="e6062-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="e6062-157">Asegúrese de que la cuenta de usuario de LRSApp esté habilitada para SIP.</span><span class="sxs-lookup"><span data-stu-id="e6062-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="e6062-158">Si sigue teniendo problemas, recopile el archivo **Trace. log** en el sistema LRS de D:\\Tracing\\LRSAdminLogs\\y, a continuación, envíelo al contacto de soporte LRS.</span><span class="sxs-lookup"><span data-stu-id="e6062-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

