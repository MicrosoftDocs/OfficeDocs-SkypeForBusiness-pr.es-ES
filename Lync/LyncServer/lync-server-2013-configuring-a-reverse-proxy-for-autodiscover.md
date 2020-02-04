---
title: 'Lync Server 2013: configuración de un proxy inverso para detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a02bf765941c7240f08fecc91d5912f31a0f2f87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="c8c46-102">Configuración de un proxy inverso para detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8c46-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8c46-103">_**Última modificación del tema:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="c8c46-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="c8c46-104">La detección automática y la compatibilidad de clientes que usan detección automática requieren la modificación de una regla de publicación de web existente o la creación de una nueva regla de publicación web para el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c8c46-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="c8c46-105">La modificación o la creación de una nueva regla de publicación no depende de la decisión de actualizar o no actualizar las listas de nombres alternativos de asunto en los certificados de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c8c46-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="c8c46-106">Si decide usar HTTPS para las solicitudes de servicio de detección automática de Lync Server 2013 y actualizar las listas de nombres alternativos de asunto en los certificados de proxy inverso, debe asignar el certificado público actualizado a la escucha de capa de sockets seguros (SSL) en su proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c8c46-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="c8c46-107">La actualización requerida para el certificado externo (público) incluirá la entrada de nombre alternativo de asunto (SAN) para lyncdiscover. \<nombre\>de dominio.</span><span class="sxs-lookup"><span data-stu-id="c8c46-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="c8c46-108">A continuación, debe modificar el agente de escucha existente para los servicios web externos o crear una nueva regla de publicación de web para la dirección URL del servicio de detección automática externa, por ejemplo **lyncdiscover.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="c8c46-109">Si todavía no tiene una regla de publicación web para la dirección URL externa de servicios Web de Lync Server 2013 para el grupo de servidores front-end y el grupo de directores (si ha implementado directores), también tendrá que publicar una regla para ello.</span><span class="sxs-lookup"><span data-stu-id="c8c46-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8c46-110">La regla de publicación y la escucha de proxy inversos pueden atender tanto los servicios web externos como el servicio Detección automática, siempre que el certificado asignado a la escucha contenga el nombre de asunto y los nombres alternativos de asunto necesarios para ambos.</span><span class="sxs-lookup"><span data-stu-id="c8c46-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="c8c46-111">Para obtener más información sobre la configuración predeterminada de la escucha de web y la regla de publicación, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuración de servidores proxy inversos para Lync Server 2013</A> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c8c46-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="c8c46-112">Si decide usar HTTP para las solicitudes de servicio de detección automática iniciales, de modo que no necesite actualizar nombres alternativos de asunto para el proxy inverso, debe crear o modificar una regla de publicación web para el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="c8c46-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="c8c46-113">Los procedimientos de esta sección describen cómo crear o modificar las reglas de publicación web en Microsoft Forefront Threat Management Gateway 2010 para el descubrimiento automático.</span><span class="sxs-lookup"><span data-stu-id="c8c46-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8c46-114">En estos procedimientos se supone que ha instalado la edición estándar de Forefront Threat Management Gateway (TMG) 2010.</span><span class="sxs-lookup"><span data-stu-id="c8c46-114">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="c8c46-115">Si está usando otro proxy inverso, los procedimientos son similares, pero deberán asignarse a la documentación del producto de terceros.</span><span class="sxs-lookup"><span data-stu-id="c8c46-115">If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="c8c46-116">Para crear una regla de publicación web para la dirección URL externa de detección automática</span><span class="sxs-lookup"><span data-stu-id="c8c46-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="c8c46-117">Haga clic en **Inicio**, seleccione **programas**, **Microsoft Forefront TMG**y, a continuación, haga clic en administración de **Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="c8c46-118">En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de Firewall**, seleccione **nuevo**y, después, haga clic en regla de **publicación de sitio web**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="c8c46-119">En la página **Asistente para nueva regla de publicación de web** , escriba un nombre para mostrar para la nueva regla de publicación (por ejemplo, LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="c8c46-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="c8c46-120">En la página **Seleccionar acción de regla** , seleccione **permitir**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="c8c46-121">En la página **tipo de publicación** , seleccione **publicar un único sitio web o un equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="c8c46-122">En la página **seguridad de conexión de servidor** , seleccione **usar SSL para conectarse al servidor web o conjunto**de servidores publicado.</span><span class="sxs-lookup"><span data-stu-id="c8c46-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="c8c46-123">En la página **Internal Publishing details** , en **nombre de sitio interno**, escriba el nombre de dominio completo (FQDN) de su grupo de directores (por ejemplo, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="c8c46-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="c8c46-124">Si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, escriba el FQDN del grupo de servidores front-end (por ejemplo, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="c8c46-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="c8c46-125">En la **página datos internos de publicación** , en **ruta de acceso (opcional)**, escriba \*\* / \*\* la ruta de acceso de la carpeta que se va a publicar y, a continuación, seleccione **reenviar el encabezado de host original**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="c8c46-126">En la página **detalles de nombre público** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8c46-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="c8c46-127">En **aceptar solicitudes por**, seleccione **este nombre de dominio**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="c8c46-128">En **nombre público**, escriba **lyncdiscover.** \<sipdomain\> (dirección URL externa del servicio de detección automática).</span><span class="sxs-lookup"><span data-stu-id="c8c46-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="c8c46-129">Si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, escriba el FQDN de los servicios web externos en el grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c8c46-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="c8c46-130">En **ruta**de acceso \*\* / \*\*, escriba.</span><span class="sxs-lookup"><span data-stu-id="c8c46-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="c8c46-131">En la página **seleccionar escucha de web** , en **escucha de web**, seleccione la escucha SSL existente con el certificado público actualizado.</span><span class="sxs-lookup"><span data-stu-id="c8c46-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="c8c46-132">En la página **delegación de autenticación** , seleccione **sin delegación, pero el cliente puede autenticar directamente**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="c8c46-133">En la página **conjunto de usuarios** , seleccione **todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="c8c46-134">En la página **finalización del Asistente para nueva regla de publicación de web** , compruebe que la configuración de la regla de publicación de web es correcta y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="c8c46-135">En la lista de reglas de publicación Web de Forefront TMG, haga doble clic en la nueva regla que acaba de agregar para abrir **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="c8c46-136">En la pestaña **para** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8c46-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="c8c46-137">Seleccione **reenviar el encabezado de host original en lugar del real**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="c8c46-138">**Las solicitudes Select parecen proceder del equipo FOREFRONT TMG**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="c8c46-139">En la pestaña **puente** , configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8c46-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="c8c46-140">Seleccione **servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="c8c46-141">Seleccione **redirigir las solicitudes al puerto http**y escriba **8080** para el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="c8c46-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="c8c46-142">Seleccione **redirigir peticiones al puerto SSL**y escriba **4443** para el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="c8c46-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="c8c46-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-143">Click **OK**.</span></span>

18. <span data-ttu-id="c8c46-144">Haga clic en **aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="c8c46-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="c8c46-145">Haga clic en **probar regla** para comprobar que la nueva regla está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c8c46-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="c8c46-146">Para modificar una regla de publicación web existente para agregar el SAN y la dirección URL de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="c8c46-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="c8c46-147">Haga clic en **Inicio**, seleccione **programas**, **Microsoft Forefront TMG**y, a continuación, haga clic en administración de **Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c8c46-148">Repetirá la modificación para cada regla de publicación y agente de escucha que tenga.</span><span class="sxs-lookup"><span data-stu-id="c8c46-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="c8c46-149">Por lo general, será una regla y una escucha para los grupos de aplicaciones para el usuario y otra para los grupos opcionales o grupos de directores, si se han implementado.</span><span class="sxs-lookup"><span data-stu-id="c8c46-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="c8c46-150">En el panel izquierdo, expanda **ServerName**, haga clic con el botón derecho en **Directiva de Firewall**, haga clic en la regla correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c8c46-150">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule.</span></span> <span data-ttu-id="c8c46-151">En la pestaña **tareas** , haga clic en **Editar regla seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-151">On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="c8c46-152">En la pestaña **nombre público** , en **esta regla se aplica a**, seleccione **solicitudes para los siguientes sitios web**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="c8c46-153">Haga clic en **Agregar**, escriba el nombre del nuevo sitio de Autodiscover (por ejemplo, "lyncdiscover.contoso.com") y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="c8c46-154">En la pestaña **agente de escucha** , haga clic en **seleccionar certificado** y asigne el nuevo certificado con las entradas de San de detección automática agregadas.</span><span class="sxs-lookup"><span data-stu-id="c8c46-154">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries.</span></span> <span data-ttu-id="c8c46-155">Cierre las propiedades de escucha y publicación de Web.</span><span class="sxs-lookup"><span data-stu-id="c8c46-155">Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="c8c46-156">Haga clic en **aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="c8c46-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="c8c46-157">Haga clic en **probar regla** para comprobar que la nueva regla está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c8c46-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="c8c46-158">Para crear una regla de publicación web para el puerto 80</span><span class="sxs-lookup"><span data-stu-id="c8c46-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="c8c46-159">Haga clic en **Inicio**, seleccione **programas**, **Microsoft Forefront TMG**y, a continuación, haga clic en administración de **Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="c8c46-160">En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de Firewall**, seleccione **nuevo**y, después, haga clic en regla de **publicación de sitio web**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="c8c46-161">En la página **Asistente para nueva regla de publicación de web** , escriba un nombre para mostrar para la nueva regla de publicación (por ejemplo, Lync Autodiscover (http)).</span><span class="sxs-lookup"><span data-stu-id="c8c46-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="c8c46-162">En la página **Seleccionar acción de regla** , seleccione **permitir**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="c8c46-163">En la página **tipo de publicación** , seleccione **publicar un único sitio web o un equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="c8c46-164">En la página **seguridad de conexión de servidor** , seleccione **usar conexiones no seguras para conectarse al servidor web o conjunto**de servidores publicado.</span><span class="sxs-lookup"><span data-stu-id="c8c46-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="c8c46-165">En la página **Internal Publishing details** , en **nombre de sitio interno**, escriba el FQDN de los servicios Web internos de su grupo de front-end (por ejemplo, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="c8c46-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="c8c46-166">En la **página datos internos de publicación** , en **ruta de acceso (opcional)**, escriba \*\* / \*\* la ruta de acceso de la carpeta que se va a publicar y, a continuación, seleccione **reenviar el encabezado de host original en lugar del especificado en el campo Nombre del sitio interno**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="c8c46-167">En la página **detalles de nombre público** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8c46-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="c8c46-168">En **aceptar solicitudes por**, seleccione **este nombre de dominio**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="c8c46-169">En **nombre público**, escriba **lyncdiscover.** \<sipdomain\> (dirección URL externa del servicio de detección automática).</span><span class="sxs-lookup"><span data-stu-id="c8c46-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="c8c46-170">En **ruta**de acceso \*\* / \*\*, escriba.</span><span class="sxs-lookup"><span data-stu-id="c8c46-170">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="c8c46-171">En la página **seleccionar escucha de web** , en **escucha de web**, seleccione una escucha de web o use el Asistente para definición de escuchas de Web nuevo para crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="c8c46-171">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="c8c46-172">En la página **delegación de autenticación** , seleccione **sin delegación y el cliente no puede autenticar directamente**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-172">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="c8c46-173">En la página **conjunto de usuarios** , seleccione **todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-173">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="c8c46-174">En la página **finalización del Asistente para nueva regla de publicación de web** , compruebe que la configuración de la regla de publicación de web es correcta y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-174">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="c8c46-175">En la lista de reglas de publicación Web de Forefront TMG, haga doble clic en la nueva regla que acaba de agregar para abrir **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-175">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="c8c46-176">En la pestaña **puente** , configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8c46-176">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="c8c46-177">Seleccione **servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-177">Select **Web server**.</span></span>
    
      - <span data-ttu-id="c8c46-178">Seleccione **redirigir las solicitudes al puerto http**y escriba **8080** para el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="c8c46-178">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="c8c46-179">Compruebe que el **puerto SSL de redirección** no está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c8c46-179">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="c8c46-180">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c8c46-180">Click **OK**.</span></span>

17. <span data-ttu-id="c8c46-181">Haga clic en **aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="c8c46-181">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="c8c46-182">Haga clic en **probar regla** para comprobar que la nueva regla está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c8c46-182">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="c8c46-183">Compruebe que la dirección URL del servicio de detección automática externa no esté definida en ninguna otra regla de publicación de Web.</span><span class="sxs-lookup"><span data-stu-id="c8c46-183">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8c46-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8c46-184">See Also</span></span>


[<span data-ttu-id="c8c46-185">Configuración de los servidores proxy inversos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8c46-185">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

