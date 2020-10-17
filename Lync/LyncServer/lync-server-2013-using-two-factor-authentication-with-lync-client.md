---
title: 'Lync Server 2013: usar la autenticación en dos fases con el cliente de Lync'
description: 'Lync Server 2013: usar la autenticación en dos fases con el cliente de Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbfde1d04d4e641c8fbe4817ffce214df891b565
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547286"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="8a5b3-103">Uso de la autenticación en dos fases con Lync Client y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a5b3-103">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a5b3-104">_**Última modificación del tema:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="8a5b3-104">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="8a5b3-105">En este tema se describió cómo aprovechar la autenticación en dos fases con el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-105">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="8a5b3-106">Iniciar sesión en Lync 2013 por primera vez</span><span class="sxs-lookup"><span data-stu-id="8a5b3-106">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="8a5b3-107">La información de inicio de sesión de Lync suele configurarse automáticamente cuando Lync 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-107">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="8a5b3-108">Pero la primera vez que use Lync, es posible que deba iniciar manualmente el cliente.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-108">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="8a5b3-109">**Para iniciar sesión en Lync por primera vez**</span><span class="sxs-lookup"><span data-stu-id="8a5b3-109">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="8a5b3-110">Inicie sesión en la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-110">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="8a5b3-111">Seleccione **iniciar** \> **todos los programas** \> **Microsoft Lync \> Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-111">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="8a5b3-112">Debería ver la pantalla de inicio de sesión de Lync.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-112">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="8a5b3-113">Si el cuadro Dirección de inicio de sesión ya está rellenado, confirme que la dirección mostrada es correcta.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-113">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="8a5b3-114">Si no es correcta o si el cuadro está vacío, escriba su dirección de inicio de sesión de Lync (normalmente es la misma que su dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="8a5b3-114">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="8a5b3-115">Si se muestra un cuadro de contraseña vacío, agregue su contraseña.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-115">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="8a5b3-116">Seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-116">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="8a5b3-117">Cerrar sesión en Lync</span><span class="sxs-lookup"><span data-stu-id="8a5b3-117">Sign out of Lync</span></span>

<span data-ttu-id="8a5b3-118">Cuando haya terminado de usar Lync, podrá cerrar la pantalla, cerrar la sesión de la sesión o salir del programa, todo desde el menú archivo.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-118">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="8a5b3-119">En la tabla siguiente se explican las diferencias de las opciones.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-119">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a5b3-120">Opción</span><span class="sxs-lookup"><span data-stu-id="8a5b3-120">Option</span></span></th>
<th><span data-ttu-id="8a5b3-121">Lo que hace</span><span class="sxs-lookup"><span data-stu-id="8a5b3-121">What it does</span></span></th>
<th><span data-ttu-id="8a5b3-122">Cómo realizarlo</span><span class="sxs-lookup"><span data-stu-id="8a5b3-122">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a5b3-123">Cerrar</span><span class="sxs-lookup"><span data-stu-id="8a5b3-123">Close</span></span></p></td>
<td><p><span data-ttu-id="8a5b3-124">Cierra la presentación de Lync, pero permite que la sesión de Lync identificada con su identificador de usuario continúe ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-124">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="8a5b3-125">Esto es así para que pueda seguir recibiendo notificaciones e interactuar con otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-125">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="8a5b3-126">Puede volver a mostrar la presentación en cualquier momento haciendo clic en el icono de Lync de la barra de tareas o en el área de notificación en la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-126">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="8a5b3-127">En la ventana principal de Lync, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8a5b3-127">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8a5b3-128">Seleccione el botón <strong>Opciones</strong> y, después, haga clic en <strong>File</strong> &gt; <strong>cerrar</strong>archivo.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-128">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="8a5b3-129">Haga clic en el botón Cerrar (X) que se <strong>incluye</strong> en la esquina superior derecha de la ventana.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-129">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a5b3-130">Cerrar sesión</span><span class="sxs-lookup"><span data-stu-id="8a5b3-130">Sign out</span></span></p></td>
<td><p><span data-ttu-id="8a5b3-131">Finaliza la sesión de Lync asociada con el identificador de usuario, pero Lync sigue ejecutándose en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-131">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="8a5b3-132">Cuando cierre sesión, aparecerá la ventana de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-132">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="8a5b3-133">Seleccione <STRONG>eliminar mi información</STRONG> de inicio de sesión al cerrar la sesión para quitar el registro del identificador de inicio de sesión y la contraseña del equipo.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-133">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="8a5b3-134">Al hacerlo, es posible que sea más fácil para los usuarios de soporte técnico solucionar problemas de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-134">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="8a5b3-135">También puede ayudar a garantizar que la información de inicio de sesión sea más segura, lo que dificulta que los usuarios no autorizados inicien sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-135">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="8a5b3-136">En la ventana principal de Lync, seleccione el botón <strong>Opciones</strong> y, después, seleccione <strong>File</strong> &gt; <strong>Cerrar sesión</strong>en el archivo.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-136">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a5b3-137">Salir</span><span class="sxs-lookup"><span data-stu-id="8a5b3-137">Exit</span></span></p></td>
<td><p><span data-ttu-id="8a5b3-138">Finaliza la sesión de Lync y cierra Lync en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-138">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="8a5b3-139">Después de salir, si quiere reiniciar Lync, seleccione <strong>iniciar</strong> &gt; <strong>todos los programas</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-139">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8a5b3-140">En la ventana principal de Lync, seleccione el botón <strong>Opciones</strong> y, a continuación, seleccione salida de <strong>archivo</strong> &gt; <strong>Exit</strong>.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-140">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="8a5b3-141">Iniciar sesión en Lync con una tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="8a5b3-141">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="8a5b3-142">Algunas organizaciones ahora usan un proceso de inicio de sesión de varios pasos, denominado autenticación en dos fases, para aumentar la seguridad de los usuarios de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-142">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="8a5b3-143">Si tiene previsto usar esta opción, necesitará una "tarjeta inteligente" para iniciar sesión en Lync.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-143">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="8a5b3-144">Las tarjetas inteligentes vienen en dos variedades, físicas y virtuales:</span><span class="sxs-lookup"><span data-stu-id="8a5b3-144">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="8a5b3-145">**Física**     Sobre el tamaño de una tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-145">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="8a5b3-146">Insértelo en un lector de tarjetas inteligentes cuando inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-146">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="8a5b3-147">**Virtual**     No es un objeto físico, sino un identificador electrónico que se escribe en un chip especial del equipo, que, en esencia, crea la tarjeta inteligente en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-147">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="8a5b3-148">Disponible solo para usar con equipos con Windows 8 que contengan el chip TPM (módulo de plataforma segura).</span><span class="sxs-lookup"><span data-stu-id="8a5b3-148">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="8a5b3-149">Inscriba su tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="8a5b3-149">Enroll your smart card</span></span>

<span data-ttu-id="8a5b3-150">Para poder iniciar sesión con una tarjeta inteligente, la tarjeta debe estar "inscrito"; es decir, las credenciales de usuario deben identificarse con la tarjeta.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-150">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="8a5b3-151">Este es el caso si la tarjeta es física o virtual.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-151">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="8a5b3-152">Es posible que este proceso ya lo haya realizado el administrador de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-152">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="8a5b3-153">Compárelas si no está seguro de si se ha hecho.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-153">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a5b3-154">Como cada tarjeta inteligente virtual solo está asociada con el dispositivo en el que está instalada, será necesario inscribir una tarjeta independiente para cada equipo con Windows 8 que use.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-154">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="8a5b3-155">**Para inscribir manualmente su tarjeta inteligente**</span><span class="sxs-lookup"><span data-stu-id="8a5b3-155">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="8a5b3-156">Inicie sesión en el equipo en el que va a ejecutar Lync.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-156">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="8a5b3-157">Con Internet Explorer, vaya a la página de inscripción Web de la entidad de certificación de la organización.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-157">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="8a5b3-158">Solicite a su administrador de Lync Server la dirección Web de este recurso si todavía no la tiene.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-158">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="8a5b3-159">La dirección URL tendrá un aspecto similar a este: https://MyCA.\ [nombredesuempresa \] . com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-159">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8a5b3-160">Si usa Internet Explorer 10, es posible que deba ver este sitio web en modo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-160">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="8a5b3-161">Cuando se le solicite que inicie sesión en la página de certificación, inicie sesión con su cuenta de dominio (en lugar de hacerlo como administrador del equipo).</span><span class="sxs-lookup"><span data-stu-id="8a5b3-161">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="8a5b3-162">En la página de bienvenida del sitio web, seleccione **solicitar un certificado**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-162">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="8a5b3-163">Seleccione **solicitud avanzada**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-163">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="8a5b3-164">Seleccione **crear y enviar una solicitud a esta CA**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-164">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="8a5b3-165">Ahora verá una página denominada estación de inscripción para tarjetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-165">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="8a5b3-166">Apruebe la solicitud para instalar el control ActiveX y, a continuación, complete el formulario de solicitud de certificado avanzado de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8a5b3-166">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="8a5b3-167">Seleccione **usuario de tarjeta inteligente** en la lista desplegable **plantilla de certificado** .</span><span class="sxs-lookup"><span data-stu-id="8a5b3-167">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="8a5b3-168">Seleccione **crear conjunto de claves nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-168">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="8a5b3-169">Busque la información del fabricante en la etiqueta de la tarjeta inteligente y seleccione ese fabricante en la lista desplegable **CSP** .</span><span class="sxs-lookup"><span data-stu-id="8a5b3-169">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="8a5b3-170">Seleccione **CSP** como el formato de solicitud, si aún no está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-170">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="8a5b3-171">Seleccione **SHA1** en la lista desplegable algoritmo hash, si aún no está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-171">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="8a5b3-172">Asigne un nombre al certificado que reconozca y haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-172">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="8a5b3-173">Ahora, inserte la tarjeta inteligente en blanco en el lector de tarjetas conectado a la estación de inscripción y haga clic en **inscribirse**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-173">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="8a5b3-174">Cuando se le solicite, escriba su número de identificación personal (PIN) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-174">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8a5b3-175">Si el personal de soporte técnico no le ha proporcionado un PIN especial para suscribirse a la tarjeta inteligente, use el valor predeterminado de PIN de la tarjeta inteligente, que es 12345678.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-175">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="8a5b3-176">Seleccione la opción para forzar al usuario (usted) a cambiar el PIN la primera vez que se use la tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-176">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="8a5b3-177">Ahora, inserte la tarjeta inteligente en blanco en el lector de tarjetas conectado a la estación de inscripción y haga clic en **inscribirse**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-177">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="8a5b3-178">Cuando se le solicite, escriba su número de identificación personal (PIN) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-178">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8a5b3-179">Si el personal de soporte técnico no le ha proporcionado un PIN especial para suscribirse a la tarjeta inteligente, use el valor predeterminado de PIN de la tarjeta inteligente, que es 12345678.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-179">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="8a5b3-180">Seleccione la opción para forzar al usuario (usted) a cambiar el PIN la primera vez que se use la tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-180">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="8a5b3-181">Haga clic en **Aceptar** para confirmar que el certificado que se muestra contiene su información.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-181">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="8a5b3-182">Una vez que vea el aviso de que se ha emitido el certificado, haga clic en **instalar este certificado** para completar el proceso de inscripción.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-182">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="8a5b3-183">Iniciar sesión en Lync con las credenciales de la tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="8a5b3-183">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="8a5b3-184">Antes de usar la tarjeta inteligente por primera vez, se recomienda que haga clic en **eliminar mi información de inicio de sesión** en la página de inicio de sesión de Lync.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-184">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="8a5b3-185">De esta manera, se borran las credenciales de inicio de sesión almacenadas en el equipo y se elimina un posible origen de error.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-185">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="8a5b3-186">**Para iniciar sesión en Lync con las credenciales de la tarjeta inteligente**</span><span class="sxs-lookup"><span data-stu-id="8a5b3-186">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="8a5b3-187">Inicie el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-187">Start the Lync client.</span></span>

2.  <span data-ttu-id="8a5b3-188">En la pantalla de inicio de sesión, escriba el nombre de la cuenta de usuario de inicio de sesión en el cuadro **dirección de inicio de sesión** y, a continuación, haga clic en **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-188">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="8a5b3-189">Si usa una tarjeta inteligente virtual, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-189">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="8a5b3-190">Si usa una tarjeta inteligente física, inserte la tarjeta inteligente en el lector de tarjetas inteligentes y se le pedirá que lo haga y, a continuación, haga clic en **Aceptar** cuando se detecte la tarjeta.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-190">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="8a5b3-191">Escriba el número de PIN de la tarjeta inteligente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-191">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8a5b3-192">Si el personal de soporte no le asignó un número PIN de tarjeta inteligente, use el valor predeterminado, que es 12345678.</span><span class="sxs-lookup"><span data-stu-id="8a5b3-192">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

