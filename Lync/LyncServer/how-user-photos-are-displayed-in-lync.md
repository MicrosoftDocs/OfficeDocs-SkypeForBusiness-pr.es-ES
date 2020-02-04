---
title: Cómo se muestran las fotos de usuario en Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd3214c3ada87db6f44f6b99373346d4f0a27d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="d71b0-102">Cómo se muestran las fotos de usuario en Lync</span><span class="sxs-lookup"><span data-stu-id="d71b0-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d71b0-103">_**Última modificación del tema:** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="d71b0-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="d71b0-104">**Resumen:** Las fotos del usuario mostradas en el cliente de Lync pueden diferir dependiendo de la característica de Lync que use, como cuando se encuentre en una conferencia o en una conversación de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="d71b0-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="d71b0-105">Lync 2010 presentó la posibilidad de incluir una foto con el perfil de Lync que se muestra a otros usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="d71b0-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="d71b0-106">También puede elegir si desea mostrar o no las fotos de los contactos en el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="d71b0-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="d71b0-107">En Lync 2013, soporte técnico para fotos de alta resolución para usuarios.</span><span class="sxs-lookup"><span data-stu-id="d71b0-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="d71b0-108">En este tema se describe cómo obtiene y muestra el cliente de Lync las fotos de los usuarios, dónde se almacenan, las limitaciones de cada origen de imagen y cómo usan las fotos de los usuarios diferentes servicios de Lync.</span><span class="sxs-lookup"><span data-stu-id="d71b0-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="d71b0-109">Consideraciones de planeación</span><span class="sxs-lookup"><span data-stu-id="d71b0-109">Planning considerations</span></span>

<span data-ttu-id="d71b0-110">Debe tener en cuenta lo siguiente al planear la implementación de las fotos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d71b0-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="d71b0-111">La compatibilidad con fotos de usuario de alta definición requiere que el buzón del usuario se encuentre en Exchange 2013 y que la cuenta de usuario de Lync esté en el grupo de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d71b0-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="d71b0-112">Las fotos de los usuarios de alta definición se admiten únicamente en un entorno en el que se usan Lync Server 2013 y Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d71b0-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="d71b0-113">Los usuarios con buzones en Exchange 2010 siempre usarán el atributo **thumbnailPhoto** de AD DS como origen de la foto de su usuario.</span><span class="sxs-lookup"><span data-stu-id="d71b0-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="d71b0-114">Una foto de usuario almacenada como el atributo **thumbnailPhoto** de AD DS no se mostrará a los contactos externos o federados.</span><span class="sxs-lookup"><span data-stu-id="d71b0-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="d71b0-115">Si las fotos de los contactos de los usuarios se almacenan en AD DS, el archivo de imagen usado se limita a 96 x 96 píxeles y no más del tamaño de archivo de 100 KB.</span><span class="sxs-lookup"><span data-stu-id="d71b0-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="d71b0-116">Si se pierde la conectividad entre Lync Server y Exchange Server, se mostrará la baja resolución de **thumbnailPhoto** del usuario de AD DS y solo a los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="d71b0-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="d71b0-117">Las fotos de los usuarios de alta resolución se muestran en las reuniones de Lync 2013 cuando un orador activo no tiene el vídeo habilitado.</span><span class="sxs-lookup"><span data-stu-id="d71b0-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="d71b0-118">Además, Si mueves el ratón sobre la foto en miniatura de la galería, se mostrará la foto de alta resolución.</span><span class="sxs-lookup"><span data-stu-id="d71b0-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="d71b0-119">Fotos de usuario en Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d71b0-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="d71b0-120">En el cliente de Lync 2010, puede elegir entre dos opciones para mostrar una foto de su perfil, una **imagen corporativa predeterminada** y **Mostrar la imagen de una dirección web**.</span><span class="sxs-lookup"><span data-stu-id="d71b0-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="d71b0-121">Imagen corporativa predeterminada</span><span class="sxs-lookup"><span data-stu-id="d71b0-121">Default corporate picture</span></span>

<span data-ttu-id="d71b0-122">Si elige la opción de **imagen corporativa predeterminada** , Lync le mostrará la foto de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d71b0-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="d71b0-123">La imagen usada es la imagen definida como el valor del atributo **thumbnailPhoto** en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d71b0-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="d71b0-124">Este es el mismo archivo que usa Exchange para mostrar imágenes en Outlook.</span><span class="sxs-lookup"><span data-stu-id="d71b0-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="d71b0-125">Entre las consideraciones para usar imágenes de los servicios de dominio de Active Directory se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d71b0-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="d71b0-126">Solo se admiten las imágenes con dimensiones de hasta 96 píxeles por 96 píxeles.</span><span class="sxs-lookup"><span data-stu-id="d71b0-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="d71b0-127">El tamaño de archivo de la imagen está limitado a 100 KB.</span><span class="sxs-lookup"><span data-stu-id="d71b0-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="d71b0-128">De forma predeterminada, los usuarios pueden cambiar la imagen que se usa para el atributo **thumbnailPhoto** , aunque no directamente a través del cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="d71b0-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="d71b0-129">Puede deshabilitarlo a través de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d71b0-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="d71b0-130">Las imágenes almacenadas en servicios de dominio de Active Directory no se muestran a los contactos externos a su organización, incluso si son contactos federados.</span><span class="sxs-lookup"><span data-stu-id="d71b0-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="d71b0-131">En organizaciones grandes, almacenar y recuperar imágenes para un gran número de usuarios puede repercutir en el tamaño y el rendimiento de la base de datos de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d71b0-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="d71b0-132">Las dimensiones de imagen y el tamaño de archivo limitados indican que solo se pueden usar imágenes de baja resolución.</span><span class="sxs-lookup"><span data-stu-id="d71b0-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="d71b0-133">Cómo administran los usuarios las fotos de los usuarios en los servicios de dominio de Active Directory</span><span class="sxs-lookup"><span data-stu-id="d71b0-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="d71b0-134">El usuario no puede cambiar la imagen usada en el perfil de los servicios de dominio de Active Directory directamente a través del cliente de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="d71b0-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="d71b0-135">Puede usar una de las siguientes opciones para hacerlo, si está disponible:</span><span class="sxs-lookup"><span data-stu-id="d71b0-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="d71b0-136">\*\*\*\*   Los usuarios de SharePoint Server pueden cargar una foto en ' mi sitio ' en un servidor de SharePoint y, a continuación, [configurar la sincronización de perfiles en SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) para sincronizar la foto con el atributo **thumbnailPhoto** en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d71b0-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="d71b0-137">**Foto almacenada en la dirección URL**   de acceso público puede configurar su foto de usuario especificando una dirección URL accesible públicamente para la imagen que desea usar.</span><span class="sxs-lookup"><span data-stu-id="d71b0-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="d71b0-138">La imagen debe ser públicamente accesible sin una contraseña.</span><span class="sxs-lookup"><span data-stu-id="d71b0-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="d71b0-139">La imagen almacenada en la dirección Web especificada se transfiere a otros usuarios a través de la categoría tarjeta de contacto de la información de presencia.</span><span class="sxs-lookup"><span data-stu-id="d71b0-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="d71b0-140">Cuando el cliente de Lync necesita mostrar una foto de usuario, recupera la imagen de la dirección Web especificada.</span><span class="sxs-lookup"><span data-stu-id="d71b0-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="d71b0-141">**Los cmdlets de Exchange 2010 para administradores de Windows PowerShell**   pueden ejecutar el cmdlet [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) en el shell de administración de Exchange 2010 en para administrar el atributo **thumbnailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="d71b0-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="d71b0-142">Cuando se importan imágenes con cmdlets de Exchange 2010, el tamaño de archivo se limita a 10 KB.</span><span class="sxs-lookup"><span data-stu-id="d71b0-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="d71b0-143">**Las herramientas**   de terceros los usuarios pueden cargar solo su propia foto para el atributo **thumbnailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="d71b0-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="d71b0-144">Mostrar una imagen de una dirección web</span><span class="sxs-lookup"><span data-stu-id="d71b0-144">Show a picture from a web address</span></span>

<span data-ttu-id="d71b0-145">Cuando elige la opción **Mostrar una imagen de una dirección web** , Lync obtiene la imagen en la dirección que escribe y la muestra para la foto de usuario en Lync.</span><span class="sxs-lookup"><span data-stu-id="d71b0-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="d71b0-146">Entre las consideraciones para usar imágenes de una dirección web se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d71b0-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="d71b0-147">Los límites de tamaño de archivo se determinan mediante el atributo **MaxPhotoSizeKB** en la Directiva de cliente, que se define con el cmdlet [New-ClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) .</span><span class="sxs-lookup"><span data-stu-id="d71b0-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="d71b0-148">El límite de tamaño predeterminado es 30 KB.</span><span class="sxs-lookup"><span data-stu-id="d71b0-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="d71b0-149">El valor máximo es 100 KB.</span><span class="sxs-lookup"><span data-stu-id="d71b0-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="d71b0-150">No hay ninguna restricción en la resolución de la imagen, pero si intenta usar un archivo de imagen que supere el límite de tamaño, no se descargará en los clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="d71b0-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="d71b0-151">Puede establecer el valor en 0 para deshabilitar que todas las fotos de los usuarios se usen en Lync.</span><span class="sxs-lookup"><span data-stu-id="d71b0-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="d71b0-152">Los contactos federados externos pueden ver las fotos de los usuarios de una dirección Web.</span><span class="sxs-lookup"><span data-stu-id="d71b0-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="d71b0-153">Administrar la foto del usuario con cmdlets de directiva de cliente</span><span class="sxs-lookup"><span data-stu-id="d71b0-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="d71b0-154">En Lync Server 2010, la configuración de la Directiva de cliente está configurada con los cmdlets de ClientPolicy.</span><span class="sxs-lookup"><span data-stu-id="d71b0-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="d71b0-155">La configuración de la Directiva configurada se envía a los clientes mediante aprovisionamiento en banda.</span><span class="sxs-lookup"><span data-stu-id="d71b0-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="d71b0-156">Los dos parámetros de los cmdlets de ClientPolicy que determinan la experiencia de foto del usuario son **DisplayPhoto** y **MaxPhotoSizeKB**.</span><span class="sxs-lookup"><span data-stu-id="d71b0-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="d71b0-157">El parámetro de aprovisionamiento dentro de banda correspondiente para **DisplayPhoto** y **MaxPhotoSizeKB** se denomina " **fotousage**".</span><span class="sxs-lookup"><span data-stu-id="d71b0-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="d71b0-158">Los valores para el parámetro de **fotouso** se envían a los clientes a través de la **endpointConfiguration** **provisionGroup**.</span><span class="sxs-lookup"><span data-stu-id="d71b0-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="d71b0-159">Para obtener más información [, vea información general sobre la configuración y las directivas de cliente](http://go.microsoft.com/fwlink/?linkid=507470) .</span><span class="sxs-lookup"><span data-stu-id="d71b0-159">See [Overview of Client Policies and Settings](http://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="d71b0-160">El valor del parámetro **DisplayPhoto** determina el origen de la imagen de foto del usuario.</span><span class="sxs-lookup"><span data-stu-id="d71b0-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="d71b0-161">En la tabla siguiente se incluyen los valores admitidos.</span><span class="sxs-lookup"><span data-stu-id="d71b0-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d71b0-162">Valor del parámetro DisplayPhoto</span><span class="sxs-lookup"><span data-stu-id="d71b0-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="d71b0-163">Origen de la imagen</span><span class="sxs-lookup"><span data-stu-id="d71b0-163">Image source</span></span></th>
<th><span data-ttu-id="d71b0-164">Configuración de cliente de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d71b0-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d71b0-165">NOPHOTO</span><span class="sxs-lookup"><span data-stu-id="d71b0-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="d71b0-166">nada</span><span class="sxs-lookup"><span data-stu-id="d71b0-166">none</span></span></p></td>
<td><p><span data-ttu-id="d71b0-167"><strong>No mostrar mi foto</strong></span><span class="sxs-lookup"><span data-stu-id="d71b0-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d71b0-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="d71b0-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="d71b0-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="d71b0-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="d71b0-170"><strong>Imagen corporativa predeterminada</strong></span><span class="sxs-lookup"><span data-stu-id="d71b0-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d71b0-171">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="d71b0-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="d71b0-172">Dirección web</span><span class="sxs-lookup"><span data-stu-id="d71b0-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="d71b0-173"><strong>Mostrar una imagen de una dirección web</strong></span><span class="sxs-lookup"><span data-stu-id="d71b0-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="d71b0-174">Cómo obtiene fotos el cliente de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d71b0-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="d71b0-175">En Lync 2010, el servicio de libreta de direcciones administra las fotos del usuario en el servidor.</span><span class="sxs-lookup"><span data-stu-id="d71b0-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="d71b0-176">El cliente de Lync obtiene las fotos del usuario al consultar primero el servicio de consulta Web de la libreta de direcciones (ABWQ) en el servidor, que se expone a través del servicio Web de expansión de la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="d71b0-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="d71b0-177">El cliente recibe el archivo de imagen y, a continuación, lo copia en la caché del usuario para evitar descargar la imagen cada vez que se debe mostrar.</span><span class="sxs-lookup"><span data-stu-id="d71b0-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="d71b0-178">Los valores de atributo devueltos de la consulta también se almacenan en la entrada del servicio de libreta de direcciones en caché para el usuario.</span><span class="sxs-lookup"><span data-stu-id="d71b0-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="d71b0-179">El servicio de libreta de direcciones elimina todas las imágenes almacenadas en caché cada 24 horas, lo que significa que puede tardar hasta 24 horas en actualizar las imágenes de usuario nuevas en la memoria caché del servidor.</span><span class="sxs-lookup"><span data-stu-id="d71b0-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="d71b0-180">Puede forzar una actualización a la caché mediante el cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .</span><span class="sxs-lookup"><span data-stu-id="d71b0-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="d71b0-181">Las fotos del usuario incluidas en el estado de presencia también tienen un valor hash asociado que el cliente de Lync usa para determinar si hay una imagen más reciente disponible.</span><span class="sxs-lookup"><span data-stu-id="d71b0-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="d71b0-182">Se notifica automáticamente al cliente los cambios en el archivo de imagen que se usa en el estado de presencia.</span><span class="sxs-lookup"><span data-stu-id="d71b0-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="d71b0-183">Como las fotos no se almacenan en la base de datos GalContacts. dB, la descarga de fotos del usuario no depende de la configuración de <STRONG>AddressBookAvailability</STRONG> de la Directiva de cliente (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">set-ClientPolicy</A>).</span><span class="sxs-lookup"><span data-stu-id="d71b0-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="d71b0-184">La consulta al servicio ABWQ incluye los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="d71b0-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="d71b0-185">**Fotohash**   el valor hash de los datos de la fotografía binaria y se usa para determinar si la foto actual ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="d71b0-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="d71b0-186">**PhotoRelPath**   la ruta de acceso relativa al archivo de imagen almacenado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="d71b0-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="d71b0-187">**Tamaño**   tamaño del archivo de imagen, en bytes.</span><span class="sxs-lookup"><span data-stu-id="d71b0-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="d71b0-188">**TimeStamp**   la fecha y la hora en las que el archivo de imagen se ha descargado por última vez desde el servidor y se ha copiado en la caché del cliente.</span><span class="sxs-lookup"><span data-stu-id="d71b0-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="d71b0-189">Después, después de recuperar el archivo de imagen, el cliente de Lync 2010 compara los valores de atributo devueltos de la consulta con los valores de atributo recibidos por el cliente de aprovisionamiento en banda para ver si son diferentes.</span><span class="sxs-lookup"><span data-stu-id="d71b0-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="d71b0-190">Si los valores son diferentes, el cliente recupera el archivo de imagen del usuario que ha iniciado sesión con una solicitud HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="d71b0-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="d71b0-191">Además, el cliente comprueba el servidor cada 24 horas desde el momento en que se creó la versión en caché del archivo de imagen para comparar el valor del atributo **fotohash** en el servidor con el valor en el cliente.</span><span class="sxs-lookup"><span data-stu-id="d71b0-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="d71b0-192">Si los valores son diferentes, el cliente sabe que el archivo de imagen ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="d71b0-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="d71b0-193">Para obtener el archivo de imagen actualizado, el cliente consulta nuevamente el servicio ABWQ para actualizar el archivo de imagen en la memoria caché del cliente con el archivo de imagen en el servidor, que también restablece la **marca de hora** en el archivo en la memoria caché del cliente.</span><span class="sxs-lookup"><span data-stu-id="d71b0-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="d71b0-194">La siguiente es una respuesta de ejemplo a una consulta para el servicio ABWQ:</span><span class="sxs-lookup"><span data-stu-id="d71b0-194">The following is an example response to a query to the ABWQ service:</span></span>
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="d71b0-195">Fotos de usuario en Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d71b0-195">User photos in Lync 2013</span></span>

<span data-ttu-id="d71b0-196">Lync 2013 presentó compatibilidad con imágenes de alta resolución para fotos de usuario.</span><span class="sxs-lookup"><span data-stu-id="d71b0-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="d71b0-197">Lync 2013 también incluye compatibilidad para almacenar fotos de usuarios en el buzón del usuario en Exchange 2013, lo que elimina la resolución de imagen y las limitaciones de tamaño presentes en Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="d71b0-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="d71b0-198">Las fotos de los usuarios en Lync 2013 pueden tener hasta 648 píxeles por 648 píxeles, con un tamaño de archivo de hasta 20 MB.</span><span class="sxs-lookup"><span data-stu-id="d71b0-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="d71b0-199">Las fotos de alta resolución de Lync 2013 deben encontrarse en el buzón del usuario en Exchange 2013, y solo se admiten con el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d71b0-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="d71b0-200">Esta integración con Exchange aprovecha el nuevo marco de autorización incluido en las versiones 2013 de Lync, Exchange y SharePoint denominado OAuth.</span><span class="sxs-lookup"><span data-stu-id="d71b0-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="d71b0-201">Si Exchange 2013 no se usa en su implementación, la compatibilidad con las fotos de los usuarios es la misma que con Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="d71b0-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="d71b0-202">Sin embargo, las opciones de usuario para elegir la foto que desea usar son diferentes en el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d71b0-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="d71b0-203">En el cliente de Lync 2013, los usuarios pueden seleccionar **ocultar mi foto** o **Mostrar mi foto**.</span><span class="sxs-lookup"><span data-stu-id="d71b0-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="d71b0-204">La opción **Mostrar una imagen de un sitio web** no está disponible de forma predeterminada, pero se puede habilitar mediante la asignación de una directiva de cliente.</span><span class="sxs-lookup"><span data-stu-id="d71b0-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="d71b0-205">Ocultar mi foto</span><span class="sxs-lookup"><span data-stu-id="d71b0-205">Hide my picture</span></span>

<span data-ttu-id="d71b0-206">La configuración de las fotos de los usuarios está en el cuadro de diálogo **Opciones** de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d71b0-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="d71b0-207">Al elegir **ocultar mi**foto, no se muestra ninguna foto de usuario en el cliente de Lync, pero la foto aún se muestra en la tarjeta de contacto y fuera de Lync.</span><span class="sxs-lookup"><span data-stu-id="d71b0-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="d71b0-208">Mostrar mi foto</span><span class="sxs-lookup"><span data-stu-id="d71b0-208">Show my picture</span></span>

<span data-ttu-id="d71b0-209">Al elegir la opción **Mostrar mi** foto, la foto del usuario se muestra en el cliente de Lync y en otros usuarios de las conversaciones de Lync.</span><span class="sxs-lookup"><span data-stu-id="d71b0-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="d71b0-210">La imagen usada es la que se almacena en AD DS.</span><span class="sxs-lookup"><span data-stu-id="d71b0-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="d71b0-211">Mostrar una imagen de un sitio web</span><span class="sxs-lookup"><span data-stu-id="d71b0-211">Show a picture from a website</span></span>

<span data-ttu-id="d71b0-212">La opción **Mostrar imagen de un sitio web** está disponible en Lync 2013 después de establecer una directiva de cliente para habilitarla.</span><span class="sxs-lookup"><span data-stu-id="d71b0-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="d71b0-213">La versión del cliente debe ser posterior a 15.0.4535.1002, que se instala con las [actualizaciones acumulativas de Lync: 2013 de noviembre](http://go.microsoft.com/fwlink/p/?linkid=509908).</span><span class="sxs-lookup"><span data-stu-id="d71b0-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](http://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="d71b0-214">Es posible que los usuarios tengan que cerrar sesión y volver a iniciarla para ver los cambios en el cliente.</span><span class="sxs-lookup"><span data-stu-id="d71b0-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="d71b0-215">Puede establecer la Directiva de cliente para habilitar la **visualización de la imagen de una configuración de sitio web** ejecutando la directiva [set-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d71b0-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="d71b0-216">En los siguientes cmdlets de ejemplo se muestra cómo establecer la Directiva globalmente para todos los usuarios de la implementación:</span><span class="sxs-lookup"><span data-stu-id="d71b0-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="d71b0-217">Cuando se carga una imagen en el buzón del usuario, Exchange crea automáticamente una versión de menor resolución de la imagen que se puede usar en las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="d71b0-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="d71b0-218">La foto del usuario también se ha actualizado en AD DS.</span><span class="sxs-lookup"><span data-stu-id="d71b0-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="d71b0-219">Cuando se actualiza un archivo de imagen en AD DS, se crea una imagen de 48 x 48 de píxeles y se usa para thumbnailPhoto en AD DS.</span><span class="sxs-lookup"><span data-stu-id="d71b0-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="d71b0-220">Se reemplaza cualquier imagen existente.</span><span class="sxs-lookup"><span data-stu-id="d71b0-220">Any existing image is replaced.</span></span> <span data-ttu-id="d71b0-221">Por lo tanto, si agregaste una imagen de 96 x 96 a AD DS, se sobrescribirá con la nueva imagen de 48 x 48.</span><span class="sxs-lookup"><span data-stu-id="d71b0-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="d71b0-222">Esto solo es importante: tiene usuarios en su entorno con clientes de Lync 2010, ya que estos clientes obtendrán fotos de usuarios de AD DS.</span><span class="sxs-lookup"><span data-stu-id="d71b0-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="d71b0-223">Puede importar imágenes de 96 x 96 pixel para reemplazar las creadas por AD DS si tiene clientes de Lync 2010 en su organización.</span><span class="sxs-lookup"><span data-stu-id="d71b0-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="d71b0-224">Compatibilidad con fotos de usuario en Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d71b0-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="d71b0-225">En Lync 2013, se admiten tres resoluciones de imagen para las fotos del usuario, como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d71b0-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="d71b0-226">La imagen que se usa está determinada por la configuración de directiva de cliente asignada a los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="d71b0-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="d71b0-227">Para obtener más información, consulte "administrar la foto del usuario con cmdlets de directivas de cliente" en este tema.</span><span class="sxs-lookup"><span data-stu-id="d71b0-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d71b0-228">Resolución de imagen (píxeles)</span><span class="sxs-lookup"><span data-stu-id="d71b0-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="d71b0-229">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d71b0-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d71b0-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="d71b0-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="d71b0-231">Se usa si no se selecciona ninguna imagen de resolución superior</span><span class="sxs-lookup"><span data-stu-id="d71b0-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d71b0-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="d71b0-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="d71b0-233">Se usa en Outlook Web App y Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="d71b0-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d71b0-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="d71b0-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="d71b0-235">Usado en el cliente de escritorio de Lync 2013 y la aplicación Web de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d71b0-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d71b0-236">Cualquier usuario con un buzón habilitado en Exchange 2013 puede cargar una imagen diferente, incluidas las fotos de alta resolución, a través de las opciones de cliente de Outlook Web Access o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d71b0-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="d71b0-237">La configuración recomendada para las imágenes que se usan incluye:</span><span class="sxs-lookup"><span data-stu-id="d71b0-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="d71b0-238">**Resolución de imagen**   648 por 648 píxeles</span><span class="sxs-lookup"><span data-stu-id="d71b0-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="d71b0-239">**Profundidad de color**   de 24 bits</span><span class="sxs-lookup"><span data-stu-id="d71b0-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="d71b0-240">**Tamaño de archivo de imagen**   de hasta 20 MB</span><span class="sxs-lookup"><span data-stu-id="d71b0-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="d71b0-241">**Formato de archivo**   JPEG</span><span class="sxs-lookup"><span data-stu-id="d71b0-241">**File format**   JPEG</span></span>

<span data-ttu-id="d71b0-242">Una imagen de JPEG de 24 bits típica, de 648 píxeles por 648 píxeles, tiene un tamaño de archivo de aproximadamente 240 KB, por lo que se necesita 1 MB de espacio de almacenamiento para cada cuatro fotos de usuario.</span><span class="sxs-lookup"><span data-stu-id="d71b0-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

