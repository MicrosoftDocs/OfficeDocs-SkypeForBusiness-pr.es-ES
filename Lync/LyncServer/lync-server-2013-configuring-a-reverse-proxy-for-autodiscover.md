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
ms.openlocfilehash: b0fb05667ea6ebcb8176353d42fda5cf2eaadfd7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515587"
---
# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="0d084-102">Configuración de un proxy inverso para detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d084-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d084-103">_**Última modificación del tema:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="0d084-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="0d084-104">La detección automática y la compatibilidad de clientes con detección automática requieren la modificación de una regla de publicación web existente o la creación de una nueva regla de publicación web para el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="0d084-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="0d084-105">La modificación o la creación de una nueva regla de publicación no depende de la decisión de actualizar o no actualizar las listas de nombres alternativos de sujeto en los certificados de proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="0d084-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="0d084-106">Si decide usar HTTPS para las solicitudes del servicio de detección automática de Lync Server 2013 y actualizar las listas de nombres alternativos de sujeto en los certificados de proxy inverso, debe asignar el certificado público actualizado a la escucha de capa de sockets seguros (SSL) en el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="0d084-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="0d084-107">La actualización necesaria para el certificado externo (público) incluirá la entrada de nombre alternativo de sujeto (SAN) para lyncdiscover. \<domain name\> .</span><span class="sxs-lookup"><span data-stu-id="0d084-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="0d084-108">A continuación, debe modificar la escucha existente para los servicios web externos o crear una nueva regla de publicación web para la dirección URL externa del servicio Detección automática, por ejemplo **lyncdiscover.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="0d084-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="0d084-109">Si aún no tiene una regla de publicación web para la dirección URL externa de servicios Web de Lync Server 2013 para el grupo de servidores front-end y el grupo de servidores de Director (si ha implementado directores), también deberá publicar una regla para ello.</span><span class="sxs-lookup"><span data-stu-id="0d084-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d084-110">La escucha y la regla de publicación de proxy inverso pueden dar servicio a los servicios web externos y el servicio Detección automática, siempre que el certificado asignado a la escucha contenga el nombre de sujeto necesario y los nombres alternativos de sujeto para ambos.</span><span class="sxs-lookup"><span data-stu-id="0d084-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="0d084-111">Para obtener información detallada sobre la configuración predeterminada de la escucha de web y la regla de publicación, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuración de servidores proxy inversos para Lync Server 2013</A> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0d084-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="0d084-112">Si decide usar HTTP para solicitudes del servicio Detección automática de manera que no tenga que actualizar nombres alternativos de sujeto para el proxy inverso, debe crear o modificar una nueva regla de publicación web para el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="0d084-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="0d084-113">Los procedimientos de esta sección describen cómo crear o modificar las nuevas reglas de publicación web en Microsoft Forefront Threat Management Gateway 2010 para la detección automática.</span><span class="sxs-lookup"><span data-stu-id="0d084-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d084-p104">Estos procedimientos asumen que ha instalado la Standard Edition de Forefront Threat Management Gateway (TMG) 2010. Si está usando otro proxy inverso, los procedimientos son similares pero tendrán que asignarse a la documentación para el producto de tercero.</span><span class="sxs-lookup"><span data-stu-id="0d084-p104">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="0d084-116">Para crear una regla de publicación web para la dirección URL externa de Detección automática</span><span class="sxs-lookup"><span data-stu-id="0d084-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="0d084-117">Haga clic en **Inicio**, señale **Programas**, señale **Microsoft Forefront TMG** y haga clic en **Administración de Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="0d084-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="0d084-118">En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de firewall**, señale **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web**.</span><span class="sxs-lookup"><span data-stu-id="0d084-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="0d084-119">En la página **Asistente para nueva regla de publicación de web**, escriba un nombre para mostrar para la regla de publicación (por ejemplo, LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="0d084-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="0d084-120">En la página **Seleccionar acción de regla**, seleccione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="0d084-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="0d084-121">En la página **Tipo de publicación**, seleccione **Publicar un único sitio web o un equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="0d084-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="0d084-122">En la página **Seguridad de conexión de servidor**, seleccione **Usar SSL para conectar al servidor web o conjunto de servidores publicado**.</span><span class="sxs-lookup"><span data-stu-id="0d084-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="0d084-123">En la página **detalles internos de publicación** , en **nombre de sitio interno**, escriba el nombre de dominio completo (FQDN) de su grupo de directores (por ejemplo, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="0d084-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="0d084-124">Si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, escriba el nombre de dominio completo (FQDN) del grupo de servidores front-end (por ejemplo, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="0d084-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="0d084-125">En la página **detalles internos de publicación** , en **ruta de acceso (opcional)**, escriba **/\*** como la ruta de acceso de la carpeta que se va a publicar y, a continuación, seleccione **reenviar el encabezado de host original**.</span><span class="sxs-lookup"><span data-stu-id="0d084-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="0d084-126">En la página **Detalles de nombre público**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="0d084-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="0d084-127">En **Aceptar peticiones para**, seleccione **Este nombre de dominio**.</span><span class="sxs-lookup"><span data-stu-id="0d084-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="0d084-128">En **nombre público**, escriba **lyncdiscover.**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="0d084-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="0d084-129">(la dirección URL externa del servicio Detección automática).</span><span class="sxs-lookup"><span data-stu-id="0d084-129">(the external Autodiscover Service URL).</span></span> <span data-ttu-id="0d084-130">Si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, escriba el nombre de dominio completo (FQDN) de los servicios web externos en el grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0d084-130">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="0d084-131">En **ruta de acceso**, escriba **/\*** .</span><span class="sxs-lookup"><span data-stu-id="0d084-131">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="0d084-132">En **Seleccionar escucha de web**, en **Escucha**, seleccione su escucha SSL existente con el certificado público actualizado.</span><span class="sxs-lookup"><span data-stu-id="0d084-132">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="0d084-133">En la página **Delegación de autenticación**, seleccione **Sin delegación, pero el cliente se puede autenticar directamente**.</span><span class="sxs-lookup"><span data-stu-id="0d084-133">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="0d084-134">En la página **Conjunto de usuarios**, seleccione **Todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0d084-134">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="0d084-135">En la página **Finalización del Asistente para nueva regla de publicación de web**, compruebe que los parámetros de la regla de publicación de web sean correctos y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0d084-135">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="0d084-136">En la lista de reglas de publicación web de Forefront TMG, haga doble clic en la nueva regla que ha agregado para abrir **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0d084-136">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="0d084-137">En la ficha **Para**, realice el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="0d084-137">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="0d084-138">Seleccione **Reenviar el encabezado de host original en lugar del real**.</span><span class="sxs-lookup"><span data-stu-id="0d084-138">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="0d084-139">Seleccione **Las peticiones parecen provenir del equipo de Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="0d084-139">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="0d084-140">En la ficha **Protocolo de puente**, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d084-140">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="0d084-141">Seleccione **Servidor web**.</span><span class="sxs-lookup"><span data-stu-id="0d084-141">Select **Web server**.</span></span>
    
      - <span data-ttu-id="0d084-142">Seleccione **Redirigir peticiones al puerto HTTP** y escriba **8080** para el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="0d084-142">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="0d084-143">Seleccione **Redirigir peticiones al puerto SSL** y escriba **4443** para el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="0d084-143">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="0d084-144">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d084-144">Click **OK**.</span></span>

18. <span data-ttu-id="0d084-145">Haga clic en  \*\*Aplicar \*\* en el panel de detalles para guardar los cambios y actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="0d084-145">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="0d084-146">Haga clic en **Probar regla** para comprobar que la nueva regla se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0d084-146">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="0d084-147">Para modificar una regla de publicación web existente para agregar la dirección URL y SAN de detección automática</span><span class="sxs-lookup"><span data-stu-id="0d084-147">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="0d084-148">Haga clic en **Inicio**, señale **Programas**, señale **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="0d084-148">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0d084-149">Repetirá la modificación para cada regla de publicación y escucha que tenga.</span><span class="sxs-lookup"><span data-stu-id="0d084-149">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="0d084-150">Normalmente, será una regla y escucha para los grupos de servidores front-end, y otra para los directores opcionales o los grupos de directores, si se han implementado.</span><span class="sxs-lookup"><span data-stu-id="0d084-150">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="0d084-p108">En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de firewall** y haga clic en la regla aplicable. En la pestaña **Tareas**, haga clic en **Editar regla seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="0d084-p108">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="0d084-153">En la pestaña **Nombre público**, en **Esta regla se aplica a**, seleccione **Peticiones para los sitios web siguientes**.</span><span class="sxs-lookup"><span data-stu-id="0d084-153">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="0d084-154">Haga clic en **Agregar**, escriba el nombre del nuevo sitio de Detección automática (por ejemplo, “lyncdiscover.contoso.com”) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d084-154">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="0d084-p109">En la pestaña **Escucha**, haga clic en **Seleccionar certificado** y asigne el nuevo certificado con las entradas SAN de detección automática agregadas. Cierre las propiedades del agente de escucha y publicación web.</span><span class="sxs-lookup"><span data-stu-id="0d084-p109">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="0d084-157">Haga clic en  \*\*Aplicar \*\* en el panel de detalles para guardar los cambios y actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="0d084-157">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="0d084-158">Haga clic en **Probar regla** para comprobar que su nueva regla se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0d084-158">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="0d084-159">Para crear una regla de publicación web para el puerto 80</span><span class="sxs-lookup"><span data-stu-id="0d084-159">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="0d084-160">Haga clic en **Inicio**, diríjase a **Programas**, haga clic en **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="0d084-160">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="0d084-161">En el panel izquierdo, expanda **Server Name**, haga clic con el botón secundario en **Directiva de firewall**, señale **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web**.</span><span class="sxs-lookup"><span data-stu-id="0d084-161">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="0d084-162">En la página **Asistente para nueva regla de publicación de web**, escriba un nombre para mostrar para la nueva regla de publicación (por ejemplo, Detección automática de Lync (HTTP)).</span><span class="sxs-lookup"><span data-stu-id="0d084-162">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="0d084-163">En la página **Seleccionar acción de regla**, seleccione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="0d084-163">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="0d084-164">En la página **Tipo de publicación**, seleccione **Publicar un único sitio web o un equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="0d084-164">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="0d084-165">En la página **Seguridad de conexión de servidor**, seleccione **Usar conexiones no seguras para conectar al servidor web o conjunto de servidores publicado**.</span><span class="sxs-lookup"><span data-stu-id="0d084-165">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="0d084-166">En la página **detalles internos de publicación** , en **nombre de sitio interno**, escriba el FQDN de servicios Web internos del grupo de servidores front-end (por ejemplo, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="0d084-166">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="0d084-167">En la página **detalles internos de publicación** , en **ruta de acceso (opcional)**, escriba **/\*** como la ruta de acceso de la carpeta que se va a publicar y, a continuación, seleccione **reenviar el encabezado de host original en lugar del especificado en el campo Nombre de sitio interno**.</span><span class="sxs-lookup"><span data-stu-id="0d084-167">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="0d084-168">En la página **Detalles de nombre público**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="0d084-168">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="0d084-169">En **Aceptar peticiones para**, seleccione **Este nombre de dominio**.</span><span class="sxs-lookup"><span data-stu-id="0d084-169">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="0d084-170">En **nombre público**, escriba **lyncdiscover.**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="0d084-170">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="0d084-171">(la dirección URL externa del servicio Detección automática).</span><span class="sxs-lookup"><span data-stu-id="0d084-171">(the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="0d084-172">En **ruta de acceso**, escriba **/\*** .</span><span class="sxs-lookup"><span data-stu-id="0d084-172">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="0d084-173">En la página **Seleccionar escucha de web**, en **Escucha de web**, seleccione una escucha de web o use el nuevo Asistente para la definición de escucha de web para crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="0d084-173">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="0d084-174">En la página **Delegación de autenticación**, seleccione **Sin delegación, y el cliente no se puede autenticar directamente**.</span><span class="sxs-lookup"><span data-stu-id="0d084-174">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="0d084-175">En la página **Conjunto de usuarios**, seleccione **Todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0d084-175">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="0d084-176">En la página **Finalización del Asistente para nueva regla de publicación de web**, compruebe que los parámetros de la regla de publicación de web sean correctos y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0d084-176">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="0d084-177">En la lista de reglas de publicación web de Forefront TMG, haga doble clic en la nueva regla que ha agregado para abrir **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0d084-177">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="0d084-178">En la ficha **Protocolo de puente**, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d084-178">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="0d084-179">Seleccione **Servidor web**.</span><span class="sxs-lookup"><span data-stu-id="0d084-179">Select **Web server**.</span></span>
    
      - <span data-ttu-id="0d084-180">Seleccione **Redirigir peticiones al puerto HTTP** y escriba **8080** para el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="0d084-180">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="0d084-181">Compruebe que **Redirigir peticiones al puerto SSL** no está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0d084-181">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="0d084-182">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d084-182">Click **OK**.</span></span>

17. <span data-ttu-id="0d084-183">Haga clic en  \*\*Aplicar \*\* en el panel de detalles para guardar los cambios y actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="0d084-183">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="0d084-184">Haga clic en **Probar regla** para comprobar que su nueva regla se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0d084-184">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="0d084-185">Compruebe que la dirección URL externa del servicio Detección automática no está definida en otra regla de publicación web.</span><span class="sxs-lookup"><span data-stu-id="0d084-185">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d084-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d084-186">See Also</span></span>


[<span data-ttu-id="0d084-187">Configuración de servidores proxy inversos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d084-187">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

