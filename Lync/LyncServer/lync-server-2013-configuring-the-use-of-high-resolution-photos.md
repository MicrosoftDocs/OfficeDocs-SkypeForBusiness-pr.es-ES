---
title: 'Lync Server 2013: configuración del uso de fotos de alta resolución'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec832d3795fc1b83c6a838b15c04be9f2e48d6d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="b0930-102">Configuración del uso de fotos de alta resolución en Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0930-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0930-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="b0930-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="b0930-104">Microsoft Lync Server 2010 proporcionó a los usuarios la posibilidad de ver fotos de sus contactos (y hacer que sus propias fotos estén disponibles para otros usuarios).</span><span class="sxs-lookup"><span data-stu-id="b0930-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="b0930-105">Normalmente, estas fotos se almacenaban como parte del atributo thumbnailPhoto del usuario en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b0930-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="b0930-106">Eso suponía una seria limitación para el tamaño y la resolución de las fotos: el atributo thumbnailPhoto solo puede contener una fotos con un tamaño máximo de 48 píxeles por 48 píxeles.</span><span class="sxs-lookup"><span data-stu-id="b0930-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="b0930-107">Sin embargo, en Microsoft Lync Server 2013, las fotos se pueden almacenar en el buzón de correo de Microsoft Exchange Server 2013 de un usuario; que permite tamaños de foto de hasta 648 píxeles por 648 píxeles.</span><span class="sxs-lookup"><span data-stu-id="b0930-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="b0930-108">Además, Exchange 2013 puede cambiar el tamaño de estas fotos automáticamente para usarlas en diferentes productos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b0930-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="b0930-109">Normalmente, esto significa tres tamaños y resoluciones de foto diferentes:</span><span class="sxs-lookup"><span data-stu-id="b0930-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="b0930-110">48 píxeles por 48 píxeles, es el tamaño usado por el atributo thumbnailPhoto de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b0930-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="b0930-111">Si carga una foto en Exchange 2013 Exchange creará automáticamente una versión de 48 píxeles por 48 píxeles de dicha foto y actualizará el atributo thumbnailPhoto del usuario.</span><span class="sxs-lookup"><span data-stu-id="b0930-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="b0930-112">Sin embargo, tenga en cuenta que el valor inverso no es verdadero: Si actualiza manualmente el atributo thumbnailPhoto en Active Directory, la foto en el buzón de Exchange 2013 del usuario no se actualizará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b0930-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="b0930-113">96 píxeles por 96 píxeles, para su uso en Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App y Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b0930-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="b0930-114">648 píxeles por 648 píxeles para su uso en Lync 2013 y Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="b0930-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0930-p104">Si tiene los recursos, es recomendable que cargue fotos de 648x648, ya que proporcionan la resolución máxima y una calidad de imagen óptima en cualquiera de las aplicaciones de Office 2013. Cada foto JPEG con un tamaño de 648x648 y una profundidad de 24 bits produce un tamaño de archivo de 240 kilobytes aproximadamente. Eso significa que necesitará aproximadamente 1 megabyte de espacio en disco por cada 4 fotos de usuario.</span><span class="sxs-lookup"><span data-stu-id="b0930-p104">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications. Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes. That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="b0930-118">Las fotos de alta resolución, a las que se tiene acceso a través de los servicios web Exchange, pueden cargarlas los usuarios que ejecutan Outlook 2013 Web App; los usuarios solo pueden actualizar su propia foto.</span><span class="sxs-lookup"><span data-stu-id="b0930-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="b0930-119">Los administradores, sin embargo, pueden actualizar la foto de cualquier usuario mediante el shell de administración de Exchange y una serie de comandos de Windows PowerShell similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b0930-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="b0930-120">El primer comando del ejemplo anterior utiliza el cmdlet Get-Content para leer el contenido del archivo C:\\fotos\\kenmyer. jpg y almacenar los datos en una variable llamada $Photo.</span><span class="sxs-lookup"><span data-stu-id="b0930-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="b0930-121">En el segundo comando, el cmdlet Set-UserPhoto de Exchange se usa para cargar la foto y adjuntarla a la cuenta de usuario de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b0930-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0930-122">En este ejemplo, el nombre para mostrar de Active Directory de Ken Myer se usa como identidad de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="b0930-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="b0930-123">También puede hacer referencia a una cuenta de usuario usando otros identificadores como la dirección SMTP del usuario o su nombre principal de usuario.</span><span class="sxs-lookup"><span data-stu-id="b0930-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="b0930-124">Consulte la documentación del cmdlet Set-UserPhoto en <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> para obtener más información</span><span class="sxs-lookup"><span data-stu-id="b0930-124">See the documentation for the Set-UserPhoto cmdlet at <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="b0930-p108">Cargar la fotografía no equivale a asignarla a la cuenta de usuario de Ken Myer. Al cargar la fotografía, el resultado es que se muestra una vista previa de dicha fotografía en la página Opciones de Outlook Web App. Para asignar realmente la fotografía a la cuenta de usuario, debe hacer clic en **Guardar** en la página Opciones o el administrador debe ejecutar el tercer comando del ejemplo. Ese tercer comando usa el parámetro Save para asignar la fotografía a la cuenta de usuario de Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="b0930-p108">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="b0930-129">Para comprobar que la nueva foto se ha asignado a la cuenta de usuario, Ken Myer puede iniciar sesión en Lync 2013, seleccione **Opciones**y, a continuación, seleccione **mi foto**.</span><span class="sxs-lookup"><span data-stu-id="b0930-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="b0930-130">La foto recién cargada debe mostrarse como la foto personal de Ken.</span><span class="sxs-lookup"><span data-stu-id="b0930-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="b0930-131">Otra opción para comprobar la foto de cualquier usuario es que los administradores inicien Internet Explorer y naveguen a una dirección URL similar a esta:</span><span class="sxs-lookup"><span data-stu-id="b0930-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="b0930-132">Si el administrador puede ver la foto con Internet Explorer pero el usuario no puede ver su foto en Lync 2013, eso suele indicar un problema de conectividad con los servicios web Exchange o con el servicio Detección automática de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b0930-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="b0930-133">Tenga en cuenta que no es necesario realizar ninguna configuración adicional para que esta foto esté disponible en Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b0930-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="b0930-134">En su lugar, la foto estará disponible al instante una vez que se haya cargado y se haya ejecutado el cmdlet Set-UserPhoto.</span><span class="sxs-lookup"><span data-stu-id="b0930-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

