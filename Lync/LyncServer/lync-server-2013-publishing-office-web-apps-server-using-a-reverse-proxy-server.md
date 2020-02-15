---
title: Publicación de Office Web Apps Server con un servidor proxy inverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1d1dae773c96cfa6d16994e5b3c6aec2504b16c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="6f779-102">Publicación de Office Web Apps Server en Lync Server 2013 con un servidor proxy inverso</span><span class="sxs-lookup"><span data-stu-id="6f779-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f779-103">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="6f779-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="6f779-104">Si desea que los usuarios externos (es decir, los usuarios que inicien sesión desde fuera del firewall de la organización) tengan acceso a las presentaciones de PowerPoint del servidor Office Web Apps, entonces deberá utilizar el servidor Office Web Apps y un servidor proxy inverso como Microsoft Forefront Threat Management Gateway.</span><span class="sxs-lookup"><span data-stu-id="6f779-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="6f779-105">Esto también significa que tendrá que crear y configurar una regla de publicación de sitios web; Esta regla le ayudará a asegurarse de que los usuarios puedan conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="6f779-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="6f779-106">Si no necesita brindar acceso a usuarios externos, entonces no necesita configurar una regla de publicación de sitio web.</span><span class="sxs-lookup"><span data-stu-id="6f779-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="6f779-107">Para configurar una regla de publicación de sitios web en Forefront Threat Management Gateway, complete el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="6f779-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="6f779-108">Haga clic en **Inicio**, en **Todos los programas**, en **Microsoft Forefront TMG** y, a continuación, en**Administración de Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="6f779-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="6f779-109">En Forefront TMG, haga clic con el botón secundario en **Directiva de firewall**, elija **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web**.</span><span class="sxs-lookup"><span data-stu-id="6f779-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="6f779-110">En el Asistente de nueva regla de publicación web, en la página **Bienvenido al Asistente de nueva regla de publicación web**, escriba un nombre para su nueva regla en el cuadro **nombre de regla de publicación web** (por ejemplo, **Regla del servidor Office Web Apps**) y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="6f779-111">En la página **Especificar acción de regla**, seleccione **Permitir** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="6f779-112">En la página **Tipo de publicación**, seleccione **Publicar un único sitio web o un equilibrador de carga** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="6f779-113">En la página **Seguridad de conexión de servidor**, seleccione **Usar SSL para conectarse al servidor web o conjunto de servidores publicado** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="6f779-p102">En la página **Detalles internos de publicación**, escriba el FQDN de su servidor Office Web Apps (por ejemplo, **officewebapps01.contoso.com**) en el cuadro **Nombre de sitio interno** y luego haga clic en **Siguiente**. El nombre ingresado en el cuadro **Nombre de sitio interno** debe aparecer en el campo Asunto o el campo Nombre alternativo de asunto del certificado que ha asignado al servidor Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="6f779-p102">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**. The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="6f779-116">En la página **detalles internos de publicación** , \*\* / \*\* escriba el cuadro **ruta de acceso (opcional)** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="6f779-117">La sintaxis\* /le ayudará a asegurarse de que se publiquen todas las carpetas y subcarpetas del sitio.</span><span class="sxs-lookup"><span data-stu-id="6f779-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="6f779-118">En la página **Detalles de nombre público**, seleccione **Este nombre de dominio (escribir debajo)** de la lista desplegable **Aceptar solicitudes de** y luego escriba el nombre de dominio completo de su servidor Office Web Apps en el cuadro Nombre público.</span><span class="sxs-lookup"><span data-stu-id="6f779-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="6f779-119">Este nombre deberá ser el nombre utilizado para acceder a su sitio web.</span><span class="sxs-lookup"><span data-stu-id="6f779-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="6f779-120">Por ejemplo, si se obtiene acceso a su sitio con la http://officewebapps01.contoso.com dirección URL, escriba **officewebapps01.contoso.com** en el cuadro **nombre público** .</span><span class="sxs-lookup"><span data-stu-id="6f779-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="6f779-121">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-121">Click **Next**.</span></span>

11. <span data-ttu-id="6f779-122">En la página **Seleccionar escucha de web**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6f779-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="6f779-123">En el Asistente para nueva definición de escucha de web, escriba un nombre para la nueva escucha de web (por ejemplo, **SSL**) en el cuadro **Nombre de escucha de web** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="6f779-124">En la página **Seguridad de la conexión de cliente**, seleccione **Requerir conexiones seguras SSL con los clientes** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="6f779-125">En la página **Direcciones IP de escucha de web**, seleccione **Externa**, seleccione **Interna** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="6f779-126">En la página **Certificados SSL de escucha**, seleccione **Usar un único certificado para esta escucha de web** y, a continuación, haga clic en **Seleccionar certificado**.</span><span class="sxs-lookup"><span data-stu-id="6f779-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="6f779-127">En el cuadro de diálogo **Seleccionar certificado**, seleccione el certificado que utilizará para esta escucha de web y, a continuación, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="6f779-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="6f779-128">En la página **Certificados SSL de escucha**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="6f779-129">En la página **Configuración de autenticación**, seleccione **Sin autenticación** de la lista desplegable **Seleccionar cómo proporcionan los clientes sus credenciales a Forefront TMG** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="6f779-130">En la página **Configuración de inicio de sesión único**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="6f779-p105">En la página **Finalización del Asistente de nueva escucha de web**, revise el resumen de las elecciones de configuración que ha realizado. Cuando esté listo, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6f779-p105">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made. When ready, click **Finish**.</span></span>

21. <span data-ttu-id="6f779-133">En la página **Seleccionar escucha de web**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="6f779-134">En la página **Delegación de la autenticación**, seleccione **Sin delegación, pero el cliente puede autenticar directamente** de la lista desplegable \*\*Seleccionar el método utilizado por Forefront TMG para autenticar al servidor web publicado \*\* y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="6f779-p106">En la página **Conjuntos de usuarios**, confirme que aparezcan listados los conjuntos de usuarios apropiados. De manera predeterminada, esto es el conjunto de usuarios **Todos los usuarios**. Haga clic en **Agregar** para agregar otros conjuntos de usuarios que haya definido. Cuando haya terminado, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f779-p106">On the **User Sets** page, confirm that the appropriate user sets are listed. By default, this is the **All Users** user set. Click **Add** to add other user sets you may have defined. When complete, click **Next**.</span></span>

24. <span data-ttu-id="6f779-139">En la página **Finalización del Asistente de nueva regla de publicación web**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6f779-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="6f779-p107">Tenga en cuenta que hacer clic en **Finalizar** no implica que haya completado el proceso; es decir, esto no aplica automáticamente ni habilita la nueva regla. En cambio, necesitará hacer clic en el botón **Aplicar** que aparecerá en la interfaz de usuario de Forefront TMG. Al hacer clic en **Aplicar** aparecerá el cuadro de diálogo **Descripción de cambio de configuración**. Haga clic en **Aplicar** en ese cuadro de diálogo para habilitar la nueva regla de publicación.</span><span class="sxs-lookup"><span data-stu-id="6f779-p107">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule. Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface. When you click **Apply** the **Configuration Change Description** dialog box will appear. Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="6f779-144">Una vez aplicada la nueva regla, tendrá que realizar algunas modificaciones menores en la regla para asegurarse de que los usuarios puedan usar las nuevas capacidades de presentación de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="6f779-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="6f779-145">Para lograr eso, realice el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="6f779-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="6f779-146">En Forefront TMG, haga clic con el botón secundario en el nombre de la nueva regla de publicación y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6f779-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="6f779-147">En el cuadro de diálogo **Propiedades**, en la pestaña **Para**, seleccione la opción **Reenviar el encabezado de host original en lugar del real**.</span><span class="sxs-lookup"><span data-stu-id="6f779-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="6f779-148">En la pestaña **Tráfico**, haga clic en **Filtrar** y, a continuación, haga clic en **Configurar HTTP**.</span><span class="sxs-lookup"><span data-stu-id="6f779-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="6f779-149">En el cuadro de diálogo **Configuración de la directiva de HTTP para la regla**, desactive la casilla **Verificar normalización** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f779-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="6f779-150">En el cuadro de diálogo **Propiedades**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f779-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="6f779-p109">En Forefront TMG, haga clic en **Aplicar** para habilitar los cambios. Cuando se abra el cuadro de diálogo **Descripción de cambio de configuración**, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6f779-p109">In Forefront TMG, click **Apply** to enable the changes. When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="6f779-153">Una vez finalizada la instalación, puede probar el servidor de Office Web Apps con los procedimientos del tema [Validating The Configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span><span class="sxs-lookup"><span data-stu-id="6f779-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

